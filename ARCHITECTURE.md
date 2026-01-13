## Ontologie minimale (fermée, générative)

### Objets

- **I** : texte brut (intention, contexte, contraintes, préférences)
- **C** : contrat structuré (GOAL, SPRINT_BACKLOG, DEFINITION_OF_DONE)
- **F** : plan d’exécution (`task_plan.md`)
- **E** : exécution traçable (mises à jour de `findings.md`, `progress.md` et statuts des phases)

### Artefacts

- `contrat/*.md`
- `task_plan.md`
- `findings.md`
- `progress.md`

---

## Logique (définition explicite des opérateurs)

### 1) φ : Clarification

#### Type
- φ : 𝕀 → 𝕮

#### Entrée (I)
- Texte brut contenant au minimum : objectif vague + contexte + contraintes

#### Sortie (C)
- `contrat/GOAL.md` : **Action + Objet + Preuve**
- `contrat/SPRINT_BACKLOG.md` : liste d’items, chaque item correspondant à une transformation
- `contrat/DEFINITION_OF_DONE.md` : critères en **ET logique**, avec preuves typées

#### Règles de compilation (bornes)
- Le GOAL doit être validable par un tiers en moins de deux minutes, sans explication orale
- Le BACKLOG possède une cardinalité bornée (par exemple : 3 à 7 items)
- Chaque critère de la DEFINITION OF DONE doit être formulé comme :
  - un test binaire
  - associé à un type de preuve explicite

#### Preuve attachée
- Existence des trois fichiers
- Respect du format attendu (structure, indépendamment de la qualité du contenu)

---

### 2) κ : Compilation de C vers F

#### Type
- κ : 𝕮 → 𝔽

#### Entrée
- Les trois composants du contrat C

#### Sortie
- `task_plan.md` contenant :
  - une section `## Phases` avec **N phases**
  - N égal à la cardinalité du SPRINT_BACKLOG (**bijection stricte**)
  - chaque phase correspondant à un item de backlog reformulé en tâche actionnable
  - un champ `Status` ∈ {pending, in_progress, complete}
  - les sections `Questions clés`, `Décisions prises`, `Erreurs rencontrées`
    (vides au moment de la compilation)

#### Règles
- **Projection** : le Goal, l’ordre du backlog et la Definition of Done sont copiés
  ou référencés depuis C, sans invention
- **Génération** : les questions, décisions et erreurs sont des résidus
  d’exécution et n’appartiennent pas au contrat C

#### Preuve attachée
- Vérification de la bijection :
  `count(backlog_items) == count(phases)`

---

### 3) ε : Exécution contrôlée (planning-with-files)

#### Type
- ε : 𝔽 → 𝔼

#### Entrée
- `task_plan.md` avec des phases à l’état `pending`

#### Sortie (E)
- Une trace d’exécution telle que :
  - `findings.md` contient des entrées datées ou structurées
  - `progress.md` contient des preuves (liens, commandes, captures, artefacts)
  - toutes les phases passent à l’état `complete` avec des preuves associées

#### Règles opérationnelles
- **Règle des 2 actions** :
  après deux actions de recherche ou de navigation,
  mise à jour obligatoire de `findings.md`
- **Règle des 3 échecs (3-strike error)** :
  à la troisième itération infructueuse, escalade vers l’humain
- **Relecture** :
  relire le plan avant toute décision majeure
  afin d’éviter la dérive d’objectif (*goal drift*)

#### Preuve attachée
- Le plan est entièrement à l’état `complete`
- Les preuves correspondantes sont présentes dans `progress.md`

#### Dépendance externe

L’opérateur ε repose sur la discipline d’exécution définie dans
**planning-with-files**, par Othman Adi.

Références :
- https://github.com/OthmanAdi/planning-with-files
- https://github.com/OthmanAdi/planning-with-files/blob/master/docs/quickstart.md

Ce dépôt ne réimplémente pas *planning-with-files*.
Il s’y compose explicitement.

---

## Invariants (rendus explicites)

- **M = ε ∘ κ ∘ φ**
- κ est bijectif sur la structure : backlog ↔ phases
- ε n’a pas le droit de rétroagir sur C (anti dérive d’objectif)

---

## Axes de variation

- Qualité initiale de I (flou → précis)
- Taille du backlog (3 à 7 recommandé)
- Rigueur de la Definition of Done (faible → typée et binaire)
- Discipline d’exécution (faible → stricte)

---

## Topologie (localisation dans le dépôt)

- Spécification : `contrat/`
- Plan : `task_plan.md`
- Journaux d’exécution : `findings.md`, `progress.md`

---

## Invariant de stratification

Cette méthode est strictement stratifiée en quatre couches non superposables :

1. **Théorie** (`/theory`)
   - Documents invariants définissant les fondations de la méthode
   - Ne doivent dépendre d’aucun sprint, d’aucune exécution
     ni d’aucun contexte de projet spécifique

2. **Architecture** (`ARCHITECTURE.md`)
   - Définit les opérateurs φ, κ, ε et leur composition
   - Fait le lien entre théorie et exécution
   - Évolue rarement et de manière délibérée

3. **Exécution** (`task_plan.md`, `findings.md`, `progress.md`)
   - Artefacts spécifiques à un sprint
   - Immuables une fois le sprint clôturé
   - Enregistrent des événements, pas des règles

4. **Instanciation** (`/contrat`, `/examples`)
   - Réalisations spécifiques à un projet ou à un sprint
   - Entièrement jetables et remplaçables

Toute violation de cette stratification invalide la méthode.
