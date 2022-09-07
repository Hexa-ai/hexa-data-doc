# API WarpScript pour envoyer des messages vers les équipements

## Envoyer un message avec ```@hdApi/deviceMsgDown```

__Paramètres__

Message à envoyer (STRING)

Namespace de l'équipement concerné (STRING)

__Retour__

Retourne TRUE ou déclanche une execption en cas d'erreur.

__Exemple__

Envoie d'un objet JSON dont l'attribut ```consigne``` a la valeur 25

Le message est envoyé à l'équipement ```demoGateway```

```
 '{"consigne":25}' 'demoGateway' @hdApi/deviceMsgDown
```

