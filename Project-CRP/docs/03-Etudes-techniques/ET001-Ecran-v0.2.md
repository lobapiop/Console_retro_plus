# Project CRP – ET001 – Fiches des modules d’affichage candidats

Version : 0.2
Statut : étude en cours

---

# 1. Objet

Cette section présente les modules d’affichage retenus pour l’étude ET001.

Les trois candidats principaux sont :

1. Raspberry Pi Touch Display 2 – 5 pouces ;
2. Waveshare 5inch 720×1280 LCD ;
3. Elecrow 5inch IPS HD Display-C 1024×600.

Chaque candidat est évalué selon :

* ses caractéristiques techniques ;
* son intégration mécanique ;
* son intégration électronique ;
* sa maintenance ;
* sa pérennité ;
* son impact global sur Project CRP.

Aucune décision définitive n’est prise dans cette version.

---

# 2. Candidat A – Raspberry Pi Touch Display 2 – 5 pouces

## 2.1 Identification

| Élément                      | Valeur                          |
| ---------------------------- | ------------------------------- |
| Fabricant                    | Raspberry Pi                    |
| Produit                      | Raspberry Pi Touch Display 2    |
| Variante étudiée             | 5 pouces Portrait               |
| Technologie                  | LCD TFT                         |
| Référence commerciale exacte | À confirmer auprès du revendeur |
| Statut                       | Candidat principal              |

Raspberry Pi commercialise officiellement le Touch Display 2 en variantes 5 et 7 pouces. La variante 5 pouces est proposée comme un module portrait destiné aux projets Raspberry Pi.

---

## 2.2 Caractéristiques techniques

| Caractéristique               | Valeur                                                |
| ----------------------------- | ----------------------------------------------------- |
| Diagonale                     | 5 pouces                                              |
| Résolution native             | 720 × 1280 pixels                                     |
| Orientation native            | Portrait                                              |
| Surface active                | 110,4 × 62,1 mm                                       |
| Profondeur de couleur         | RGB 24 bits                                           |
| Type de dalle                 | LCD TFT                                               |
| Surface                       | Antireflet                                            |
| Tactile                       | Capacitif, jusqu’à cinq points                        |
| Interface vidéo               | DSI                                                   |
| Interface tactile             | Intégrée à la liaison du module                       |
| Alimentation                  | Depuis le GPIO du Raspberry Pi                        |
| Connexions nécessaires        | DSI + alimentation GPIO                               |
| Luminosité                    | Non indiquée sur la page produit officielle consultée |
| Consommation                  | À confirmer                                           |
| Fréquence de rafraîchissement | À confirmer                                           |
| Poids                         | À confirmer                                           |
| Dimensions hors tout          | À relever dans le modèle STEP officiel                |

Le module utilise une liaison DSI pour l’image et reçoit son alimentation depuis le Raspberry Pi. Raspberry Pi indique une résolution de 720 × 1280, un tactile capacitif cinq points et une surface active de 110,4 × 62,1 mm pour la variante 5 pouces.

---

## 2.3 Intégration mécanique

### Points favorables

* La surface active correspond exactement à une dalle de 5 pouces au format proche de 16:9.
* L’absence de connecteur HDMI sur le module peut réduire le nombre de connecteurs rigides derrière l’écran.
* Raspberry Pi fournit un modèle STEP officiel de la variante 5 pouces, ce qui facilitera la modélisation précise du boîtier.
* Le module est conçu pour être fixé mécaniquement avec un Raspberry Pi.

### Points défavorables ou à vérifier

* Le module est conçu nativement en orientation portrait.
* L’encombrement total de la carte arrière doit être extrait du fichier STEP officiel.
* Il faudra vérifier si la carte électronique arrière entre en conflit avec :

  * le Raspberry Pi 5 ;
  * le ventilateur ;
  * la batterie ;
  * les cartes de commandes.
* Le positionnement du connecteur DSI impose un trajet de nappe à prévoir précisément.
* Le montage d’origine est davantage pensé pour une tablette ou un panneau que pour une console portable très compacte.

