# Ajouter un équipement dans un projet

Les équipements permettent de remonter des données dans Hexa-data. Un équipement peut être un automate, une carte électronique ou un ordinateur industriel. Afin d'échanger avec Hexa-data, l'équipement doit répondre aux critères suivants.

* Disposer d'un client MQTT
* Respecter le [formatage](./formatMqtt.md) attendu par Hexa-data

## Bibliothèques officielles

actuellement deux bibliothèques prêtes à l'emploi sont disponibles.

* Noeud Node-Red [node-red-contrib-hexa-data-connector](https://flows.nodered.org/node/@hexa-ai/node-red-contrib-hexa-data-connector)
* Bibliothèque Codesys 3.5 / e!COCKPIT (WAGO Contact) [codesys-hexa-data-connector](https://gitlab.com/julien.talbourdet/codesys-hexa-data-connector/-/package_files/48640460/download)




Pour ajouter un équipement, il faut se rendre dans le menu ```Equipements``` d'un projet et cliquer sur le bouton d'ajout (en haut à droite).

![menu équipement](./_medias/ajoutEquipement.gif)

## Formulaire de création

| Champ             | Requis | Modifiable | Description                                                                                                                                                                              |
|-------------------|--------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nom               | x      | Oui        | Nom visible dans Hexa-data                                                                                                                                                               |
| Namespace         |        | Non        | Généré automatiquement à partir du nom. Le namespace préfixe le nom des variables afin d'identifier visuellement leur appartenance à un équipement                                         |
| Description       |        | Oui        | Description visible dans Hexa-data                                                                                                                                                       |
| Tableau de bord   |        | Oui        | Permet de rattacher un tableau de bord à l'équipement. Sur la carte de la page d'information, l'utilisateur pourra cliquer sur le marqueur de l'équipement et accéder au tableau de bord |
| Adresse           |        | Oui        | Adresse de l'équipement (nom utilisé actuellement)                                                                                                                               |
| Latitude          |        | Oui        | Coordonnée permettant la localisation de l'équipement sur la carte                                                                                                                        |
| Longitude         |        | Oui        | Coordonnée permettant la localisation de l'équipement sur la carte                                                                                                                        |
| ClientID          | x      | Oui        | Client-ID permettant d'authentifier le client MQTT                                                                                                                                       |
| Nom d'utilisateur | x      | Oui        | Nom d'utilisateur permettant d'authentifier le client MQTT                                                                                                                               |
| Mot de passe      | x      | Oui        | Mot de passe permettant d'authentifier le client MQTT                                                                                                                                    |
