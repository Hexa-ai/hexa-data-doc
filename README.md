# Introduction

Hexa-data est une application permettant l'analyse et la visualisation de données issues d'intallations industrielles.
Le développement d'Hexa-data a pour objectif de rassembler les briques de bases nécessaires au développement de projets IIOT (IOT Industriel)

## Fonctionnalités

- Collecte de données horodatées avec le protocole MQTT
- Stockage des mesures dans une base de données dédiée aux séries temporelles (WARP10)
- Analyse de données avec le moteur de script (WarpScript)
- Interactions avec les équipements (WarpScript)
- Visualisation des données sous forme de tableaux de bord personnalisables
- Cloisonnement des données et utilisateurs par projet
- Stockage de fichiers par projet (Ex: Shémas, manuels, documentation)
- Génération de rapports texte et CSV (WarpScript)

## Architecture standards

Hexa-data a été conçu pour trois architectures types.

 * Edge (PC-Industriel)
 * Serveur
 * Cloud

![Schémas](./_media/Hexa-data%20sch%C3%A9mas.png)