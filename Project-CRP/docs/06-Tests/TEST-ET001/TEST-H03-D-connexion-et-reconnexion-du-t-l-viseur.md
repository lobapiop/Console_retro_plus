# Project CRP – TEST-H03 – Déconnexion et reconnexion du téléviseur

Version : 0.1  
Statut : réalisé  
Étude associée : ET001 – Module d’affichage  
Composant testé : Elecrow 5inch IPS HD Display-C 1024×600  
Référence attendue : DLH04950B  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  

---

## 1. Objectif

Simuler le retrait et la remise en place de la console dans son futur dock.

## 2. Procédure

1. Démarrer avec le téléviseur connecté.
2. Vérifier l’affichage.
3. Déconnecter le câble HDMI du téléviseur.
4. Observer l’Elecrow.
5. Reconnecter le téléviseur.
6. Vérifier l’image et le son.

## 3. Résultats

| Contrôle | Résultat |
|---|---|
| Retour automatique sur l’Elecrow | Oui |
| Perte temporaire de l’image | Oui |
| Redémarrage nécessaire | Non |
| Interface toujours utilisable | Oui |
| Son correctement redirigé | pas de son |
| Reconnexion TV détectée | Oui |

## 4. Conclusion

Résultat : Réussi 

Remarques : quand je reconnecte l'écran tv, l'écran Elecrow ne se remet pas.
