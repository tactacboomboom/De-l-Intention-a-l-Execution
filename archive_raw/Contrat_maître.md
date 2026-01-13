# 1. Ontologie du Contrat (C)

• **Objets** : Sprint Goal, Definition of Done (DoD), Sprint Backlog.

• **Opérateur** : Spec(H)→C (L'humain spécifie le cadre).

• **Morphisme** : f2​:C→Fp​ (La compilation du contrat en plan actionnable).
___

# 2. Invariants et Tensions

3. **C précède l'action** : Aucune tâche n'est entreprise sans être ancrée dans C.

4. **Un sprint = Un DoD testable** : Le contrat doit aboutir à un résultat observable (URL, test, bouton).

5. **Tension** : Plus C est strict, moins l'agent (A) a de marge d'interprétation, ce qui réduit le risque de dérive mais exige une précision maximale de l'humain (H) lors de la rédaction.

--------------------------------------------------------------------------------

# 3. Template détaillé : `CONTRAT_DE_SPRINT.md`

Ce document appartient à la **Catégorie Planification** et doit tenir sur **un seul écran** pour rester stable et lisible.

# 📄 CONTRAT DE SPRINT : [ID_ITERATION]

## 🎯 1. Sprint Goal (L'Intention)
> [Une phrase unique décrivant l'objectif métier ou technique. Doit être ininterprétable].
> *Lien direct avec le "Goal" de task_plan.md* [6, 11].


## ✅ 2. Definition of Done (DoD)
Le livrable est considéré comme "Fini" si et seulement si :
- [ ] Critère 1 : [ex: URL de déploiement active et testée] [10].
- [ ] Critère 2 : [ex: Tous les tests dans progress.md sont PASS] [12, 13].
- [ ] Critère 3 : [ex: Documentation technique à jour dans findings.md] [11].
- [ ] Critère 4 : [Signature humaine effectuée via commit/push] [9].

## 📋 3. Sprint Backlog (Le Périmètre)
*Liste exhaustive des modules ou fonctionnalités à traiter :*
1. [Module A] -> *Deviendra Phase 1 de Fp*
2. [Module B] -> *Deviendra Phase 2 de Fp*
3. [Module C] -> *Deviendra Phase 3 de Fp*

## 🛡️ 4. Contraintes et Limites
- **Temps** : [Durée de l'itération].
- **Technique** : [ex: Pas de nouvelles dépendances sans note dans findings.md].
- **Qualité** : Règle des 2 actions et Protocole 3-Strike obligatoires [12, 14].

## ✍️ 5. Validation (Sign)
- **H (Humain)** : [Signature/Date]
- **État Initial du Repo** : [Hash du dernier commit]

___

# 4. Analyse de la règle Fp​∘C=C∘Fp​

Cette règle assure la **cohérence interne** du système :

• **Sens** C→Fp​ **(Compilation)** : Le contrat dicte la structure du plan. Si le backlog contient 3 items, Fp​ doit contenir 3 phases correspondantes.

• **Sens** Fp​→C **(Validation)** : Le statut `complete` dans Fp​ n'est valide que s'il satisfait les critères de la DoD dans C.

• **Commutativité** : L'ordre n'influence pas la vérité finale ; que vous vérifiez le succès via le plan (tâches cochées) ou via le contrat (DoD respectée), vous devez aboutir à la même conclusion sur l'état du livrable (Fd​).

# 5. Mesure de Stabilité

Le contrat est jugé **stable** si la **DoD est observable** (URL, test automatique). Il devient **instable** si le Sprint Goal devient narratif ou flou, ce qui augmente mathématiquement le risque de dérive (Rdeˊrive​).

**Analogie** : Le Contrat de Sprint est le **règlement d'une course**. Le `task_plan.md` est la feuille de route du coureur. La commutativité assure que si le coureur suit sa feuille de route, il respecte forcément le règlement, et que le juge (H), en regardant le règlement, peut valider la course sans ambiguïté.