### Informations manquantes

* épaisseur maximale réelle ;
* dimensions hors tout ;
* position exacte des fixations ;
* rayon minimal recommandé pour la nappe DSI ;
* espace nécessaire derrière la carte contrôleur.

---

## 2.4 Intégration électronique

### Points favorables

* Intégration officielle avec Raspberry Pi.
* Une seule liaison DSI transporte l’affichage.
* Le tactile est géré officiellement par Raspberry Pi OS.
* Aucun contrôleur HDMI supplémentaire n’est nécessaire.
* Le port micro-HDMI restant peut être réservé à la sortie TV.

### Points défavorables ou à vérifier

* La compatibilité exacte avec Batocera sur Raspberry Pi 5 devra être validée expérimentalement.
* L’écran dépend de l’interface DSI du Raspberry Pi et est donc moins universel qu’un écran HDMI.
* Le module utilise aussi une alimentation provenant du Raspberry Pi, ce qui devra être intégré au bilan de puissance.
* Le remplacement par un écran générique serait difficile sans modifier l’architecture.

---

## 2.5 Maintenance et pérennité

### Maintenance

* Le module pourra être remplacé sans soudure si la fixation et la nappe restent accessibles.
* La nappe DSI devra être protégée contre les pincements lors de l’ouverture de la console.
* Le boîtier devra permettre de retirer l’écran sans démonter toute la partie alimentation.

### Pérennité

Raspberry Pi annonce que le Touch Display 2 restera en production au moins jusqu’en janvier 2030. Ce candidat obtient donc un très bon niveau de confiance pour la disponibilité à moyen terme.

---

## 2.6 Impact sur Project CRP

| Domaine                   | Impact estimé                                                       |
| ------------------------- | ------------------------------------------------------------------- |
| Architecture mécanique    | Moyen à important : module arrière et nappe DSI à intégrer          |
| Architecture électronique | Favorable : liaison DSI simple, sans contrôleur HDMI externe        |
| Consommation              | À mesurer avant décision                                            |
| Refroidissement           | Le module arrière peut réduire l’espace disponible derrière l’écran |
| Sortie TV                 | Favorable : les ports micro-HDMI du Pi restent disponibles          |
| Maintenance               | Bonne si le module est monté sur vis et nappe accessible            |
| Évolutivité               | Moyenne : forte dépendance à l’écosystème Raspberry Pi              |
| Pérennité                 | Très bonne                                                          |
| Documentation             | Excellente                                                          |

---

## 2.7 Avantages principaux

* produit officiel Raspberry Pi ;
* résolution élevée ;
* bonne pérennité annoncée ;
* modèle mécanique officiel disponible ;
* intégration DSI propre ;
* port HDMI du Raspberry Pi préservé pour la télévision.

---

## 2.8 Inconvénients principaux

* dépendance au DSI ;
* consommation non encore confirmée ;
* encombrement complet à mesurer dans le fichier STEP ;
* compatibilité Batocera à valider ;
* remplacement futur moins universel qu’un module HDMI.

---

## 2.9 Essais requis

* tester le démarrage et l’affichage sous Batocera ;
* vérifier la rotation en paysage ;
* mesurer la consommation à plusieurs niveaux de luminosité ;
* mesurer le temps de démarrage de l’écran ;
* vérifier le comportement lors de la sortie HDMI vers la TV ;
* contrôler l’espace occupé par la nappe et la carte arrière.

---

# 3. Candidat B – Waveshare 5inch 720×1280 LCD

## 3.1 Identification

| Élément             | Valeur                      |
| ------------------- | --------------------------- |
| Fabricant           | Waveshare                   |
| Produit             | 5inch 720x1280 LCD          |
| Référence Waveshare | Part No. 5inch 720x1280 LCD |
| SKU constructeur    | 28919                       |
| Technologie         | IPS                         |
| Statut              | Candidat principal          |

Waveshare présente ce module comme un écran tactile capacitif universel de 5 pouces, compatible avec les appareils HDMI standards et notamment le Raspberry Pi 5.

---

