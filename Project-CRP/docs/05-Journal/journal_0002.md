# Project CRP – Journal de développement 0002

Date : 5 juillet 2026  
Statut : étude ET001 en cours  
Sujet principal : sélection et commande du module d’affichage

---

# 1. Contexte

L’étude technique ET001 porte sur le choix du module d’affichage de Project CRP.

Trois candidats principaux ont été étudiés :

1. Raspberry Pi Touch Display 2 – 5 pouces ;
2. Waveshare 5inch 720×1280 LCD ;
3. Elecrow 5inch IPS HD Display-C 1024×600.

L’objectif de cette étape était de comparer les caractéristiques techniques, l’intégration mécanique, l’intégration électronique, la maintenance, la pérennité et l’impact global de chaque solution sur Project CRP.

---

# 2. Méthode de comparaison

La matrice de décision provisoire utilise les pondérations suivantes :

| Critère | Pondération |
|---|---:|
| Compatibilité Raspberry Pi | 20 % |
| Intégration mécanique | 20 % |
| Intégration électronique | 15 % |
| Qualité d’affichage | 20 % |
| Maintenance | 10 % |
| Pérennité | 10 % |
| Documentation | 5 % |
| Prix | 0 % – informatif uniquement |

Le prix n’intervient pas encore dans la décision technique.

La qualité, la fiabilité, la maintenance et la pérennité sont prioritaires.

---

# 3. Décision concernant le candidat Elecrow

Le module suivant est retenu comme candidat prioritaire pour les essais :

**Elecrow 5inch IPS HD Display-C 1024×600**

Référence étudiée :

**DLH04950B**

Cette sélection n’est pas encore une validation définitive.

Le module Elecrow devient le candidat favori provisoire en raison de :

- son orientation native en paysage ;
- sa résolution de 1024×600 ;
- sa dalle IPS ;
- sa luminosité annoncée ;
- sa faible consommation annoncée ;
- son interface HDMI standard ;
- son alimentation USB-C ;
- ses dimensions mécaniques favorables ;
- sa documentation disponible ;
- sa facilité de test sur un banc indépendant.

---

# 4. Vérification du plan mécanique

Un plan coté du module Elecrow a été retrouvé et examiné.

Les dimensions suivantes ont été relevées :

| Dimension | Valeur |
|---|---:|
| Largeur hors tout | 121,11 ± 0,2 mm |
| Hauteur hors tout | 77,93 ± 0,2 mm |
| Zone active | 108 × 64,8 mm |
| Profondeur maximale | 13,94 ± 0,2 mm |
| Épaisseur de la partie principale | 7,66 ± 0,2 mm |

La valeur commerciale d’environ 10 mm trouvée précédemment ne représente donc pas l’encombrement maximal complet.

Pour la future CAO, une profondeur réservée de **15 à 16 mm** devra être prévue autour du module afin d’intégrer :

- les tolérances ;
- les composants les plus hauts ;
- les connecteurs ;
- les fixations ;
- une marge de sécurité ;
- l’absence de contact entre le PCB et la coque.

La hauteur réelle de 77,93 mm est favorable pour la cible mécanique de Project CRP, estimée autour de 110 mm.

---

# 5. Classement provisoire

À la suite de l’analyse du plan mécanique, l’Elecrow devient le candidat présentant le meilleur compromis provisoire.

Classement actuel :

1. Elecrow 5inch IPS HD Display-C 1024×600 ;
2. Raspberry Pi Touch Display 2 – 5 pouces ;
3. Waveshare 5inch 720×1280 LCD.

Ce classement reste provisoire.

Les notes finales seront recalculées après les essais matériels.

---

# 6. Compatibilité Batocera

La compatibilité générale de Batocera avec le Raspberry Pi 5 est considérée comme acquise pour la plateforme.

Cependant, la page de compatibilité Batocera ne permet pas de valider directement un modèle particulier d’écran HDMI.

La compatibilité réelle du module Elecrow doit donc être vérifiée expérimentalement.

Les principaux points à valider sont :

