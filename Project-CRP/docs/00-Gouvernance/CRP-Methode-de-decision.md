# Project CRP – Méthode de décision

Version : 1.0

---

# 1. Objectif

Ce document définit la méthode utilisée pour concevoir **Project CRP**.

Son objectif est de garantir des décisions cohérentes, justifiées et traçables tout au long du projet.

Toutes les décisions techniques devront respecter cette méthode.

---

# 2. Philosophie

Project CRP est développé selon une approche d'ingénierie progressive.

Avant toute décision, nous cherchons à :

* comprendre le besoin ;
* identifier les contraintes ;
* comparer plusieurs solutions ;
* choisir la solution la plus adaptée au projet.

L'objectif n'est pas de retenir le composant le plus performant ou le moins cher, mais celui qui répond le mieux aux besoins de Project CRP.

---

# 3. Principes de conception

## Règle CRP n°1 – Simplicité

Une architecture ne sera complexifiée que si un bénéfice technique clairement identifié le justifie.

Cela concerne notamment :

* le nombre de PCB ;
* le nombre de connecteurs ;
* le nombre de nappes ;
* les mécanismes particuliers.

La solution la plus simple est privilégiée lorsqu'elle répond au besoin.

---

## Règle CRP n°2 – Ergonomie

Chaque élément visible ou accessible de la console doit avoir une justification fonctionnelle ou ergonomique.

Son emplacement ne doit jamais être choisi uniquement pour des raisons esthétiques ou par imitation d'une autre console.

Avant de valider son implantation, les questions suivantes doivent être posées :

* Est-il facilement accessible ?
* Peut-il être actionné involontairement ?
* Simplifie-t-il la maintenance ?
* Simplifie-t-il la conception ?
* Améliore-t-il réellement l'expérience utilisateur ?

---

## Règle CRP n°3 – Décision objective

Aucun composant ne sera retenu sans avoir été comparé à au moins deux alternatives.

Chaque étude technique devra comporter une comparaison argumentée et une matrice de décision.

Les décisions ne seront jamais prises sur une simple impression.

---

## Règle CRP n°4 – Évolutivité

Une décision reste valide tant qu'aucune meilleure solution objectivement démontrée n'existe.

Si un nouveau composant apparaît ou si une meilleure solution est identifiée, elle pourra être évaluée selon la même méthode avant de modifier le projet.

## Règle CRP n°5 

Aucun plan mécanique ne peut être considéré comme définitif tant que les composants structurants n'ont pas été sélectionnés.
---

### Règle CRP n°6 – Pérennité

Project CRP privilégie les composants dont la disponibilité est durable.

Lorsqu'un choix est possible entre plusieurs composants offrant des performances comparables, la préférence est donnée à celui qui :

* est distribué par un fabricant reconnu ;
* est disponible auprès de plusieurs revendeurs ;
* bénéficie d'une documentation maintenue ;
* présente de bonnes chances de rester disponible sur le long terme.

Le prix n'est pas un critère décisionnel pendant la phase de conception. Il est renseigné à titre informatif et sera pris en compte uniquement lors de la validation finale de la nomenclature (BOM).

## Règle CRP n°7 – Évaluation de l'impact système

Chaque composant étudié devra être évalué non seulement sur ses caractéristiques propres, mais également sur son impact global sur Project CRP.

Cette analyse permettra de mesurer les conséquences du choix d'un composant sur l'ensemble de la console.

Pour chaque étude technique, une section **"Impact sur Project CRP"** devra être ajoutée.

Cette section analysera au minimum les points suivants :

| Domaine                   | Questions à se poser                                                                       |
| ------------------------- | ------------------------------------------------------------------------------------------ |
| Architecture mécanique    | Le composant influence-t-il les dimensions du boîtier ? Son implantation est-elle simple ? |
| Architecture électronique | Modifie-t-il le câblage, le nombre de PCB ou les connecteurs ?                             |
| Consommation électrique   | Quel est son impact sur l'autonomie et le système d'alimentation ?                         |
| Refroidissement           | Génère-t-il davantage de chaleur ? Influence-t-il le flux d'air ?                          |
| Maintenance               | Peut-il être remplacé facilement ? Nécessite-t-il un démontage important ?                 |
| Évolutivité               | Facilite-t-il les futures évolutions du projet ?                                           |
| Pérennité                 | Le composant a-t-il de bonnes chances d'être disponible plusieurs années ?                 |
| Documentation             | La documentation est-elle suffisante pour assurer la maintenance du projet ?               |

Cette analyse ne remplace pas la matrice de décision. Elle vient la compléter en apportant une vision globale des conséquences de chaque choix.

L'objectif est de privilégier les composants qui apportent le meilleur équilibre pour l'ensemble du projet, plutôt que ceux présentant uniquement les meilleures caractéristiques individuelles.


# 4. Cycle de décision

Chaque étude technique suit le cycle suivant :

1. Définition du besoin.
2. Identification des contraintes.
3. Recherche des solutions disponibles.
4. Comparaison des solutions.
5. Prototype ou validation lorsque nécessaire.
6. Décision.
7. Mise à jour de la documentation.
8. Mise à jour de la BOM si la décision est définitive.

Une étude n'est considérée comme terminée qu'après une décision clairement documentée.

---

# 5. Matrice de décision

Sauf exception justifiée, les composants seront évalués selon les critères suivants :

| Critère                        | Pondération |
| ------------------------------ | ----------: |
| Compatibilité avec Project CRP |        30 % |
| Intégration mécanique          |        20 % |
| Maintenance                    |        15 % |
| Disponibilité                  |        15 % |
| Documentation                  |        10 % |
| Prix                           |        10 % |

Les pondérations pourront être adaptées lorsque la nature du composant le justifie.

Chaque critère est noté sur 10.

Le score final est obtenu par pondération.

---

# 6. Documentation

Toute décision importante doit être reportée dans :

* le cahier des charges, si elle modifie les objectifs du projet ;
* le document d'architecture concerné, si elle modifie la conception ;
* le journal de développement, afin de conserver l'historique ;
* la BOM, lorsque le composant est définitivement retenu.

Le dépôt GitHub constitue la référence officielle du projet.

---

# 7. Gestion des évolutions

Une décision validée ne sera pas remise en question sans justification technique.

Toute évolution devra préciser :

* le problème identifié ;
* les solutions étudiées ;
* les raisons du changement ;
* les impacts sur le projet.

L'objectif est de garantir la stabilité de la conception tout en restant ouvert aux améliorations.

---

# 8. Prototype avant optimisation

Le projet privilégie une approche progressive.

Lorsqu'une fonction complexe peut être validée avec un module du commerce, cette solution est privilégiée pour le prototype.

Une version personnalisée ne sera développée qu'après validation du fonctionnement.

Exemples :

* Raspberry Pi Pico utilisé avant l'intégration du RP2040 sur un PCB dédié.
* Module d'alimentation du commerce utilisé avant la conception d'une carte CRP.

---

# 9. Philosophie générale

Project CRP privilégie :

* la simplicité ;
* la robustesse ;
* la réparabilité ;
* la modularité lorsque celle-ci apporte une réelle valeur ;
* la documentation complète.

Chaque décision doit permettre de rendre la console plus fiable, plus facile à maintenir et plus simple à comprendre.

---

# 10. Devise du projet

> **Construire simplement. Documenter systématiquement. Décider objectivement. Améliorer continuellement.**
