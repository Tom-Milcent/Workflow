---
id: GUIDE-DOC
title: Guide de documentation EDT_Temple
type: guide
version: 1.0
date_creation: 2024-03-22
date_modification: 2024-03-22
auteur: Thomas
tags:
  - #guide
  - #documentation
  - #methodologie
---

# Guide de documentation EDT_Temple

Ce guide établit les conventions et standards à suivre pour toute la documentation du projet EDT_Temple.

## Principes fondamentaux

1. **Cohérence terminologique**
   - Utiliser le vocabulaire défini dans le glossaire du projet
   - Maintenir une terminologie cohérente entre tous les documents

2. **Structure standardisée**
   - Chaque document doit avoir un frontmatter YAML complet
   - Suivre les templates définis pour chaque type de document
   - Maintenir une hiérarchie de titres logique (H1 → H2 → H3)

3. **Interconnexion documentaire**
   - Toujours créer des liens bidirectionnels entre documents connexes
   - Inclure des références explicites aux documents source/cible
   - Utiliser la notation wiki pour les liens `[[chemin/vers/document|Texte affiché]]`

4. **Identifiants uniques**
   - Chaque document doit avoir un identifiant unique dans son frontmatter
   - Format des IDs par type de document:
     - Spécifications: `SPEC-YYMMDD-XXX`
     - Plans: `PLN-XXX`
     - Rapports: `RAPPORT-XXX`
     - Prompts: `PROMPT-XXX`

## Structure YAML frontmatter

### Structure commune à tous les documents
```yaml
---
id: ID-UNIQUE                     # Identifiant unique du document
title: Titre du document          # Titre complet
type: specification|plan|rapport  # Type de document
version: 1.0                      # Version (incrémentée lors de changements majeurs)
date_creation: YYYY-MM-DD         # Date de création initiale
date_modification: YYYY-MM-DD     # Date de dernière modification
auteur: Prénom Nom                # Auteur principal
tags:                             # Liste de tags pour la recherche et le filtrage
  - #tag1
  - #tag2
---
```

### Propriétés spécifiques aux spécifications
```yaml
modules:                          # Liste des modules concernés
  - module1
  - module2
implements:                       # Exigences implémentées
  - REQ-001
  - REQ-002
implemented_by:                   # Plans d'implémentation qui réalisent cette spec
  - PLN-001
  - PLN-002
```

### Propriétés spécifiques aux plans d'implémentation
```yaml
module: nom-module                # Module principal
implements: SPEC-001              # Spécification implémentée
implemented_by: []                # Fichiers de code qui implémentent ce plan
prompt_template: prompts/...      # Chemin vers le prompt Cursor
rapport: 8-Suivi-Implementation/... # Chemin vers le rapport d'implémentation
```

### Propriétés spécifiques aux prompts
```yaml
plan_source: PLN-001              # Plan d'implémentation source
fichiers_cibles:                  # Fichiers cibles pour l'implémentation
  - src/fichier1.py
utilisation:                      # Historique d'utilisation du prompt
  - 2024-03-22: Implémentation initiale
```

### Propriétés spécifiques aux rapports
```yaml
fonctionnalité: PLN-001           # Fonctionnalité implémentée
plan_source: chemin/vers/plan     # Plan source
prompt_utilisé: chemin/vers/prompt # Prompt utilisé
commits:                          # Liste des commits associés
  - hash: abc123
    message: "Description du commit"
fichiers_modifiés:                # Fichiers modifiés lors de l'implémentation
  - src/fichier1.py
```

## Structure de dossiers

