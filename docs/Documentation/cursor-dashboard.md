# Tableau de bord projet EDT_Temple pour Cursor

## Guide de navigation pour Cursor AI

Ce document est conçu pour vous aider à naviguer efficacement dans la base de connaissances du projet EDT_Temple.

## 🔍 Points d'entrée principaux

- [[index|Index global du projet]]
- [[1-Vision-et-charte/objectifs-du-projet|Objectifs du projet]]
- [[2-Architecture-systeme/vue-generale|Vue générale de l'architecture]]
- [[8-Suivi-Implementation/registre-fonctionnalites|Registre des fonctionnalités]]

## 📚 Structure de la documentation

- **Documents conceptuels**: `1-Vision-et-charte/` et `2-Architecture-systeme/`
- **Spécifications**: `3-Specifications-fonctionnelles/`
- **Plans d'implémentation**: `4-Plan-technique/plan-d-implementation/`
- **Documentation technique**: `5-Implementation/`
- **Référentiels et dépendances**: `6-Referentiels-contextuels/`
- **Tests et acceptance**: `7-Criteres-acceptation/`
- **Suivi et rapports**: `8-Suivi-Implementation/`

## 🧩 Modules principaux

```dataview
TABLE
    module as "Module",
    implements as "Implémente spécifications",
    tags as "Tags"
FROM #plan
GROUP BY module
```

## 📈 État d'avancement

```dataview
TABLE
    length(rows) as "Nombre"
FROM #plan
GROUP BY status
```

## 🛠️ Fonctionnalités récentes

```dataview
TABLE
    id as "ID",
    title as "Titre",
    status as "Statut"
FROM #plan
SORT date_modification DESC
LIMIT 5
```

## 🔄 Workflow d'implémentation

1. **Consultation des spécifications**:
   - Commencez par [[3-Specifications-fonctionnelles/module-[nom-module]|la spécification du module]]

2. **Analyse du plan d'implémentation**:
   - Passez au [[4-Plan-technique/plan-d-implementation/plan-feature-XXX|plan d'implémentation]]

3. **Utilisation du prompt**:
   - Référez-vous au [[prompts/implementation-feature-XXX|prompt d'implémentation]]

4. **Développement code**:
   - Implémentez dans les fichiers spécifiés dans le prompt

5. **Documentation des résultats**:
   - Créez un [[8-Suivi-Implementation/rapports/rapport-feature-XXX|rapport d'implémentation]]

6. **Mise à jour du registre**:
   - Mettez à jour le [[8-Suivi-Implementation/registre-fonctionnalites|registre des fonctionnalités]]

## 🧠 Contexte technique global

Les technologies principales de ce projet sont:
- Python pour le backend
- Framework de résolution de contraintes (PuLP)
- Base de données PostgreSQL

## 📑 Guides et références rapides

- [[5-Implementation/guides/conventions-codage|Conventions de codage]]
- [[6-Referentiels-contextuels/bibliotheques-externes|Bibliothèques externes]]
- [[9-Methodologie/workflow-cursor-obsidian|Workflow Cursor-Obsidian]] 