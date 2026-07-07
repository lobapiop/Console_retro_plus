# Project CRP – Cahier de tests ET001

Version : 0.1  
Statut : à exécuter  
Objet : validation expérimentale du module d’affichage Elecrow 5 pouces 1024×600

---

## 1. Ordre recommandé

### Priorité 1 — Identification et premier démarrage

1. TEST-A01
2. TEST-A02
3. TEST-B01
4. TEST-B02
5. TEST-C01
6. TEST-C02
7. TEST-C03

### Priorité 2 — Qualité et usage

8. TEST-D01
9. TEST-D02
10. TEST-D03
11. TEST-D04
12. TEST-E01
13. TEST-E02
14. TEST-E03
15. TEST-F01

### Priorité 3 — Fonctions complémentaires

16. TEST-G01
17. TEST-G02
18. TEST-H01
19. TEST-H02
20. TEST-H03
21. TEST-I01
22. TEST-J01

### Priorité 4 — Relevé mécanique

23. TEST-K01
24. TEST-K02
25. TEST-K03

---

## 2. Fichiers

| Code | Test | Fichier |
|---|---|---|
| TEST-A01 | Identification du module | `TEST-A01-Identification-du-module.md` |
| TEST-A02 | Comparaison avec le plan mécanique | `TEST-A02-Comparaison-avec-le-plan-m-canique.md` |
| TEST-B01 | Mise sous tension de l’écran | `TEST-B01-Mise-sous-tension-de-l-cran.md` |
| TEST-B02 | Premier affichage avec le Raspberry Pi | `TEST-B02-Premier-affichage-avec-le-Raspberry-Pi.md` |
| TEST-C01 | Détection de la résolution | `TEST-C01-D-tection-de-la-r-solution.md` |
| TEST-C02 | Géométrie de l’image | `TEST-C02-G-om-trie-de-l-image.md` |
| TEST-C03 | Redémarrages successifs | `TEST-C03-Red-marrages-successifs.md` |
| TEST-D01 | Luminosité | `TEST-D01-Luminosit.md` |
| TEST-D02 | Couleurs contraste et uniformité | `TEST-D02-Couleurs-contraste-et-uniformit.md` |
| TEST-D03 | Angles de vision | `TEST-D03-Angles-de-vision.md` |
| TEST-D04 | Fluidité et rémanence | `TEST-D04-Fluidit-et-r-manence.md` |
| TEST-E01 | Interface EmulationStation | `TEST-E01-Interface-EmulationStation.md` |
| TEST-E02 | Jeux rétro au format 4 sur 3 | `TEST-E02-Jeux-r-tro-au-format-4-sur-3.md` |
| TEST-E03 | Jeux au format large | `TEST-E03-Jeux-au-format-large.md` |
| TEST-F01 | Affichage Nintendo DS | `TEST-F01-Affichage-Nintendo-DS.md` |
| TEST-G01 | Détection et calibration du tactile | `TEST-G01-D-tection-et-calibration-du-tactile.md` |
| TEST-G02 | Tactile dans un émulateur Nintendo DS | `TEST-G02-Tactile-dans-un-mulateur-Nintendo-DS.md` |
| TEST-H01 | Sortie vers un téléviseur seul | `TEST-H01-Sortie-vers-un-t-l-viseur-seul.md` |
| TEST-H02 | Double sortie HDMI | `TEST-H02-Double-sortie-HDMI.md` |
| TEST-H03 | Déconnexion et reconnexion du téléviseur | `TEST-H03-D-connexion-et-reconnexion-du-t-l-viseur.md` |
| TEST-I01 | Fonctionnement prolongé et température | `TEST-I01-Fonctionnement-prolong-et-temp-rature.md` |
| TEST-J01 | Consommation électrique de l’écran | `TEST-J01-Consommation-lectrique-de-l-cran.md` |
| TEST-K01 | Dimensions principales du module | `TEST-K01-Dimensions-principales-du-module.md` |
| TEST-K02 | Fixations du module | `TEST-K02-Fixations-du-module.md` |
| TEST-K03 | Connecteurs et composants saillants | `TEST-K03-Connecteurs-et-composants-saillants.md` |

---

## 3. Statuts possibles

- **Réussi** : exigences satisfaites.
- **Réussi avec configuration** : fonctionnement validé après réglage documenté.
- **Acceptable avec réserve** : utilisable, mais une limitation doit être suivie.
- **Test complémentaire requis** : résultat insuffisant.
- **Échec** : exigence non satisfaite.
- **Non applicable** : test sans objet pour la configuration évaluée.

---

## 4. Règle de validation

L’écran ne doit être déclaré définitivement validé qu’après :

- réussite du premier affichage ;
- résolution et géométrie correctes ;
- stabilité après redémarrages ;
- qualité d’image jugée suffisante ;
- fonctionnement prolongé sans défaut critique ;
- intégration mécanique jugée possible ;
- absence de blocage majeur pour la sortie TV.
