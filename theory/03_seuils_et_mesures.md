# 03 — Seuils et mesures (L)

Ce document définit les mesures quantitatives et les seuils de décision.
Il ne contient ni axiomes ni règles opératoires.

---

## M1 — Mesure d’ambiguïté μ(ambiguïté)

### Définition
μ(ambiguïté) mesure la proportion de zones interprétables
dans un Contrat de Sprint C.

### Domaine
μ(ambiguïté) ∈ [0,1]

### Interprétation
- 0 : contrat entièrement non interprétable
- 1 : contrat entièrement ambigu

### Seuil de décision
- μ(ambiguïté) ≥ 0.5 ⇒ **Contrat non compilable**
- μ(ambiguïté) < 0.5 ⇒ Compilation autorisée

---

## M2 — Mesure de validation μ(validation)

### Définition
μ(validation) mesure la proportion de critères de la DoD
associés à des preuves vérifiables sans discussion.

### Domaine
μ(validation) ∈ [0,1]

### Interprétation
- 0 : aucune validation objectivable
- 1 : validation entièrement objective

### Seuil de décision
- μ(validation) ≥ 0.7 ⇒ Validation robuste
- μ(validation) < 0.7 ⇒ Validation fragile

---

## M3 — Seuil de saturation attentionnelle

### Définition
Nombre maximal d’actions élémentaires exécutées
sans relecture explicite du plan.

### Seuil
- > 50 micro-actions consécutives ⇒ relecture obligatoire de `task_plan.md`

---

## M4 — Seuil de taille du plan

### Définition
Taille maximale acceptable du fichier `task_plan.md`
avant perte de lisibilité opérationnelle.

### Seuil
- > 1 page standard ⇒ le plan doit être scindé

---

## M5 — Test de générativité externe

### Définition
Test qualitatif de cohérence globale :
un lecteur externe doit pouvoir comprendre et valider
l’exécution d’un sprint sans explication orale.

### Résultat
- PASS : la méthode est générative
- FAIL : ambiguïté structurelle résiduelle

---

## Relation aux opérateurs

- M1 et M2 s’appliquent **avant** κ (filtre a priori)
- M3 et M4 s’appliquent **pendant** ε (contrôle d’exécution)
- M5 s’applique **après** ε (validation globale)

