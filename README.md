# Projet de Téléphonie sur IP pour un Atelier d'Artistes

Ce README détaille la mise en œuvre d'une infrastructure de téléphonie sur IP performante pour un atelier d'artistes. Le projet, réalisé dans le cadre de SAé2.04 PARTIE 4, a impliqué un travail autonome pour choisir et configurer un système IPBX.

## Problématique et Objectifs

L'objectif principal était de mettre en place une infrastructure téléphonique performante pour l'atelier d'artistes. Le projet a nécessité le choix d'une solution de Téléphonie sur IP (comme FREEPBX ou un autre IPBX) et sa configuration sur une VM. Le système devait gérer le flux d'appels en fonction de l'emploi du temps de l'atelier et acheminer les appels vers les artistes.

## Configuration et Fonctionnalités

### Architecture Générale

L'infrastructure s'articule autour du numéro principal de l'installation, le 0466666666. Un serveur vocal interactif permet de joindre les postes. Les appels vers ce numéro sont gérés en fonction de conditions de temps (CONDITION TIME), vérifiant d'abord si l'atelier est en vacances puis les heures d'ouverture de l'atelier.

### Gestion du Temps

L'atelier est ouvert 7j/7 du 01/09 au 30/06 de 8h00 à 18h00. Cela correspond à 2 mois de vacances.

* **Pendant les vacances ou en dehors des heures d'ouverture :** Si des appels entrants ont lieu en dehors des heures de travail ou pendant les vacances, des annonces spécifiques sont lancées automatiquement avant de raccrocher.
* **Pendant les heures d'ouverture :** Les appels sont dirigés vers un Serveur Vocal Interactif (IVR 1).

### Extensions et IVR

Il y a 4 extensions à créer pour les 4 artistes présents dans l'atelier. Le plan de numérotation utilise des extensions à 3 chiffres.

Les détails de routage sont les suivants :

| Touche IVR | Extension | Numéro SDA (Numéro Publique) | Nom Artiste |
| :---: | :---: | :---: | :--- |
| 0 | 200 | 0477777777 | LEON ARDAVINCI |
| 1 | 201 | | PAUL PICASSO |
| 2 | 202 | 0488888888 | MICKAEL ANGELO |
| 3 | 203 | | SALVATORE DALIDA |

**SDA (Direct Inward Dialing) :** Des SDA ont été achetés pour quelques artistes qui doivent être joints directement.

### Gestion d'Absence (Messagerie Vocale)

En cas d'absence prévue, les artistes peuvent mettre leur softphone en mode "ABSENT". Dans ce cas, les appels doivent aboutir sur un répondeur enregistreur.

## Réalisation Technique

Le projet a impliqué le choix d'une solution de téléphonie sur IP et la configuration du serveur correspondant à la problématique demandée sur une VM (locale ou sur un cloud). Des tests de bon fonctionnement ont été effectués, incluant des appels entrants et sortants, pour valider la configuration.

## Livrables du Projet

Ce projet comprend la documentation et les artefacts suivants :

* **SUJET 2025.pdf :** Le sujet détaillé du projet.
* **Compte Rendu :** Un rapport détaillé écrit ou sous forme vidéo à rendre sur MOODLE pour le 16/06 avant 23h59.
* **Vidéo des Tests Finaux :** Une vidéo démontrant le bon fonctionnement du système de téléphonie sur IP, validant la configuration par des appels entrants et sortants.
* Une soutenance orale était également requise.
