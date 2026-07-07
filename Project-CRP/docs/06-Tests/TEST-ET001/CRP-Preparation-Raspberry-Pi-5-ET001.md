# Project CRP – Préparation du Raspberry Pi 5 pour les tests ET001

Version : 0.1  
Statut : à exécuter  
Étude associée : ET001 – Module d’affichage  
Plateforme : Raspberry Pi 5 – 4 Go  
Système : Batocera  
Écran candidat : Elecrow 5 pouces IPS 1024×600  

---

# 1. Objet

Ce document décrit la préparation du Raspberry Pi 5 avant les tests du module d’affichage Elecrow.

L’objectif est d’obtenir une plateforme de référence :

- correctement assemblée ;
- correctement alimentée ;
- équipée d’une carte microSD Batocera fonctionnelle ;
- testée d’abord sur un téléviseur ou un moniteur HDMI connu ;
- configurée avec une manette PS4 ou PS5 en USB ;
- accessible par le réseau pour faciliter le diagnostic ;
- laissée aussi proche que possible de la configuration Batocera d’origine.

La résolution 1024×600 de l’écran Elecrow ne doit pas être forcée avant le premier essai. La détection automatique fait partie du protocole ET001.

---

# 2. Principe de préparation

La préparation est séparée en deux étapes.

## Étape 1 — Validation du Raspberry Pi seul

Le Raspberry Pi doit d’abord être validé avec un téléviseur ou un moniteur HDMI dont le fonctionnement est déjà connu.

Cette étape permet de confirmer :

- que la carte microSD démarre ;
- que Batocera fonctionne ;
- que l’alimentation est correcte ;
- que le refroidisseur fonctionne ;
- que la manette est reconnue ;
- que le réseau et l’accès distant fonctionnent.

## Étape 2 — Test de l’écran Elecrow

Une fois la plateforme de référence validée, le téléviseur est remplacé par l’écran Elecrow.

Ainsi, une éventuelle absence d’image pourra être attribuée à la chaîne d’affichage Elecrow et non à une installation Batocera défectueuse.

---

# 3. Matériel nécessaire

| Élément | Requis | Remarque |
|---|---|---|
| Raspberry Pi 5 – 4 Go | Oui | Plateforme cible de CRP |
| Refroidisseur actif | Oui | À installer avant le premier démarrage |
| Alimentation USB-C adaptée au Pi 5 | Oui | Alimentation officielle 27 W recommandée |
| Carte microSD de 64 Go ou plus | Oui | Son contenu sera effacé |
| Ordinateur avec accès Internet | Oui | Pour télécharger et flasher Batocera |
| Lecteur de carte microSD | Oui | Interne ou USB |
| Téléviseur ou moniteur HDMI connu | Oui | Pour valider le Pi avant l’Elecrow |
| Câble micro-HDMI vers HDMI | Oui | Brancher avant la mise sous tension |
| Manette PS4 ou PS5 | Oui | Utilisation en USB pour la préparation |
| Câble USB de la manette | Oui | Données et alimentation |
| Câble Ethernet | Facultatif | Plus simple que le Wi-Fi pour le diagnostic |
| Clavier USB | Facultatif | Utile uniquement en cas de diagnostic |

---

# 4. Précautions

1. Travailler sur une surface propre et non conductrice.
2. Ne jamais poser le Raspberry Pi allumé sur du métal.
3. Installer le refroidisseur actif avant les essais prolongés.
4. Effectuer les branchements HDMI hors tension.
5. Ne jamais retirer la carte microSD lorsque le système est alimenté.
6. Utiliser l’arrêt logiciel de Batocera avant de couper l’alimentation.
7. Ne pas modifier plusieurs paramètres à la fois.
8. Noter chaque modification dans le journal de test.
9. Ne pas connecter la machine à un réseau public.
10. Conserver une copie des fichiers modifiés avant toute expérimentation.

---

# 5. Assemblage matériel du Raspberry Pi

## 5.1 Inspection

Avant l’assemblage, vérifier :

- l’absence de dommage visible sur le Raspberry Pi ;
- l’état du logement microSD ;
- l’état des deux ports micro-HDMI ;
- l’état du connecteur USB-C ;
- l’absence d’élément libre dans l’emballage.

## 5.2 Installation du refroidisseur

Installer le refroidisseur conformément à sa notice.

Vérifier :

- que les protections éventuelles des surfaces thermiques sont retirées ;
- que les fixations sont correctement engagées ;
- que le câble du ventilateur est branché sur le connecteur prévu ;
- que le ventilateur peut tourner librement ;
- qu’aucun câble ne touche ses pales.

