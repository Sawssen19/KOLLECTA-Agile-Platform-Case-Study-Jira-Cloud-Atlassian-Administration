# 📝 8. Post-Mortem & Release Notes Automatisées

## 🚨 Template de Post-Mortem Confluence (Incident Management)

Lorsqu'un incident majeur (P1 Critical) survient en production, l'équipe rédige un Post-Mortem Blameless sur Confluence pour identifier les causes racines et prévenir toute récidive.

---

### **Structure du Post-Mortem : Incident P1-2026-08 (Rupture Service KYC)**

* **Date de l'incident :** 18 Août 2026
* **Durée d'interruption :** 1 heure 15 minutes
* **Sévérité :** P1 - Critical (SLA 4h respecté)
* **Lead Incident :** Hannibal Barca (Tech Lead)

#### **1. Résumé de l'Incident**
Échec de validation des pièces d'identité lors des inscriptions suite au déploiement du module KYC (`KOL-12`). Les appels API vers le service de vérification d'identité renvoyaient une erreur `500 Internal Server Error`.

#### **2. Chronologie des Événements (Timeline)**
* **14:00** — Déploiement de la version v1.0.0 en Production.
* **14:10** — Remontée du premier ticket support JSM par un utilisateur bloqué.
* **14:15** — Alerte automatique Slack via la règle JSM P1 Critical. Prise en charge par le Tech Lead.
* **14:35** — Identification de la cause racine : clé API de prod expirée sur l'environnement de vérification d'identité.
* **15:00** — Renouvellement de la clé d'API et déploiement du patch correctif (`HOTFIX-KOL-12`).
* **15:15** — Tests de recette OK et clôture de l'incident.

#### **3. Actions Correctives & Préventives (CAPA)**
* [x] Renouveler la clé d'API et la stocker dans le Vault de clés secrets d'environnement.
* [ ] **`KOL-55`** : Mettre en place un monitoring de validité des clés API avec alerte à J-30.
* [ ] **`KOL-56`** : Ajouter un test d'intégration automatique du provider KYC dans le pipeline CI/CD.

---

## 🏷️ Release Notes Automatisées — Version v1.0.0 (Sprint 4)

Génération automatique du Changelog basé sur les tickets Jira clôturés du **Sprint 4**.

### **🚀 KOLLECTA Release v1.0.0 — Changelog**

#### **🌟 Nouvelles Fonctionnalités (Features / User Stories)**
* **`KOL-12`** : Module de validation des comptes et vérification des pièces d'identité KYC.
* **`KOL-20`** : Formulaire de création et soumission d'une promesse de don.
* **`KOL-23`** : Espace d'administration pour la consultation des promesses reçues.

#### **🐛 Corrections de Bugs (Bug Fixes)**
* **`KOL-47`** : Correction de l'accès anonyme non autorisé à une page restreinte.
* **`KOL-50`** : Correction du bouton de réinitialisation inactif sur les résolutions mobiles.
* **`KOL-51`** : Correction de l'export CSV tronqué sur le tableau des promesses.

#### **🔧 Tâches Techniques & Infrastructure**
* **`KOL-05`** : Configuration du pipeline CI/CD GitHub Actions pour les déploiements automatiques.