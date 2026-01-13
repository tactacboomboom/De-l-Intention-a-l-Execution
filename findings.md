# 🎯 Exigences & contraintes

- L’architecture doit définir explicitement φ, κ et ε avec leurs entrées, sorties et règles.
- Les dépendances externes doivent être localisées dans l’opérateur qui en dépend (ε).
- La méthode doit pouvoir s’appliquer à son propre dépôt sans contradiction.

---

# 🔍 Découvertes (Research Findings)

- *planning-with-files* exige que les artefacts d’exécution (`findings`, `progress`)
  consignent des **événements**, et non des règles.  
  Source : https://github.com/OthmanAdi/planning-with-files/blob/master/docs/quickstart.md

- La combinaison de `task_plan.md` + `progress.md` + `findings.md` est suffisante
  pour restaurer le contexte d’exécution après une interruption.

- Le tableau de redémarrage en 5 questions permet une réhydratation mentale rapide
  de l’état du sprint.

- Un lecteur externe peut reconstruire l’intégralité de la chaîne d’exécution
  (φ → κ → ε) en utilisant uniquement `README.md`, `ARCHITECTURE.md`
  et le fichier d’exemple.

---

# 🛠 Décisions techniques

| Décision                                              | Rationnel (Pourquoi ?)                                                      |
|-------------------------------------------------------|-----------------------------------------------------------------------------|
| `ARCHITECTURE.md` est l’unique source de vérité pour φ, κ, ε | Éviter la duplication et l’ambiguïté entre le README et les documents de méthode |
| Dépendance *planning-with-files* localisée dans ε     | ε est le seul opérateur reposant sur une discipline d’exécution externe     |

---

# ⚠️ Problèmes & blocages

| Problème rencontré                                              | Résolution / piste                                      |
|-----------------------------------------------------------------|---------------------------------------------------------|
| Ambiguïté sur l’emplacement de la référence à *planning-with-files* | Dépendance localisée explicitement dans la définition de ε |
| Incertitude sur l’action suivante après une interruption        | Le test de redémarrage clarifie la phase en cours et l’étape suivante |