## 5.3 Branchements pour la première validation

Le branchement initial doit être :

```text
Téléviseur ou moniteur connu
          ▲
          │ HDMI
          │
   câble micro-HDMI
          │
          ▼
    Raspberry Pi 5
       │       │
       │       └──► Manette PS4/PS5 en USB
       │
       └──────────► Alimentation USB-C
```

Pour le premier démarrage, ne pas encore connecter l’écran Elecrow.

---

# 6. Téléchargement de Batocera

## 6.1 Image à sélectionner

Télécharger l’image officielle destinée au :

**Raspberry Pi 5 / architecture bcm2712**

Ne pas utiliser une image destinée au Raspberry Pi 4 ou à un ordinateur x86-64.

La page officielle des versions Batocera fournit un chemin distinct pour le Raspberry Pi 5 sous l’identifiant `bcm2712`.

## 6.2 Version à retenir

Utiliser la version stable proposée au moment du téléchargement.

Noter immédiatement :

| Information | Valeur |
|---|---|
| Date du téléchargement |  |
| Version Batocera |  |
| Architecture | bcm2712 |
| Nom exact du fichier |  |
| Taille du fichier |  |
| Somme de contrôle publiée |  |
| Somme de contrôle vérifiée |  |

## 6.3 Remarque sur le statut du Raspberry Pi 5

La documentation officielle Batocera n’est pas parfaitement homogène : la page de choix d’un ordinateur monocarte peut encore qualifier la prise en charge du Raspberry Pi 5 de « beta », tandis que la page des versions publie un répertoire stable spécifique à `bcm2712`.

Pour Project CRP, la règle est donc :

- utiliser l’image stable officiellement publiée pour `bcm2712` ;
- noter précisément sa version ;
- ne pas supposer que tous les comportements sont définitifs ;
- documenter tout problème reproductible.

---

# 7. Écriture de l’image sur la carte microSD

## 7.1 Outil recommandé

La documentation Batocera recommande un outil d’écriture d’image tel que :

- Raspberry Pi Imager ;
- USBImager ;
- ou un outil équivalent capable d’écrire une image disque compressée.

## 7.2 Procédure

1. Insérer la carte microSD dans l’ordinateur.
2. Vérifier deux fois que la bonne carte est sélectionnée.
3. Sélectionner l’image Batocera pour Raspberry Pi 5.
4. Lancer l’écriture.
5. Attendre la fin complète de l’opération.
6. Utiliser la fonction de vérification si elle est proposée.
7. Éjecter proprement la carte.
8. Insérer la carte dans le Raspberry Pi hors tension.

## 7.3 Avertissement

L’écriture de l’image efface entièrement la carte microSD sélectionnée.

Ne pas sélectionner un disque contenant des données importantes.

---

# 8. Premier démarrage sur un écran connu

## 8.1 Avant la mise sous tension

Vérifier :

- carte microSD insérée ;
- câble micro-HDMI connecté au Raspberry Pi ;
- câble HDMI connecté au téléviseur ;
- bonne entrée HDMI sélectionnée sur le téléviseur ;
- manette USB connectée avec les sticks et gâchettes au repos ;
- refroidisseur branché ;
- alimentation encore déconnectée.

## 8.2 Démarrage

1. Brancher l’alimentation du Raspberry Pi.
2. Ne toucher à aucun bouton de la manette pendant sa détection.
3. Attendre plusieurs minutes lors du premier démarrage.
4. Ne pas couper l’alimentation pendant l’initialisation.
5. Vérifier l’apparition de l’interface EmulationStation.

## 8.3 Relevé du premier démarrage

| Contrôle | Résultat |
|---|---|
| Écran de démarrage visible |  |
| Interface Batocera affichée |  |
| Image stable |  |
| Ventilateur fonctionnel |  |
| Aucune alerte d’alimentation visible |  |
| Manette détectée |  |
| Temps approximatif du premier démarrage |  |

---

# 9. Configuration initiale minimale

Pour conserver une base de référence propre, ne modifier que les éléments nécessaires.

## 9.1 Langue et fuseau horaire

Dans les paramètres système :

- sélectionner la langue souhaitée ;
- sélectionner le fuseau horaire local ;
- redémarrer uniquement si Batocera le demande.

Noter les menus utilisés, car leur intitulé peut varier selon la version.

## 9.2 Nom de la machine

Conserver de préférence le nom par défaut `BATOCERA` pendant ET001.

Cela simplifie :

- l’accès réseau ;
- la comparaison avec la documentation ;
- le dépannage.