## 3.2 Caractéristiques techniques

| Caractéristique               | Valeur                                          |
| ----------------------------- | ----------------------------------------------- |
| Diagonale                     | 5 pouces                                        |
| Résolution native             | 720 × 1280 pixels                               |
| Orientation native            | Portrait                                        |
| Surface active                | 62,1 × 110,4 mm                                 |
| Angle de vision               | 178°                                            |
| Technologie                   | IPS                                             |
| Luminosité maximale           | 350 cd/m²                                       |
| Contraste                     | 800:1                                           |
| Gamut annoncé                 | 70 % NTSC                                       |
| Fréquence de rafraîchissement | 60 Hz                                           |
| Interface vidéo               | HDMI standard                                   |
| Interface tactile             | USB-C                                           |
| Tactile                       | Capacitif, jusqu’à cinq points                  |
| Protection                    | Verre renforcé 6H                               |
| Assemblage optique            | Optical bonding                                 |
| Alimentation                  | USB-C, 5 V                                      |
| Courant nominal annoncé       | 400 mA                                          |
| Consommation annoncée         | Environ 2 W                                     |
| Sortie audio                  | Connecteur interne 4 broches pour haut-parleurs |
| Poids                         | À confirmer                                     |
| Dimensions hors tout          | À relever sur le plan coté constructeur         |

Les valeurs de résolution, luminosité, contraste, fréquence, alimentation et consommation sont données dans le wiki officiel Waveshare.

---

## 3.3 Intégration mécanique

### Points favorables

* Le module utilise une surface active identique à celle du Touch Display 2.
* Le verre renforcé et l’assemblage optique limitent le risque de poussière entre le tactile et la dalle.
* Le module est présenté comme fin et léger.
* Le contrôleur est intégré directement au module.
* Le plan coté est fourni par Waveshare et devra être utilisé dans le futur plan d’implantation.

### Points défavorables ou à vérifier

* Les connecteurs HDMI et USB-C sont montés sur la carte arrière.
* Un connecteur HDMI standard peut être volumineux pour une console portable.
* L’utilisation d’un adaptateur ou d’une nappe micro-HDMI vers HDMI sera probablement nécessaire.
* Les câbles et leurs rayons de courbure peuvent augmenter l’épaisseur locale.
* Les dimensions hors tout doivent être reprises directement du plan mécanique officiel avant la CAO.
* Il faudra vérifier si les connecteurs peuvent être desservis par des nappes FPC ou des câbles coudés.

---

## 3.4 Intégration électronique

### Points favorables

* Interface HDMI universelle.
* Compatibilité annoncée avec Raspberry Pi 5.
* Fonctionnement sous RetroPie annoncé par Waveshare.
* Alimentation simple en 5 V.
* Consommation annoncée d’environ 2 W.
* Réglage logiciel du rétroéclairage.
* Sortie interne pour deux haut-parleurs disponible.

### Points défavorables ou à vérifier

* Deux connexions sont nécessaires :

  * HDMI pour l’image ;
  * USB pour le tactile et/ou l’alimentation.
* Le tactile n’est pas indispensable à CRP, mais son interface reste présente.
* L’un des ports micro-HDMI du Pi sera occupé par l’écran interne.
* Le deuxième port micro-HDMI resterait disponible pour la TV, sous réserve de la configuration Batocera.
* Le wiki demande une configuration HDMI personnalisée pour la résolution native ; cette configuration devra être validée avec Batocera.

---

## 3.5 Maintenance et pérennité

### Maintenance

* L’interface HDMI facilite le test du module indépendamment de la console.
* Un écran de remplacement peut être validé sur banc avant montage.
* Les câbles HDMI et USB peuvent être remplacés séparément.
* Le connecteur HDMI est cependant mécaniquement plus encombrant et peut subir des contraintes.

### Pérennité

* Waveshare est un fabricant spécialisé dans les écrans et accessoires pour cartes de développement.
* La référence exacte est documentée par un wiki constructeur.
* Aucun engagement public de durée de production comparable à celui de Raspberry Pi n’a été identifié dans les sources consultées.
* La pérennité est donc estimée bonne, mais moins garantie que celle du module officiel Raspberry Pi.

