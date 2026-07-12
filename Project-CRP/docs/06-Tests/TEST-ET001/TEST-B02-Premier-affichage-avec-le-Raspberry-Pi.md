# Project CRP – TEST-B02 – Premier affichage avec le Raspberry Pi

Version : 0.1  
Statut : réalisé 
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Vérifier que le Raspberry Pi 5 affiche correctement la séquence de démarrage et Batocera sur l’écran.

## 2. Branchement

```text
Alimentation Pi 5 ──► Raspberry Pi 5
Raspberry Pi 5 ── micro-HDMI/HDMI ──► Elecrow
Chargeur USB 5 V ── USB-C ──► Elecrow
Manette PS4/PS5 ── USB ──► Raspberry Pi 5
```

## 3. Procédure

1. Couper toutes les alimentations.
2. Insérer la microSD Batocera.
3. Brancher le câble HDMI.
4. Alimenter l’écran.
5. Alimenter le Raspberry Pi.
6. Observer toute la séquence pendant au moins deux minutes.

## 4. Résultats

| Point contrôlé | Résultat |
|---|---|
| Logo ou texte visible au démarrage | oui |
| Affichage pendant le chargement | oui |
| Démarrage de Batocera | oui |
| Image centrée | oui |
| Image complète | oui |
| Image stable | oui |
| Couleurs normales | oui |
| Absence de scintillement | oui |
| Absence de lignes parasites | oui |

## 5. Critère de réussite

Batocera apparaît de manière stable et exploitable.

## 6. Conclusion

Résultat : Réussi 

Remarques : je n'ai pas testé sur un jeu DS mais Nintendo 64 (dongkey kong) qui est par défaut sur le système.