Un nom spécifique à CRP pourra être défini après la validation de l’écran.

## 9.3 Son

Pour la préparation sur téléviseur :

- sélectionner la sortie HDMI du téléviseur si nécessaire ;
- régler un volume modéré ;
- vérifier qu’un son système ou un jeu de test est audible.

Le son n’est pas un critère principal d’ET001, mais il peut confirmer que le système a correctement démarré.

---

# 10. Configuration de la manette PS4 ou PS5

## 10.1 Connexion recommandée

Pour les premiers essais :

- connecter la manette par câble USB ;
- ne pas utiliser le Bluetooth ;
- laisser les sticks, gâchettes et boutons au repos pendant la détection.

Batocera prend en charge les grandes familles de manettes et utilise une base interne pour reconnaître les modèles courants. Une configuration manuelle peut toutefois être demandée.

## 10.2 Mappage

Si Batocera demande un mappage :

1. suivre les indications à l’écran ;
2. associer les boutons selon leur position physique ;
3. affecter une touche `HOTKEY` ;
4. utiliser de préférence le bouton PlayStation comme `HOTKEY`, s’il est reconnu ;
5. maintenir un bouton déjà configuré pour ignorer une entrée absente, si l’interface le permet.

## 10.3 Vérification

Tester :

- croix directionnelle ;
- quatre boutons principaux ;
- Start ;
- Select ou équivalent ;
- sticks ;
- L1, R1, L2, R2 ;
- retour au menu avec la combinaison de sortie.

| Élément | Résultat |
|---|---|
| Modèle de manette | PS4 / PS5 |
| Connexion USB détectée |  |
| Mappage automatique |  |
| Mappage manuel nécessaire |  |
| Hotkey attribuée à |  |
| Navigation correcte |  |

---

# 11. Configuration du réseau

Le réseau est utile pour :

- relever l’adresse IP ;
- accéder aux fichiers de configuration ;
- établir une connexion SSH ;
- vérifier que Batocera fonctionne même si l’affichage devient indisponible.

## 11.1 Méthode recommandée

Pour la préparation, préférer dans l’ordre :

1. Ethernet ;
2. Wi-Fi du réseau domestique de confiance.

Ethernet se configure normalement automatiquement.

## 11.2 Wi-Fi

Dans Batocera :

1. ouvrir le menu principal ;
2. ouvrir les paramètres réseau ;
3. activer le Wi-Fi ;
4. attendre l’apparition des réseaux ;
5. sélectionner le réseau domestique ;
6. saisir le mot de passe ;
7. attendre l’apparition de l’adresse IP.

Un redémarrage peut être nécessaire après la première activation.

## 11.3 Relevé réseau

| Information | Valeur |
|---|---|
| Méthode | Ethernet / Wi-Fi |
| Nom de la machine | BATOCERA |
| Adresse IP |  |
| Accès au partage réseau | Réussi / Échec |
| Accès SSH | Réussi / Échec |

Ne jamais inscrire le mot de passe Wi-Fi dans le dépôt GitHub.

---

# 12. Préparation de l’accès SSH

Batocera recommande SSH pour accéder au terminal depuis un autre ordinateur. SSH est normalement activé par défaut.

## 12.1 Vérification simple

Depuis un ordinateur connecté au même réseau, tenter une connexion à la machine Batocera en utilisant son nom ou son adresse IP.

Exemple générique :

```bash
ssh root@BATOCERA
```

ou :

```bash
ssh root@ADRESSE_IP
```

Ne pas publier de mot de passe dans GitHub.

## 12.2 Configuration concernée

La propriété suivante doit être active dans :

`/userdata/system/batocera.conf`

```ini
system.ssh.enabled=1
```

Ne modifier ce fichier que si l’accès SSH ne fonctionne pas et après en avoir conservé une copie.

## 12.3 Utilité pendant ET001

Si l’Elecrow reste noir mais que :

- la machine répond au réseau ;
- SSH fonctionne ;
- les sons de Batocera sont audibles ;

alors le problème est probablement lié à l’affichage et non au démarrage complet du Raspberry Pi.

---

# 13. Création d’un état de référence

Avant de brancher l’Elecrow, relever l’état de la plateforme.

## 13.1 Informations à noter

| Information | Valeur |
|---|---|
| Version de Batocera |  |
| Architecture | bcm2712 |
| Date de l’installation |  |
| Téléviseur de référence |  |
| Port micro-HDMI utilisé | HDMI 0 / HDMI 1 |
| Résolution du téléviseur |  |
| Manette utilisée |  |
| Réseau fonctionnel | Oui / Non |
| SSH fonctionnel | Oui / Non |
| Nombre de redémarrages réussis |  |