- démarrage de Batocera sur l’écran ;
- détection de la résolution 1024×600 ;
- fonctionnement à 60 Hz ;
- absence de déformation ;
- absence de recadrage ;
- absence de scintillement ;
- lisibilité de l’interface EmulationStation ;
- comportement des émulateurs ;
- utilisation Nintendo DS ;
- fonctionnement du tactile ;
- fonctionnement du second port HDMI ;
- basculement vers un téléviseur ;
- comportement après redémarrage.

---

# 7. Décision de réaliser un banc de test

Il a été décidé de ne pas valider définitivement l’écran sur la seule base des fiches techniques et des avis disponibles.

Un banc de test réel sera construit autour du matériel cible de Project CRP.

Le banc doit reproduire au minimum :

- le Raspberry Pi 5 4 Go ;
- le refroidissement actif ;
- l’alimentation officielle du Raspberry Pi ;
- Batocera sur carte microSD ;
- l’écran Elecrow ;
- une liaison micro-HDMI vers HDMI ;
- une alimentation USB indépendante pour l’écran ;
- une manette USB ou Bluetooth ;
- un téléviseur pour le test de la seconde sortie HDMI.

---

# 8. Matériel déjà disponible

Les éléments suivants sont déjà disponibles :

- manette PlayStation 4 ou PlayStation 5 ;
- câble USB-A vers USB-C ;
- chargeur de téléphone USB pouvant être utilisé pour l’alimentation séparée de l’écran, sous réserve de fournir au minimum 5 V / 1 A.

La manette sera utilisée en USB lors des premiers essais afin d’éviter qu’un éventuel problème Bluetooth ne perturbe la validation de l’affichage.

---

# 9. Commande du matériel

La commande du matériel nécessaire au banc de test a été lancée.

Livraison prévue :

**mardi 7 juillet 2026**

Le contenu exact de la commande devra être vérifié à la réception.

Les éléments attendus pour le test comprennent notamment :

- Raspberry Pi 5 4 Go ;
- système de refroidissement actif ;
- alimentation USB-C adaptée au Raspberry Pi 5 ;
- carte microSD ;
- câble micro-HDMI vers HDMI ;
- module d’affichage Elecrow 5 pouces 1024×600.

Un second câble micro-HDMI vers HDMI pourra être nécessaire pour tester simultanément :

- l’écran interne Elecrow ;
- la sortie vers un téléviseur.

---

# 10. Décision actuelle

La décision actuelle est la suivante :

> Le module Elecrow DLH04950B est retenu comme candidat prioritaire pour la phase de prototype et de validation expérimentale.

Cette décision ne constitue pas encore une sélection définitive pour Project CRP.

La sélection définitive dépendra des résultats du protocole d’essai.

---

# 11. Critères de validation

Le module pourra être validé si les essais confirment :

- un démarrage fiable sous Batocera ;
- une résolution native correcte ;
- une image sans défaut visible ;
- une luminosité suffisante ;
- une latence acceptable ;
- une température raisonnable ;
- une consommation compatible avec l’objectif d’autonomie ;
- une intégration mécanique possible ;
- un câblage interne réalisable ;
- une sortie TV fonctionnelle ;
- une maintenance simple ;
- un comportement stable après plusieurs cycles d’arrêt et de redémarrage.

---

# 12. Risques encore ouverts

Les risques suivants restent ouverts :

- configuration manuelle éventuelle du mode 1024×600 ;
- compatibilité avec certaines versions de Batocera ;
- encombrement réel des câbles HDMI et USB ;
- rayon de courbure des câbles ;
- épaisseur totale avec les connecteurs branchés ;
- disponibilité à long terme du module ;
- comportement du tactile sous Batocera ;
- comportement de la double sortie HDMI ;
- consommation réelle selon la luminosité ;
- qualité réelle de l’affichage ;
- lisibilité des jeux Nintendo DS sur 5 pouces.

---

# 13. Prochaine étape

La prochaine étape principale sera l’exécution du protocole de validation ET001 à la réception du matériel.

En attendant la livraison, les travaux documentaires, logiciels et mécaniques préparatoires peuvent continuer sans prendre de décision irréversible.