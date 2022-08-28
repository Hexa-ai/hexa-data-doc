# Variables / GTS

L'application Hexa-data est developpée autour d'une base de données  [WARP10](https://www.warp10.io/).

WARP10 est une technologie Open-source, developpée par la société francaise [SenX](https://senx.io/).

Cette base de données est l'élément central de l'application, car responsable du stockage et du traitement des données.


Chaque variable remontée dans l'application est une GTS (Geo Time Serie) au sens WARP10.

Le nom defini dans Hexa-data correspond au classname de la GTS.

## Variable / GTS

Une variable (GTS au sens WARP10) permet de représenter une mesure dans le temps (ex: température, pression ...).

### Structure d'une variable / GTS

* Classname

    Représente le nom de la variable / GTS (Ex: ```batimentA.rdc.mesure.temperature``` )

!> _Important_ Le classname est immuable, une variable ne peut donc pas être renommée.

* Labels

    Représente les caractéristiques de la variable / GTS
    Dans Hexa-data les labels des variables sont créés automatiquement en fonction de la nomenclature de la variable (classname). Lorsque que le nom de la variable contient des ```.``` chaque sous-chaine correspond à la valeur d'un label de l-0 à l-(n-1).

!> _Important_ Les labels sont des caractéristiques immuables.

    Ex:

    Nom de la variable:  ```batimentA.rdc.mesure.temperature```

    Labels générés par Hexa-data: ```"l-0" = "batimentA", "l-1" = "rdc", "l-2" = "mesure", "l-3" = "temperature"```

* Datapoints
    Les datapoints correspondent aux mesures. Du point de vue WARP10, un point de mesure est composé d'un timestamp en µSeconde, d'une latitude, d'une longitude, d'une élévation et d'une mesure.

    Actuellement les éléments latitude, longitude et élévation ne sont pas gérés dans Hexa-data. Les principaux éléments à prendre en compte sont le timestamp et la mesure.
* Attributs
    Les attributs permettent de documenter la variable / GTS et peuvent être modifiés après la création.
    Lors de la création d'une variable Hexa-data crée automatiquement trois attributs

    * ```descriptionL1``` Valeur du champ description dans le formulaire d'édition de variable (Langue n° 1 du projet)
    * ```descriptionL2``` Valeur du champ description dans le formulaire d'édition de variable (Langue n° 2 du projet)
    * ```descriptionL3``` Valeur du champ description dans le formulaire d'édition de variable (Langue n° 3 du projet)
    * ```unit``` Valeur du champ unité dans le formulaire d'édition de variable


