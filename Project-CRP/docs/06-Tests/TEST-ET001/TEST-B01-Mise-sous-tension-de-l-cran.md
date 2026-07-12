# Project CRP – TEST-B01 – Mise sous tension de l’écran

Version : 0.1  
Statut : réalisé
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Vérifier que l’écran s’allume normalement lorsqu’il est alimenté seul.

## 2. Précautions

- poser le module sur une surface non conductrice ;
- effectuer les branchements hors tension ;
- utiliser une alimentation USB 5 V ;
- ne pas toucher les composants pendant l’essai.

## 3. Procédure

1. Connecter le câble USB-C à l’écran.
2. Connecter le câble à un chargeur USB 5 V.
3. Mettre le chargeur sous tension.
4. Observer le module pendant au moins 30 secondes.
5. Couper immédiatement l’alimentation en cas d’odeur, de bruit ou de chauffe anormale.

## 4. Résultats

| Observation | Résultat |
|---|---|
| Rétroéclairage visible | Oui |
| Message d’absence de signal | Oui |
| LED d’état éventuelle | je n'ai pas vu de led |
| Bruit anormal |non |
| Odeur anormale | non |
| Chauffe immédiate anormale | non |

## 5. Critère de réussite

L’écran s’allume sans comportement dangereux ou anormal.

## 6. Conclusion

Résultat : Réussi 

Remarques :
