# ITEM #2 — SPRINT BACKLOG

## 1) Ensembles

On définit l’ensemble des items de backlog valides :

$$
\mathcal{B} = { b_i \mid b_i \text{ est transformable en UNE phase de } Fp }  
$$

Autrement dit :  
**1 item de backlog ⇔ 1 phase dans `task_plan.md`**  
(c’est déjà un invariant que tu poses, et il est excellent).

Sous-ensembles utiles :
- $(\mathcal{B}_A)$ : items actionnables
- $(\mathcal{B}_S)$ : items sprint-sized
- $(\mathcal{B}_M)$ : items mappables sans interprétation

---

## 2) Logique (opérateurs)

Le backlog n’est **pas** une liste d’idées.  
C’est une **décomposition du Goal en unités de transformation**.

On définit l’opérateur :

$$
[  
\textsf{decompose} : Goal \rightarrow {b_1, b_2, \dots, b_n}  
]
$$

avec contrainte forte :

$$
[  
\forall b_i,\quad \textsf{compile}(b_i) = \textsf{Phase}_i  
]
$$

Si un item ne peut pas devenir **directement** une Phase, il est invalide.

---

## 3) Invariants (ce que le Backlog doit garantir)

### Invariant 1 — Bijection stricte
- Nombre d’items Backlog = nombre de Phases dans `task_plan.md`
- Ordre conservé (Backlog → Phases chronologiques)

### Invariant 2 — Action, pas thème
Un item **doit décrire une action de transformation**, pas un domaine.

❌ “Auth”, “Frontend”, “API”, “Sécurité”  
✅ “Implémenter endpoint POST /login”, “Créer page Signup statique”

### Invariant 3 — Sprint-sized

Un item doit être :
- réalisable **sans dépendre d’un autre sprint**
- vérifiable **avant la DoD globale**

---

## 4) Axes de variation (ce qui est autorisé)

- Type d’action :
    - création (create)
    - modification (update)
    - intégration (connect)
    - vérification (validate)

- Support :
    - code
    - configuration
    - documentation minimale (si et seulement si liée à un artefact)

---

## 5) Analyse (seuils / stabilité)

### Seuil critique d’ambiguïté

Un item est **instable** si :
- tu dois expliquer oralement ce qu’il signifie
- ou s’il peut être interprété en **plus d’une Phase possible**

➡️ Dans ce cas, $(\mu(\text{ambiguïté})$ > 0.5)

### Seuil de stabilité

Un item est **stable** si :
- il peut être renommé automatiquement en  
    `Phase N: [verbe + objet précis]`
- et si une checklist de tâches actionnables en découle **sans invention**

---

## 6) Catégories (cohérence interne)

On impose **3 catégories exclusives** d’items Backlog.  
Chaque item doit appartenir à **une seule**.

### Catégorie B1 — Build
> Créer ou modifier un artefact exécutable

- ex: “Créer endpoint POST /api/leads”
- ex: “Implémenter logique de calcul du score”

### Catégorie B2 — Integrate
> Relier deux éléments existants

- ex: “Connecter formulaire signup à /api/leads”
- ex: “Brancher endpoint à sqlite”

### Catégorie B3 — Verify
> Rendre testable / observable

- ex: “Ajouter test de création de lead”
- ex: “Déployer et exposer URL publique”

⚠️ **Documentation seule** n’est jamais un item B valide.  
Elle est **une tâche** dans une Phase, pas un item de backlog.

---

## 7) Topologie (mapping C → Fp)

Mapping canonique, **sans enrichissement** :

|Sprint Backlog (C)|task_plan.md (Fp)|
|---|---|
|Item i|Phase i|
|Intitulé item|Titre de Phase|
|Catégorie (B1/B2/B3)|Nature des tâches|
|Ordre backlog|Ordre chronologique|

Les sections **Key Questions**, **Decisions**, **Errors** de Fp  
👉 **ne viennent PAS du Backlog**  
👉 elles sont des **résidus d’exécution**, donc hors (C).  
(C’est important pour réduire $(\mu(\mathcal{A}_M))$.)

---

## 8) Probabilités / mesure (pré-scoring futur)

Indicateurs simples qu’on utilisera plus tard :

### Ambiguïté ↑ si :
- nom contient un nom abstrait (“auth”, “infra”, “optimisation”)
- pas de verbe clair
- pas de borne implicite de taille

### Validation ↑ si :
- l’item contribue directement à un critère de DoD
- on peut dire “cet item est terminé” indépendamment des autres

---

## Format minimal du Sprint Backlog (template final)

À coller dans `CONTRAT_DE_SPRINT.md`

```
## 📋 Sprint Backlog

1. [BUILD] <verbe> <objet précis>
2. [INTEGRATE] <verbe> <objet A> with <objet B>
3. [VERIFY] <verbe> <preuve observable>
```

### Exemples concrets

**Bon**

```
1. [BUILD] Create POST /api/leads endpoint
2. [INTEGRATE] Connect signup form with /api/leads
3. [VERIFY] Deploy app and expose public URL
```

**Mauvais**

```
1. Auth
2. Frontend
3. Tests
```

---

## Tensions signalées (sans les résoudre à ta place)

- Plus le backlog est **verbeux**, plus il est humain-lisible  ↔ plus il devient non-compilable.
- Plus le backlog est **strict**, plus l’intention initiale doit être clarifiée **avant** Scrum (ce que tu assumes pleinement).

---

### Résultat net pour le Backlog

- $(\mu(\text{ambiguïté}))$ : **faible à moyen**, si format imposé
- $(\mu(\text{validation}))$ : **moyen à élevé**, car chaque item est borné et indépendant
- Mapping vers `task_plan.md` : **direct, sans invention**
