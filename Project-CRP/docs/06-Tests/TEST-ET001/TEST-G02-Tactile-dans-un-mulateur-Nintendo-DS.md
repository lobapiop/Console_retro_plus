# Project CRP – TEST-G02 – Tactile dans un émulateur Nintendo DS

Version : 0.1  
Statut : réalisé – réussi avec réserve
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Vérifier l’utilisation du tactile dans les jeux Nintendo DS.

## 2. Procédure

1. Lancer un jeu nécessitant le stylet.
2. Tester des pressions précises.
3. Tester des glissements.
4. Changer la disposition des deux écrans.
5. Refaire les mêmes actions.

## 3. Résultats

| Contrôle | Conforme | Remarque |
|---|---|---|
| Position du toucher correcte |  |  |
| Réactivité suffisante |  |  |
| Glissements reconnus |  |  |
| Absence de décalage important |  |  |
| Fonctionnement après changement de disposition |  |  |


| USB-C écran connecté au Raspberry Pi | Oui |
| Nouveau périphérique détecté dans /proc/bus/input/devices | Oui |
| Nom du périphérique tactile | QDtech MPI5001 |
| Handler détecté |  event0 |
| Type d’entrée | Coordonnées absolues |
| Réaction tactile dans Batocera | Oui |
| Réaction tactile dans jeu DS | Oui après changement emulateur (melonDS)|
| Calibration nécessaire | À confirmer |

## Résultat TEST-G02 – Tactile dans un émulateur Nintendo DS

Jeu testé :  
Émulateur initial : autre cœur DS / configuration initiale non retenue
Émulateur validé : melonDS  

Le tactile physique de l’écran est détecté par Batocera sous le nom `QDtech MPI5001`.

Avec l’émulateur initial, le stylet DS pouvait être contrôlé au joystick, mais ni la souris USB ni le tactile physique de l’écran ne fonctionnaient dans le jeu.

Après passage à l’émulateur `melonDS`, le tactile physique fonctionne correctement dans le jeu Nintendo DS.

Résultat :

| Contrôle | Conforme | Remarque |
|---|---|---|
| Périphérique tactile détecté par Batocera | Oui | `QDtech MPI5001` |
| Toucher simple reconnu dans le jeu DS | Oui | Avec melonDS |
| Position du toucher correcte | Oui  |  |
| Glissement reconnu | Oui |  |
| Réactivité suffisante | Oui  |  |
| Fonctionnement via souris USB | Non  | Non fonctionnel avec l’émulateur initial |
| Fonctionnement via joystick | Oui | Fonctionnel avec l’émulateur initial |
| Fonctionnement après changement d’émulateur | Oui | melonDS |


## 4. Conclusion

Résultat : Réussi avec réserve
Réserve : confort Nintendo DS dépendant de la disposition d’écran et de l’émulateur utilisé.

Le tactile Nintendo DS est validé avec `melonDS`.

Réserve :

Le tactile physique n’est pas validé avec tous les émulateurs DS disponibles. Pour Project CRP, `melonDS` devient l’émulateur recommandé pour les tests Nintendo DS nécessitant le tactile.