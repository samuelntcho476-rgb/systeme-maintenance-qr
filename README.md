# 📱 Système de maintenance par QR Code — Historique Machines QR

Application Power Apps développée pour **Sigma Cylinders CI** permettant de consulter l'historique de maintenance de chaque machine directement depuis un smartphone, en scannant un QR code posé à différents endroits.

*(Projet en cours — automatisation du suivi de maintenance, actuellement basé sur des feuilles papier, vers une application mobile)*

---

## 🎯 Objectif

Digitaliser l'accès à l'historique des interventions de maintenance pour les techniciens, en remplaçant le suivi papier par une consultation instantanée sur téléphone via QR code, directement sur le terrain.

---

## 📊 Fonctionnement

L'application propose une navigation en cascade sur 3 écrans :

1. **Section** → liste des sous-sections (ex. Soudure_Anse_Rod, Soudure_Circulaire, Soudure_Collorette...)
2. **Machine** → liste des machines de la sous-section sélectionnée (ex. SOU-FW 01 à SOU-FW 09)
3. **Historique** → liste des interventions de la machine sélectionnée, avec pour chaque intervention :
   - Numéro de bon d'intervention et date
   - Type de maintenance (Préventive / Corrective / Réactive)
   - Problème rencontré et description de l'intervention
   - Pièces consommées
   - Technicien et durée d'arrêt

Un **QR code par section** (11 au total) donne un accès direct filtré à la bonne section depuis le lien publié de l'application.

---

## 🛠️ Stack technique

`Power Apps` `Power Automate` `SharePoint` `Office Scripts`

- **Référentiel machines** : liste SharePoint (349 codes machine, 11 sections / 59 sous-sections)
- **Historique interventions** : liste SharePoint (~14 000 lignes)
- **Navigation** : 3 écrans dans Power Apps, filtrage en cascade Section → Sous-section → Machine → Historique via variables globales
- **Synchronisation des données** : flux Power Automate déclenchant un Office Script qui lit directement le fichier Excel de suivi maintenance, avec filtrage automatique des interventions déjà importées

---

## 🖼️ Aperçu de l'application

### Écran 1 — Sélection de la section
![Écran section](01-ecran-section.png)

### Écran 2 — Sélection de la machine
![Écran machine](02-ecran-machine.png)

### Écran 3 — Historique des interventions
![Écran historique](03-ecran-historique.png)

---

## 🔒 Confidentialité

Les données affichées (machines, interventions, techniciens) sont des **données réelles de l'entreprise Sigma Cylinders CI**, partagées à titre illustratif uniquement.

---

## 💡 Ce que ce projet démontre

- Conception d'une application métier complète avec Power Apps (UX en cascade, filtrage dynamique)
- Automatisation de flux de données avec Power Automate et Office Scripts
- Modélisation de données relationnelles dans SharePoint à grande échelle (~14 000 lignes d'historique)
- Vision produit : transformation d'un processus papier en outil digital utilisable sur le terrain
