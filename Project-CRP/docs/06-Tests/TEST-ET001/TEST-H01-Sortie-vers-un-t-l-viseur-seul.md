# Project CRP – TEST-H01 – Sortie vers un téléviseur seul

Version : 0.1  
Statut : à exécuter  
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Vérifier que Batocera fonctionne normalement avec un téléviseur sans l’écran Elecrow comme sortie vidéo.

## 2. Branchement

```text
Raspberry Pi 5 ── micro-HDMI/HDMI ──► Téléviseur
```

## 3. Procédure

1. Éteindre le Raspberry Pi.
2. Déconnecter le signal HDMI de l’Elecrow.
3. Connecter le téléviseur.
4. Démarrer Batocera.
5. Tester l’image, le son et un jeu.

## 4. Résultats

| Contrôle | Résultat |
|---|---|
| Image affichée sur la TV | Oui |
| Résolution correcte | Oui |
| Son HDMI fonctionnel | Oui  |
| Menus lisibles | Oui |
| Jeux fonctionnels | Oui |

## 5. Conclusion

Résultat : Réussi 
Remarques :
