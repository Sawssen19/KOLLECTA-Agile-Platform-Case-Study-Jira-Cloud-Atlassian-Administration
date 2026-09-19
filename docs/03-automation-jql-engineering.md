# 🤖 3. Automatisation & Ingénierie JQL

## ⚡ Règles Jira Automation Actives
1. **`KOL - Auto Comment Resolved Bugs`** : Injection automatique d'un commentaire d'audit lors du passage d'un Bug à `Done`.
2. **`KOL - Auto Assign QA on Testing`** : Assignation automatique à la QA dès qu'un ticket passe en `Testing`.
3. **`KOL - Alert Highest Priority Bug`** : Notification prioritaire instantanée sur création d'un Bug de priorité `Highest`.

![Automation Rules](screenshots/05-automation-rules-list.png)

---

## 🔍 Filtres JQL Optimisés
* **Bugs Prioritaires :**
  ```jql
  project = "KOL" AND type = Bug AND priority IN (High, Highest)