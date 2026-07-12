# Project CRP – TEST-C03 – Redémarrages successifs

Version : 0.1  
Statut : réalisé
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Vérifier que l’affichage revient de manière fiable après plusieurs arrêts et démarrages.

## 2. Procédure

Effectuer cinq cycles :

1. démarrer ;
2. vérifier l’image ;
3. arrêter proprement Batocera ;
4. attendre 15 secondes ;
5. redémarrer.

## 3. Résultats

| Cycle | Affichage au démarrage | Résolution correcte | Défaut observé |
|---:|---|---|---|
| 1 | Oui | Oui | Non |
| 2 | Oui | Oui | Non |
| 3 | Oui | Oui | Non |
| 4 | Oui | Oui | Non |
| 5 | Oui | Oui | Non |

## 4. Critère de réussite

Les cinq cycles doivent produire le même comportement d’affichage.

## 5. Conclusion

Résultat : Réussi 

Remarques :