## 13.2 Redémarrages de validation

Effectuer trois cycles :

1. arrêt propre ;
2. attente de 15 secondes ;
3. redémarrage ;
4. vérification de l’image ;
5. vérification de la manette ;
6. vérification du réseau.

| Cycle | Démarrage | Image | Manette | Réseau |
|---:|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |

La plateforme est prête pour ET001 si les trois cycles sont réussis.

---

# 14. Sauvegarde de la configuration initiale

Avant toute modification liée à l’Elecrow, sauvegarder au minimum :

- `/userdata/system/batocera.conf` ;
- les éventuels fichiers de configuration de démarrage accessibles sur la partition système ;
- la version exacte de Batocera ;
- les captures ou photos des réglages importants.

Dossier proposé dans le dépôt :

```text
software/Batocera/reference-ET001/
```

Ne pas déposer dans GitHub :

- les ROMs ;
- les BIOS protégés ;
- les mots de passe ;
- les clés Wi-Fi ;
- les clés privées SSH ;
- des fichiers contenant des informations personnelles.

---

# 15. Préparation des contenus de test

Pour tester l’écran, préparer uniquement des contenus dont l’utilisation est légale.

## 15.1 Mire de géométrie

Prévoir une image contenant :

- une bordure sur les quatre côtés ;
- une grille régulière ;
- un cercle ;
- un carré ;
- du texte fin ;
- des aplats rouge, vert, bleu, noir et blanc.

## 15.2 Jeux de test

Préparer quelques jeux légalement disponibles ou des logiciels libres permettant de tester :

- défilement horizontal ;
- défilement vertical ;
- mouvements rapides ;
- texte de petite taille ;
- format 4:3 ;
- format large ;
- Nintendo DS et tactile, lorsque les fichiers nécessaires sont légalement disponibles.

## 15.3 Organisation

Créer un tableau dans le cahier ET001 indiquant :

| Usage | Système | Contenu utilisé | Provenance légale |
|---|---|---|---|
| Défilement horizontal |  |  |  |
| Défilement vertical |  |  |  |
| 3D |  |  |  |
| Nintendo DS |  |  |  |
| Mire d’affichage | Image |  | Créée pour CRP |

---

# 16. Passage du téléviseur à l’écran Elecrow

## 16.1 Règle principale

Le premier test de l’Elecrow doit être effectué sans forcer la résolution.

La détection automatique fait partie de `TEST-C01`.

## 16.2 Procédure

1. Arrêter proprement Batocera.
2. Attendre l’extinction complète de l’activité.
3. Débrancher l’alimentation du Raspberry Pi.
4. Déconnecter le câble HDMI du téléviseur.
5. Connecter le même câble à l’Elecrow.
6. Alimenter l’Elecrow séparément en 5 V.
7. Sélectionner l’entrée HDMI correcte sur l’Elecrow si nécessaire.
8. Alimenter le Raspberry Pi.
9. Exécuter `TEST-B02`.
10. Enchaîner avec `TEST-C01`.

## 16.3 Ne pas faire au premier essai

Ne pas :

- modifier immédiatement `config.txt` ;
- forcer 1024×600 avant d’observer le comportement ;
- changer simultanément de câble, de port HDMI et de configuration ;
- alimenter l’écran depuis le Raspberry Pi lors du tout premier test ;
- connecter en même temps le téléviseur et l’Elecrow.

---

# 17. En cas d’absence d’image

Suivre cet ordre sans improviser.

## Étape 1 — Vérifications simples

- écran alimenté ;
- bonne entrée HDMI ;
- câble entièrement inséré ;
- câble utilisé avec succès sur le téléviseur ;
- Raspberry Pi réellement démarré ;
- aucune alerte visible sur le Pi.

## Étape 2 — Vérification réseau

Rechercher :

- la machine `BATOCERA` sur le réseau ;
- son partage de fichiers ;
- sa réponse SSH ;
- les sons éventuels de l’interface.

## Étape 3 — Test croisé

1. Éteindre complètement le système.
2. Rebrancher le téléviseur de référence.
3. Redémarrer sans autre modification.

Si le téléviseur fonctionne encore, la plateforme Batocera reste valide et le diagnostic peut se concentrer sur l’Elecrow, le câble, le port utilisé ou le mode vidéo.

## Étape 4 — Changement unique

Tester une seule modification à la fois :

