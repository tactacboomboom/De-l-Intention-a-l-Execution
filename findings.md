# Findings & Decisions (Mémoire de Travail)

## 🎯 Requirements & Contraintes
- Séparer strictement le sujet S (corpus transmissible)
  de la méthode de gestion De-l-Intention-à-l-Exécution.
- Travailler simultanément sur deux dépôts distincts :
  - Repo S : contenu transmissible du sujet.
  - Repo M : pilotage, traçabilité et preuves d’exécution.
- Respecter l’arborescence définie par « Faire un REPO GitHub Optimal.md ».
- Appliquer strictement les phases φ / κ / ε sans saut d’étape.
- L’absence d’un point d’entrée normé (`00_START_HERE`) empêche un lecteur externe d’évaluer la transmissibilité, même si le contenu conceptuel est correct.
- La conformité à une arborescence cible est une condition nécessaire à la preuve PASS / FAIL du dépôt.


## 🔍 Research Findings (Découvertes)
- La confusion initiale entre sujet et contrainte de production
  entraîne des ambiguïtés structurelles dans le contrat.
- La traçabilité d’exécution (progress.md) doit être mise à jour
  avant toute avancée supplémentaire dans Repo S.
- La méthode De-l-Intention-à-l-Exécution impose que toute action
  exécutée soit immédiatement attestée par une preuve factuelle.

**Pointeurs :**
- Repo M : `contrat/GOAL.md`, `contrat/SPRINT_BACKLOG.md`, `contrat/DEFINITION_OF_DONE.md`
- Repo M : `task_plan.md`, `progress.md`
- Repo S : `01_ONTOLOGY/`

## 🛠 Décisions Techniques

| Décision | Rationnel (Pourquoi ?) |
| :------- | :--------------------- |
| Séparation Repo S / Repo M | Éviter toute confusion entre contenu transmis et méthode de pilotage |
| Traçabilité obligatoire avant poursuite | Garantir la cohérence φ / κ / ε |
| Utilisation de templates stricts | Éviter les dérives et les refactors ultérieurs |
| Ajout du triptyque `00_START_HERE` | Garantir un point d’entrée actionnable et testable par un lecteur externe |


## ⚠️ Issues & Blocages

| Problème rencontré | Résolution / Piste |
| :----------------- | :----------------- |
| Avance non tracée dans Repo S | Pause de l’exécution et synchronisation via `progress.md` |
| Ambiguïté initiale du GOAL | Reformulation stricte Action / Objet / Preuve |
| Arborescence initialement incomplète | Ajout explicite de `00_map.md` et des deux quickstarts |


## 🖼 Observations Visuelles / Browser
- Observation de l’interface GitHub :
  la création de dossiers via `Add file → Create new file` impose une attention particulière au chemin du fichier.
- Vérification manuelle de la cohérence de l’arborescence après chaque commit dans Repo S.
- Constat qu’un dépôt sans dossier `00_START_HERE` ne permet pas à un tiers de déterminer par où commencer la lecture.