---

## 3.6 Impact sur Project CRP

| Domaine                   | Impact estimé                                                       |
| ------------------------- | ------------------------------------------------------------------- |
| Architecture mécanique    | Important : connecteurs HDMI et USB-C à loger derrière l’écran      |
| Architecture électronique | Simple et universelle, mais plus de câblage                         |
| Consommation              | Favorable : environ 2 W annoncés                                    |
| Refroidissement           | À surveiller autour de la carte contrôleur et des câbles            |
| Sortie TV                 | Utilise un port HDMI interne ; le second devra être réservé au dock |
| Maintenance               | Bonne grâce aux liaisons standard                                   |
| Évolutivité               | Bonne : HDMI universel                                              |
| Pérennité                 | Bonne, sans garantie de durée publiée                               |
| Documentation             | Très bonne                                                          |

---

## 3.7 Avantages principaux

* HDMI universel ;
* résolution 720 × 1280 ;
* consommation documentée ;
* très bons angles de vision ;
* verre renforcé et optical bonding ;
* documentation détaillée ;
* compatibilité Raspberry Pi 5 annoncée.

---

## 3.8 Inconvénients principaux

* câblage HDMI et USB plus encombrant ;
* luminosité limitée à 350 cd/m² ;
* orientation native portrait ;
* paramètres HDMI spécifiques à valider dans Batocera ;
* un port micro-HDMI du Raspberry Pi sera occupé en permanence.

---

## 3.9 Essais requis

* vérifier la configuration native sous Batocera ;
* tester la rotation paysage ;
* mesurer la latence d’affichage ;
* vérifier le basculement vers la sortie TV ;
* tester l’utilisation simultanée des deux sorties HDMI du Pi 5 ;
* mesurer la consommation réelle selon la luminosité ;
* tester des nappes ou adaptateurs HDMI à angle droit.

---

# 4. Candidat C – Elecrow 5inch IPS HD Display-C 1024×600

## 4.1 Identification

| Élément     | Valeur                 |
| ----------- | ---------------------- |
| Fabricant   | Elecrow                |
| Produit     | 5inch IPS HD Display-C |
| Modèle      | DLH04950B              |
| Résolution  | 1024 × 600             |
| Technologie | IPS                    |
| Statut      | Candidat principal     |

Elecrow présente ce module comme un écran IPS HDMI de 5 pouces avec tactile capacitif, menu OSD, réglage de luminosité et interfaces d’extension FPC.

---

## 4.2 Caractéristiques techniques

| Caractéristique               | Valeur                                 |
| ----------------------------- | -------------------------------------- |
| Diagonale                     | 5 pouces                               |
| Résolution native             | 1024 × 600 pixels                      |
| Orientation native            | Paysage                                |
| Surface active                | 108 × 64,8 mm                          |
| Dimensions hors tout          | 121,11 × 95,24 mm                      |
| Poids net                     | 112 g                                  |
| Technologie                   | IPS                                    |
| Angle de vision               | 178°                                   |
| Luminosité                    | 410 cd/m²                              |
| Fréquence de rafraîchissement | 60 Hz                                  |
| Interface vidéo principale    | HDMI                                   |
| Interface vidéo secondaire    | Extension FPC 20 broches               |
| Tactile                       | Capacitif, cinq points                 |
| Interface tactile             | USB                                    |
| Alimentation                  | USB-C, 5 V                             |
| Consommation annoncée         | 0,30 A × 5 V, soit environ 1,5 W       |
| Audio                         | Prise jack 3,5 mm                      |
| Réglages                      | Menu OSD, luminosité et contraste      |
| Extension tactile             | Connecteur 4 broches au pas de 1,25 mm |

Les dimensions, le poids, la consommation, la luminosité et les interfaces sont publiés dans le wiki officiel Elecrow.

---

## 4.3 Intégration mécanique

### Points favorables

