# 🎧 7. Gouvernance Jira Service Management (JSM) & Matrice SLA

## 🎯 Stratégie Support & Incident Management
Pour assurer la continuité de service de la plateforme **KOLLECTA**, le support N2/N3 s'appuie sur une politique d'engagements de service (SLA) stricte. Chaque incident de production ou demande support est catégorisé selon son impact métier.

---

## ⏱️ Matrice des SLA (Service Level Agreements)

| Niveau de Sévérité | Description / Critères d'Impact | Premier Temps de Réponse (TTR) | Temps de Résolution (TTD) | Escalade Automatique |
| :--- | :--- | :--- | :--- | :--- |
| **P1 - Critical** | Indisponibilité totale de la plateforme, panne du système de don/paiement, brèche de sécurité. | **< 15 min** | **< 4 heures** | Alerte immédiate Slack/SMS au Tech Lead & PO |
| **P2 - High** | Dysfonctionnement majeur sans contournement rapide (ex: échec du module KYC pour > 20% des utilisateurs). | **< 1 heure** | **< 8 heures** | Alerte Email Product Owner & QA Lead |
| **P3 - Medium** | Anomalie fonctionnelle contournable ou problème d'affichage UI non bloquant. | **< 4 heures** | **< 24 heures** | Notification dans le canal standard de l'équipe |
| **P4 - Low** | Demande d'assistance utilisateur, correction de texte/typo, petite amélioration UI. | **< 24 heures** | **Prochaine Release** | Traitement au fil de l'eau par le support N1 |

---

## 🛠️ Configuration des Queues (Files d'Attente JSM)

Les tickets entrants sont automatiquement routés vers 4 queues dédiées :
1. **`🚨 Unassigned Critical Incidents`** : Incidents P1 en attente de prise en charge urgente.
2. **`🔍 KYC & Security Review`** : Blocages de validation d'identité et vérifications de compte.
3. **`💳 Payment & Donations Support`** : Problèmes liés aux transactions et promesses de don.
4. **`💡 Feature Requests & Feedback`** : Demandes d'évolution à analyser par le PO.

---

## 🤖 Règles d'Automation JSM Associées
* **Escalade P1 :** Tout incident P1 non assigné au bout de 20 minutes bascule automatiquement à l'état `Escalated`.
* **Synchro Statut Client :** Envoi automatique d'une notification au demandeur dès qu'un agent passe le ticket à `In Progress` ou `Resolved`.