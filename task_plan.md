# Template : task_plan.md
---

# Task Plan: [Nom du Sprint/Projet]

## 🎯 Goal

[Une phrase unique décrivant l'état final souhaité. Ce but doit être issu du Contrat de Sprint C] [5, 6].
## 📍 Current Phase

**Phase [N]**

## 🗓 Phases

### Phase 1: [Titre de la Phase]
- [ ] [Tâche actionnable 1]
- [ ] [Tâche actionnable 2]
- [ ] Documenter les découvertes dans `findings.md`
- **Status:** [pending | in_progress | complete]

### Phase 2: [Titre de la Phase]
- [ ] [Tâche actionnable]
- **Status:** pending

---
## ❓ Key Questions

1. [Question critique à résoudre pour avancer]
2. [Incertitude technique à lever]

## 🛠 Decisions Made
| Décision | Rationnel (Pourquoi ?) |
| :--- | :--- |
| [Choix technique] | [Justification basée sur les contraintes] |

## 🚨 Errors Encountered (Protocole 3-Strike)
| Error              | Attempt     | Resolution / Mutation                |
| :----------------- | :---------- | :----------------------------------- |
| [Message d'erreur] | [1, 2 ou 3] | [Action différente de la précédente] |

## 📝 Notes & Rappels
- **Règle de Récitation :** Relire ce plan avant chaque décision majeure (Manipulation de l'attention).
- **Règle des 2 Actions :** Après 2 recherches/vues, écrire dans `findings.md`.
- **3-Strike :** Si une action échoue 2 fois, la 3ème tentative doit être une approche radicalement différente.
- 

> [!NOTE]
> **En résumé :** À la Tentative 3, vous modifiez **le "Comment"** (les phases et les méthodes dans votre `task_plan.md`) et vous remettez à plat vos certitudes techniques. Vous ne touchez **au "Quoi"** (le Contrat C) que si, après avoir tout tenté au Strike 3, vous devez admettre que l'objectif est inatteignable, déclenchant ainsi une renégociation du contrat avec vous-même (en tant que décideur H).

___
# 1. Ontologie et Ensembles (Fp​)

Dans l'ontologie minimale, Fp​ **(task_plan.md)** est le "Plan-file", un objet primitif nécessaire pour éviter la dérive de but (_goal drift_). Il appartient à la **Catégorie Planification**.

**Les Ensembles de Métadonnées Invariantes :** Le document doit obligatoirement contenir les sous-ensembles suivants pour être valide :

• **Goal** : Une phrase unique décrivant l'état final visé.

• **Current Phase** : Un pointeur dynamique vers la phase active.

• **Phases** : Une liste structurée de blocs contenant des cases à cocher et un champ **Status**.

• **Key Questions** : Les incertitudes à lever pour réussir la mission.

• **Decisions Made** : Un tableau consignant les choix techniques et leur rationnel.

• **Errors Encountered** : Un tableau de suivi des échecs (Erreur, Tentative, Résolution).
___
# 2. Logique et Morphismes : La Commutativité C→Fp​

Il existe un morphisme explicite f2​:Contrat→task_plan.md nommé l'opérateur **Compile**.
**Le Morphisme Commutatif :** Pour que le système soit stable, la structure du **Contrat de Sprint (C)** — composé du Sprint Goal, de la Definition of Done (DoD) et du Backlog — doit être projetée de manière univoque dans Fp​.

• Le **Sprint Goal** de C devient le **Goal** de Fp​.
• Le **Backlog** de C est transformé en **Phases** chronologiques dans Fp​.
• La **DoD** de C contraint les critères d'achèvement de chaque phase pour que le résultat final soit testable. Cette relation est dite "commutative" car l'état d'avancement de la réalisation (Fd​) doit toujours pouvoir être vérifié par rapport au plan (Fp​), lequel doit rester fidèle au contrat original (C).
___
# 3. Le Protocole d'Erreur "3-Strike"

Ce protocole est l'algorithme de réaction obligatoire consigné dans les métadonnées de Fp​ pour garantir la progression malgré les échecs.

• **Strike 1 : Diagnostiquer et Réparer.** Analyser l'erreur, identifier la cause racine et appliquer un correctif ciblé.
• **Strike 2 : Approche Alternative.** Si l'échec persiste, il est **formellement interdit** de répéter la même action. On change de méthode, d'outil ou de bibliothèque.
• **Strike 3 : Remise en question globale.** Si le blocage demeure, on questionne les hypothèses de base et on envisage de modifier le plan lui-même dans Fp​.

• **Après 3 échecs : Escalade.** L'Agent doit s'arrêter et demander l'arbitrage de l'Humain (H) en expliquant les tentatives précédentes.
___

# 4. Topologie et Analyse de Stabilité

**Invariants de structure :**

• **Statut des Phases** : Chaque phase doit utiliser strictement les étiquettes `pending`, `in_progress`, ou `complete`.
• **Anti-hallucination** : Fp​ doit être relu avant chaque décision majeure (principe de "recitation" pour manipuler l'attention)

**Seuils de Stabilité :**

• Le système est **stable** si Fp​ reste court (idéalement moins d'une page) et vivant.

• Le système devient **instable** si Fp​ devient narratif au lieu de rester une liste de phases actionnables.

> [!MESURE M3]
> **Mesure de Performance (M3​) :** Le succès est mesuré par l'évitement des erreurs récurrentes grâce aux traces laissées dans le tableau "Errors Encountered".

En résumé, le **task_plan.md** est la "mémoire de travail sur disque" qui transforme les intentions abstraites du contrat en étapes matérielles suivies avec une rigueur mathématique, où chaque échec est un actif documenté servant à muter l'approche.
