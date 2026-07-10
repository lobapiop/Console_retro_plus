# Project CRP – TEST-G01 – Détection et calibration du tactile

Version : 0.1  
Statut : à exécuter  
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Vérifier la détection, l’orientation et la précision du tactile.

## 2. Procédure

1. Connecter l’USB du tactile.
2. Démarrer Batocera.
3. Tester le centre et les quatre coins.
4. Effectuer un glissement.
5. Tester plusieurs pressions rapides.
6. Vérifier l’orientation après toute rotation d’écran.

## 3. Résultats

| Contrôle | Résultat |
|---|---|
| Tactile détecté automatiquement | Oui |
| Coin supérieur gauche correct | Pas testable |
| Coin supérieur droit correct | Pas testable |
| Coin inférieur gauche correct | Ok |
| Coin inférieur droit correct | Ok |
| Centre correct | Ok |
| Glissement correct | Ok |
| Multitouch détecté | Pas testable |
| Calibration nécessaire | Non |
| Orientation tactile correcte | Oui |

## 4. Conclusion

Résultat : Réussi 

Paramètres nécessaires :

Commentaires : Je ne pouvais pas tester les angles pour savoir si tout est ok (pas de bouton disponible sur les angles). Même constat pour le multitouch.
