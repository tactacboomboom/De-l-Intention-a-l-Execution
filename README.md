# De l’Intention à l’Exécution

### Une méthode formelle pour transformer une intention humaine en action traçable

## Ce qu’est ce dépôt

Ce dépôt définit une **méthode formelle de structuration de l’action** permettant de transformer une intention humaine floue en un plan exécutable, traçable et vérifiable.

Il ne s’agit ni :

* d’un framework logiciel,
* ni d’un outil automatisé,
* ni d’un gestionnaire de tâches.

C’est une **méthode d’ingénierie de l’intention**, applicable à tout projet complexe : logiciel, produit, recherche, organisation.

---

## Problème traité

Une intention humaine est par nature :

* ambiguë,
* instable dans le temps,
* sujette à dérive (goal drift),
* difficilement vérifiable a posteriori.

La question centrale traitée ici est :

> **À quelles conditions une intention humaine peut-elle être considérée comme exécutable, puis exécutée sans perte de sens ?**

---

## Architecture conceptuelle

La méthode repose sur la composition stricte de trois opérateurs :

```
I ──φ──▶ C ──κ──▶ F ──ε──▶ E
```

* **I** — Intention brute (texte humain non fiable)
* **C** — Contrat de Sprint (objet structuré et validable)
* **F** — Plan exécutable (`task_plan.md`)
* **E** — Exécution traçable (`findings.md`, `progress.md`)

Composition globale :

```
M = ε ∘ κ ∘ φ
```

L’architecture complète est définie dans [`ARCHITECTURE.md`](./ARCHITECTURE.md).

---

## Les trois opérateurs

### φ — Clarification de l’intention

φ transforme une intention brute en un **Contrat de Sprint C**, composé de trois objets invariants :

1. **GOAL**
   Forme stricte : **Action + Objet + Preuve**
   → validable par un tiers en moins de 2 minutes, sans explication orale.

2. **SPRINT BACKLOG**
   Décomposition du goal en unités de transformation.
   → bijection stricte avec les phases du plan.

3. **DEFINITION OF DONE (DoD)**
   Critères de fin définis par un **ET logique strict**, chaque critère étant associé à une preuve typée.

Ces éléments sont matérialisés dans le dossier `/contrat`.

---

### κ — Compilation du contrat

κ compile le Contrat C en un plan exécutable `task_plan.md` :

* une phase = un item de backlog,
* aucun ajout conceptuel,
* uniquement projection et reformulation opérationnelle.

Invariant clé :

```
|backlog| = |phases|
```

---

### ε — Exécution contrôlée

ε applique une discipline d’exécution externe (*planning-with-files*) sans la redéfinir.

L’exécution produit :

* `findings.md` → découvertes, recherches, décisions,
* `progress.md` → actions, preuves, erreurs,
* statuts de phases dans `task_plan.md`.

Une fois un sprint clôturé, ces artefacts sont **gelés**.

---

## Système de scoring (filtre a priori)

Avant toute compilation, le contrat C est évalué par deux mesures indépendantes :

### μ(ambiguïté)

Mesure la proportion de zones interprétables dans le contrat.

* μ ≥ 0.5 → contrat **non compilable**
* μ < 0.5 → compilation autorisée

### μ(validation)

Mesure la proportion de critères de DoD objectivement vérifiables.

* μ ≥ 0.7 → validation robuste
* μ < 0.7 → validation fragile

Les seuils sont définis dans `theory/03_seuils_et_mesures.md`.

---

## Stratification du dépôt

Le dépôt est strictement stratifié. Toute violation invalide la méthode.

### 1. Theory (`/theory`)

Documents invariants :

* définitions,
* axiomes,
* règles,
* seuils.

Indépendants de tout sprint ou projet.

### 2. Architecture

* `ARCHITECTURE.md`

Définit φ, κ, ε et leurs relations.

### 3. Exécution

* `task_plan.md`
* `findings.md`
* `progress.md`

Artefacts **spécifiques à un sprint**, immuables une fois clôturés.

### 4. Instanciation

* `/contrat`
* `/examples`

Cas concrets, jetables, remplaçables.

---

## Démarrage rapide (Quickstart)

1. Créer les trois fichiers d’exécution :

   * `task_plan.md`
   * `findings.md`
   * `progress.md`

2. Définir 3 à 7 phases dans `task_plan.md`.

3. Pendant l’exécution :

   * toute découverte → `findings.md`,
   * toute action/progression → `progress.md`,
   * mise à jour des statuts de phase.

4. Appliquer :

   * la règle des 2 actions,
   * le protocole 3-strike,
   * le test de reboot (5 questions).

Le protocole détaillé est décrit dans [`quickstart.md`](./quickstart.md).

---

## Exemple minimal

Le fichier [`examples/example_01_intent_to_execution.md`](./examples/example_01_intent_to_execution.md) démontre une exécution complète :

* intention initiale,
* clarification,
* compilation,
* exécution,
* preuves de complétion.

Un lecteur externe peut reconstruire toute la chaîne **sans explication orale**.

---

## Dépendance externe

L’opérateur ε repose sur la discipline *planning-with-files* :

* [https://github.com/OthmanAdi/planning-with-files](https://github.com/OthmanAdi/planning-with-files)

Cette discipline n’est **pas re-implémentée**, seulement composée.

---

## État du projet

* Méthode fonctionnelle sur cas minimal
* Non encore testée sur des projets SaaS complexes
* Outil automatisant φ non implémenté
* Scoring μ formalisé mais non outillé

Ce dépôt constitue une **base canonique**, pas une fin.

---

## Ce que ce dépôt n’est pas

* ❌ Un outil magique d’IA
* ❌ Un framework logiciel
* ❌ Un gestionnaire de tâches
* ❌ Un générateur automatique de projets

C’est une **méthode formelle pour rendre l’action humaine compilable**.
