---
id: WORKFLOW-01
title: Workflow Cursor-Obsidian
type: methodologie
version: 1.0
date_creation: 2024-03-22
date_modification: 2024-03-22
auteur: Thomas
tags:
  - #methodologie
  - #cursor
  - #obsidian
  - #workflow
---

# Workflow Cursor-Obsidian

Ce document décrit la méthodologie d'interconnexion entre la documentation dans Obsidian et l'implémentation dans Cursor AI.

## Principes fondamentaux

Notre workflow repose sur quatre piliers essentiels :

1. **Graphe de connaissances bidirectionnel**
   - Documentation interconnectée avec liens bidirectionnels
   - Navigation fluide entre spécifications, plans et implémentation
   - Structure permettant à Cursor de comprendre le contexte global

2. **Documentation structurée et normalisée**
   - Frontmatter YAML standardisé pour tous les documents
   - Classification hiérarchique via tags et propriétés
   - Relations explicites entre documents

3. **Points d'entrée stratégiques**
   - Documents d'index comme portails principaux
   - Maps of Content (MOCs) pour les concepts transversaux
   - Tableau de bord spécifique pour Cursor

4. **Traçabilité complète**
   - Lien explicite entre spécifications et implémentation
   - Documentation des décisions techniques
   - Rapports d'implémentation liés aux plans

## Flux de travail

### 1. Phase de spécification

1. **Rédiger la spécification fonctionnelle**
   - Utiliser le template standard avec frontmatter complet
   - Créer dans `3-Specifications-fonctionnelles/module-[nom].md`
   - Ajouter aux index pertinents

2. **Créer le plan d'implémentation**
   - Dériver du template avec références à la spécification
   - Placer dans `4-Plan-technique/plan-d-implementation/plan-feature-XXX.md`
   - Lier bidirectionnellement à la spécification

### 2. Phase de préparation pour Cursor

1. **Créer le prompt d'implémentation**
   - Utiliser le template de prompt Cursor
   - Placer dans `prompts/implementation-feature-XXX.md`
   - Inclure des références précises aux documents pertinents

2. **Consulter le contexte documentaire**
   - Explorer les dépendances techniques via les liens
   - Vérifier les standards de codage applicables
   - Analyser les implémentations similaires existantes

### 3. Phase d'implémentation avec Cursor

1. **Ouvrir Cursor avec le contexte approprié**
   - Utiliser le prompt préparé comme base
   - Référencer le tableau de bord Cursor pour orientation
   - Partager les liens vers les documents clés

2. **Développer avec guidance documentaire**
   - Suivre les directives du plan d'implémentation
   - Respecter les conventions identifiées
   - Documenter les décisions d'implémentation

### 4. Phase de documentation post-implémentation

1. **Créer le rapport d'implémentation**
   - Documenter dans `8-Suivi-Implementation/rapports/rapport-feature-XXX.md`
   - Inclure références au code implémenté
   - Noter les écarts par rapport au plan initial

2. **Mettre à jour le registre de fonctionnalités**
   - Actualiser dans `8-Suivi-Implementation/registre-fonctionnalites.md`
   - Utiliser la syntaxe Dataview pour maintenir le tableau

3. **Mettre à jour les indices et MOCs**
   - S'assurer que les nouveaux documents sont référencés
   - Maintenir la cohérence du graphe de connaissances

## Structure de prompt optimisée pour Cursor

Pour maximiser l'efficacité avec Cursor, structurez vos prompts ainsi :

```markdown
# Analyse de la documentation EDT_Temple: [FEATURE-XXX]

## Documents à consulter en priorité
- [[3-Specifications-fonctionnelles/module-[nom].md]]
- [[4-Plan-technique/plan-d-implementation/plan-feature-XXX.md]]
- [[5-Implementation/notes-techniques/approche-specifique.md]]

## Objectif de l'implémentation
[Description claire et concise]

## Contexte architectural
[Référence aux composants existants]

## Limitations et contraintes techniques
[Liste des contraintes importantes]

## Structure des fichiers à modifier
```src
src/
  module/
    fichier1.py  # À modifier pour implémenter A
    fichier2.py  # À créer pour implémenter B
```

## Format de rapport attendu
[Description du format de rapport souhaité]
```

## Conventions pour Cursor

Utilisez ces commentaires spéciaux dans vos fichiers source pour communication avec Cursor :

- `// CURSOR: Commentaire pour Cursor`
- `// TODO: Action à effectuer`
- `// NOTE: Information importante`
- `// WARNING: Point d'attention`
- `// REFERENCE: Lien vers la documentation [[path/to/doc.md]]`

## Plugins Obsidian essentiels

Pour maintenir ce workflow, ces plugins sont nécessaires :

1. **Dataview** - Pour les tableaux de bord dynamiques
2. **Templater** - Pour templates avancés avec insertion automatique
3. **Obsidian Git** - Pour synchronisation avec repository
4. **QuickAdd** - Pour création rapide de notes interconnectées
5. **Dynamic Table of Contents** - Pour navigation intra-document

## Maintenance du système documentaire

- Effectuer des revues régulières des liens et de la cohérence
- Standardiser progressivement les documents existants
- Former tous les contributeurs aux conventions documentaires
- Recueillir le feedback sur l'efficacité du workflow

---

Pour toute question sur ce workflow, contacter l'équipe documentation ou consulter le [[9-Methodologie/guide-documentation|Guide de documentation]].
