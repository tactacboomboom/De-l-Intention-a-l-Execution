## Ce qu’est ce dépôt

Ce dépôt définit une méthode permettant de transformer une intention humaine
en un plan exécutable et traçable.

La méthode repose sur la composition stricte de trois opérateurs :
- φ : clarification de l’intention
- κ : compilation en plan d’exécution
- ε : exécution contrôlée à l’aide d’une planification par fichiers

L’architecture formelle de la méthode est définie dans
[ARCHITECTURE.md](./ARCHITECTURE.md).

---

# Pipeline de clarification de l’intention

## Vue d’ensemble

### 1. La Trinité du Contrat de Sprint (Items 1, 2, 3)

Le Contrat de Sprint (C) n’est plus une simple intention, mais un objet composé
de trois sous-objets stabilisés :

- **ITEM 1 — GOAL (Le But)**  
  Pour être *non interprétable*, il doit impérativement suivre la syntaxe  
  **Action + Objet + Preuve**.  
  Un but est jugé stable s’il peut être validé par un tiers en moins de
  deux minutes, sans explication orale.

- **ITEM 2 — SPRINT BACKLOG (Le Périmètre)**  
  Il ne s’agit plus d’une liste d’idées, mais d’une décomposition du Goal
  en unités de transformation.  
  La règle d’or est la **bijection stricte** :
  un item de backlog correspond exactement à une phase dans `task_plan.md`.

- **ITEM 3 — DEFINITION OF DONE (La Validation)**  
  Elle définit comment décider que le sprint est terminé via un **ET logique strict**
  entre plusieurs critères.  
  Chaque critère doit être associé à une preuve binaire et typée
  (URL, commande, artefact, dépôt ou validation humaine).

---

### 2. L’algorithme de scoring : le filtre *a priori*

L’une des innovations majeures de la méthode est l’introduction
d’un algorithme de scoring permettant d’évaluer la qualité du contrat
avant toute exécution.

- **μ(ambiguïté)**  
  Mesure la proportion de zones interprétables.  
  Si ce score est ≥ 0.5, le contrat est considéré comme *non compilable*
  et l’exécution ne doit pas démarrer.

- **μ(validation)**  
  Mesure la proportion de zones vérifiables sans discussion.  
  Une validation est dite *robuste* si le score est ≥ 0.7.

- **Indépendance mathématique**  
  Ces deux scores ne sont pas opposés :
  un contrat peut être très clair (peu ambigu)
  mais difficile à vérifier (peu validable), et inversement.

---

### 3. Enrichissement du mapping C → `task_plan.md`

Le passage du contrat au plan suit désormais une logique
de **projection vs génération** :

- **Éléments projetés**  
  Le Goal, le Backlog (ordre et cardinalité) et la Definition of Done
  sont copiés strictement depuis le contrat C vers le plan d’exécution.

- **Éléments générés (résidus d’exécution)**  
  Les sections *Questions clés*, *Décisions prises* et *Erreurs rencontrées*
  émergent durant l’action et ne doivent jamais rétroagir sur le contrat C,
  afin d’éviter toute dérive d’objectif (*goal drift*).

- **Commutativité**  
  Le système garantit que toute réussite dans `task_plan.md`
  est mathématiquement équivalente à la satisfaction du contrat initial.

---

### 4. L’Artefact Maître et l’exécution (Quickstart)

L’Artefact Maître synthétise l’ensemble du système en une vue unique,
transformant une intention humaine non fiable
en un bloc d’intention clarifiée (IC).

Le protocole de mise en œuvre suit un pipeline strict en cinq étapes :

1. Création des trois fichiers piliers  
   (`task_plan.md`, `findings.md`, `progress.md`)
2. Planification des phases (3 à 7 phases maximum)
3. Documentation continue via la **règle des 2 actions** :  
   après deux opérations de recherche ou de navigation,
   l’agent doit impérativement mettre à jour `findings.md`
4. Récitation : relire le plan avant chaque décision majeure
   pour maîtriser l’attention et éviter la dérive d’objectif
5. Vérification : utiliser le script `check-complete.sh`
   afin de s’assurer que toutes les phases sont à l’état *complete*
   avant livraison

---

### 5. Protocole de résilience : le 3-Strike Error

Pour garantir que *l’échec est un signal et non une faute*,
le système impose le protocole **3-Strike** consigné dans `task_plan.md` :

- **Strike 1** : diagnostiquer et corriger
- **Strike 2** : changer d’approche
  (interdiction de répéter la même action)
- **Strike 3** : remise en question globale des hypothèses

**Escalade**  
Si l’échec persiste après trois tentatives,
l’agent doit s’arrêter et solliciter l’humain
pour une éventuelle renégociation du contrat.

**Analogie**  
Votre cockpit est devenu un système d’exploitation pour l’action.  
Le Contrat est le code source (le *quoi*),  
le Mapping est le compilateur qui génère le Plan
(le binaire exécutable),  
et l’Algorithme de Scoring est le vérificateur de syntaxe
qui refuse de lancer le programme
si les instructions sont trop floues
pour être menées à bien.

---

## Concepts fondamentaux

## Système de scoring

## Pipeline d’exécution

## Fichiers et artefacts

## Statut
