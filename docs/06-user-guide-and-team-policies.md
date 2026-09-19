# 📖 6. Guide Utilisateur & Politiques d'Équipe Jira Software

## 👥 Chartes d'Utilisation par Rôle

### **1. Équipe de Développement (Devs)**
* **Prise en charge :** Assigner le ticket à son nom et passer le statut de `To Do` à `In Progress`.
* **Commits & Branches Git :** Utiliser la clé du ticket Jira dans les messages Git (ex: `feat(kyc): KOL-12 implement account validation`).
* **Transition Recette :** Dès le déploiement en Staging, passer le ticket à **`Testing`** et fournir la procédure de test.

### **2. Équipe Assurance Qualité (QA)**
* **Validation (Pass) :** Passer le ticket de `Testing` à **`Done`**.
* **Rejet (Fail) :** Repasser le ticket en `In Progress` ou `Reopened` avec un commentaire détaillant le comportement observé, le comportement attendu et les logs/captures.
* **Déclaration de Bug :** Tout bug doit spécifier un composant (*Component*) et un niveau de priorité.

### **3. Product Owner (PO)**
* **Backlog Refinement :** Seuls les tickets estimés en Story Points et documentés (*Definition of Ready*) entrent en Sprint.
* **Definition of Done (DoD) :** Une Story est `Done` uniquement après validation QA et mise à jour de la documentation Confluence.

### **4. Scrum Master (SM)**
* **Facilitation des Cérémonies :** Animation de la Daily Standup, Sprint Planning, Review et Retrospective.
* **Gestion des Bloqueurs (*Impediments*) :** Identifier et lever les points de blocage signalés par les développeurs ou la QA.
* **Suivi de la Vélocité & Santé du Sprint :** Analyse quotidienne des graphiques Burndown Chart et gestion du cycle de vie du Sprint (Ouverture / Clôture du Sprint sur Jira).
* **Housekeeping Jira :** S'assurer du respect des règles d'équipe, du nettoyage des tickets périmés et de la cohérence des estimations.