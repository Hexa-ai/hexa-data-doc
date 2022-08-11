# Utilisation du noeud Node-Red

Le noeud Node-Red s'installe directement depuis la palette Node-Red.
Taper dans la barre de recherche ```@hexa-ai/node-red-contrib-hexa-data-connector```

![palette Node-Red](./_medias/paletteNodeRed.png ':size=50%')

## Exemple de flow Node-Red

![flow Node-Red](./_medias/flowNodeRed.png ':size=70%')

* Le Noeud ```Echantillonnage``` permet, dans cet exemple, de cadencer l'échantillonage de valeurs. Il s'agit d'un noeud ```Inject``` à éxécution cyclique (Ex: 200ms).

* Les noeuds ```Pression``` et ```Température``` décrivent la variable à remonter.

    Exemple de mise en forme de la pression:

    ```
    msg.payload={name:"Pression","ts": Date.now()*1000,"value":Math.round(Math.random() *100.1)/10 ,"type":"real"}
    return msg;
    ```

    * Le champ ```name``` du payload correspond au nom de la variable déclarée dans Hexa-data.
    * Le champ ```ts``` correspond au timestamp du système en micro-secondes.
    * Le champ ```value``` correspond à la valeur à envoyer.
    * Le champ ```type``` correspond au type de la variable (```real```, ```integer```, ```boolean```, ```string```).

* Le Noeud ```hd-up``` gère le buffer et la mise en forme des messages pour Hexa-data.
* Le Noeud ```mqtt out```est le client MQTT précedemment paramétré.
