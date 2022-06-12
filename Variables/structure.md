# Structure des données

Toutes les mesures sont stockées dans une base de données open source [WARP10](https://www.warp10.io).


## Jetons

Pour chaque projet, Hexa-data crée une paire de jetons WARP10 pour la lecture et l'écriture des données liées à ce projet. Ces jetons ont une durée de vie de 24h et sont renouvelés tous les jours à 01h00.

La plupart du temps, les jetons sont automatiquement intégrés dans le script utilisateur par Hexa-data. Cette intégration dynamique est gérée côté backend afin de maximiser la sécurité et de ne pas exposer ces jetons.

### Exemple de paire de jetons

```
[
    {
        "ident": "0906eaabb6f23c90",
        "params": {
            "owner": "3b8a4db4-d653-4aea-993c-681b7cb88cfe",
            "application": "hexaData",
            "issuance": 1638968172017000,
            "owners": [
                "3b8a4db4-d653-4aea-993c-681b7cb88cfe"
            ],
            "expiry": 1639054572017000,
            "type": "READ",
            "producers": [
                "3b8a4db4-d653-4aea-993c-681b7cb88cfe"
            ],
            "applications": [
                "hexaData"
            ],
            "labels": {
                "type": "globalInfo",
                "projectId": "1"
            }
        },
        "token": "mt1bQvcpmyqcg7Nz6ZJ9XxYPT0IV4Ac2OKTjvQeHoaNnZQDZOoLKggoJ.W_QZH5E9gEZk0Sv_g1q5wcDd8BGJvykgckMpXrmxHVA7g.FsztkaWJSPMhkWa2cVgXSXqDXFzvRvyYLmdsmOfeWWOyDi5PqRoMb2j5g21gGDMNA3D9i9JbV8r5RbN7bH_.Sw2x848JZA5dBoqZ"
    },
    {
        "ident": "67cdcee394f62827",
        "params": {
            "owner": "3b8a4db4-d653-4aea-993c-681b7cb88cfe",
            "application": "hexaData",
            "issuance": 1638968172017000,
            "producer": "3b8a4db4-d653-4aea-993c-681b7cb88cfe",
            "expiry": 1639054572017000,
            "type": "WRITE",
            "labels": {
                "type": "globalInfo",
                "projectId": "1"
            }
        },
        "token": "C7PBfuIxFq8QmglhRQo.TMgjEVq.u4ILU9VOdUFF3nUUxlzThKONg9qR1AZScOqxoJRDck0OntGV._iBQTQVu27tXTu_IfJwOPAmhmN86k2FIhmPSKh7JM7UfUi9GiQr8ZxxZTGnMQAIcnxCVpzs1ZaGRI3HXVY8"
    }
]
```
Chaque jeton contient le label "projectId" correspondant à l'ID du projet auquel il est rattaché

## WARP10 GTS

Chaque série temporelle Warp10 GTS intègre automatiquement le label "projectId" correspondant à l'id de son projet. 
