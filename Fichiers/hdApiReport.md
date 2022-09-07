# API WarpScript pour la manipulation des rapports

## Création d'un rapport ```@hdApi/storeReport```

__Paramètres__

Données à écrire dans le fichier (<LIST>LIST | STRING)

Nom du fichier à créer (STRING)

__Retour__

Retourne TRUE ou déclanche une execption en cas d'erreur.

__Exemple__

Création d'un fichier text ```test.txt``` avec pour contenu ```Bonjour Hexa-data```

```
'Bonjour Hexa-data' 'test.txt' @hdApi/storeReport
```

Création d'un fichier CSV ```test.csv```

```
[ [ 'capteur' 'valeur' ] [ 'TemperatureCuve' 23 ] ] 'test.csv' @hdApi/storeReport
```


## Lister les rapport ```@hdApi/indexReport```

__Paramètres__

Nombre de résultats par page (STRING)

Numero de la page à afficher (STRING)

Filtre de recherche (STRING)

__Retour__

Retourne une MAP avec les informations de pagination ainsi que la liste des rapports.
La liste des rapports contient notamment l'ID, le nom du fichier et le lien sécurisé de téléchargement (valable 30mins) 

__Exemple__

Liste les rapports dont le nom contient ```.txt``` en affichant 3 résultats par page. 

```
'3' '' '.txt' @hdApi/indexReport
```

## Supprimer un rapport ```@hdApi/destroyReport```

__Paramètres__

Id du rapport à supprimer (LONG)

__Retour__

Retourne TRUE ou déclanche une execption en cas d'erreur.

__Exemple__

Supprime le rapport avec l'ID 39.

```
39 @hdApi/destroyReport
```