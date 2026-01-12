# 1 - Ontologie minimale (H=A)

• **Sujet (S**) : L'Humain-Agent (H=A), unique source d'action et de décision.

• **Support (R**) : Le coffre Obsidian (le "disque dur").

• **Flux (Φ**) : Le mouvement de l'information entre votre cerveau (RAM volatile) et les fichiers Markdown (Espace persistant).

• **Clôture** : Une itération est finie quand l'état du disque reflète l'intention et que le commit est poussé.
____
# 2 - L'ensemble des règles Rg​ est divisé en trois sous-ensembles :

• Efond​ **(Fondamentaux)** : Les lois immuables de persistance.

• Eproc​ **(Protocoles)** : Les algorithmes de réaction face à l'erreur.

• Edec​ **(Décision)** : La matrice de choix entre lecture et écriture.

**Logique opératoire :**

• **Interdit** : Agir sans que l'action ne soit issue d'une phase de `task_plan.md`.

• **Obligation** : Si une information est visuelle ou complexe, elle doit être extraite en texte immédiatement
___
# 3 - Invariants et Tensions

4. **La vérité est dans le coffre** : Si une idée n'est pas écrite, elle n'existe pas pour le projet.

5. **Le Plan précède l'Action** : Ne jamais ouvrir un fichier de code ou un outil sans avoir relu le `task_plan.md`.

6. **L'erreur est un actif** : Un échec non documenté est une faute technique ; un échec documenté est un gain de connaissance.

**Tension signalée** : L'effort cognitif de la "double saisie" (faire et noter) crée une friction qui incite à l'oubli. La règle doit être perçue comme un **investissement anti-hallucination** et non comme une bureaucratie.
___
# 4 - Template Détaillé : `REGLES_DU_JEU.md`

# 📜 RÈGLES DU JEU (Loi du Projet)

## 1. Principes de Persistance (Manus)

*   **Le Disque est la Vérité** : Mon cerveau est une RAM volatile. Tout ce qui est important doit être écrit sur le "disque" (Obsidian/Git).

*   **Manipulation de l'Attention** : Avant chaque décision ou changement de fichier, je RELIS les 30 premières lignes de `task_plan.md`.

*   **Zéro Répétition d'Échec** : Les "mauvais virages" restent dans le contexte (`findings.md`) pour que je ne reprenne jamais le même chemin infructueux.

___
## 2. Protocoles Opérationnels

### 🚨 La Règle des 2 Actions

*Après deux actions de recherche, de lecture de doc ou de navigation web :*
**👉 JE DOIS écrire mes découvertes dans `findings.md` avant toute autre action.**
*But : Empêcher la perte de l'information multimodale/visuelle.

### 🛠 Protocole d'Erreur "3-Strike"

*Si je rencontre un blocage ou une erreur :*

1.  **Strike 1 (Diagnostic)** : Lire l'erreur, identifier la cause, tenter un fix ciblé.

2.  **Strike 2 (Alternative)** : Si l'erreur persiste, CHANGER de méthode. Ne jamais répéter l'action du Strike 1.

3.  **Strike 3 (Rethink)** : Remettre en question le plan. Chercher une solution radicale ou changer d'outil.

___
## 3. Matrice de Décision (Read vs Write)

| Situation                       | Action Immédiate              | Raison                                        |
| :------------------------------ | :---------------------------- | :-------------------------------------------- |
| Je viens de modifier un fichier | **NE PAS relire** le plan     | Le contenu est encore frais en RAM [9].       |
| J'ai lu une documentation web   | **ÉCRIRE** dans `findings.md` | Les infos externes s'évaporent vite [9].      |
| Je commence une nouvelle phase  | **LIRE** `task_plan.md`       | Réaligner l'attention sur le but [10].        |
| Une erreur survient             | **LIRE** le fichier concerné  | Diagnostic sur l'état réel, pas supposé [10]. |

___

## 4. Invariant de Signature

*   L'itération n'est close que si `check-complete.sh` (ou vérification manuelle) confirme que toutes les phases sont `complete`.

*   Le commit Git est ma **signature matérielle** d'approbation.



___
# 5 - Analyse (Seuils et Stabilité)

• **Stabilité** : Votre système est stable tant que vous ne dépassez pas le seuil critique de **50 micro-actions** sans relire votre plan. À partir de là, la "dérive de but" (_goal drift_) est mathématiquement probable.

• **Seuil de rupture** : Si `task_plan.md` dépasse une page, l'attention humaine sature. Vous devez alors **scinder** l'itération en sous-sprints.

# 6 - Topologie et Mesure

La topologie du fichier est une **boucle de rétroaction** : `Task Plan (Action) -> Findings (Apprentissage) -> Progress (Preuve)`.

**Mesure de succès (M) :**

> [!MESURE M1]
> • M1​ : Ai-je évité de refaire une erreur notée hier ? (Valeur : 0 ou 1).

> [!Mesure M2]
> • M2​ : Mon `findings.md` contient-il au moins une note par heure de travail ?.

> [!MESURE M3]
> **Mesure de Performance (M3​) :** Le succès est mesuré par l'évitement des erreurs récurrentes grâce aux traces laissées dans le tableau "Errors Encountered".

**Vecteur Cognitif :**

• **Abstraction** : Élevée (lois du système).

• **Concrétude** : Maximale (templates markdown).

• **Normativité** : Stricte (interdiction de la répétition).

• **Incertitude** : Gérée par le protocole 3-Strike.

**Analogie** : Ce fichier est le **Code de la Route** de votre projet. Sans lui, vous conduisez à l'instinct. Avec lui, même si vous changez de véhicule (d'outil ou de technologie), vous savez comment naviguer sans causer d'accident de logique.
