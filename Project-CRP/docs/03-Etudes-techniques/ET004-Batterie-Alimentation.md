# Project CRP – Étude technique 001 – Alimentation

Version : 0.1

---

# 1. Objectif

Cette étude définit l’architecture d’alimentation de Project CRP.

Elle doit permettre :

* une autonomie cible d’environ 6 heures ;
* l’utilisation pendant la recharge ;
* le branchement/débranchement du chargeur sans extinction ;
* une recharge USB-C Power Delivery ;
* une batterie remplaçable ;
* une alimentation stable pour le Raspberry Pi 5.

---

# 2. Contraintes du Raspberry Pi 5

Le Raspberry Pi 5 doit être alimenté en 5 V avec une capacité recommandée de 5 A pour fonctionner confortablement, notamment avec des périphériques. L’alimentation officielle Raspberry Pi 27 W fournit 5,1 V / 5 A et propose aussi des profils USB-C PD 9 V, 12 V et 15 V.

Pour Project CRP, on retiendra donc comme contrainte de conception :

```text
Sortie système cible : 5 V / 5 A minimum
Puissance disponible cible : 25 W minimum
```

---

# 3. Estimation de consommation

Consommation estimée :

| Élément               | Estimation |
| --------------------- | ---------: |
| Raspberry Pi 5        |    4 à 9 W |
| Écran 5" HDMI         |    2 à 4 W |
| Audio                 |  0,5 à 2 W |
| Ventilateur           |  0,5 à 1 W |
| RP2040 + LED + divers |    < 0,5 W |

Consommation moyenne cible :

```text
8 à 11 W
```

Pour 6 heures d’autonomie :

```text
10 W × 6 h = 60 Wh
```

La batterie devra donc viser environ :

```text
55 à 65 Wh utiles
```

---

# 4. Capacité batterie cible

Une batterie Li-ion/LiPo est généralement annoncée à sa tension nominale, autour de 3,7 V.

Pour obtenir environ 60 Wh :

```text
60 Wh / 3,7 V ≈ 16 200 mAh
```

Capacité recommandée :

```text
15 000 à 18 000 mAh
```

Une batterie de 10 000 mAh risque de donner plutôt 3 à 4,5 heures selon l’usage.

---

# 5. Architecture recommandée

Architecture retenue pour l’étude :

```text
Chargeur USB-C PD
        ↓
Module Power Path / Charge
        ↓
Batterie LiPo
        ↓
Convertisseur 5 V / 5 A
        ↓
Raspberry Pi 5 + écran + audio + ventilateur
```

Le point important est le **Power Path**.

Il permet :

* d’alimenter la console pendant la recharge ;
* de recharger la batterie en même temps ;
* de passer du chargeur à la batterie sans coupure.

---

# 6. USB-C Power Delivery

Le chargeur externe recommandé sera :

```text
USB-C PD 45 W minimum
```

Pourquoi 45 W ?

* marge confortable ;
* recharge pendant le jeu ;
* moins de chauffe côté chargeur ;
* compatibilité facile avec les chargeurs modernes.

Le Pi 5 lui-même utilise une alimentation officielle 27 W, mais CRP doit aussi recharger une batterie en parallèle.

---

# 7. Temps de recharge estimé

Pour une batterie d’environ 60 Wh :

| Puissance réelle de charge batterie | Temps estimé |
| ----------------------------------- | -----------: |
| 15 W                                |      4 à 5 h |
| 25 W                                |  2,5 à 3,5 h |
| 35 W                                |    2 à 2,5 h |
| 45 W                                |  1,5 à 2,5 h |

Estimation réaliste pour CRP :

```text
Recharge complète : environ 2,5 à 3,5 heures
```

Pourquoi pas 1 h 30 systématiquement ?

Parce que la charge Li-ion ralentit fortement en fin de charge pour préserver la batterie.

---

# 8. Solutions possibles

## Option A – Module UPS/HAT du commerce

Exemples à étudier :

* DFRobot UPS HAT Raspberry Pi 5
* Waveshare / Geekworm UPS pour Raspberry Pi 5
* SunFounder PiPower 5

Certains modules existants annoncent une sortie 5 V / 5 A et une gestion UPS/Power Path, ce qui correspond bien au besoin du Pi 5.

Avantages :

