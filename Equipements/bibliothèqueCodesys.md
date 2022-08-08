# Utilisation de la bibliothèque Codesys 3.5

La bibliothèque Codesys 3.5 peut-être utilisé sur Codesys mais aussi d'autres environement dérivés de Codesys comme par exemple e!COCKPIT pour les automates de marque WAGO. Cette bibliothèque à été développée dans Codesys 3.5 SP18 et testé dans e!COCKPIT avec un automate WAGO PFC200, elle devrait aussi fonctionner sur d'autre environnement comme TwinCAT3.

Afin de permettre l'inter opérabilité avec plusieurs constructeurs la bibliothèque se concentre uniquement sur le formatage du payload.

## 1. Importer la bibliothèque avec le gestionnaire de bibliothèques Codesys.

![Import bibliothèque](./_medias/importLibCodesys.png ':size=60%')

## 2. Utilisation du bloc-fonction ```FbHdUp()```

![Utilisation du Fb](./_medias/useFb.png ':size=80%')

L'instance du bloc-fonction FbHdUp est exécutée ligne 6 et prend deux paramètres:

* uliTimestamp (ULINT) Timestamp en milliseconde de la plateforme.
    Recupération possible avec la fonction ```SysTimeRtc.SysTimeRtcHighResGet()```
* asGtsNames (Tableau de STRING) Liste des variable à remonter dans Hexa-data.
    Ces variables doivent avoir été préalablement déclarés dans Hexa-data.

Les variables sont échantillonées de la ligne 21 à 24 avec la methode ```logValue()```.
Cette methode accepte trois paramètres:

* iGtsIndex (INT) Position de la variable à échantillonner dans le tableau asGtsNames.
* sValue (STRING) Valeur de la variable à échantillonner convertie en chaine de caractères.
* eTyp (eDataTyp) Enumeration permettant de décrire le type de la variable ()
    * ```boolTyp```: Pour les boolean
    * ```numTyp```: Pour les entiers et réels
    * ```stringTyp```: Pour les chaines de caractères

Le bloc fonction ajoute l'enregistrement dans une pile à chaque appel de la methode. La pile peut contenir un maximum de 10000 enregistrement, une fois remplie, les données sont mises à disposition pour l'envoie MQTT. Les données à envoyer sont disponibles dans la variable wsPayloadBuffer (tableau d'octets). La variable xSendTrigger (BOOL) est passée à TRUE le temps d'un tour de cycle afin d'informer de la présence de donner à envoyer.

