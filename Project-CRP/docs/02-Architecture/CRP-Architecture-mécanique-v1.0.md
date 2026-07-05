# Project CRP - Architecture mécanique

Version : 1.0

---

# 1. Objectif

Ce document décrit l'architecture mécanique générale de Project CRP.

Il définit l'implantation des principaux composants, les principes de montage, la circulation de l'air ainsi que la stratégie de maintenance.

Il ne constitue pas un plan de fabrication mais la référence qui guidera la conception du boîtier 3D.

---

# 2. Philosophie de conception

Project CRP privilégie :

* l'ergonomie ;
* la robustesse ;
* la réparabilité ;
* la simplicité d'assemblage.

La compacité n'est pas une priorité absolue.

Le boîtier devra permettre une intervention rapide sur les principaux composants.

---

# 3. Dimensions cibles

Dimensions provisoires :

* Largeur : 245 à 255 mm
* Hauteur : 110 mm
* Épaisseur : 25 à 30 mm (hors joysticks)

Poids cible :

* inférieur à 600 g

Ces valeurs pourront évoluer pendant la conception.

---

# 4. Implantation générale

Vue simplifiée :

```text
 ┌─────────────────────────────────────────────────────┐
 │ L1  L2                                 R1  R2       │
 │                                                     │
 │                                                     │
 │          Écran IPS 5 pouces (zone centrale)         │
 │                                                     │
 │ D-Pad                              X  Y             │
 │ Stick G                            A  B             │
 │                                                     │
 │           Start          Select                     │
 │                           Stick D                  │
 │                                                     │
 ├─────────────────────────────────────────────────────┤
 │ micro-HDMI │ USB-C │ Jack 3,5 mm │ Microphone       │
 └─────────────────────────────────────────────────────┘
```

Les connecteurs sont regroupés sur la tranche inférieure afin de simplifier le dock.

---

# 5. Implantation interne

L'organisation interne suit les principes suivants :

## Avant

* écran IPS ;
* haut-parleurs ;
* cartes boutons.

## Centre

* Raspberry Pi 5 ;
* système de refroidissement.

## Arrière

* batterie LiPo ;
* RP2040 (prototype : Raspberry Pi Pico) ;
* module d'alimentation.

---

# 6. Batterie

La batterie devra être :

* centrée pour équilibrer le poids ;
* facilement accessible ;
* montée sur connecteur ;
* remplaçable sans dessoudage.

Le boîtier devra permettre son remplacement sans démonter l'ensemble de la console.

---

# 7. Refroidissement

Le Raspberry Pi sera équipé d'un ventilateur.

Le boîtier devra intégrer :

* une entrée d'air ;
* une sortie d'air ;
* un chemin de circulation direct.

Le ventilateur devra être remplaçable.

Le système de fixation sera prévu dès la première version, même si le pilotage intelligent est développé ultérieurement.

---

# 8. Maintenance

Objectif :

Temps moyen d'ouverture inférieur à 5 minutes.

Ordre de démontage :

1. Déposer les vis arrière.
2. Retirer la coque arrière.
3. Déconnecter la batterie.
4. Accéder aux composants principaux.

Les éléments suivants devront être remplaçables individuellement :

* batterie ;
* Raspberry Pi ;
* ventilateur ;
* écran ;
* joysticks ;
* haut-parleurs.

---

# 9. Fixations

Le boîtier utilisera :

* des vis métriques standard (M2 ou M2.5, à confirmer) ;
* des inserts filetés en laiton chauffés dans le PETG.

Les composants seront fixés mécaniquement, sans collage.

---

# 10. Cheminement des câbles

Les câbles devront être :

* les plus courts possible ;
* maintenus dans des guides intégrés au boîtier ;
* éloignés du ventilateur.

Les nappes de l'écran devront pouvoir être remplacées sans démontage complet.

---

# 11. Dock

Le dock recevra la console par le dessous.

La console viendra s'aligner naturellement grâce au boîtier.

Le dock intégrera :

* un connecteur USB-C d'alimentation ;
* un connecteur micro-HDMI ;
* une LED d'alimentation.

L'insertion devra être guidée afin de limiter les contraintes sur les connecteurs.

---

# 12. Ergonomie

Le boîtier devra être confortable pour les grandes mains.

Les poignées arrière seront légèrement galbées.

Les boutons seront suffisamment espacés pour limiter les appuis involontaires.

Le poids devra être réparti de manière équilibrée entre les deux mains.

---

# 13. Évolutions prévues

Le boîtier devra permettre, sans refonte complète :

* une batterie de capacité supérieure ;
* un nouveau ventilateur ;
* un RP2040 intégré sur PCB ;
* une évolution du dock.

L'architecture mécanique devra rester compatible avec ces améliorations.

---

# 14. Validation

Avant la conception détaillée du boîtier 3D, les points suivants devront être validés :

* choix définitif de la batterie ;
* dimensions de l'écran ;
* dimensions des joysticks ;
* dimensions du ventilateur ;
* dimensions du module d'alimentation.
