# 00 — Définitions (D)

Ce document définit le vocabulaire et le typage minimal de la méthode.
Aucune règle opérationnelle, aucun seuil, aucun protocole ici.

---

## 0) Notation

- Les lettres (H, I, IC, C, Fp, Fn, R, E) désignent des **objets**.
- Les symboles (φ, κ, ε, f₂, f₃) désignent des **opérateurs** (transformations).
- Les fichiers `.md` sont des **artefacts** (supports matériels de preuve).

---

## 1) Objets (types)

### H — Intention brute (entrée humaine)
Texte non fiabilisé décrivant un objectif, un contexte, des contraintes et des préférences.
- Propriété : peut être vague, contradictoire, implicite.

### IC — Intention clarifiée
Version structurée de H produite par un questionnaire minimal.
- But : rendre l’intention *actionnable* sans explication orale.

### C — Contrat de Sprint
Objet contractuel structuré :
- C = (GOAL, SPRINT_BACKLOG, DEFINITION_OF_DONE)

### GOAL — But
Énoncé stable sous la forme :
- **Action + Objet + Preuve**

### SPRINT_BACKLOG — Périmètre
Liste ordonnée d’items, chaque item représentant une **transformation** nécessaire.

### DEFINITION_OF_DONE — Validation (DoD)
Conjonction logique stricte (**ET**) de critères binaires, chacun associé à une preuve typée.

---

### Fp — Plan d’exécution (task_plan.md)
Artefact décrivant les phases du sprint.
- Contient N phases.
- Chaque phase possède un statut.

### Fn — Découvertes (findings.md)
Artefact consignant la mémoire de travail :
- exigences / contraintes,
- découvertes,
- décisions techniques,
- blocages.

### R — Preuves / Journal d’exécution (progress.md)
Artefact consignant les actions réalisées + preuves associées :
- actions,
- fichiers modifiés,
- résultats de tests,
- erreurs et tentatives.

### E — Exécution traçable
État résultant lorsque :
- les phases de Fp sont complétées,
- Fn et R contiennent une trace suffisante,
- la DoD est satisfaisable et vérifiable.

---

## 2) Artefacts (fichiers)

Artefacts minimaux du système :

- `contrat/GOAL.md`
- `contrat/SPRINT_BACKLOG.md`
- `contrat/DEFINITION_OF_DONE.md`
- `task_plan.md` (Fp)
- `findings.md` (Fn)
- `progress.md` (R)

---

## 3) Statuts (phases)

Ensemble des statuts autorisés pour une phase :

- `pending`
- `in_progress`
- `complete`

---

## 4) Types de preuve (typage minimal)

Une preuve associée à un critère DoD est de type :

- **URL** (lien vérifiable)
- **Commande** (commande exécutable + sortie attendue)
- **Artefact** (fichier, build, capture, export)
- **Repo** (état du dépôt, commit, tag, release)
- **Humain** (validation explicite par un tiers identifié)

---

## 5) Opérateurs (signatures)

### φ — Clarification
- φ : H → C
Produit un contrat C à partir d’une intention brute H (via IC si nécessaire).

### κ — Compilation
- κ : C → Fp
Compile C en `task_plan.md` tel que :
- N(phases) = N(items du SPRINT_BACKLOG)
- correspondance stricte un-à-un (bijection structurelle)

### ε — Exécution contrôlée
- ε : Fp → E
Produit une exécution traçable E en mettant à jour Fn et R, et en faisant passer les phases à `complete` lorsque la DoD est satisfaite.

---

## 6) Morphismes auxiliaires (notation)

### f₂ — Compilation du contrat en plan
- f₂ : C → Fp
Alias opérationnel de κ (même intention : passer du contrat à un plan exécutable).

### f₃ — Validation finale
- f₃ : (Fp, Fn, R) → Validation
Décide si le sprint est validé à partir du plan + découvertes + preuves.

---

## 7) Mesures (définition, sans seuils)

### μ(ambiguïté)
Mesure la proportion de zones interprétables dans C.

### μ(validation)
Mesure la proportion de zones vérifiables sans discussion dans C.

Note : les seuils et critères de calcul appartiennent à `03_seuils_et_mesures.md`, pas ici.

---

## 8) Dépendance externe (définition)

**planning-with-files** : discipline d’exécution externe sur laquelle s’appuie ε.
Ce dépôt ne la réimplémente pas, il s’y compose.

