# Format HDM MQTT

La connexion avec les équipements s'effectue selon le protocole MQTT.
Le protocole MQTT étant plutôt ouvert, concernant le formatage des données, nous avons donc défini un formatage performant et simple à implémenter : HDM.

## Histrorical data metric format (HDM)

HDM est un format simple et ouvert, basé sur JSON, développé pour Hexa-data pour remonter des mesures horodatées et par paquets de plusieurs mesures.

## Topic

Les topics de messages MQTT s'assemblent de la manière suivante :

* Messages montants (de l'équipement vers Hexa-data): HD/[clientID]/up
* Messages descendants (d'Hexa-data vers l'équipement): HD/[clientID]/down

Pour la connexion MQTT, un équipement doit possèder un clientID, qui doit être défini dans la page d'édition de l'équipement.

  Ex: L'équipement nommé "ma passerelle" disposera du namespace ```maPasserelle```.


![namespace](./_medias/namespace.png ':size=50%')

### Exemple pour un message montant

#### Topic

```HD/maPasserelle/up```

#### Payload

```
{
  version: '1.0',
  protocol: 'hdmp',
  gtsNames: [
    'NiveauCuve',
    'NbBoitesProduites',
    'alMoteurConvoyeur',
    'alPompeRemplissage',
    'alVanneSoutirage',
    'doMoteurConvoyeur',
    'doPompeRemplissage',
    'doVanneSoutirage'
  ],
  datas: [
    [ 0, 1639124070058000, 1673.788 ],
    [ 1, 1639124070058000, 8408 ],
    [ 2, 1639124070058000, false ],
    [ 3, 1639124070058000, false ],
    [ 4, 1639124070058000, false ],
    [ 5, 1639124070058000, true ],
    [ 6, 1639124070058000, true ],
    [ 7, 1639124070058000, false ]
  ]
}
```

|  Attribut         |  Description                                                                                             |
|-------------------|----------------------------------------------------------------------------------------------------------|
| version           | Version du profil de communication                                                                       |
| protocol          | Profil du protocole (en prévision de futures variations du format incorporant d'autres fonctionnalités)  |
| gtsNames          | Tableau contenant le nom des variables à remonter                                                        |
| datas             | Pile d'enregistrements à remonter [gtsName_id, timestamp en µSecond, valeur]                             |

### Exemple pour un message descendant

Les messages descendants n'ont pour l'instant pas de formatage précis. Nous préconisons l'utilisation d'un objet JSON avec des clés valeurs. 

#### Topic

```HD/maPasserelle/down```

#### Payload

{
  doVanneSoutirage: true
}


## Traitement des messages MQTT

Lorsqu'un nouveau message arrive, le service d'acquisition vérifie l'attribut ```protocol``` avant de le traiter. Ce service valide également la déclaration des variables dans l'application, ainsi que le type des données remontées.

Afin d'offrir de bonnes performances, la liste des balises autorisées est mise à jour cycliquement (toutes les 10 secondes) et chargée en mémoire.

Tous les messages autorisés sont alors empilés dans un buffer. Ce dernier est vidé cycliquement dans la base de données WARP10.
