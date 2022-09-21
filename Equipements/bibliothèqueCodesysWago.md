# Utilisation de la bibliothèque Codesys 3.5 WAGO

La bibliothèque Codesys 3.5 WAGO peut-être utilisée sur Codesys ou e!COCKPIT avec des automates de marque WAGO uniquement.
Cette bibliothèque intègre la liaison avec le module CloudConnectivy de WAGO afin d'en simplifier l'intégration.

[hexa-data-connector-wago-0-0-1.compiled-library](https://gitlab.com/julien.talbourdet/codesys-hexa-data-connector-wago/-/package_files/53631149/download)

## 1. Importer la bibliothèque avec le gestionnaire de bibliothèque Codesys.

![Import bibliothèque](./_medias/importLibCodesysWago.png ':size=60%')

## 2. Utilisation du bloc-fonction ```FbHdUpWago()```

![Utilisation du Fb](./_medias/useFbWago.png ':size=80%')

L'instance du bloc-fonction FbHdUpWago accepte deux paramètres

* asGtsNames (Tableau de STRING) Liste des variables à remonter dans Hexa-data.
  Ces variables doivent avoir été préalablement déclarées dans Hexa-data.
* sClientId (STRING) Correspond au paramètre ClientId de l'équipement


L'échantillonnage des valeurs s'effectue avec la méthode ```logValue()```.

Cette méthode accepte trois paramètres :

* iGtsIndex (INT) Position de la variable à échantillonner dans le tableau asGtsNames.
* sValue (STRING) Valeur de la variable à échantillonner, convertie en chaine de caractères.
* eType (eDataTyp) Enumeration permettant de décrire le type de la variable ()
    * ```boolTyp``` : Pour les booléens
    * ```numTyp``` : Pour les entiers et réels
    * ```stringTyp``` : Pour les chaines de caractères