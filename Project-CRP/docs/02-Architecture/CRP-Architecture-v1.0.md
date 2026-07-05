# Project CRP - Architecture

Version : 1.0

---

# 1. Objectif

Ce document décrit l'architecture générale de Project CRP.

Il définit les principaux sous-systèmes de la console ainsi que leurs interactions.

L'objectif est de garantir une architecture modulaire, facilement maintenable et évolutive.

---

# 2. Vue d'ensemble

```
                        +----------------------+
                        |    Raspberry Pi 5    |
                        |        4 Go          |
                        +----------+-----------+
                                   |
        +------------+-------------+-------------+--------------+
        |            |             |             |              |
        |            |             |             |              |
     HDMI        USB 2.0        GPIO        Bluetooth       Wi-Fi
        |            |             |
        |            |             |
        |        RP2040        Boutons
        |            |
        |            |
        |     Batterie / LEDs
        |
    Ecran IPS
```

Le Raspberry Pi constitue le cœur du système.

Tous les éléments périphériques sont organisés autour de lui.

---

# 3. Modules principaux

## Module de calcul

Fonction :

* exécuter Batocera ;
* faire fonctionner les émulateurs ;
* gérer l'affichage ;
* gérer les communications réseau.

Composant principal :

* Raspberry Pi 5 (4 Go)

---

## Module d'affichage

Fonction :

* affichage principal de la console.

Caractéristiques :

* écran IPS 5 pouces ;
* interface HDMI.

L'écran devra être facilement remplaçable.

---

## Module de commande

Fonction :

* lecture des commandes utilisateur.

Il comprend :

* D-Pad
* ABXY
* Start
* Select
* Volume
* Power
* L1
* L2
* R1
* R2
* deux joysticks Hall Effect

Les commandes seront regroupées sur un ou plusieurs PCB dédiés.

---

## Module audio

Fonction :

* restitution sonore.

Il comprend :

* deux haut-parleurs ;
* une prise casque 3,5 mm ;
* un microphone.

---

## Module alimentation

Fonction :

* alimentation de la console ;
* recharge de la batterie ;
* alimentation pendant la recharge ;
* protection électrique.

Il devra fonctionner de manière totalement transparente pour l'utilisateur.

---

## Module batterie

Objectifs :

* autonomie cible : environ 6 heures ;
* batterie facilement remplaçable ;
* connecteur démontable.

La capacité exacte sera définie ultérieurement.

---

## Module ventilation

Fonction :

* refroidissement du Raspberry Pi.

Le ventilateur sera présent sur toutes les versions.

Le contrôle intelligent restera optionnel.

---

## Module Dock

Fonctions :

* recharge ;
* alimentation ;
* sortie HDMI vers le téléviseur.

Le dock restera volontairement simple.

---

## Module RP2040

Le RP2040 constitue le contrôleur embarqué de la console.

Il sera indépendant du Raspberry Pi.

Fonctions envisagées :

* gestion du bouton Power ;
* surveillance de la batterie ;
* contrôle des LED ;
* contrôle du ventilateur ;
* gestion des sécurités d'alimentation.

Cette architecture permet au Raspberry Pi de rester concentré sur l'émulation.

## Stratégie d'intégration du RP2040

Le RP2040 est retenu comme contrôleur matériel de Project CRP.

Il assurera les fonctions suivantes :

* gestion du bouton Power ;
* extinction propre du Raspberry Pi ;
* contrôle des LED ;
* surveillance de la batterie ;
* contrôle du ventilateur ;
* détection du dock ;
* gestion de certaines sécurités matérielles.

### Prototype V0

Pour le premier prototype, le projet utilisera un **Raspberry Pi Pico** complet.

Ce choix permet :

* de réduire la complexité électronique initiale ;
* de faciliter les tests ;
* de remplacer facilement le module en cas d'erreur ;
* de simplifier le développement du firmware.

### Version V1 / V2

Une fois les fonctions validées, le RP2040 pourra être intégré directement sur un PCB dédié CRP.

Ce choix permettra :

* de réduire l'encombrement ;
* de limiter le câblage ;
* d'améliorer la fiabilité ;
* de rendre l'intégration plus propre.

Cette évolution ne sera réalisée qu'après validation complète du prototype.


---

# 4. Implantation générale

Vue simplifiée :

```
 ___________________________________________

   L1 L2                         R1 R2

+-------------------------------------------+

|                                           |
|               Ecran IPS 5"                |
|                                           |

| DPad                      X  Y            |
|                           A  B            |

| Stick G        Start  Select     Stick D  |

+-------------------------------------------+

| micro-HDMI | USB-C | Jack | Microphone    |

---------------------------------------------
```

Le Raspberry Pi sera implanté derrière l'écran.

La batterie sera placée derrière le Raspberry Pi.

Les cartes boutons seront situées de chaque côté.

---

# 5. Philosophie de maintenance

Toutes les pièces devront être remplaçables.

Ordre de démontage souhaité :

1. Retrait de la coque arrière.
2. Déconnexion de la batterie.
3. Accès au Raspberry Pi.
4. Accès aux haut-parleurs.
5. Accès aux joysticks.
6. Accès aux cartes boutons.

Aucune pièce ne devra être collée.

---

# 6. Architecture logicielle

Le Raspberry Pi exécutera :

* Batocera ;
* les émulateurs ;
* l'interface utilisateur.

Le RP2040 exécutera :

* la gestion matérielle ;
* le contrôle du ventilateur ;
* la surveillance de la batterie ;
* les LED.

Les deux systèmes communiqueront via une interface série (UART) ou USB, à déterminer lors de la conception électronique.

---

# 7. Évolutivité

L'architecture doit permettre :

* le remplacement de la batterie ;
* le remplacement de l'écran ;
* le remplacement des joysticks ;
* l'évolution du firmware RP2040 ;
* l'amélioration du dock.

---

# 8. Principes retenus

Le projet suit les principes suivants :

* simplicité ;
* robustesse ;
* modularité ;
* maintenance ;
* documentation complète.

Chaque sous-système devra pouvoir être testé indépendamment avant l'assemblage final.

---

# 9. Travaux suivants

Les prochaines étapes seront :

* choix des composants ;
* définition du système batterie ;
* définition du système audio ;
* définition des connecteurs ;
* conception du boîtier 3D ;
* réalisation de la nomenclature officielle (BOM).