```
Documentation/
├── 1-Vision-et-charte/           # Vision et objectifs du projet
├── 2-Architecture-systeme/       # Architecture globale
├── 3-Specifications-fonctionnelles/ # Spécifications fonctionnelles par module
├── 4-Plan-technique/             # Plans d'implémentation techniques
│   └── plan-d-implementation/    # Plans détaillés par fonctionnalité
├── 5-Implementation/             # Documentation technique d'implémentation
│   ├── guides/                   # Guides de développement
│   └── notes-techniques/         # Notes techniques détaillées
├── 6-Referentiels-contextuels/   # Références et contexte technique
├── 7-Criteres-acceptation/       # Critères et cas de test
├── 8-Suivi-Implementation/       # Suivi d'implémentation et rapports
│   └── rapports/                 # Rapports d'implémentation par fonctionnalité
├── 9-Methodologie/               # Méthodologie et processus
├── _assets/                      # Images et ressources
├── _templates/                   # Templates pour chaque type de document
├── prompts/                      # Prompts pour Cursor
├── moc-*.md                      # Maps of Content (MOCs)
├── cursor-dashboard.md           # Tableau de bord pour Cursor
└── index.md                      # Index global du projet
```

## Conventions de nommage

### Noms de fichiers
- Utiliser des noms en minuscules
- Séparer les mots par des tirets (`-`)
- Inclure les identifiants numériques dans les noms lorsque pertinent
- Exemples:
  - `module-planification.md`
  - `plan-feature-007.md`
  - `rapport-implementation-007.md`

### Tags
- Commencer les tags par `#`
- Utiliser des tags pour catégoriser les documents
- Tags standards:
  - `#spec`: Spécifications
  - `#plan`: Plans d'implémentation
  - `#rapport`: Rapports d'implémentation
  - `#prompt`: Prompts Cursor
  - `#moc`: Maps of Content
  - Modules: `#planification`, `#solver`, `#interface`...
  - Statuts: `#en_cours`, `#complété`, `#bloqué`...

## Création de liens

### Liens internes
- Toujours utiliser la notation wiki: `[[chemin/vers/fichier|Texte affiché]]`
- Pour les sections spécifiques: `[[chemin/vers/fichier#section|Texte affiché]]`
- Exemple: `[[3-Specifications-fonctionnelles/module-planification#Interface|Interface de planification]]`

### Liens vers le code
- Référencer les fichiers de code source avec des liens internes commentés
- Format: `src/path/to/file.py - Description de ce que fait ce fichier`

### Références bidirectionnelles
- Toujours créer des liens dans les deux sens:
  1. Du document source vers le document cible
  2. Du document cible vers le document source
- Utiliser les sections "Références" ou "Voir aussi" pour regrouper les liens connexes

## Utilisation de Dataview

### Requêtes standards
- Utiliser la syntaxe Dataview pour créer des vues dynamiques
- Exemples de requêtes:
  ```dataview
  TABLE
      id as "ID",
      status as "Statut"
  FROM #plan
  WHERE module = "planification"
  SORT id ASC
  ```

### Formats de tableaux de bord
- Créer des tableaux de bord avec des requêtes Dataview
- Utiliser des requêtes pour:
  - Lister les documents par type
  - Afficher l'état d'avancement
  - Montrer les relations entre documents

## Workflow de documentation

### Création de nouveaux documents
1. Utiliser les templates appropriés
2. Remplir complètement le frontmatter YAML
3. Ajouter les liens bidirectionnels vers les documents connexes
4. Mettre à jour les index et MOCs pertinents

### Mise à jour de documents existants
1. Mettre à jour la date de modification
2. Incrémenter la version si nécessaire
3. Maintenir les liens bidirectionnels
4. S'assurer que les tableaux de bord sont à jour

## Conventions pour l'IA (Cursor)

Pour faciliter l'analyse par Cursor, suivre ces conventions dans tous les documents:

1. **Commentaires spécifiques pour l'IA**
   - `// CURSOR: Information spécifique pour Cursor`
   - `// NOTE: Information contextuelle importante`
   - `// WARNING: Point d'attention critique`

2. **Structure des prompts**
   - Utiliser le template de prompt défini
   - Inclure des liens explicites vers la documentation pertinente
   - Fournir un contexte complet

3. **Conventions de commentaires dans le code**
   - Ajouter des références vers la documentation:
     `// REFERENCE: [[chemin/vers/document.md]]`
   - Inclure le contexte des décisions d'implémentation

---

Ce guide doit être suivi pour tous les documents du projet. Pour toute question ou suggestion d'amélioration, contacter l'équipe de documentation. 