* Orientation native paysage.
* Dimensions hors tout documentées.
* Largeur de 121,11 mm, compatible avec la zone centrale envisagée pour CRP.
* Consommation faible, réduisant les contraintes thermiques.
* Connecteur FPC permettant d’envisager un acheminement vidéo plus plat qu’un câble HDMI standard.
* Boutons OSD intégrés pouvant être laissés inaccessibles après configuration, sous réserve qu’ils ne soient pas nécessaires en fonctionnement normal.
* Prise jack déjà présente, pouvant éventuellement simplifier le prototype audio.

### Points défavorables ou à vérifier

* Hauteur totale de 95,24 mm relativement importante par rapport à la hauteur cible du boîtier, fixée autour de 110 mm.
* Il ne resterait qu’environ 14,76 mm cumulés au-dessus et au-dessous du module dans une coque de 110 mm, avant prise en compte :

  * de l’épaisseur des parois ;
  * des gâchettes ;
  * des boutons Start et Select ;
  * des tolérances ;
  * des fixations.
* Le poids de 112 g est significatif pour un seul composant.
* Les boutons OSD et la prise jack occupent de la place sur la carte.
* L’épaisseur maximale n’est pas indiquée dans le tableau de spécifications consulté.
* Le connecteur FPC vidéo nécessite une nappe et probablement une adaptation spécifique côté Raspberry Pi.

---

## 4.4 Intégration électronique

### Points favorables

* Interface HDMI universelle.
* Résolution paysage native, réduisant le besoin de rotation.
* Consommation annoncée d’environ 1,5 W.
* Alimentation et tactile regroupés sur USB-C.
* Extension HDMI sur FPC 20 broches.
* Extension tactile sur connecteur compact quatre broches.
* Menu OSD permettant le réglage matériel de l’image.
* Prise casque disponible pour le prototypage.

### Points défavorables ou à vérifier

* Une configuration personnalisée `1024 × 600 à 60 Hz` est indiquée dans la documentation Raspberry Pi du fabricant.
* Les instructions publiées semblent viser principalement Raspberry Pi OS et peuvent contenir des paramètres anciens ; leur compatibilité avec Batocera et le pilote graphique actuel du Pi 5 doit être vérifiée.
* La liaison FPC n’est pas directement compatible avec le micro-HDMI du Raspberry Pi : elle ne supprime donc pas nécessairement le besoin d’une carte ou d’un adaptateur.
* La présence d’un circuit audio intégré ne dispense pas automatiquement de notre architecture audio CRP.

---

## 4.5 Maintenance et pérennité

### Maintenance

* Les interfaces HDMI et USB rendent le module facile à tester sur banc.
* Les dimensions et le brochage FPC sont documentés.
* L’écran peut être remplacé sans soudure si les nappes utilisent des connecteurs démontables.
* La carte contrôleur intégrée signifie que la dalle et son électronique seront probablement remplacées ensemble.
* Les boutons OSD devront être protégés contre les appuis involontaires.

### Pérennité

* Le produit possède un modèle identifié : DLH04950B.
* Une documentation constructeur détaillée et des brochages sont disponibles.
* Aucune durée minimale de production n’est annoncée dans les sources officielles consultées.
* La présence d’interfaces standard HDMI et USB facilite néanmoins une future substitution par un écran équivalent.

---

## 4.6 Impact sur Project CRP

| Domaine                   | Impact estimé                                                    |
| ------------------------- | ---------------------------------------------------------------- |
| Architecture mécanique    | Potentiellement important à cause de la hauteur de 95,24 mm      |
| Architecture électronique | Favorable : HDMI, USB et extensions documentées                  |
| Consommation              | Très favorable : environ 1,5 W annoncés                          |
| Refroidissement           | Faible impact thermique attendu                                  |
| Sortie TV                 | Occupe un port HDMI interne ; second port à réserver au dock     |
| Maintenance               | Bonne, interfaces standard et brochages documentés               |
| Évolutivité               | Bonne grâce au HDMI, malgré le format mécanique propre au module |
| Pérennité                 | Bonne, mais sans engagement de durée publié                      |
| Documentation             | Très bonne                                                       |

