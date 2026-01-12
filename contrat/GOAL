## GOAL — Pipeline d’analyse sémantique (cible = format minimal + bornes + preuve)

### 1) Ensembles

- Ensemble des Goals valides :  
$$
    \mathcal{G} = { g \mid g \text{ décrit un résultat observable en 1 sprint} }  
$$
- Ensemble des preuves possibles :
    - $(\Pi_{url})$ = URL/endpoint qui répond
    - $(\Pi_{ui})$ = action UI démontrable (bouton, écran)
    - $(\Pi_{test})$ = commande de test/lint qui passe
    - $(\Pi_{artifact})$ = fichier généré (build, rapport, export)
    - $(\Pi_{repo})$ = commit hash + diff attendu

### 2) Logique (opérateurs)

Objectif: rendre (g) **non-interprétable** en le forçant à contenir 3 opérateurs:
- **Action** (verbe) : “ajouter / exposer / déployer / calculer…”
- **Objet** (quoi précisément) : “page / endpoint / workflow / fichier…”
- **Preuve** (comment on sait que c’est fait) : une preuve unique et testable

Donc:  
$$
g := \textsf{Action} + \textsf{Objet} + \textsf{Preuve}  
$$
### 3) Invariants (ce que Goal doit garantir)
- **1 sprint = 1 résultat** (pas 3 features déguisées)
- **0 mot flou non borné** (“améliorer”, “optimiser”, “propre”, “intuitif”, “robuste”…)
- **preuve unique principale** (sinon tu te noies)

### 4) Axes de variation (ce que Goal a le droit de changer)
- Type de preuve (URL vs test vs UI)
- Surface (1 écran vs 1 endpoint vs 1 script)
- Contexte (nouveau projet vs repo existant)

### 5) Analyse (seuils / stabilité)

**Seuil de stabilité**: si ton Goal peut être validé par une seule personne en moins de 2 minutes, il est stable.
- Si validation > 2 minutes → $(\mu(\text{ambiguïté}))$ remonte (trop d’implicite)
- Si besoin d’expliquer → Goal mal formé
- Si tu peux le confier à un tiers qui coche “done” sans te parler → bon

### 6) Catégories (cohérence interne)

On impose 4 catégories de Goal (tu choisis une seule catégorie par sprint):
1. **URL/Produit** : “Une URL publique qui fait X”
2. **Fonction** : “Une commande qui retourne Y”
3. **CI/Qualité** : “Tests/lint passent sur Z”
4. **Artefact** : “Un fichier généré conforme”

### 7) Topologie (liens vers le reste)

Goal doit se projeter en `task_plan.md` sans invention :
- Goal → `# Goal`
- Type de preuve → alimente DoD plus tard
- Objet → découpe Backlog plus tard

### 8) Probabilités / mesure (pré-scoring futur)

Indices simples qu’on utilisera plus tard (sans coder maintenant):
- Ambiguïté ↑ si mots flous présents
- Validation ↑ si preuve est une commande ou une URL

---

## Format minimal du Goal (template final)

Colle ça dans ton SprintContract:

**GOAL (1 ligne, format imposé)**

```
[VERB] [OBJECT] so that [USER/USE] — PROOF: [ONE proof]
```

**Bornes (obligatoires, 3 champs)**

```
SCOPE: [max 1 screen OR 1 endpoint OR 1 script]
TIMEBOX: [<= 1 sprint]
NON-GOALS: [2 bullets max]
```

**Exemples ultra concrets**

1. SaaS simple

```
Create a public landing page with one CTA button — PROOF: URL loads and CTA scrolls to signup section.
SCOPE: 1 page
TIMEBOX: 1 sprint
NON-GOALS: payments, auth
```

2. API

```
Expose POST /api/leads that stores email in sqlite — PROOF: curl returns 201 and row exists.
SCOPE: 1 endpoint + 1 table
TIMEBOX: 1 sprint
NON-GOALS: email verification, analytics
```

3. Qualité

```
Make `npm test` pass on main branch — PROOF: GitHub Actions run is green.
SCOPE: tests only
TIMEBOX: 1 sprint
NON-GOALS: refactor features, new UI
```

---

## Tensions (signalées, pas cachées)

- Tu veux un Goal “humain-compréhensible” **et** “robot-compilable”.  
    Solution: 1 ligne humaine + 3 champs bornés + 1 preuve dure.
- Si tu mets “so that [USER/USE]” tu ajoutes un peu d’interprétation (bonne pour l’humain).  
    Mais la preuve doit rester **non-discutable** (bonne pour le robot).
