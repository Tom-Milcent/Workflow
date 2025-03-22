---
id: <% "RAPPORT-" + tp.file.title.split("-")[2] %>
title: <% tp.file.title %>
type: rapport
status: complété
date_creation: <% tp.date.now("YYYY-MM-DD") %>
fonctionnalité: <% "PLN-" + tp.file.title.split("-")[2] %>
plan_source: [[4-Plan-technique/plan-d-implementation/plan-feature-<% tp.file.title.split("-")[2] %>]]
prompt_utilisé: [[prompts/implementation-<% tp.file.title.split("-")[2] %>.md]]
commits:
  - hash: ""
    message: ""
fichiers_modifiés:
  - src/path/to/file.py
tags:
  - #rapport
  - #implementation
---

# Rapport d'implémentation: <% tp.file.title %>

## Fonctionnalité implémentée
Cette implémentation correspond au plan:
[[4-Plan-technique/plan-d-implementation/plan-feature-<% tp.file.title.split("-")[2] %>|Plan <% tp.file.title.split("-")[2] %>]]

## Approche d'implémentation
<!-- Description détaillée de l'approche adoptée -->

## Fichiers modifiés
- `src/...`: Description des changements
- `src/...`: Description des changements

## Écarts par rapport au plan
<!-- Documentez ici les différences entre l'implémentation et le plan -->

## Difficultés rencontrées et solutions
- **Problème 1**: Solution adoptée...
- **Problème 2**: Solution adoptée...

## Tests effectués
<!-- Description des tests -->

## Prochaines étapes
<!-- Améliorations futures -->

## Mise à jour du registre
La fonctionnalité a été marquée comme [[8-Suivi-Implementation/registre-fonctionnalites#<% "PLN-" + tp.file.title.split("-")[2] %>|implémentée]] dans le registre.

## Impact sur la documentation
<!-- Mise à jour nécessaire dans d'autres documents -->
- Document 1: Modification requise...
- Document 2: Modification requise...

## Retour d'expérience
<!-- Leçons apprises lors de l'implémentation -->