---

## 4.7 Avantages principaux

* résolution 1024 × 600 native en paysage ;
* luminosité de 410 cd/m² ;
* faible consommation annoncée ;
* dimensions documentées ;
* interfaces d’extension FPC ;
* HDMI et USB standards ;
* menu OSD ;
* documentation détaillée.

---

## 4.8 Inconvénients principaux

* hauteur totale de 95,24 mm, potentiellement problématique dans un boîtier de 110 mm ;
* poids de 112 g ;
* épaisseur totale encore inconnue ;
* instructions logicielles à valider avec Batocera et Raspberry Pi 5 ;
* carte incluant plusieurs fonctions dont CRP n’a peut-être pas besoin.

---

## 4.9 Essais requis

* vérifier la compatibilité avec Batocera ;
* vérifier que le Pi 5 détecte correctement le mode 1024 × 600 ;
* mesurer la latence ;
* tester la lisibilité de la Nintendo DS ;
* vérifier l’encombrement des boutons OSD ;
* mesurer l’épaisseur maximale ;
* tester la sortie TV simultanée ;
* étudier la faisabilité réelle d’une liaison vidéo FPC interne.

---

# 5. Comparaison factuelle préliminaire

| Caractéristique             |     Raspberry Pi Touch Display 2 |      Waveshare 720×1280 | Elecrow 1024×600 |
| --------------------------- | -------------------------------: | ----------------------: | ---------------: |
| Diagonale                   |                               5" |                      5" |               5" |
| Technologie                 |                          LCD TFT |                     IPS |              IPS |
| Résolution                  |                         720×1280 |                720×1280 |         1024×600 |
| Orientation native          |                         Portrait |                Portrait |          Paysage |
| Surface active              |                    110,4×62,1 mm |           110,4×62,1 mm |      108×64,8 mm |
| Dimensions hors tout        |               À extraire du STEP | À extraire du plan coté |  121,11×95,24 mm |
| Luminosité                  |                      À confirmer |               350 cd/m² |        410 cd/m² |
| Rafraîchissement            |                      À confirmer |                   60 Hz |            60 Hz |
| Interface vidéo             |                              DSI |                    HDMI |         HDMI/FPC |
| Alimentation                |                             GPIO |               USB-C 5 V |        USB-C 5 V |
| Consommation                |                      À confirmer |             Environ 2 W |    Environ 1,5 W |
| Tactile                     |                         5 points |                5 points |         5 points |
| Poids                       |                      À confirmer |             À confirmer |            112 g |
| Engagement de disponibilité | Jusqu’en janvier 2030 au minimum |              Non publié |       Non publié |

---

# 6. Observations préliminaires

## Raspberry Pi Touch Display 2

Candidat présentant la meilleure intégration officielle et la meilleure garantie de disponibilité. Son encombrement mécanique et sa consommation restent à préciser.

## Waveshare 5inch 720×1280 LCD

Candidat présentant la meilleure combinaison entre résolution élevée, HDMI universel et documentation technique. Son câblage HDMI/USB pourrait toutefois compliquer l’épaisseur du boîtier.

## Elecrow 5inch IPS HD Display-C

Candidat présentant une consommation faible, une orientation native paysage et des interfaces intéressantes. Sa hauteur totale de 95,24 mm est cependant un risque mécanique majeur pour la console.

---

# 7. Données à obtenir avant notation

Avant de remplir la matrice de décision, il reste à obtenir ou confirmer :

* les dimensions hors tout du Raspberry Pi Touch Display 2 ;
* l’épaisseur et le poids du Raspberry Pi Touch Display 2 ;
* sa consommation selon plusieurs niveaux de luminosité ;
* les dimensions hors tout, l’épaisseur et le poids du Waveshare ;
* l’épaisseur totale de l’Elecrow ;
* la compatibilité réelle de chaque candidat avec Batocera ;
* le comportement avec une sortie TV simultanée ;
* la disponibilité auprès de plusieurs revendeurs européens ;
* les conditions de remplacement à moyen terme.

---
# Matrice de décision provisoire

