---
id: PROMPT-<% tp.file.title.split("-")[2] %>
title: <% tp.file.title %>
type: prompt
plan_source: <% "PLN-" + tp.file.title.split("-")[2] %>
status: en_cours
date_creation: <% tp.date.now("YYYY-MM-DD") %>
utilisation: 
  - <% tp.date.now("YYYY-MM-DD") %>: Implémentation initiale
fichiers_cibles:
  - src/
tags:
  - #prompt
---

# Prompt: <% tp.file.title %>

## Contexte du projet
Ce prompt fait partie du projet EDT_Temple et se rapporte au plan d'implémentation [[4-Plan-technique/plan-d-implementation/plan-feature-<% tp.file.title.split("-")[2] %>|Plan <% tp.file.title.split("-")[2] %>]].

## Objectif
<!-- Description de l'objectif -->

## Contexte technique
<!-- Résumé du contexte technique -->

## Fonctionnalités à implémenter
1. 
2. 
3. 

## Spécifications à respecter
<!-- Liens vers les spécifications pertinentes -->
- [[3-Specifications-fonctionnelles/module-<% "nom-module" %>]]

## Architecture existante
<!-- Description de l'architecture existante -->

## Fichiers à modifier
- `src/...`
- `src/...`

## Considérations particulières
<!-- Points d'attention -->

## Références documentaires
- [[<% "Lien vers document pertinent 1" %>]]
- [[<% "Lien vers document pertinent 2" %>]] 