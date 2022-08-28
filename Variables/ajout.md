# Ajouter une variable sur un projet

L'ajout et la modification de variable s'effectue depuis la page ```Variables```

![Variables](./_medias/variables.png ':size=60%')

## Les actions possibles

La visualisation et modification d'une variable s'effectue en cliquant sur la variable.

L'ajout, l'importation et l'exportation en format CSV sont possibles depuis la barre d'outils (en haut à droite).

![Menu variables](./_medias/menuVariables.png ':size=40%')

## Export CSV

Le bouton export CSV de la barre d'outils exporte la déclaration de toutes les variables du projet.

Exemple de fichier:

![Exemple export CSV](./_medias/exportCsv.png ':size=40%')

### Format du fichier CSV

| Champ         | Description                                                                                   |
|---------------|-----------------------------------------------------------------------------------------------|
| id            | identifiant de la variable dans la base de données Hexa-data                                   |
| name          | nom de la variable sans le préfixe de ```namespace```                                      |
| descriptionL1 | Valeur du champ description dans le formulaire d'édition de variable (Langue n° 1 du projet) |
| descriptionL2 | Valeur du champ description dans le formulaire d'édition de variable (Langue n° 2 du projet) |
| descriptionL3 | Valeur du champ description dans le formulaire d'édition de variable (Langue n° 3 du projet) |
| unit          | Valeur du champ unité dans le formulaire d'édition de variable                               |
| type          | Type d'élément ( 1=GTS, 3=Macro )                                                             |
| valueType     | Type de valeur pour la variable / GTS (1=Boolean, 2=Integer, 3=Real, 4=String)                |
| deviceId      | Type de l'équipement auquel est rattaché cette variable                                       |


?> Les identifiants tels que l'id de la variable ou le deviceId peuvent être retrouvés dans l'url de la page concernée.

**Exemple**:

Sur la capture ci-dessous, la variable ```edgeDemo.r1.mesu.temp.salon``` possède l'id 120.

![Id variable](./_medias/variableId.png ':size=40%')

## Import CSV

L'import CSV permet de créer ou de modifier des déclarations de variable avec le même format CSV que pour l'export.

?> Pour toute création de variable, le champ id doit être vide, il serat créé automatiquement par Hexa-data.