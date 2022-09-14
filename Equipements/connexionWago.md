# Connexion d'un automate WAGO (_e!COCKPIT_)

La connexion à Hexa-data depuis un automate WAGO se paramètre dans le WBM (Web Based Management).

Dans l'onglet ```Configuration```, se rendre dans le menu ```Cloud Connectivity``` puis ```Connection 1```

![alt](./_medias/navWbmWago.png ':size=70%')

* Cocher ```Enabled```
* Sélectionner ```MQTT AnyCloud``` dans le champ ```Cloud plateform```
* Saisir l'url de l'application dans ```Hostname```

?> Attention à ne pas saisir de ```http://url/``` mais uniquement l'url ou l'IP de votre serveur.

* Saisir le numéro de port ```8883```
* Saisir le ```Client ID``` déclaré dans Hexa-data
* Cocher ```Clen session``` et ```TLS```
* Saisir l'identifiant et le mot de passe déclaré dans Hexa-data dans les champs ```User``` et ```Password```
* Télécharger et saisir le chemin vers vers le certificat root de LetsEncrypt dans le champ ```CA file```
* Sélectionner ```Native MQTT``` dans le champ ```Data protocol```
* Soumettre le formulaire et redémarrer l'automate pour prise en compte.

![alt](./_medias/formWbmWago.png ':size=70%')

## Téléchargement et installation du certificat root de LetsEncrypt

LetsEncrypt est une autorité de certification permettant de valider des certificats TLS d'applications exposées sur internet.

Pour authentifier le certificat du serveur, le client doit disposer d'un certificat principal délivré par l'autorité de certification.

### Téléchargement depuis l'automate (ssh)

Une fois connecté en ssh à l'automate, se rendre dans le répertoire des certificats.

```
cd /etc/ssl/certs
```

Créer un nouveau répertoire pour le certificat LetsEncrypt.

```
sudo mkdir letsencrypt.org

cd letsencrypt.org/
```

Télécharger le certificat

```
wget "https://letsencrypt.org/certs/isrgrootx1.pem"
```

Une fois ce certificat téléchargé, le paramètre de connexion ```CA file``` (dans le WBM) pourra être réglé sur:

```
/etc/ssl/certs/letsencrypt.org/isrgrootx1.pem
```




