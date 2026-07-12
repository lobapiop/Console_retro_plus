# Project CRP – TEST-F01 – Affichage Nintendo DS

Version : 0.1  
Statut : réalisé
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Évaluer la lisibilité et l’ergonomie de la Nintendo DS sur l’écran de 5 pouces.

## 2. Dispositions à tester

- écrans l’un au-dessus de l’autre ;
- écrans côte à côte ;
- écran principal agrandi et secondaire réduit ;
- écran unique avec changement par bouton.

## 3. Résultats

| Disposition | Lisibilité principal | Lisibilité secondaire | Confort | Note globale |
|---|---:|---:|---:|---:|
| Verticale |  |  |  |  |
| Côte à côte |  |  |  |  |
| Principal agrandi |  |  |  |  |
| Écran unique |  |  |  |  |

## 4. Contrôles

| Contrôle | Résultat |
|---|---|
| Texte lisible | Oui |
| Écrans suffisamment grands | Oui |
| Changement de disposition accessible | Oui |
| Absence de déformation | Oui |
| Performances suffisantes | Oui |
| Tactile utilisable | Non |

## Observation sauvegarde Nintendo DS

Après installation des fichiers BIOS Nintendo DS requis, le jeu Pokémon DS fonctionne correctement au relancement après sauvegarde.

Résultat :

- jeu lancé : oui ;
- sauvegarde interne créée : oui ;
- fermeture propre de l’émulateur : oui ;
- relance après sauvegarde : oui ;
- erreur de communication après relance : non après ajout des BIOS ;
- cause probable du problème initial : BIOS / firmware Nintendo DS manquants.

Conclusion :

Le problème observé n’était pas lié au module d’affichage Elecrow.  
Le test Nintendo DS peut reprendre avec un environnement logiciel corrigé.

## 5. Conclusion

Disposition préférée : haut d'abord 

Note globale sur 10 : 8

Résultat : Acceptable avec réserve (j'aimerais pouvoir faire fonctionné le tactile ou au moins le joystik)