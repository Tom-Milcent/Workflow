---
id: MOC-PLAN
title: Map of Content - Planification
type: moc
version: 1.0
date_creation: 2024-03-22
date_modification: 2024-03-22
auteur: Thomas
tags:
  - #moc
  - #planification
  - #navigation
---

# Map of Content: Planification

Cette Map of Content rassemble tous les documents liés au module de planification du projet EDT_Temple.

## Vue d'ensemble du module

Le module de planification est le cœur du système EDT_Temple. Il est responsable de :
- Générer des plannings optimisés selon les contraintes
- Proposer des relaxations de contraintes en cas d'impossibilité
- Permettre l'édition manuelle et la validation des plannings

## Documents conceptuels

- [[2-Architecture-systeme/architecture-module-planification|Architecture du module de planification]]
- [[3-Specifications-fonctionnelles/module-planification|Spécifications du module de planification]]

## Spécifications détaillées

### Contraintes et préférences
- [[3-Specifications-fonctionnelles/contraintes-planification|Contraintes de planification]]
- [[3-Specifications-fonctionnelles/preferences-utilisateurs|Préférences utilisateurs]]

### Algorithmes et approches
- [[3-Specifications-fonctionnelles/algorithme-planification|Algorithme de planification]]
- [[3-Specifications-fonctionnelles/relaxation-contraintes|Relaxation de contraintes]]

## Plans d'implémentation

```dataview
TABLE
    id as "ID",
    title as "Plan",
    status as "Statut",
    implements as "Implémente"
FROM #plan
WHERE module = "planification"
SORT id ASC
```

## Documentation technique

- [[5-Implementation/notes-techniques/approche-relaxation-contraintes|Approche de relaxation des contraintes]]
- [[5-Implementation/notes-techniques/optimisation-performances-solver|Optimisation des performances du solveur]]
- [[5-Implementation/guides/guide-developpement-planification|Guide de développement - Planification]]

## Prompts Cursor

```dataview
TABLE
    id as "ID",
    plan_source as "Plan source",
    date_creation as "Date création"
FROM #prompt
WHERE contains(file.content, "planification")
SORT date_creation DESC
```

## Rapports d'implémentation

```dataview
TABLE
    id as "ID",
    fonctionnalité as "Fonctionnalité",
    date_creation as "Date"
FROM #rapport
WHERE contains(fonctionnalité, "PLN-")
SORT date_creation DESC
```

## Bibliothèques et dépendances

- [[6-Referentiels-contextuels/bibliotheques-externes#PuLP|PuLP - Solveur de programmation linéaire]]
- [[6-Referentiels-contextuels/bibliotheques-externes#OR-Tools|OR-Tools - Bibliothèque d'optimisation]]

## Critères d'acceptation

- [[7-Criteres-acceptation/cas-test-planification|Cas de test - Planification]]
- [[7-Criteres-acceptation/metriques-qualite-planning|Métriques de qualité des plannings]]

## Références connexes

- [[moc-solver|MOC - Solver]]
- [[moc-interface|MOC - Interface]]

---

**Note**: Cette MOC est mise à jour régulièrement pour refléter l'état actuel de la documentation sur la planification. 