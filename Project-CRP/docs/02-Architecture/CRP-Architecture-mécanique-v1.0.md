# Project CRP - Architecture mécanique

Version : 1.1

---

# 1. Objectif

Ce document décrit l'architecture mécanique de Project CRP.

Il définit les principes d'implantation des composants, les contraintes mécaniques et les objectifs de maintenance.

Il constitue la référence pour la conception du futur boîtier 3D.

---

# 2. Philosophie

La conception mécanique suit les principes suivants :

* privilégier l'ergonomie ;
* privilégier la réparabilité ;
* limiter la complexité inutile ;
* prévoir l'évolution du projet ;
* conserver une architecture simple.

## Règle CRP n°1

**Une architecture ne sera complexifiée que si un bénéfice technique clairement identifié le justifie.**

Autrement dit :

* pas de PCB supplémentaire sans nécessité ;
* pas de connecteur supplémentaire sans bénéfice ;
* pas de mécanisme complexe si une solution simple répond au besoin.

---

# 3. Dimensions cibles

Objectifs actuels :

* largeur : 245 à 255 mm
* hauteur : environ 110 mm
* épaisseur : 25 à 30 mm (hors joysticks)

Poids cible :

* inférieur à 600 g

Ces dimensions restent des objectifs et pourront évoluer au cours de la conception.

---

# 4. Architecture générale

La console est organisée en plusieurs zones fonctionnelles.

```text
┌─────────────────────────────────────────────────────────────┐

      L1 L2                                 R1 R2

┌─────────────────────────────────────────────────────────────┐

                  Écran IPS 5 pouces

 D-Pad                                      ABXY

 Stick G                                  Stick D

              Start             Select

└─────────────────────────────────────────────────────────────┘

 micro-HDMI │ USB-C │ Jack │ Microphone

└─────────────────────────────────────────────────────────────┘
```

Les connecteurs sont volontairement regroupés sur la tranche inférieure afin de simplifier la conception du dock.

---

# 5. Architecture interne

L'intérieur de la console est organisé en couches.

De l'avant vers l'arrière :

1. coque avant ;
2. écran IPS ;
3. cartes de commandes (ou carte I/O selon la solution retenue) ;
4. Raspberry Pi 5 ;
5. batterie ;
6. module d'alimentation ;
7. coque arrière.

Le positionnement définitif sera validé après le choix des composants.

---

# 6. Cartes électroniques

À ce stade du projet, le nombre définitif de PCB n'est pas figé.

Les modules fonctionnels identifiés sont :

* Raspberry Pi 5 ;
* module alimentation ;
* module d'entrées/sorties (I/O) incluant le RP2040 et les commandes.

La répartition physique sur un ou plusieurs PCB sera décidée après les études techniques afin d'éviter une complexité inutile.

---

# 7. Batterie

Objectifs :

* autonomie cible : environ 6 heures ;
* batterie facilement remplaçable ;
* montage sur connecteur ;
* accès rapide après ouverture de la coque.

La batterie devra participer à l'équilibrage du poids de la console.

---

# 8. Refroidissement

Toutes les versions de CRP intégreront un ventilateur.

Le boîtier devra prévoir :

* une entrée d'air ;
* une sortie d'air ;
* un chemin de circulation direct vers le Raspberry Pi.

Le contrôle intelligent de la vitesse est une fonctionnalité logicielle optionnelle.

Le ventilateur devra pouvoir être remplacé facilement.

---

# 9. Maintenance

Objectif :

Ouverture complète en moins de cinq minutes.

Ordre souhaité :

1. retrait des vis arrière ;
2. ouverture de la coque ;
3. déconnexion de la batterie ;
4. accès immédiat aux principaux composants.

Les composants suivants devront être remplaçables :

* batterie ;
* Raspberry Pi ;
* ventilateur ;
* écran ;
* joysticks ;
* haut-parleurs.

Le démontage ne devra nécessiter aucun décollage de pièce.

---

# 10. Fixations

Le boîtier utilisera :

* vis métriques standard ;
* inserts filetés en laiton intégrés au PETG.

Le collage sera évité autant que possible.

---

# 11. Cheminement des câbles

Les câbles devront :

* rester courts ;
* être guidés dans des logements dédiés ;
* être protégés des parties mobiles ;
* ne pas gêner le flux d'air.

Les nappes de l'écran devront rester accessibles.

---

# 12. Dock

Le dock constitue un accessoire indépendant.

Fonctions :

* alimentation USB-C ;
* sortie HDMI ;
* LED indiquant la présence de l'alimentation.

Le dock ne comporte aucun composant actif dans sa première version.

L'insertion devra être guidée afin de protéger les connecteurs USB-C et micro-HDMI.

---

# 13. Ergonomie

La console est conçue pour offrir un bon confort aux utilisateurs ayant de grandes mains.

Les objectifs sont :

* poignées arrière légèrement galbées ;
* commandes suffisamment espacées ;
* répartition équilibrée du poids ;
* accès facile aux gâchettes.

Le confort est privilégié par rapport à la recherche d'une taille minimale.

---

# 14. Évolutivité

L'architecture devra permettre sans refonte complète :

* une nouvelle batterie ;
* un ventilateur différent ;
* un RP2040 intégré sur un PCB personnalisé ;
* une évolution du dock ;
* une évolution de la carte I/O.

---

# 15. Validation

Avant la conception du boîtier 3D, devront être validés :

* la batterie ;
* l'écran ;
* les joysticks ;
* le ventilateur ;
* le module d'alimentation ;
* la stratégie de répartition des PCB.

Aucune décision sur le nombre de PCB ne sera prise avant la fin des études techniques.
