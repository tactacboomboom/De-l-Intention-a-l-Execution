## Ontologie minimale (fermée, générative)

Objets:

* **I**: texte brut (intention, contexte, contraintes, préférences)
* **C**: contrat structuré (GOAL, BACKLOG, DoD)
* **F**: plan exécutable (`task_plan.md`)
* **E**: exécution traçable (updates `findings.md` + `progress.md` + statuts phases)

Artefacts:

* `contrat/*.md`
* `task_plan.md`
* `findings.md`
* `progress.md`

---

## Logique (définition explicite des opérateurs)

### 1) φ : Clarification

**Type**

* φ : 𝕀 → 𝕮

**Entrée (I)**

* Texte brut contenant au minimum : (objectif vague) + (contexte) + (contraintes)

**Sortie (C)**

* `contrat/GOAL.md` : **Action + Objet + Preuve**
* `contrat/SPRINT_BACKLOG.md` : liste d’items, chacun = une transformation
* `contrat/DEFINITION_OF_DONE.md` : critères en **ET** logique, preuves typées

**Règles de compilation (bornes)**

* GOAL validable par un tiers en <2 min, sans oral
* BACKLOG cardinalité bornée (ex: 3–7 items)
* DoD: chaque critère = (test binaire) + (type de preuve)

**Preuve attachée**

* Existence des 3 fichiers + format respecté (structure, pas contenu parfait)

---

### 2) κ : Compilation C → F

**Type**

* κ : 𝕮 → 𝔽

**Entrée**

* Les 3 composants de C

**Sortie**

* `task_plan.md` avec :

  * section `## Phases` contenant **N phases**
  * N = cardinalité du BACKLOG (**bijection stricte**)
  * chaque phase = un item de backlog reformulé en tâche actionnable
  * `Status` ∈ {pending, in_progress, complete}
  * sections `Key Questions`, `Decisions Made`, `Errors Encountered` (vides au départ)

**Règles**

* Projection: Goal + ordre backlog + DoD sont copiés/référencés (pas inventés)
* Génération: Questions/Décisions/Erreurs sont **résidus d’exécution** (pas dans C)

**Preuve attachée**

* Vérifier la bijection: `count(backlog_items) == count(phases)`

---

### 3) ε : Exécution contrôlée (PwF)

**Type**

* ε : 𝔽 → 𝔼

**Entrée**

* `task_plan.md` (phases en pending)

**Sortie (E)**

* Une trace telle que:

  * `findings.md` contient des entrées datées ou structurées
  * `progress.md` contient des preuves (liens, commandes, captures, artefacts)
  * toutes les phases passent à `complete` avec preuves associées

**Règles opérationnelles**

* Règle des 2 actions: après 2 actions de recherche/navigation → update `findings.md`
* 3-strike error: à la 3e itération d’échec → escalade humain
* Relecture: relire plan avant décision majeure (anti drift)

**Preuve attachée**

* Le plan est “complete” + preuves présentes dans `progress.md`

**External dependency**

The operator ε relies on the execution discipline defined in
"planning-with-files" by Othman Adi.

See:
- https://github.com/OthmanAdi/planning-with-files
- https://github.com/OthmanAdi/planning-with-files/blob/master/docs/quickstart.md

This repository does not reimplement planning-with-files.
It composes with it.


---

## Invariants (rendus explicites)

* M = ε ∘ κ ∘ φ
* κ est bijectif sur la structure: backlog ↔ phases
* ε n’a pas le droit de rétroagir sur C (anti goal drift)

---

## Axes de variation

* Qualité initiale de I (flou → précis)
* Taille de backlog (3–7 recommandé)
* Rigueur DoD (faible → typée et binaire)
* Discipline d’exécution (faible → stricte)

---

## Topologie (où ça vit dans ton repo)

* Spécification: `contrat/`
* Plan: `task_plan.md`
* Run logs: `findings.md`, `progress.md`
