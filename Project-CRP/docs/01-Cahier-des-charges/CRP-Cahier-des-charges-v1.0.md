# Project CRP - Cahier des charges

Version : 1.0

---

# 1. Présentation

Project CRP (Console Retro Plus) est un projet de conception d'une console portable de rétrogaming basée sur un Raspberry Pi 5.

L'objectif est de concevoir une console fiable, ergonomique, facilement réparable et entièrement documentée.

Le projet est développé dans une logique de qualité et de durabilité. La facilité de maintenance est privilégiée par rapport à la recherche d'une compacité maximale.

---

# 2. Objectifs

Le projet devra permettre :

* de jouer aux consoles rétro jusqu'à la Nintendo DS, PSP, Dreamcast et, lorsque cela est possible, GameCube ;
* d'utiliser Batocera comme système principal ;
* de fonctionner aussi bien en mode portable qu'en mode TV grâce à un dock dédié ;
* de proposer une autonomie d'environ 6 heures dans un usage standard.

---

# 3. Caractéristiques matérielles

## Carte principale

* Raspberry Pi 5 (4 Go)

## Affichage

* écran IPS 5 pouces
* résolution cible : 1280 × 720
* interface HDMI

## Commandes

* D-Pad
* boutons ABXY
* deux joysticks Hall Effect
* boutons Start et Select
* boutons Volume + / -
* bouton Power
* gâchettes L1 / L2
* gâchettes R1 / R2

Aucun bouton supplémentaire n'est prévu en façade.

---

# 4. Audio

La console devra intégrer :

* deux haut-parleurs stéréo ;
* une prise casque 3,5 mm ;
* un microphone intégré compatible avec les jeux Nintendo DS.

---

# 5. Connectivité

La console devra intégrer :

* Wi-Fi
* Bluetooth
* USB-C Power Delivery
* sortie vidéo HDMI via micro-HDMI
* dock externe HDMI + alimentation USB-C

---

# 6. Dock

Le dock devra permettre :

* l'alimentation de la console ;
* la recharge de la batterie ;
* la connexion à un téléviseur HDMI ;
* une indication visuelle (LED) confirmant que la console est correctement alimentée.

Aucun port USB supplémentaire n'est prévu dans la première version.

---

# 7. Batterie

Objectifs :

* autonomie cible : environ 6 heures ;
* batterie remplaçable ;
* recharge par USB-C Power Delivery ;
* possibilité de jouer pendant la recharge.

Le choix définitif de la technologie et de la capacité de la batterie sera réalisé lors de la phase de sélection des composants.

---

# 8. Refroidissement

La console intégrera un ventilateur.

Le contrôle intelligent de la vitesse du ventilateur sera prévu dans l'architecture logicielle, mais pourra être activé ou désactivé selon les besoins.

---

# 9. Boîtier

Le boîtier devra :

* être imprimable en PETG ;
* être démontable sans destruction ;
* permettre un remplacement simple de la batterie ;
* permettre un remplacement simple des joysticks ;
* permettre un remplacement simple des haut-parleurs ;
* permettre un accès rapide au Raspberry Pi.

Le boîtier devra être conçu avec une logique de maintenance.

---

# 10. Dimensions cibles

Objectifs actuels :

* largeur : 245 à 255 mm ;
* hauteur : environ 110 mm ;
* épaisseur : 25 à 30 mm (hors joysticks) ;
* poids cible : inférieur à 600 g.

Ces dimensions pourront évoluer au cours du projet.

---

# 11. Logiciel

Le système principal sera :

* Batocera.

Le projet devra permettre :

* l'utilisation de ROM légalement obtenues ;
* les sauvegardes automatiques ;
* les sauvegardes rapides (save states) ;
* la connexion Wi-Fi pour les mises à jour et le transfert des jeux.

---

# 12. Philosophie de conception

Le projet suit les principes suivants :

* privilégier la robustesse ;
* privilégier la maintenance ;
* documenter chaque décision ;
* utiliser des composants facilement disponibles ;
* limiter les soudures au strict nécessaire ;
* conserver une architecture propre et évolutive.

---

# 13. Documentation

Toutes les étapes du projet seront documentées.

Le dépôt GitHub constituera la référence officielle du projet.

Chaque évolution importante donnera lieu :

* à une mise à jour du cahier des charges ;
* à une entrée dans le journal de développement ;
* à une mise à jour de la nomenclature (BOM), si nécessaire.

---

# 14. État actuel

Version : 1.0

Statut :

* Cahier des charges initial validé.
* Sélection détaillée des composants à venir.
* Architecture matérielle à définir.
