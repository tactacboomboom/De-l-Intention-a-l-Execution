# Intent Clarification Pipeline
## Overview

1. La Trinité du Contrat de Sprint (Items 1, 2, 3)
Le Contrat de Sprint (C) n'est plus une simple intention, mais un objet composé de trois sous-objets stabilisés :
• ITEM 1 — GOAL (Le But) : Pour être "non-interprétable", il doit impérativement suivre la syntaxe Action + Objet + Preuve. Un but est jugé stable s'il peut être validé par un tiers en moins de 2 minutes sans explication orale.
• ITEM 2 — SPRINT BACKLOG (Le Périmètre) : Il ne s'agit plus d'une liste d'idées, mais d'une décomposition du Goal en unités de transformation. La règle d'or est la bijection stricte : un item de backlog équivaut exactement à une phase dans task_plan.md.
• ITEM 3 — DEFINITION OF DONE (La Validation) : Elle définit comment décider que c'est fini via un ET logique strict entre plusieurs critères. Chaque critère doit être associé à une preuve binaire et typée (URL, Commande, Artefact, Repo ou Humain).
2. L'Algorithme de Scoring : Le Filtre a Priori
L'une des innovations majeures de vos sources est l'introduction d'un algorithme de scoring permettant d'évaluer la qualité du contrat avant toute exécution.
• μ(ambigu 
ı
¨
 t 
e
ˊ
 ) : Mesure la proportion de zones interprétables. Si ce score est ≥0.5, le contrat est considéré comme "non compilable" et l'exécution ne doit pas démarrer.
• μ(validation) : Mesure la proportion de zones vérifiables sans discussion. Une validation est dite "robuste" si le score est ≥0.7.
• Indépendance mathématique : Ces deux scores ne sont pas opposés ; un contrat peut être très clair (peu ambigu) mais très difficile à vérifier (peu validable).
3. Enrichissement du Mapping C→task_plan.md
Le passage du contrat au plan (f 
2
​
 ) suit désormais une logique de projection vs génération :
• Éléments Projetés : Le Goal, le Backlog (ordre et cardinalité) et la DoD sont copiés strictement depuis C vers F 
p
​
 .
• Éléments Générés (Résidus d'exécution) : Les sections Key Questions, Decisions Made et Errors Encountered naissent durant l'action et ne doivent jamais rétroagir sur le contrat C pour éviter la dérive.
• Commutativité : Le système garantit que toute réussite dans task_plan.md est mathématiquement équivalente à la satisfaction du contrat initial.
4. L'Artefact Maître et l'Exécution (Quickstart)
L'Artefact Maître synthétise l'ensemble du système en une vue unique, transformant l'intention humaine non fiable en un bloc d'intention clarifiée (IC).
Le protocole de mise en œuvre suit un pipeline strict en 5 étapes (Quickstart) :
1. Création des trois fichiers piliers (task_plan.md, findings.md, progress.md).
2. Planification des phases (3 à 7 phases maximum).
3. Documentation continue via la Règle des 2 Actions : après deux opérations de recherche ou de navigation, l'agent doit impérativement mettre à jour findings.md.
4. Récitation : Relire le plan avant chaque décision majeure pour manipuler l'attention et éviter le "goal drift".
5. Vérification : Utiliser le script check-complete.sh pour s'assurer que toutes les phases sont à l'état complete avant de livrer.
5. Protocole de Résilience : Le 3-Strike Error
Pour garantir que "l'échec est un signal et non une faute", le système impose le Protocole 3-Strike consigné dans task_plan.md :
• Strike 1 : Diagnostiquer et fixer.
• Strike 2 : Changer d'approche (interdiction de répéter la même action).
• Strike 3 : Remise en question globale des hypothèses.
• Escalade : Si l'échec persiste après trois tentatives, l'agent doit s'arrêter et solliciter l'humain pour une éventuelle renégociation du contrat.
Analogie : Votre cockpit est devenu un système d'exploitation pour l'action. Le Contrat est le code source (le "quoi"), le Mapping est le compilateur qui génère le Plan (le binaire exécutable), et l'Algorithme de Scoring est le vérificateur de syntaxe qui refuse de lancer le programme si les instructions sont trop floues pour être menées à bien.

## Core Concepts
## Scoring System
## Execution Pipeline
## Files & Artifacts
## Status
