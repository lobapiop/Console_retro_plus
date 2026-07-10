# Project CRP – TEST-H02 – Double sortie HDMI

Version : 0.1  
Statut : à exécuter  
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Observer le comportement lorsque l’Elecrow et le téléviseur sont connectés simultanément.

## 2. Branchement

```text
Raspberry Pi 5 – micro-HDMI 0 ──► Écran Elecrow
Raspberry Pi 5 – micro-HDMI 1 ──► Téléviseur
```

## 3. Observation 

| Observation                                   | Résultat             |
| --------------------------------------------- | -------------------- |
| Logo / texte de démarrage visible sur Elecrow | Oui                  |
| Logo / texte de démarrage visible sur TV      | Oui                  |
| Interface Batocera visible sur Elecrow        | Oui                  |
| Interface Batocera visible sur TV             | Non                  |
| Les deux écrans affichent la même image       | Non                  |
| Un seul écran affiche l’image                 | TV / Aucun           |
| Image déformée sur Elecrow                    | Non                  |
| Image déformée sur TV                         | Non                  |


## 2.1 Branchement

```text
Raspberry Pi 5 – micro-HDMI 0 ──► Téléviseur
Raspberry Pi 5 – micro-HDMI 1 ──► Écran Elecrow

```

## 3.1 Observation 

| Observation                                   | Résultat             |
| --------------------------------------------- | -------------------- |
| Logo / texte de démarrage visible sur Elecrow | Oui                  |
| Logo / texte de démarrage visible sur TV      | Oui                  |
| Interface Batocera visible sur Elecrow        | Oui                  |
| Interface Batocera visible sur TV             | Non                  |
| Les deux écrans affichent la même image       | Non                  |
| Un seul écran affiche l’image                 | Elecrow / Aucun           |
| Image déformée sur Elecrow                    | Non                  |
| Image déformée sur TV                         | Non                  |


## 4. Résultats

| Contrôle | Résultat |
|---|---|
| Démarrage avec les deux écrans | Oui |
| Elecrow détecté | Oui |
| Téléviseur détecté | Oui |
| Image sur un seul écran | Oui |
| Image sur les deux écrans | Non |
| Écran principal identifiable | Oui |
| Résolutions correctes | Oui |
| Son envoyé au bon périphérique | pas de son |
| Basculement sans redémarrage | Oui |
| Basculement après redémarrage | Non testé |

## 5. Description détaillée

Comportement observé :

Configuration nécessaire :

## 5. Conclusion

Résultat : Réussi 