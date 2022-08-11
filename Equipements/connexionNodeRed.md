# Connexion Node-Red

La connexion à Hexa-data depuis Node-Red se paramètre dans le noeud ```MQTT out```.

* Le topic reprend la structure HD/[namespace]/up
* Le niveau de QOS doit être réglé sur 1.

![MQTT Out](./_medias/formNodeRed0.png ':size=50%')

* L'adresse du serveur dépend de votre installation (addresse IP ou nom de domaine).

* Le ClientID correspond à celui saisi dans le formaulaire de création d'Hexa-data.

![Connexion MQTT Node-Red](./_medias/formNodeRed1.png ':size=50%')

?> _Important_ Si la connexion nécessite d'être sécurisée, choisir le port 8883 et cocher la case ```Use TLS```

* Saisir ensuite l'identifiant ainsi que le mot de passe déclaré dans Hexa-data.

![Connexion MQTT Node-Red](./_medias/formNodeRed2.png ':size=50%')
