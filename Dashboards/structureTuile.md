# Structure tuile

L'édition de tableau de bord Continuum se base sur le Webcomposant Warp10 ```discovery-tile```.
La structure du WarpScript est une map qui dispose d'un tronc commun à tout les Widgets.

| Attribut           | Type                       | Description                                         |
|--------------------|----------------------------|-----------------------------------------------------|
| ```data```         | GTS, GTS[], string, number | Données à afficher dans la tuile                    |
| ```globalParams``` | Options                    | Options de la tuile                                 |
| ```events```       | Map[]                  | Evénements émis par la tuile                        |
| ```params```       | Map[]                  | Liste d'options concernant chaque données affichées |

## Paramètres globaux (```globalParams```)

L'attribut ```globalParams``` regroupes les paramètres liés à la tuile.

| Attribut        | Type   | Description                           | Valeurs                                                                                                                                                                                                    |
|-----------------|--------|---------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ```scheme```    | string | Jeux de couleur du widget             | COHESIVE, COHESIVE_2, BELIZE, VIRIDIS, MAGMA, INFERNO,<br>PLASMA, YL_OR_RD, YL_GN_BU, BU_GN, WARP10,<br>NINETEEN_EIGHTY_FOUR, ATLANTIS, DO_ANDROIDS_DREAM,<br>DELOREAN, CTHULHU, ECTOPLASM, T_MAX_400_FILM |
| ```bgColor```   | string | Couleur d'arrière plan en hexadécimal |                                                                                                                                                                                                            |
| ```fontColor``` | string | Couleur de la police en hexadécimal   |                                                                                                                                                                                                            |
| ```timeZone```  | string | Fuseau horaire                        | AUTO, UTC   
| ```hideYAxis```         | booléen | Masque l'axe Y                         |
| ```showRangeSelector``` | booléen | Affiche le curseur de zoom sur l'axe X |
| ```fullDateDisplay```   | booléen | Affiche la date complète sur l'axe X   |
| ```showDots``` | booléen | Affiche les points sur les courbes |
| ```showLoader``` | booléen | Affiche l'animation en cours de chargment |
| ```bounds``` | options | Map avec les attribut ```minAge``` et ```maxAge``` (limite de l'axe X ) ainsi que ```yRange``` (list contenant les limites de l'axe Y)|

## Evènements (```events```)

L'attribut ```events``` est un tableau de Maps décrivant chacune un évènement à emettre.
Ces évenements peuvent ensuite être écouté par les autre tuiles du tableau de bord.

### Structure d'un évènement

| Attribut       | Type     | Description                                                                                                                        | Valeurs         |
|----------------|----------|------------------------------------------------------------------------------------------------------------------------------------|-----------------|
| ```type```     | string   | Type d'évènement émis                                                                                                              | variable, data  |
| ```tags```     | string[] | Liste de tags décrivant l'évènement.<br>Ces tags permettant aux autres tuile de les filtrer pour n'écouter que certains évènements |                 |
| ```selector``` | string   | Nom de la variable émise (pour l'évènement de type ```variable```)                                                                 |                 |
| ```value```    |          | Valeur à envoyer dans le cas du type ```data```                                                                                    |                 |


Le type d'évènement ```variable``` envoie les données de la tuile dans une variable dont le nom est donné avec l'attribut ```selector```

Le type d'évènement ```data``` envoie une variable qui sera traité comme étant le résultat de l'attribut ```data``` de la tuile réceptrice. la variable à envoyer passe par l'attribut ```value```. 
### Paramètre de données (```params```)

Ces paramètre sont propre aux tuile affichant plusieurs Variables / GTS.

