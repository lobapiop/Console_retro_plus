# Project CRP – TEST-ET001 – Validation du module d’affichage

Version : 0.1  
Statut : à finalisé après l'arrivé du test USB
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

# 1. Objet

Ce document définit le protocole de validation du module d’affichage Elecrow retenu comme candidat prioritaire pour Project CRP.

L’objectif est de vérifier expérimentalement :

- la conformité du produit reçu ;
- sa compatibilité avec le Raspberry Pi 5 ;
- sa compatibilité avec Batocera ;
- la qualité réelle de l’affichage ;
- la stabilité de fonctionnement ;
- le fonctionnement du tactile ;
- le comportement de la sortie TV ;
- son intégration mécanique préliminaire ;
- son aptitude à devenir l’écran définitif de Project CRP.

La validation finale de l’écran ne doit pas reposer uniquement sur les caractéristiques commerciales ou les avis disponibles.

---

# 2. Périmètre

Le présent protocole couvre :

- l’inspection visuelle du module ;
- le relevé des références ;
- le premier branchement ;
- le premier démarrage ;
- la détection de la résolution ;
- l’utilisation de Batocera ;
- l’affichage des jeux rétro ;
- l’émulation Nintendo DS ;
- le tactile ;
- la sortie HDMI vers un téléviseur ;
- la stabilité thermique ;
- la consommation de l’écran, si un appareil de mesure est disponible ;
- les principales dimensions mécaniques.

Le protocole ne couvre pas encore :

- l’alimentation sur batterie ;
- l’autonomie finale de la console ;
- l’intégration dans la coque ;
- l’électronique de gestion d’alimentation ;
- le dock définitif ;
- la carte de commandes ;
- l’audio définitif de la console.

---

# 3. Critères de décision

À la fin des essais, le module recevra l’un des statuts suivants :

| Statut | Signification |
|---|---|
| Validé | Le module répond aux exigences principales de Project CRP |
| Validé sous réserve | Le module est utilisable, mais des limitations restent à traiter |
| Test complémentaire requis | Les résultats sont insuffisants pour prendre une décision |
| Rejeté | Le module présente une incompatibilité ou une contrainte majeure |

Un défaut critique entraîne normalement le rejet du module.

Exemples de défauts critiques :

- absence d’affichage sous Batocera ;
- image instable ou fortement déformée ;
- impossibilité d’utiliser la résolution native ;
- panne après échauffement ;
- encombrement mécanique incompatible ;
- câblage interne irréalisable ;
- incompatibilité majeure avec la sortie TV.

---

# 4. Matériel nécessaire

## 4.1 Matériel principal

| Élément | Requis | Disponible | Remarque |
|---|---|---|---|
| Raspberry Pi 5 – 4 Go | Oui |  | Plateforme cible CRP |
| Refroidisseur actif pour Raspberry Pi 5 | Oui |  | À installer avant les tests prolongés |
| Alimentation USB-C adaptée au Pi 5 | Oui |  | Alimentation officielle recommandée |
| Carte microSD | Oui |  | 64 Go minimum recommandé |
| Batocera compatible Raspberry Pi 5 | Oui |  | Version à noter |
| Écran Elecrow 5 pouces 1024×600 | Oui |  | Référence à confirmer |
| Câble micro-HDMI vers HDMI | Oui |  | Pour l’écran |
| Câble USB-A vers USB-C | Oui |  | Alimentation et éventuellement tactile |
| Chargeur USB 5 V | Oui |  | 1 A minimum, 2 A recommandé |
| Manette PS4 ou PS5 | Oui |  | Connexion USB pour le premier test |
| Téléviseur ou moniteur HDMI | Pour test TV |  |  |
| Second câble micro-HDMI vers HDMI | Pour test TV |  |  |

## 4.2 Matériel de mesure facultatif

| Élément | Utilité |
|---|---|
| Pied à coulisse | Mesure des dimensions du module |
| Règle métallique | Contrôle approximatif des dimensions |
| Testeur USB | Mesure de la tension, du courant et de la puissance |
| Multimètre | Vérifications électriques complémentaires |
| Thermomètre infrarouge | Mesure approximative des températures |
| Appareil photo ou téléphone | Documentation du test |

---

# 5. Informations générales du test

| Information | Valeur |
|---|---|
| Date du test | 2026-07-12 |
| Testeur | Lobapiop |
| Version de Batocera | batocera-bcm2712-43.1-20260529 |
| Modèle du Raspberry Pi | PI 5 |
| Quantité de mémoire | 4Gbi |
| Référence de l’écran | QDtech MPI5001 |
| Référence indiquée sur le PCB |  |
| Référence indiquée sur l’emballage | 5inch HD Diplay-C |
| Type de carte microSD | 64go |
| Type d’alimentation du Pi | Origine |
| Type d’alimentation de l’écran | Origine |
| Téléviseur utilisé | MSI optix MAG241CV |
| Version du firmware Raspberry Pi, si disponible |  |

---

# 6. Précautions

Avant tout branchement :

1. poser le Raspberry Pi et l’écran sur une surface non conductrice ;
2. ne pas poser les cartes électroniques sur du métal ;
3. installer le refroidisseur actif sur le Raspberry Pi ;
4. vérifier l’orientation des connecteurs ;
5. effectuer les branchements hors tension ;
6. ne pas forcer les prises HDMI ou USB-C ;
7. éviter de toucher directement les composants lorsque le système est alimenté ;
8. ne pas placer d’objet conducteur sous les cartes ;
9. vérifier que le chargeur de l’écran fournit une tension de 5 V ;
10. ne pas utiliser de câble visiblement endommagé.

Pour les premiers essais, le Raspberry Pi et l’écran doivent être alimentés séparément.

---

# 7. Schéma de branchement initial

```text
Alimentation officielle USB-C
            │
            ▼
     Raspberry Pi 5
            │
            │ micro-HDMI vers HDMI
            ▼
      Écran Elecrow

Chargeur USB 5 V
            │
            │ USB-A vers USB-C
            ▼
      Écran Elecrow

Manette PS4 ou PS5
            │
            │ USB
            ▼
     Raspberry Pi 5
```

# 8.Décision :

L’écran Elecrow 5 pouces 1024×600 est retenu comme candidat prioritaire pour Project CRP.

Statut :

Validé sous réserve.

Score après essais :

8,2 / 10.

Réserves restantes :

- consommation électrique réelle non mesurée ;
- câbles droits incompatibles avec la coque cible ;
- câbles coudés ou adaptation interne nécessaires ;
- protection obligatoire des nappes FPC ;
- validation mécanique finale à réaliser dans FreeCAD.