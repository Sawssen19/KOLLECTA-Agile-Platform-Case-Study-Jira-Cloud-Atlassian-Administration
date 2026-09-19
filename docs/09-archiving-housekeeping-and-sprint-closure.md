# 🧹 9. Stratégie d'Archivage, Backlog Housekeeping & Fermeture de Sprint

## 🔄 Procédure de Clôture de Sprint (Sprint Closure)

Pour maintenir la propreté du Board Jira et garantir la précision des métriques d'équipe, chaque fin de Sprint suit un rituel strict :

1. **Revue des Work Items :** S'assurer que tous les tickets en `Testing` ont été validés par la QA et passés à `Done`.
2. **Gestion des Tickets Inachevés (*Unfinished Issues*) :**
   * Tout ticket non terminé en fin de Sprint est automatiquement réassigné au **Backlog Général** ou basculé dans le Sprint suivant après arbitrage du Product Owner.
   * Ré-estimation des Story Points restants (*Remaining Estimate*).
3. **Clôture Officielle sur Jira :**
   * Action : `Complete Sprint` dans l'interface Backlog / Active Sprints.
   * Export du rapport de Sprint (*Sprint Report*) et analyse de la vélocité.

---

## 🗄️ Stratégie d'Archivage & Housekeeping

Afin de préserver les performances de l'instance Jira Cloud et la lisibilité du projet :

* **Archivage des Releases / Versions :** Les versions dont 100% des tickets sont à l'état `Done` sont marquées comme **`Released`** et archivées.
* **Nettoyage du Backlog (*Backlog Refinement*) :**
  * Suppression ou archivage des idées/tickets obsolètes depuis plus de 3 mois.
  * Marquage en `Won't Do` des demandes d'évolution refusées par le PO.
* **Gouvernance des Composants & Labels :**
  * Fusion des labels doublons (ex: `ui-bug` et `bug-ui`).
  * Révision trimestrielle de la liste des 9 composants pour coller aux évolutions de l'architecture microservices.