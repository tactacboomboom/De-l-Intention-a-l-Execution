# Guide de démarrage rapide

Suivez ces 5 étapes pour utiliser le modèle *planning-with-files*.

---

## Étape 1 : Créer les fichiers de planification

**Quand :** Avant de commencer tout travail sur une tâche complexe

**Action :** Créer les trois fichiers à l’aide des modèles :

# Option 1 : Utiliser le script d’initialisation (s’il est disponible)
./scripts/init-session.sh

# Option 2 : Copier manuellement les modèles
cp templates/task_plan.md task_plan.md
cp templates/findings.md findings.md
cp templates/progress.md progress.md

Mise à jour : Renseigner la section Objectif dans task_plan.md
avec la description de votre tâche.
___
Étape 2 : Planifier les phases

Quand : Juste après la création des fichiers

Action : Découper votre tâche en 3 à 7 phases dans task_plan.md

Exemple :
### Phase 1 : Exigences et découverte
- [ ] Comprendre l’intention utilisateur
- [ ] Rechercher des solutions existantes
- **Statut :** in_progress

### Phase 2 : Implémentation
- [ ] Écrire le code principal
- **Statut :** pending

Mise à jour :

task_plan.md : définir les phases

progress.md : noter que la planification est terminée
___
Étape 3 : Travailler et documenter

Quand : Tout au long de la tâche

Action : Mettre à jour les fichiers au fil du travail :

| Ce qui se produit                                 | Fichier à mettre à jour | Contenu à ajouter                                          |
| ------------------------------------------------- | ----------------------- | ---------------------------------------------------------- |
| Vous faites une recherche                         | `findings.md`           | Ajouter dans « Découvertes »                               |
| Vous consultez 2 résultats (navigateur/recherche) | `findings.md`           | **MISE À JOUR OBLIGATOIRE** (règle des 2 actions)          |
| Vous prenez une décision technique                | `findings.md`           | Ajouter dans « Décisions techniques » avec justification   |
| Vous terminez une phase                           | `task_plan.md`          | Changer le statut : `in_progress` → `complete`             |
| Vous terminez une phase                           | `progress.md`           | Journaliser les actions réalisées et les fichiers modifiés |
| Une erreur survient                               | `task_plan.md`          | Ajouter dans le tableau « Erreurs rencontrées »            |
| Une erreur survient                               | `progress.md`           | Ajouter dans le journal des erreurs avec horodatage        |

Exemple de flux de travail :
1. Recherche → Mise à jour de findings.md
2. Recherche → Mise à jour de findings.md (2e fois — OBLIGATOIRE)
3. Prise de décision → Mise à jour de « Décisions techniques » dans findings.md
4. Implémentation → Mise à jour de « Actions réalisées » dans progress.md
5. Fin de phase → Mise à jour du statut dans task_plan.md
6. Fin de phase → Résumé de la phase dans progress.md
___
Étape 4 : Relire avant les décisions

Quand : Avant de prendre des décisions majeures
(automatique avec les hooks dans Claude Code)

Action : Le hook PreToolUse lit automatiquement task_plan.md
avant toute opération d’écriture, d’édition ou de commande Bash.

Rappel manuel (si vous n’utilisez pas les hooks) :
Avant toute décision importante, relisez task_plan.md
afin de rafraîchir l’objectif.

Pourquoi :
Après de nombreux appels à des outils, l’objectif initial peut être oublié.
La relecture le remet au premier plan.
___

Étape 5 : Finaliser et vérifier

Quand : Lorsque vous pensez que la tâche est terminée

Action : Vérifier la complétion :

Vérifier task_plan.md
Toutes les phases doivent avoir le statut complete

Vérifier progress.md
Toutes les phases doivent être journalisées avec les actions réalisées

Lancer la vérification de complétion
(si vous utilisez les hooks, cela se fait automatiquement) :
./scripts/check-complete.sh

Si ce n’est pas complet :
Le hook d’arrêt (ou le script) empêche l’arrêt.
Poursuivez le travail jusqu’à ce que toutes les phases soient terminées.

Si c’est complet :
Livrez votre travail !
Les trois fichiers de planification documentent intégralement votre processus.
___
Référence rapide : quand mettre à jour quel fichier
┌─────────────────────────────────────────────────────────┐
│  task_plan.md                                            │
│  Mettre à jour lorsque :                                 │
│  • La tâche commence (le créer en premier !)             │
│  • Une phase est terminée (changement de statut)         │
│  • Une décision majeure est prise                         │
│  • Une erreur est rencontrée                              │
│  • Relecture avant décision (automatique via hook)       │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  findings.md                                             │
│  Mettre à jour lorsque :                                 │
│  • Une découverte est faite (recherche, exploration)     │
│  • Après 2 consultations (règle des 2 actions)           │
│  • Une décision technique est prise (avec justification) │
│  • Des ressources utiles sont trouvées (URLs, docs)      │
│  • Des images ou PDF sont consultés (capturer en texte)  │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  progress.md                                             │
│  Mettre à jour lorsque :                                 │
│  • Une nouvelle phase commence (heure de début)          │
│  • Une phase est terminée (actions, fichiers modifiés)   │
│  • Des tests sont exécutés                                │
│  • Des erreurs surviennent (journal + horodatage)        │
│  • Reprise après une pause (test des 5 questions)        │
└─────────────────────────────────────────────────────────┘
___
Erreurs courantes à éviter
| À ne pas faire                                               | À faire à la place                                  |
| ------------------------------------------------------------ | --------------------------------------------------- |
| Commencer sans créer `task_plan.md`                          | Toujours créer le plan en premier                   |
| Oublier de mettre à jour `findings.md` après 2 consultations | Rappel : « 2 actions = mise à jour de findings.md » |
| Ne pas journaliser une erreur corrigée rapidement            | Journaliser **toutes** les erreurs                  |
| Répéter une action qui a échoué                              | Changer d’approche après échec                      |
| Mettre à jour un seul fichier                                | Les trois fichiers fonctionnent ensemble            |
___
Étapes suivantes

Voir examples/README.md pour des exemples complets de bout en bout

Voir workflow.md pour le diagramme visuel du flux de travail

Voir troubleshooting.md en cas de problème
