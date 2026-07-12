# Project CRP – TEST-K03 – Connecteurs et composants saillants

Version : 0.1  
Statut : réalisé
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Déterminer les volumes à réserver autour des connecteurs, boutons et composants arrière.

## 2. Procédure

1. Repérer chaque connecteur.
2. Mesurer sa position depuis deux bords de référence.
3. Mesurer son débord.
4. Brancher les câbles sans alimenter le système.
5. estimer le rayon de courbure et le dégagement nécessaire.

## 3. Résultats

| Connecteur | Débord rigide avec câble branché | Rayon de courbure estimé | Dégagement recommandé |
|---|---:|---:|---:|
| USB-C écran | 40 mm | 10 mm | 55 mm |
| HDMI | 40 mm | 20 mm | 65 mm |
| Jack audio  | 40 mm | 10 mm | 55 mm |
| Connecteur FPC |  |  |  |
| Boutons OSD |  |  |  |
| Composant le plus haut |  |  |  |

## 4. Câblage

| Câble | Connecteur droit/coudé | Rayon minimal observé | Compatible avec la coque cible |
|---|---|---:|---|
| HDMI | Droit | 20mm |  Non  |
| USB-C | Droit | 10mm |  Non |
| Audio | Droit | 10mm  |  Non |

## 5. Conclusion

Profondeur de réservation recommandée :

`65 mm`

Câbles coudés nécessaires : Oui 

Remarques :

Connecteur FPC principal dalle LCD : Oui
Position : centre-bas de la carte
Nappe présente : Oui, nappe orange large
Risque mécanique : élevé
Remarque : ne pas plier fortement, ne pas écraser, prévoir un dégagement dans la coque.

Connecteur FPC Display secondaire : Oui
Position : sous le connecteur HDMI
Nappe présente : Non
Risque mécanique : moyen à élevé
Remarque : zone à protéger, proche du connecteur HDMI.

Petit connecteur FPC secondaire : Oui
Position : partie haute-gauche de la carte, sous la zone earphone / touch
Nappe présente : Oui
Risque mécanique : moyen
Remarque : petite nappe fragile, ne pas mettre en contrainte.

## Connecteurs FPC observés

| Élément | Présence | Position | Remarque |
|---|---|---|---|
| FPC principal dalle LCD | Oui | centre-bas de la carte | grande nappe orange, zone critique |
| FPC Display secondaire | Oui | sous le connecteur HDMI | proche du HDMI, à protéger |
| Petit FPC secondaire | Oui | haut-gauche / zone Touch | petite nappe fragile |
| Connecteur 5V/Uart/GND | Non FPC | haut-centre | connecteur filaire, probablement JST |
| Boutons OSD | Non FPC | bord bas | boutons physiques de réglage écran |

Conclusion :

Le module comporte plusieurs nappes FPC visibles. Ces zones sont mécaniquement sensibles et devront être protégées dans la future coque. Aucun appui direct de la coque, d’une entretoise ou d’un câble ne devra être exercé sur les nappes ou sur leurs connecteurs.