Les notes suivantes sont provisoires. Elles reposent sur les données constructeur actuellement disponibles et devront être confirmées par des essais matériels.

| Critère                      | Pondération | Raspberry Pi Touch Display 2 | Waveshare 5inch 720×1280 | Elecrow 5inch 1024×600 |
| ---------------------------- | ----------: | ---------------------------: | -----------------------: | ---------------------: |
| Compatibilité Raspberry Pi   |        20 % |                          8,5 |                        8 |                      8 |
| Intégration mécanique        |        20 % |                          5,5 |                        7 |                      8 |
| Intégration électronique     |        15 % |                            9 |                        7 |                    8,5 |
| Qualité d’affichage          |        20 % |                            8 |                      8,5 |                      8 |
| Maintenance                  |        10 % |                            8 |                        8 |                      8 |
| Pérennité                    |        10 % |                           10 |                        7 |                      7 |
| Documentation                |         5 % |                           10 |                        9 |                      9 |
| **Score pondéré provisoire** |   **100 %** |                   **8,0/10** |               **7,7/10** |             **8,0/10** |

## Analyse

Le Raspberry Pi Touch Display 2 et l’Elecrow obtiennent des scores presque identiques, mais pour des raisons différentes.

Le Raspberry Pi Touch Display 2 est avantagé par :

* sa compatibilité officielle ;
* son excellente documentation ;
* son engagement de disponibilité jusqu’en janvier 2030 ;
* son câblage DSI relativement simple.

Il est pénalisé par :

* ses dimensions hors tout ;
* sa profondeur ;
* sa forte dépendance à l’écosystème Raspberry Pi ;
* la compatibilité Batocera qui reste à valider.

L’Elecrow est avantagé par :

* son orientation native paysage ;
* ses dimensions plus favorables en largeur ;
* sa faible consommation annoncée ;
* son interface HDMI universelle ;
* ses extensions FPC documentées ;
* sa luminosité annoncée de 410 cd/m².

Il est pénalisé par :

* sa hauteur de 95,24 mm ;
* son épaisseur encore inconnue ;
* l’absence d’engagement officiel de disponibilité à long terme ;
* la nécessité de valider sa configuration sous Batocera.

Le Waveshare reste un excellent candidat, notamment grâce à sa résolution, mais son utilisation combinée de HDMI et USB et sa luminosité plus faible le placent légèrement derrière les deux autres.

## Conclusion provisoire

L’Elecrow 5inch IPS HD Display-C est actuellement le candidat présentant le meilleur compromis pratique pour Project CRP.

Il ne pourra cependant être retenu définitivement qu’après validation de :

* son épaisseur totale ;
* son intégration dans le volume mécanique cible ;
* sa compatibilité avec Batocera ;
* son fonctionnement avec la sortie HDMI TV ;
* sa disponibilité auprès de plusieurs revendeurs.

## Mise à jour — Plan mécanique constructeur

Un plan coté daté du 4 janvier 2025 confirme les dimensions suivantes pour le module Elecrow :

- largeur hors tout : 121,11 ± 0,2 mm ;
- hauteur hors tout : 77,93 ± 0,2 mm ;
- zone active : 108 × 64,8 mm ;
- profondeur maximale : 13,94 ± 0,2 mm ;
- épaisseur de la partie principale dalle et PCB : 7,66 ± 0,2 mm.

Pour la conception mécanique de Project CRP, une profondeur réservée de 15 à 16 mm sera utilisée afin d’intégrer les tolérances, les fixations et une marge de sécurité.

La hauteur réelle de 77,93 mm est nettement plus favorable que la valeur de 95,24 mm précédemment relevée. Elle laisse environ 32 mm disponibles sur une hauteur cible de boîtier de 110 mm, avant déduction des parois et tolérances.

La note provisoire d’intégration mécanique de l’Elecrow est portée à 9/10.


# 8. Statut

Les trois candidats restent dans la sélection.

Aucune note ni décision définitive n’est attribuée tant que les informations structurantes et les essais logiciels ne sont pas disponibles.
