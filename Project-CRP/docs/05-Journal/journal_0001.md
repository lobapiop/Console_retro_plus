# Project CRP - Journal de développement

## Journal n°0001

**Date :** 05 juillet 2026

---

# Début du projet

Aujourd'hui marque le lancement officiel de **Project CRP (Console Retro Plus)**.

L'objectif du projet est de concevoir une console portable de rétrogaming moderne, basée sur un Raspberry Pi 5, offrant une expérience proche d'une console du commerce tout en restant entièrement documentée, réparable et reproductible.

Dès le début du projet, il a été décidé que la priorité ne serait pas la compacité maximale, mais la qualité de conception, l'ergonomie et la maintenance.

---

# Objectifs initiaux

Les objectifs retenus sont les suivants :

* développer une console portable fiable ;
* utiliser Batocera comme système principal ;
* assurer une autonomie cible d'environ 6 heures ;
* permettre une utilisation sur téléviseur grâce à un dock dédié ;
* documenter intégralement le projet sur GitHub.

---

# Choix techniques validés

## Carte principale

Le Raspberry Pi 5 (4 Go) est retenu comme plateforme principale.

Motivations :

* performances adaptées au rétrogaming ;
* excellente compatibilité avec Batocera ;
* Wi-Fi et Bluetooth intégrés ;
* large communauté.

---

## Logiciel

Batocera est retenu comme système principal.

Motivations :

* simplicité d'utilisation ;
* grand nombre d'émulateurs intégrés ;
* excellente compatibilité avec le Raspberry Pi 5.

---

## Écran

Le projet utilisera un écran IPS de 5 pouces.

Ce format constitue un bon compromis entre confort de jeu, consommation électrique et dimensions générales de la console.

---

## Ergonomie

La console ne cherchera pas à reproduire exactement les dimensions d'une Nintendo Switch.

Les dimensions cibles sont volontairement légèrement supérieures afin de privilégier :

* le confort pour les grandes mains ;
* une meilleure maintenance ;
* une intégration plus simple des composants.

Dimensions provisoires :

* largeur : 245 à 255 mm ;
* hauteur : environ 110 mm ;
* épaisseur : 25 à 30 mm.

---

## Commandes

La disposition retenue comprend :

* un D-Pad ;
* quatre boutons ABXY ;
* deux joysticks Hall Effect ;
* Start ;
* Select ;
* Volume + / - ;
* Power ;
* L1/L2 ;
* R1/R2.

Le choix a été fait de limiter volontairement le nombre de boutons afin d'éviter les appuis accidentels et de conserver une bonne ergonomie.

---

## Batterie

Les objectifs retenus sont :

* environ 6 heures d'autonomie ;
* recharge USB-C Power Delivery ;
* possibilité de jouer pendant la recharge ;
* batterie facilement remplaçable.

La capacité définitive sera déterminée après les calculs de consommation et le choix des composants.

---

## Dock

Le dock est volontairement simple.

Fonctions prévues :

* alimentation de la console ;
* recharge de la batterie ;
* sortie HDMI vers un téléviseur ;
* LED indiquant la présence de l'alimentation.

Le choix a été fait de ne pas intégrer de ports USB supplémentaires dans la première version.

---

## Refroidissement

La console intégrera un ventilateur.

Le contrôle intelligent de sa vitesse sera prévu, mais restera une fonctionnalité optionnelle pouvant être activée ou désactivée.

---

## Boîtier

Le boîtier sera imprimé en PETG.

Les objectifs principaux sont :

* robustesse ;
* démontage facile ;
* maintenance rapide ;
* remplacement simple des composants principaux.

---

# Philosophie du projet

Plusieurs principes de développement ont été adoptés dès le lancement :

* documenter toutes les décisions ;
* privilégier la qualité à la compacité ;
* utiliser des composants standards ;
* limiter les soudures au strict nécessaire ;
* rendre le projet facilement reproductible.

Le projet sera développé de manière incrémentale, chaque étape étant validée avant de passer à la suivante.

---

# Organisation du dépôt GitHub

Le dépôt GitHub devient la source officielle de toutes les informations du projet.

Chaque évolution importante devra être accompagnée :

* d'une mise à jour de la documentation ;
* d'un journal de développement ;
* d'une mise à jour de la nomenclature si nécessaire.

---

# Prochaine étape

La prochaine phase du projet consistera à définir l'architecture générale de la console.

Les travaux porteront notamment sur :

* l'implantation des composants ;
* le système d'alimentation ;
* le cheminement des câbles ;
* la stratégie de maintenance ;
* les interfaces entre les différents modules.

---

## État du projet

Le projet entre officiellement en phase de conception.
