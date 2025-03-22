---
id: <% "SPEC-" + tp.date.now("YYMMDD") + "-" + tp.file.title.slice(-3) %>
title: <% tp.file.title %>
type: specification
status: brouillon
version: 0.1
date_creation: <% tp.date.now("YYYY-MM-DD") %>
date_modification: <% tp.date.now("YYYY-MM-DD") %>
auteur: <% tp.user.name %>
modules:
  - <% "module-principal" %>
implements:
  - <% "REQ-XXX" %>
implemented_by: []
tags:
  - #spec
  - #<% "module-principal" %>
---

# Spécification: <% tp.file.title %>

## Résumé
<!-- Description concise de la fonctionnalité -->

## Contexte
<!-- Contexte et motivations -->

## Exigences fonctionnelles
1. **Exigence 1**
   - Description détaillée
   - Critères d'acceptation

2. **Exigence 2**
   - Description détaillée
   - Critères d'acceptation

## Interface utilisateur
<!-- Description des interfaces utilisateur si applicable -->

## Modèle de données
<!-- Description des entités et relations de données -->

## Contraintes et limitations
<!-- Contraintes techniques, légales ou business -->

## Dépendances
<!-- Dépendances avec d'autres modules ou systèmes -->
- [[3-Specifications-fonctionnelles/module-<% "autre-module" %>]]

## Comportements attendus
<!-- Description des comportements attendus du système -->

## Cas particuliers et exceptions
<!-- Gestion des cas limites et exceptions -->

## Critères d'acceptation
<!-- Critères objectifs pour valider l'implémentation -->

## Plans d'implémentation
<!-- Liens vers les plans d'implémentation -->

## Documentation associée
<!-- Références à d'autres documents pertinents -->
- [[2-Architecture-systeme/<% "document-pertinent" %>]] 