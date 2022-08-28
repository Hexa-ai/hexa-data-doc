# Utilisation de la bibliothèque Codesys 3.5

La bibliothèque Codesys 3.5 peut-être utilisée sur Codesys, mais aussi d'autres environnements dérivés de Codesys, comme par exemple e!COCKPIT pour les automates de la marque WAGO. Cette bibliothèque a été développée dans Codesys 3.5 SP18 et testée dans e!COCKPIT avec un automate WAGO PFC200. Elle devrait aussi fonctionner sur d'autres environnements comme TwinCAT3.

Afin de permettre l'interopérabilité avec plusieurs constructeurs, la bibliothèque se concentre uniquement sur le formatage du payload.

## 1. Importer la bibliothèque avec le gestionnaire de bibliothèque Codesys.

![Import bibliothèque](./_medias/importLibCodesys.png ':size=60%')

## 2. Utilisation du bloc-fonction ```FbHdUp()```

![Utilisation du Fb](./_medias/useFb.png ':size=80%')

L'instance du bloc-fonction FbHdUp est exécutée ligne 6 et prend deux paramètres:

* uliTimestamp (ULINT) Timestamp de la plateforme en millisecondes.
    Recupération possible avec la fonction ```SysTimeRtc.SysTimeRtcHighResGet()```
* asGtsNames (Tableau de STRING) Liste des variables à remonter dans Hexa-data.
    Ces variables doivent avoir été préalablement déclarées dans Hexa-data.

Les variables sont échantillonées de la ligne 21 à 24 avec la méthode ```logValue()```.
Cette méthode accepte trois paramètres:

* iGtsIndex (INT) Position de la variable à échantillonner dans le tableau asGtsNames.
* sValue (STRING) Valeur de la variable à échantillonner, convertie en chaine de caractères.
* eTyp (eDataTyp) Enumeration permettant de décrire le type de la variable ()
    * ```boolTyp```: Pour les booléens
    * ```numTyp```: Pour les entiers et réels
    * ```stringTyp```: Pour les chaines de caractères

Le bloc fonction ajoute l'enregistrement dans une pile à chaque appel de la méthode. La pile peut contenir un maximum de 10000 enregistrements. Une fois remplie, les données sont mises à disposition pour l'envoi MQTT. Les données à envoyer sont disponibles dans la variable wsPayloadBuffer (tableau d'octets). La variable xSendTrigger (BOOL)  passe à TRUE le temps d'un tour de cycle afin d'informer de la présence de données à envoyer.

