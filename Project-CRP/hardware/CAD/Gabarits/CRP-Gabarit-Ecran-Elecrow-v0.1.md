
# Objectif du gabarit :

Créer une représentation mécanique simplifiée mais dimensionnellement fiable du module écran Elecrow afin de préparer son intégration dans Project CRP.

Le gabarit sert à valider l’encombrement, les fixations, la zone visible, les connecteurs, les nappes fragiles et les volumes de dégagement nécessaires avant toute conception de coque complète.


Module complet : 121,31 × 95,47 × 10 mm
Rectangle écran physique : 121,31 × 75,65 mm
Zone active visible : environ 108 × 64,8 mm
Trous de fixation : Ø 3 mm
Trous hauts : environ Y = 5 mm
Trous bas : environ Y = 91 mm
Profondeur de réservation avec câbles droits : 65 mm
Câbles coudés nécessaires : oui
Zones FPC : à protéger


1. créer le gabarit 2D simple du module ;
2. placer les quatre trous de fixation ;
3. placer la zone écran visible ;
4. ajouter les volumes interdits pour les connecteurs ;
5. ajouter les zones fragiles FPC ;
6. extruder en volume simple 3D ;
7. vérifier si ça rentre dans l’enveloppe CRP cible ;
8. documenter les réserves.


# Données 
Module complet :
121,31 mm × 95,47 mm × 10 mm

Rectangle écran physique :
121,31 mm × 75,65 mm

Zone active visible :
environ 108 mm × 64,8 mm

Trous de fixation :
diamètre 3 mm

Positions des trous :
T1 : X = 5 mm, Y = 5 mm
T2 : X = 117,57 mm, Y = 5 mm
T3 : X = 5 mm, Y = 91 mm
T4 : X = 117,57 mm, Y = 91 mm

# Repère

Origine = coin supérieur gauche du module
X = vers la droite
Y = vers le bas
Z = épaisseur

T1 haut gauche : X = 5 mm, Y = 95,47 - 5 = 90,47 mm
T2 haut droit : X = 117,57 mm, Y = 90,47 mm
T3 bas gauche : X = 5 mm, Y = 95,47 - 91 = 4,47 mm
T4 bas droit : X = 117,57 mm, Y = 4,47 mm

Position verticale de la zone écran physique à confirmer

| Élément | Mesure |
|---|---:|
| Largeur totale avec pattes | 121,31 mm |
| Hauteur totale avec pattes | 95,47 mm |
| Largeur corps principal sans pattes | 121,31 mm |
| Hauteur corps principal sans pattes | 78 mm |
| Dépassement patte gauche | 9 mm |
| Dépassement patte droite | 9 mm |
| Dépassement patte haute | 9 mm |
| Dépassement patte basse | 9 mm |
| Largeur d’une patte | 7.5 mm |
| Diamètre trou fixation | 3 mm |