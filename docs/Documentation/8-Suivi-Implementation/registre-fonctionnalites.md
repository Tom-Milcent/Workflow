---
id: REGISTRE-FONC
title: Registre des fonctionnalités
type: registre
version: 1.0
date_creation: 2024-03-22
date_modification: 2024-03-22
auteur: Thomas
tags:
  - #registre
  - #implementation
  - #suivi
---

# Registre des fonctionnalités

Ce document sert de registre centralisé pour toutes les fonctionnalités planifiées, en cours et implémentées du projet EDT_Temple.

## Vue d'ensemble

```dataview
TABLE
    status as "Statut",
    count(status) as "Nombre"
FROM #plan
GROUP BY status
SORT length(rows) DESC
```

## Fonctionnalités planifiées

```dataview
TABLE
    id as "ID",
    title as "Fonctionnalité",
    module as "Module",
    implements as "Spécification",
    date_creation as "Date création"
FROM #plan
WHERE status = "planifié"
SORT date_creation DESC
```

## Fonctionnalités en cours d'implémentation

```dataview
TABLE
    id as "ID",
    title as "Fonctionnalité",
    module as "Module",
    implements as "Spécification",
    date_modification as "Dernière mise à jour"
FROM #plan
WHERE status = "en_cours"
SORT date_modification DESC
```

## Fonctionnalités implémentées

```dataview
TABLE
    id as "ID",
    title as "Fonctionnalité",
    date_modification as "Date complétion",
    rapport as "Rapport"
FROM #plan
WHERE status = "complété"
SORT date_modification DESC
```

## Détails des fonctionnalités par module

### Module Planification

```dataview
TABLE
    id as "ID",
    title as "Fonctionnalité",
    status as "Statut",
    implements as "Spécification",
    rapport as "Rapport"
FROM #plan
WHERE module = "planification"
SORT id ASC
```

### Module Solver

```dataview
TABLE
    id as "ID",
    title as "Fonctionnalité",
    status as "Statut",
    implements as "Spécification",
    rapport as "Rapport"
FROM #plan
WHERE module = "solver"
SORT id ASC
```

### Module Interface

```dataview
TABLE
    id as "ID",
    title as "Fonctionnalité",
    status as "Statut",
    implements as "Spécification",
    rapport as "Rapport"
FROM #plan
WHERE module = "interface"
SORT id ASC
```

## Traçabilité complète

```dataview
TABLE
    id as "ID",
    type as "Type",
    status as "Statut",
    implements as "Implémente",
    implemented_by as "Implémenté par"
FROM #plan OR #spec
SORT type ASC, id ASC
```

## Fonctionnalités à risque

```dataview
TABLE
    id as "ID",
    title as "Fonctionnalité",
    status as "Statut"
FROM #plan
WHERE contains(file.content, "Risque: Élevé") OR contains(file.content, "Impact: Élevé")
SORT id ASC
```

## Notes importantes

- Les liens dans les colonnes "Spécification" et "Rapport" permettent d'accéder directement aux documents correspondants
- Le statut "bloqué" indique un problème nécessitant une résolution avant de pouvoir continuer
- Les fonctionnalités marquées comme "à risque" ont des risques élevés documentés dans leur plan d'implémentation
