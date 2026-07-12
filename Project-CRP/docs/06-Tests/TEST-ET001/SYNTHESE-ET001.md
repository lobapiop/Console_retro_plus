# Project CRP – Synthèse des tests ET001

Version : 0.1  
Statut : quasi final – J01 reporté

---

## 1. Informations générales

| Information | Valeur |
|---|---|
| Date du début des essais | 2026-07-06 |
| Date de fin des essais | 2026-07-12 |
| Testeur | Lobapiop |
| Version de Batocera | batocera-bcm2712-43.1-20260529 |
| Modèle du Raspberry Pi | Raspberry Pi 5 – 4 Go |
| Référence de l’écran | QDtech MPI5001 |
| Référence du PCB |  |
| Alimentation du Pi | Origine PI 5 |
| Alimentation de l’écran | Orgine écran |

---

## 2. Résultats

| Test | Résultat | Critique | Action |
|---|---|---|---|
| TEST-A01 – Identification du module | Réussi | Oui |  |
| TEST-A02 – Comparaison avec le plan mécanique | Réussi | Oui | Plan constructeur non retenu comme référence finale |
| TEST-B01 – Mise sous tension de l’écran | Réussi | Oui |  |
| TEST-B02 – Premier affichage avec le Raspberry Pi | Réussi | Oui |  |
| TEST-C01 – Détection de la résolution | Réussi | Oui |  |
| TEST-C02 – Géométrie de l’image | Réussi | Oui |  |
| TEST-C03 – Redémarrages successifs | Réussi | Oui |  |
| TEST-D01 – Luminosité | Réussi | Oui |  |
| TEST-D02 – Couleurs contraste et uniformité | Réussi | Oui |  |
| TEST-D03 – Angles de vision | Réussi | Oui |  |
| TEST-D04 – Fluidité et rémanence | Réussi | Oui |  |
| TEST-E01 – Interface EmulationStation | Réussi | Oui |  |
| TEST-E02 – Jeux rétro au format 4 sur 3 | Réussi | Oui |  |
| TEST-E03 – Jeux au format large | Réussi | Oui |  |
| TEST-F01 – Affichage Nintendo DS | Réussi avec réserve | Oui | Utiliser melonDS et une disposition adaptée |
| TEST-G01 – Détection et calibration du tactile | Réussi | Oui |  |
| TEST-G02 – Tactile dans un émulateur Nintendo DS | Réussi avec réserve | Oui | Utiliser melonDS |
| TEST-H01 – Sortie vers un téléviseur seul | Réussi | Oui |  |
| TEST-H02 – Double sortie HDMI | Réussi | Oui | Comportement documenté |
| TEST-H03 – Déconnexion et reconnexion du téléviseur | Réussi | Oui |  |
| TEST-I01 – Fonctionnement prolongé et température | Réussi | Oui |  |
| TEST-J01 – Consommation électrique de l’écran | Reporté | Non | À faire avec testeur USB |
| TEST-K01 – Dimensions principales du module | Réussi | Oui |  |
| TEST-K02 – Fixations du module | Réussi | Oui |  |
| TEST-K03 – Connecteurs et composants saillants | Réussi avec réserve | Oui | Câbles coudés nécessaires |

## 3. Notes expérimentales

| Critère | Pondération | Note avant essai | Note après essai | Justification après essai |
|---|---:|---:|---:|---|
| Compatibilité Raspberry Pi | 20 % | 8 | 9 | Fonctionne avec Raspberry Pi 5 et Batocera, résolution 1024×600 validée, HDMI fonctionnel, tactile détecté. |
| Intégration mécanique | 20 % | 9 | 7,5 | Dimensions réelles acceptables, fixation possible, mais câbles droits HDMI/USB-C/jack trop encombrants pour la coque cible. Câbles coudés ou adaptation nécessaire. |
| Intégration électronique | 15 % | 8,5 | 8 | Fonctionne correctement, tactile USB reconnu, HDMI OK. Réserve restante sur consommation réelle non mesurée et câblage interne à optimiser. |
| Qualité d’affichage | 20 % | 8 | 9 | Géométrie, couleurs, luminosité, angles de vision et fluidité validés. Très bon résultat pour Project CRP. |
| Maintenance | 10 % | 8 | 8 | Module remplaçable et connectique accessible, mais présence de nappes FPC fragiles à protéger. |
| Pérennité | 10 % | 7 | 7 | Produit disponible et bien adapté, mais dépend d’un module commercial tiers non officiel Raspberry Pi. |
| Documentation | 5 % | 9 | 8,5 | Documentation suffisante, marquages PCB utiles, mais plan mécanique trouvé non conforme au module reçu. Les mesures réelles deviennent prioritaires. |
| **Score pondéré** | **100 %** | **Provisoire** | **8,2 / 10** | Écran validé sous réserve mécanique et alimentation. |


Compatibilité Raspberry Pi : 9 × 20 % = 1,80
Intégration mécanique : 7,5 × 20 % = 1,50
Intégration électronique : 8 × 15 % = 1,20
Qualité d’affichage : 9 × 20 % = 1,80
Maintenance : 8 × 10 % = 0,80
Pérennité : 7 × 10 % = 0,70
Documentation : 8,5 × 5 % = 0,425

Score total = 8,225 / 10
Score arrondi = 8,2 / 10

---

## 4. Points forts constatés

- 
- 
- 

## 5. Points faibles constatés

- 
- 
- 

## 6. Risques restant ouverts

- 
- 
- 

## 7. Impact sur Project CRP

### Architecture mécanique

Conclusion :

### Architecture électrique

Conclusion :

### Refroidissement

Conclusion :

### Maintenance

Conclusion :

### Évolutivité et pérennité

Conclusion :

---

## 8. Décision

- [ ] Écran validé
- [X] Écran validé sous réserve
- [ ] Tests complémentaires nécessaires
- [ ] Écran rejeté

Justification :
Après essais, l’écran Elecrow 5 pouces 1024×600 obtient un score pondéré de **8,2 / 10**.

Il est validé comme **candidat prioritaire pour Project CRP**, sous réserve de validation mécanique finale.


Réserves :

- consommation électrique réelle non encore mesurée ;
- câbles droits HDMI, USB-C et audio incompatibles avec la profondeur cible ;
- nécessité probable de câbles coudés ou d’une solution d’adaptation interne ;
- intégration mécanique à confirmer dans FreeCAD ;
- protection obligatoire des nappes FPC ;
- validation finale à réaliser après conception du gabarit mécanique.

Actions suivantes :

1. remplir SYNTHESE-ET001.md
2. mettre à jour ET001-Ecran.md avec la décision “validé sous réserve” 
3. préparer le gabarit FreeCAD du module Elecrow.
