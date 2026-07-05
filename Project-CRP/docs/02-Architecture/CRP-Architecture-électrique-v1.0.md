# Project CRP - Architecture électrique

Version : 1.0

---

# 1. Objectif

Ce document décrit l'architecture électrique générale de Project CRP.

Il définit les différents modules électriques, leurs responsabilités ainsi que les interfaces de communication entre eux.

Il ne constitue pas un schéma électronique mais la référence fonctionnelle qui guidera la conception des futurs PCB.

---

# 2. Vue d'ensemble

```text
                        Chargeur USB-C PD
                               │
                               ▼
                     Module Power / BMS
                               │
             ┌─────────────────┴──────────────────┐
             │                                    │
             ▼                                    ▼
      Batterie LiPo                    Alimentation 5V
             │                                    │
             │                              Raspberry Pi 5
             │                                    │
             │        ┌───────────────────────────┼─────────────────────────────┐
             │        │                           │                             │
             ▼        ▼                           ▼                             ▼
        Jauge batterie RP2040                 HDMI                       USB / GPIO
                 │                             │                             │
                 │                             ▼                             ▼
                 │                       Écran IPS                     Audio / Entrées
                 │
                 ▼
         LED - Ventilateur
         Bouton Power
```

---

# 3. Sous-systèmes

## 3.1 Module Power

Responsabilités :

* réception de l'alimentation USB-C ;
* négociation USB-C Power Delivery ;
* recharge de la batterie ;
* alimentation simultanée du système et de la batterie (Power Path) ;
* protections électriques.

Ce module constitue le cœur de l'alimentation de la console.

---

## 3.2 Batterie

Objectifs :

* batterie LiPo remplaçable ;
* autonomie cible : 6 heures ;
* connecteur démontable.

Le choix définitif de la capacité sera réalisé lors de la BOM.

---

## 3.3 Raspberry Pi 5

Le Raspberry Pi assure :

* Batocera ;
* les émulateurs ;
* le réseau ;
* la vidéo ;
* l'audio logiciel.

Le Raspberry Pi ne pilote pas directement l'alimentation générale.

---

## 3.4 RP2040

Le RP2040 est le contrôleur matériel.

Il reste alimenté indépendamment du Raspberry Pi.

Il pilote notamment :

* bouton Power ;
* LED d'état ;
* ventilateur ;
* surveillance batterie ;
* démarrage et arrêt du Raspberry Pi.

Prototype V0 :

* Raspberry Pi Pico.

Version V1/V2 :

* RP2040 intégré au PCB principal.

---

## 3.5 Écran

Connexion :

HDMI

Alimentation :

5 V

L'écran est indépendant du RP2040.

---

## 3.6 Audio

Comprend :

* amplificateur ;
* deux haut-parleurs ;
* prise jack ;
* microphone.

Le détail de l'architecture audio sera défini dans une version ultérieure.

---

## 3.7 Ventilateur

Ventilateur 5 V.

Piloté par le RP2040.

La vitesse pourra être :

* fixe ;
* automatique ;
* configurable.

---

# 4. Interfaces

| Interface    | Utilisation               |
| ------------ | ------------------------- |
| HDMI         | Écran interne             |
| micro-HDMI   | Téléviseur                |
| USB-C PD     | Recharge                  |
| GPIO         | Commandes                 |
| UART (prévu) | Communication Pi ↔ RP2040 |
| I²C (prévu)  | Capteurs éventuels        |
| PWM          | Ventilateur               |
| I²S ou USB   | Audio (à confirmer)       |

---

# 5. Démarrage

1. Appui sur Power.
2. Le RP2040 active l'alimentation principale.
3. Le Raspberry Pi démarre.
4. Le RP2040 surveille le système.
5. Les LED indiquent l'état de fonctionnement.

---

# 6. Arrêt

1. Appui sur Power.
2. Le RP2040 demande un arrêt propre au Raspberry Pi.
3. Le Raspberry Pi s'éteint.
4. Le RP2040 coupe l'alimentation principale.

En cas de blocage :

* un appui long forcera l'extinction.

---

# 7. Recharge

Le système devra permettre :

* recharge console éteinte ;
* recharge console allumée ;
* utilisation pendant la recharge ;
* branchement ou débranchement du chargeur sans extinction.

---

# 8. Dock

Le dock est entièrement passif.

Il fournit :

* alimentation USB-C ;
* sortie HDMI ;
* LED de présence d'alimentation.

Aucun composant actif n'est prévu dans la première version.

---

# 9. Maintenance

Tous les modules devront être indépendants.

Les éléments suivants devront pouvoir être remplacés sans dessoudage :

* batterie ;
* écran ;
* Raspberry Pi ;
* ventilateur ;
* haut-parleurs.

Les connecteurs seront privilégiés lorsque cela est possible.

---

# 10. Évolutions prévues

Les éléments suivants pourront être ajoutés ultérieurement :

* jauge de batterie avancée ;
* profils de ventilation ;
* mode veille amélioré ;
* dock intelligent ;
* intégration complète du RP2040 sur PCB.