* plus simple pour débuter ;
* moins risqué ;
* permet de prototyper rapidement.

Inconvénients :

* format parfois peu adapté au boîtier ;
* batteries souvent imposées ;
* intégration mécanique moins propre.

---

## Option B – Carte alimentation CRP personnalisée

Avantages :

* intégration propre ;
* meilleure gestion du boîtier ;
* batterie choisie librement ;
* solution plus professionnelle.

Inconvénients :

* plus complexe ;
* nécessite conception électronique ;
* plus risqué pour un premier prototype.

---

# 9. Décision provisoire

Pour Project CRP, la stratégie recommandée est :

## Prototype V0

Utiliser un module UPS/Power Path du commerce capable de fournir :

```text
5 V / 5 A minimum
```

Objectif : valider l’autonomie, la recharge et le comportement sans coupure.

## Version V1/V2

Concevoir une carte alimentation CRP personnalisée si le prototype valide les besoins.

---

# 10. Points à décider

À décider dans la prochaine itération :

* batterie LiPo plate ou pack 18650/21700 ;
* capacité exacte ;
* module UPS de prototypage ;
* connecteur batterie ;
* emplacement mécanique de la batterie ;
* système de mesure du niveau batterie ;
* communication avec le RP2040.

---

# 11. Décision actuelle

Décisions retenues :

* autonomie cible : 6 heures ;
* puissance système : 5 V / 5 A minimum ;
* recharge USB-C PD ;
* chargeur recommandé : 45 W minimum ;
* Power Path obligatoire ;
* batterie remplaçable ;
* prototype basé sur un module du commerce ;
* carte alimentation CRP personnalisée envisagée après validation.

---

# 12. Statut

Statut : étude ouverte.

Prochaine étape : comparer les solutions batterie et modules UPS compatibles Raspberry Pi 5.
# 13. Solutions UPS candidates

## Option A – DFRobot FIT0992

Référence : **DFRobot FIT0992 – Raspberry Pi 5 18650 Battery UPS HAT**

Caractéristiques principales :

* sortie 5 V jusqu'à 5 A ;
* batterie 18650 ;
* gestion UPS ;
* communication I2C ;
* jauge batterie ;
* charge rapide jusqu'à environ 3 A ;
* module conçu pour Raspberry Pi 5.

Cette solution est intéressante pour le prototype V0, car elle couvre déjà plusieurs besoins critiques : alimentation stable, bascule UPS, mesure batterie et gestion logicielle.

## Option B – Geekworm X1200 / X1202

Références candidates :

* **Geekworm X1200** : 2 cellules 18650, sortie 5,1 V / 5 A ;
* **Geekworm X1202** : 4 cellules 18650, sortie 5,1 V / 5 A ;
* **Geekworm X1206** : 4 cellules 21700, sortie 5,1 V / 6 A.

Ces cartes sont intéressantes car Geekworm propose plusieurs formats selon l'encombrement disponible et la capacité souhaitée.

---

# 14. Analyse pour Project CRP

Pour CRP, la priorité est :

1. alimentation stable du Raspberry Pi 5 ;
2. autonomie proche de 6 heures ;
3. recharge pendant le jeu ;
4. intégration mécanique propre ;
5. maintenance simple.

Les modules à 2 cellules 18650 risquent d'être trop limités pour atteindre 6 heures.

Les modules à 4 cellules sont plus intéressants pour l'autonomie, mais ils peuvent être plus encombrants.

La solution 21700 pourrait offrir une meilleure capacité, mais elle risque d'augmenter l'épaisseur de la console.

---

# 15. Choix provisoire

Pour le prototype V0, les candidats prioritaires sont :

1. **DFRobot FIT0992**
2. **Geekworm X1202**
3. **Geekworm X1206**

Le choix définitif dépendra de :

* dimensions exactes ;
* orientation des batteries ;
* compatibilité mécanique avec notre boîtier ;
* disponibilité en Europe ;
* facilité d'intégration avec le RP2040.

---

# 16. Décision actuelle

Décision provisoire :

* ne pas concevoir immédiatement une carte alimentation personnalisée ;
* tester d'abord un module UPS du commerce ;
* privilégier une solution 4 cellules ;
* vérifier si une solution 21700 reste compatible avec l'épaisseur cible.

Statut : étude ouverte.
