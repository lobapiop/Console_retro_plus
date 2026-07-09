# Project CRP – TEST-A02 – Comparaison avec le plan mécanique

Version : 0.1  
Statut : à exécuter  
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Déterminer si le plan mécanique précédemment trouvé correspond réellement au module reçu.

## 2. Matériel nécessaire

- module Elecrow ;
- plan mécanique trouvé ;
- règle ou pied à coulisse ;
- appareil photo.

## 3. Procédure

1. Comparer la forme générale du PCB.
2. Comparer la position et l’orientation des connecteurs.
3. Compter les boutons et les trous de fixation.
4. Comparer les dimensions générales.
5. Photographier chaque différence.

## 4. Résultats

| Élément comparé | Identique | Différent | Remarque |
|---|---|---|---|
| Forme générale du PCB | Identique |  |  |
| Position du port HDMI | Identique |  |  |
| Position du port USB-C | Identique |  |  |
| Nombre de boutons | Identique |  |  |
| Position des boutons | Identique |  |  |
| Nombre de trous de fixation | Identique |  |  |
| Position des trous | Identique |  |  |
| Forme des composants arrière | Identique |  |  |
| Dimensions générales | Identique |  |  |

## 5. Décision documentaire

Plan correspondant au produit :

- [X] Oui, correspondance confirmée
- [ ] Correspondance partielle
- [ ] Non, modèle différent
- [ ] Impossible à déterminer

Plan utilisable pour FreeCAD :

- [ ] Oui
- [ ] Non
- [X] Seulement après correction

## 6. Conclusion

Résultat : Réussi 

Corrections à apporter au plan : 
## Mise à jour – Distinction entre hauteur totale et zone écran

Le module Elecrow reçu mesure approximativement :

- longueur horizontale totale : 121,31 mm ;
- hauteur totale du module : 95,47 mm ;
- profondeur approximative : 10 mm ;
- rectangle physique de l’écran : 75,65 mm de hauteur.

La différence entre la hauteur totale du module et le rectangle physique de l’écran est d’environ :

95,47 mm - 75,65 mm = 19,82 mm.

Cette zone supplémentaire semble correspondre principalement à une zone technique liée aux fixations, au PCB ou aux connecteurs, et non à la surface visible de l’écran.

Cette distinction est importante pour Project CRP :

- la façade visible ne doit pas nécessairement exposer les 95,47 mm complets ;
- l’ouverture esthétique peut être dimensionnée autour de la zone écran ;
- la zone technique supérieure peut être cachée derrière la coque ;
- l’encombrement interne total reste néanmoins de 95,47 mm.

La contrainte mécanique est donc moins sévère que si toute la hauteur était visible en façade.

La note provisoire d’intégration mécanique de l’Elecrow est corrigée à 8/10.

Le module reste candidat prioritaire sous réserve de validation du câblage, des fixations et des tests d’affichage.
