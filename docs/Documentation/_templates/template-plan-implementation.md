---
id: <% "PLN-" + tp.file.title.split("-")[2] %>
title: <% tp.file.title %>
type: plan
status: planifié
version: 1.0
date_creation: <% tp.date.now("YYYY-MM-DD") %>
date_modification: <% tp.date.now("YYYY-MM-DD") %>
auteur: <% tp.user.name %>
module: <% "nom-module" %>
implements: <% "SPEC-XXX" %>
implemented_by: []
prompt_template: prompts/implementation-<% tp.file.title.split("-")[2] %>.md
rapport: 8-Suivi-Implementation/rapports/rapport-feature-<% tp.file.title.split("-")[2] %>.md
tags:
  - #plan
---

# Plan d'implémentation: <% tp.file.title %>

## Résumé
<!-- Résumé de la fonctionnalité -->

## Spécifications implémentées
Ce plan implémente les spécifications:
- [[3-Specifications-fonctionnelles/module-<% "nom-module" %>#<% "Section" %>]]

## Approche technique
<!-- Description de l'approche technique -->

## Découpage en tâches
1. **Tâche 1**
   - Détails
   - Fichiers: `src/...`

2. **Tâche 2**
   - Détails
   - Fichiers: `src/...`

## Dépendances
<!-- Liste des dépendances techniques -->
- [[6-Referentiels-contextuels/bibliotheques-externes#<% "Bibliothèque" %>]]

## Risques et mitigations
| Risque | Impact | Probabilité | Mitigation |
|--------|--------|-------------|------------|
| Risque 1 | Élevé | Moyen | Stratégie... |

## Prompt pour Cursor
Le prompt détaillé pour l'implémentation sera généré dans:
[[prompts/implementation-<% tp.file.title.split("-")[2] %>.md]]

## Rapport d'implémentation
Le rapport d'implémentation sera documenté dans:
[[8-Suivi-Implementation/rapports/rapport-feature-<% tp.file.title.split("-")[2] %>.md]]

## Traçabilité
<!-- Liens bidirectionnels pour la traçabilité -->
- **Implémente**: [[3-Specifications-fonctionnelles/module-<% "nom-module" %>]]
- **Utilisé par**: <!-- À compléter lors de l'utilisation -->

## Décisions techniques
<!-- Documentation des décisions techniques importantes -->
1. Décision 1: Justification...
2. Décision 2: Justification... 