# Project CRP – Architecture mécanique

Version : 1.2

---

# 1. Objectif

Ce document définit l'architecture mécanique de Project CRP.

Il décrit :

* les dimensions cibles ;
* l'implantation générale des commandes ;
* les zones fonctionnelles internes ;
* les principes de maintenance ;
* les contraintes mécaniques.

Il constitue la référence avant la modélisation 3D.

---

# 2. Philosophie de conception

Project CRP privilégie :

* une excellente ergonomie ;
* une maintenance simple ;
* une architecture évolutive ;
* une conception robuste ;
* une documentation complète.

La compacité maximale n'est **pas** un objectif.

Le confort d'utilisation et la réparabilité sont prioritaires.

---

# 3. Règles CRP

## Règle n°1

Une architecture ne sera complexifiée que si un bénéfice technique clairement identifié le justifie.

Cela concerne notamment :

* le nombre de PCB ;
* le nombre de connecteurs ;
* le nombre de nappes ;
* les mécanismes particuliers.

---

## Règle n°2

Chaque élément extérieur de la console doit avoir une justification ergonomique ou fonctionnelle.

Son emplacement ne doit jamais être choisi uniquement pour des raisons esthétiques ou par imitation d'une autre console.

Avant de valider son implantation, les questions suivantes doivent être posées :

* est-il facilement accessible ?
* risque-t-il d'être actionné involontairement ?
* simplifie-t-il la maintenance ?
* simplifie-t-il la conception ?
* améliore-t-il l'expérience utilisateur ?

---

# 4. Dimensions cibles

Objectifs actuels :

* Largeur : 245 à 255 mm
* Hauteur : environ 110 mm
* Épaisseur : 25 à 30 mm (hors joysticks)

Poids cible :

* inférieur à 600 g

Ces dimensions pourront évoluer au cours du projet.

---

# 5. Implantation générale

## Façade

```text
┌────────────────────────────────────────────────────────────┐

        L1   L2                          R1   R2

                    Sortie d'air

 D-Pad                                   X   Y

 Stick G                               Stick D

               ┌───────────────────┐
               │                   │
               │   Écran IPS 5"    │
               │                   │
               └───────────────────┘

               Start        Select

────────────────────────────────────────────────────────────

 micro-HDMI   USB-C   Jack   Microphone

└────────────────────────────────────────────────────────────┘
```

Le dock utilisera uniquement les connecteurs situés sur la tranche inférieure.

---

# 6. Vue supérieure

```text
┌────────────────────────────────────────────────────────────┐

L1   L2

          microSD

          Power   ● LED RGB

          Volume +

          Volume -

                             R1   R2

└────────────────────────────────────────────────────────────┘
```

Le dessus de la console regroupe :

* le bouton Power ;
* la LED RGB ;
* les boutons Volume ;
* le lecteur microSD.

Cette disposition évite les appuis involontaires pendant le jeu.

---

# 7. Vue arrière

La face arrière comprend :

* les vis d'ouverture ;
* les entrées d'air ;
* le bouton RESET (accessible avec un trombone).

Le bouton RESET est destiné au développement et aux cas exceptionnels.

---

# 8. Architecture interne

L'organisation interne est définie par zones fonctionnelles.

De l'avant vers l'arrière :

1. coque avant ;
2. écran IPS ;
3. cartes de commandes ;
4. Raspberry Pi 5 ;
5. système de refroidissement ;
6. batterie LiPo ;
7. module d'alimentation ;
8. coque arrière.

Le nombre définitif de PCB sera déterminé ultérieurement.

---

# 9. Batterie

Objectifs :

* autonomie cible : environ 6 heures ;
* batterie remplaçable ;
* connecteur démontable ;
* remplacement sans dessoudage.

La batterie devra être centrée afin d'équilibrer le poids.

---

# 10. Refroidissement

Toutes les versions de Project CRP intégreront un ventilateur.

Le boîtier devra prévoir :

* une entrée d'air ;
* une sortie d'air ;
* un chemin d'air direct vers le Raspberry Pi.

Le ventilateur devra être facilement remplaçable.

Le contrôle intelligent de sa vitesse est une fonctionnalité logicielle optionnelle.

---

# 11. Connecteurs

## Face inférieure

* micro-HDMI
* USB-C Power Delivery
* Jack 3,5 mm
* Microphone

Tous les connecteurs sont regroupés afin de simplifier la conception du dock.

---

## Face supérieure

* Lecteur microSD
* Bouton Power
* LED RGB
* Volume +
* Volume -

---

## Face arrière

* RESET

---

# 12. LED RGB

Une seule LED RGB est utilisée.

Elle est placée à proximité du bouton Power.

Codes retenus :

* Bleu fixe : console allumée.
* Orange fixe : batterie en charge.
* Vert fixe : batterie complètement chargée.
* Rouge fixe : batterie faible.
* Rouge clignotant : batterie critique.
* Blanc bref : confirmation d'un appui sur Power.
* Éteinte : console éteinte (hors recharge).

Aucune LED Bluetooth n'est prévue.

Les informations Bluetooth seront affichées directement par Batocera.

---

# 13. Maintenance

Objectif :

Ouverture complète de la console en moins de cinq minutes.

Ordre souhaité :

1. retirer les vis arrière ;
2. ouvrir la coque ;
3. débrancher la batterie ;
4. accéder immédiatement aux principaux composants.

Les éléments suivants devront être remplaçables :

* batterie ;
* Raspberry Pi ;
* ventilateur ;
* écran ;
* joysticks ;
* haut-parleurs.

Le démontage ne devra nécessiter aucun collage.

---

# 14. Fixations

Le boîtier utilisera :

* des vis métriques standard ;
* des inserts filetés en laiton.

Le collage sera évité autant que possible.

---

# 15. Cheminement des câbles

Les câbles devront :

* être les plus courts possible ;
* être guidés dans des logements dédiés ;
* ne pas gêner la circulation de l'air ;
* ne jamais être pincés lors de la fermeture du boîtier.

---

# 16. Dock

Le dock est volontairement simple.

Fonctions :

* alimentation USB-C ;
* sortie HDMI ;
* LED de présence d'alimentation.

Aucun port USB supplémentaire n'est prévu dans la première version.

---

# 17. Évolutivité

L'architecture devra permettre ultérieurement :

* un changement de batterie ;
* un changement de ventilateur ;
* un RP2040 intégré sur PCB ;
* une évolution du dock.

---

# 18. Points restant à valider

Les éléments suivants seront définis lors des études techniques :

* référence exacte de l'écran ;
* référence de la batterie ;
* référence des joysticks Hall Effect ;
* référence du ventilateur ;
* architecture définitive des PCB.

Aucune décision sur le nombre final de PCB ne sera prise avant la fin des études techniques.