1. autre entrée de l’écran ;
2. autre câble ;
3. autre port micro-HDMI du Raspberry Pi ;
4. redémarrage complet ;
5. seulement ensuite, étude d’une configuration vidéo manuelle.

Chaque tentative doit être inscrite dans la fiche de test.

---

# 18. Configuration vidéo manuelle : règle de projet

Une configuration vidéo manuelle ne doit être appliquée que si :

- le Raspberry Pi fonctionne sur l’écran de référence ;
- l’Elecrow est correctement alimenté ;
- le câble est validé ;
- la détection automatique a échoué ;
- les résultats sont consignés dans `TEST-C01`.

La documentation Batocera décrit des options historiques de résolution personnalisée dans `config.txt`, mais leur pertinence exacte dépend de la version de Batocera, du Raspberry Pi et de la pile d’affichage utilisée.

Pour cette raison :

1. conserver une copie du fichier avant modification ;
2. vérifier le chemin réellement utilisé par l’image Batocera installée ;
3. ajouter une seule modification à la fois ;
4. noter la ligne ajoutée ;
5. redémarrer ;
6. revenir immédiatement à la sauvegarde en cas d’échec.

Aucune ligne de configuration personnalisée n’est imposée dans ce document avant l’observation du matériel réel.

---

# 19. Critères « Raspberry Pi prêt pour ET001 »

Le Raspberry Pi est considéré comme prêt lorsque :

- [ ] le refroidisseur est installé et fonctionne ;
- [ ] l’alimentation est stable ;
- [ ] Batocera `bcm2712` démarre sur le téléviseur de référence ;
- [ ] la version de Batocera est notée ;
- [ ] la manette PS4 ou PS5 fonctionne en USB ;
- [ ] un arrêt logiciel est maîtrisé ;
- [ ] trois redémarrages de référence sont réussis ;
- [ ] le réseau local fonctionne ;
- [ ] l’adresse IP est connue ;
- [ ] SSH ou un autre moyen de diagnostic est disponible ;
- [ ] les fichiers de configuration initiaux sont sauvegardés ;
- [ ] aucune résolution Elecrow n’a encore été forcée ;
- [ ] les contenus de test sont préparés légalement.

---

# 20. Fiche de résultat

| Élément | Résultat |
|---|---|
| Raspberry Pi inspecté |  |
| Refroidisseur installé |  |
| Carte microSD flashée |  |
| Image Batocera correcte |  |
| Architecture bcm2712 |  |
| Premier démarrage réussi |  |
| Téléviseur de référence validé |  |
| Manette USB validée |  |
| Réseau validé |  |
| SSH validé |  |
| Trois redémarrages réussis |  |
| Sauvegarde réalisée |  |
| Plateforme prête pour ET001 | Oui / Non |

Remarques :

---

# 21. Décision

- [ ] Plateforme Raspberry Pi prête pour les tests d’écran
- [ ] Plateforme prête sous réserve
- [ ] Préparation incomplète
- [ ] Défaut matériel ou logiciel à diagnostiquer

Réserves :

Actions nécessaires :

1. 
2. 
3. 

---

# 22. Sources officielles

- [Batocera – Page de téléchargement](https://batocera.org/download)
- [Batocera – Versions actuelles, précédentes et bêta](https://wiki.batocera.org/current_and_previous_releases)
- [Batocera – Guide d’installation](https://wiki.batocera.org/install_batocera)
- [Batocera – Choisir un ordinateur monocarte](https://wiki.batocera.org/choose_a_single_board_computer)
- [Batocera – Configurer une manette](https://wiki.batocera.org/configure_a_controller)
- [Batocera – Manettes prises en charge](https://wiki.batocera.org/supported_controllers)
- [Batocera – Configuration Wi-Fi](https://wiki.batocera.org/wifi_ssid)
- [Batocera – Accès SSH et commandes courantes](https://wiki.batocera.org/access_the_batocera_via_ssh)
- [Batocera – Problèmes d’affichage](https://wiki.batocera.org/display_issues)
- [Batocera – Ajouter un écran TFT sur Raspberry Pi](https://wiki.batocera.org/add_tft_screen_rpi_only)
- [Raspberry Pi – Documentation matérielle](https://www.raspberrypi.com/documentation/computers/raspberry-pi.html)
- [Raspberry Pi – Configuration config.txt](https://www.raspberrypi.com/documentation/computers/config_txt.html)

---

# 23. Historique

| Version | Date | Modification |
|---|---|---|
| 0.1 | 7 juillet 2026 | Création de la procédure de préparation du Raspberry Pi 5 pour ET001 |
