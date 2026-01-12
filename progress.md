Le fichier **progress.md** (intégré dans l'ensemble F comme composant de la réalisation et du suivi) est votre **journal de bord chronologique**. Alors que le `task_plan.md` est tourné vers l'avenir (ce qu'il reste à faire) et le `findings.md` vers le savoir (ce qui a été appris), le `progress.md` est le témoin du passé immédiat (ce qui a été exécuté).

Voici la structure rigoureuse pour une gestion manuelle (H=A).
___

# 1. Ontologie et Logique de `progress.md`

• **Objet** : Trace séquentielle de l'exécution Act(A,ctx)→ΔFd​.

• **Fonction** : Réduire la charge cognitive en externalisant l'historique des actions et des tests.

• **Clôture** : Ce fichier permet le passage du test de cohérence interne avant la signature (Sign).

--------------------------------------------------------------------------------
# 2. Invariants et Tension

3. **L'observabilité des tests** : Chaque action technique doit être validée par un résultat binaire (Succès/Échec) consigné dans le journal.

4. **Le "Reboot" systématique** : À chaque reprise de session ou après une interruption, la relecture de ce fichier est obligatoire pour restaurer l'état de la RAM mentale.

5. **Tension** : Entre la précision du log et la vitesse d'exécution. Si le log est trop succinct, la cause d'une erreur passée devient invisible (échec du principe d'anti-répétition).
  
--------------------------------------------------------------------------------
# 3. Template Détaillé : `progress.md`

# Progress Log : [NOM DU PROJET]

## 📅 Session du : [DATE]

### Suivi des Phases (Chronologique)
#### Phase [N] : [Titre de la Phase]
- **Status :** [in_progress | complete]
- **Début :** [Heure]
- **Actions réalisées :**
    - [Action 1 : ex. Création de la structure SQL]
    - [Action 2 : ex. Test de connexion]
- **Fichiers modifiés/créés :**
    - `src/db/schema.sql`

---

## 🧪 Résultats des Tests
| Test | Entrée | Attendu | Réel | Status |
| :--- | :--- | :--- | :--- | :--- |
| Login API | {user: "admin"} | 200 OK | 200 OK | ✅ PASS |
| Validation Form | Vide | Error 400 | null | ❌ FAIL |

---

## 📑 Journal des Erreurs (Log)
| Timestamp | Erreur | Tentative n° | Résolution / Mutation |
| :--- | :--- | :--- | :--- |
| 14:05 | Connection Timeout | 1 | Vérification du firewall (OK) |
| 14:12 | Connection Timeout | 2 | Changement du port 5432 -> 5433 |

---
Le **5-Question Reboot Test**, c'est votre **point d'orientation** toutes les heures.
## 🔄 Test de Reboot (5 Questions)
| Question              | Réponse                         | Source         |                                                        |
| :-------------------- | :------------------------------ | :------------- | ------------------------------------------------------ |
| **Où en suis-je ?**   | Phase [X] en cours              | task_plan.md   | (Indiquer la phase actuelle dans le `task_plan.md`     |
| **Où vais-je ?**      | Prochaines étapes : [Y]         | task_plan.md   | Lister les phases restantes                            |
| **Quel est le but ?** | [Goal Statement de l'itération] | task_plan.md   | Relire l'énoncé de l'objectif dans le plan             |
| **Qu'ai-je appris ?** | [Synthèse rapide]               | findings.md    | Synthétiser les dernières entrées de `findings.md`     |
| **Qu'ai-je fait ?**   | [Dernière action stable]        | Voir plus haut | Résumé des actions notées plus haut dans `progress.md` |
==• **Reprise de travail :** Si vous arrêtez votre projet le soir et reprenez le lendemain, ce tableau vous permet de **restaurer votre contexte mental** en moins de deux minutes.==

--------------------------------------------------------------------------------
# 4. Protocole de mise à jour (Règles strictes)

• **Fréquence** : Vous devez mettre à jour ce fichier **après chaque phase complétée** ou dès qu'une erreur survient.

• **Règle de l'Erreur** : Si une action échoue, vous ne devez **jamais répéter la même action** sans avoir consigné l'échec et muté votre approche dans le log d'erreurs.

• **Le "5-Question Reboot Test"** : Ce tableau en fin de fichier est votre assurance-vie contextuelle. Si vous pouvez y répondre, votre gestion du contexte est solide.

--------------------------------------------------------------------------------
# 5. Analyse de Stabilité et Mesure

• **Seuil de Stabilité** : Le projet est considéré comme "sous contrôle" si le `progress.md` permet à un tiers (ou à vous-même après 48h d'arrêt) de reprendre le travail en moins de 5 minutes.

> [!MESUR M2]
> • **Mesure** M2​ : Le succès est validé si la colonne "Actual" de votre tableau de tests correspond à la "Definition of Done" (DoD) de votre contrat de départ.

**Analogie** : Le `progress.md` est le **registre de bord d'un ingénieur moteur**. Le plan dit d'augmenter la puissance, les notes expliquent la thermodynamique du fluide, mais le journal de progrès consigne chaque tour de clé de 12 et chaque pression mesurée sur le manomètre. C'est le seul document qui prouve que le travail a été _réellement_ fait et testé.

___
Dans la méthode **planning-with-files**, la rigueur de la saisie dans les sections **Résultats des Tests** et **Journal des Erreurs** est ce qui transforme un simple bloc-notes en une **mémoire de travail externe** capable de diriger l'action sans dérive.

Voici la définition structurelle et l'usage de ces deux sections pour votre projet :

1. ==La section "Résultats des Tests" (Le pivot de la DoD)==

Située dans le fichier `progress.md`, cette section est le tribunal de votre avancement.

• **La colonne "Actual" (Résultat Réel) :** Elle doit consigner la donnée brute observée (ex: "Code erreur 404", "JSON retourné : {id: 123}", ou "Le bouton ne réagit pas au clic"). C'est la **preuve matérielle** qui s'oppose à la "volatilité" de la mémoire humaine.

• **Le "Status" (✅ PASS / ❌ FAIL) :** Ce n'est pas une évaluation subjective, mais le résultat d'une comparaison logique : si **Actual** est strictement identique à **Expected** (défini par votre Definition of Done), alors le statut est PASS.

• **Utilité technique :** Cette section garantit que chaque incrément est **testable et observable**, l'un des critères de stabilité de la méthode.

2. ==Le "Journal des Erreurs" (Log)==

Cette section, présente dans `progress.md` (pour la session) et `task_plan.md` (pour le projet), applique le **Principe n°5 de Manus : "Keep the wrong stuff in"** (Conserver les erreurs).

• **Pourquoi consigner l'échec ?** Documenter les erreurs avec leurs traces (stack traces, messages) permet de mettre à jour vos "croyances" sur le système et d'éviter la répétition cyclique des mêmes fautes.

• **La colonne "Attempt" (Tentative) :** Elle est essentielle pour le **Protocole d'Erreur "3-Strike"**. Si vous consignez "Tentative 1" et qu'elle échoue, la règle impose que l'action suivante soit **différente** de la précédente.

• **Lien avec la planification :** Une erreur consignée dans le log est ce qui force "la mémoire à corriger la planification" : si une erreur est bloquante, vous devez muter votre approche directement dans le `task_plan.md`.

3. Synthèse de l'enjeu opérationnel

L'enjeu n'est pas seulement de noter ce qui se passe, mais de créer une **boucle de rétroaction fermée**.

• **Le succès** est validé lorsque toutes les phases du `task_plan.md` sont marquées comme `complete` et que tous les tests dans `progress.md` affichent un statut `PASS`.

• **La signature (Sign)** ne devrait intervenir que lorsque la colonne **Actual** de vos tests prouve que le livrable final (Fd​) est conforme au contrat initial (C).

En résumé, si vous ne remplissez pas la colonne **Actual**, vous travaillez à l'aveugle. Si vous ne remplissez pas le **Journal des Erreurs**, vous condamnez votre futur "moi" (ou votre futur agent IA) à redécouvrir douloureusement des problèmes déjà rencontrés.

Pour visualiser cela, imaginez un **scientifique dans son laboratoire** : le plan est son protocole, les _Findings_ sont ses observations, mais le tableau des tests avec la colonne **Actual** est son **compte-rendu d'expérience**. Sans cette colonne, il n'a pas fait de science, il a seulement pris des notes ; il ne peut pas prouver que son résultat est reproductible ou vrai.
