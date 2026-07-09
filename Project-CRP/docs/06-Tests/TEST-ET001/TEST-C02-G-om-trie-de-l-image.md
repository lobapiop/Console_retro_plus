# Project CRP – TEST-C02 – Géométrie de l’image

Version : 0.1  
Statut : à exécuter  
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Vérifier l’absence d’étirement, de recadrage et de déformation.

## 2. Image de référence

Utiliser une mire comprenant :

- un cercle ;
- un carré ;
- une grille ;
- une bordure sur chaque côté ;
- du texte de petite taille.

## 3. Résultats

| Contrôle | Conforme | Remarque |
|---|---|---|
| Le cercle reste circulaire | Oui  |  |
| Le carré reste carré | Oui |  |
| Les quatre bordures sont visibles | Oui |  |
| L’image est centrée | Oui |  |
| Aucun recadrage | Oui |  |
| Aucun étirement horizontal | Oui |  |
| Aucun étirement vertical | Oui |  |
| Texte net et lisible | Oui |  |

## 4. Critère de réussite

Aucune déformation gênante ne doit être visible.

## 5. Conclusion

Résultat : Réussi

Remarques :
