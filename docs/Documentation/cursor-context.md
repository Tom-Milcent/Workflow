---
title: "Contexte global pour Cursor"
created: {{date}}
modified: {{date}}
type: guidance
---

# Contexte global du projet EDT_Temple pour Cursor

Ce document fournit une vue d'ensemble du projet EDT_Temple destinée à être utilisée comme contexte par Cursor pour une assistance IA plus efficace.

## Vue d'ensemble du projet

EDT_Temple est un système de planification d'emplois du temps pour bars qui permet:
- La génération automatique de plannings optimisés
- Le respect des contraintes des employés et établissements
- La communication efficace des plannings aux équipes
- L'analyse et reporting des données de planification

## Architecture technique

Le projet est structuré en modules:
1. **Backend**: Python avec FastAPI
2. **Frontend**: Vue.js avec Vuetify
3. **Base de données**: PostgreSQL
4. **Services auxiliaires**: Redis pour le cache, Celery pour les tâches asynchrones

## Structure du code

```
/src
  /api             # Routes API FastAPI
  /models          # Modèles de données Pydantic et SQLAlchemy
  /services        # Logique métier
    /employees     # Service de gestion des employés
    /bars          # Service de gestion des bars
    /scheduling    # Service de planification
    /communication # Service de communication
    /analytics     # Service d'analyse et reporting
  /utils           # Utilitaires partagés
  /tasks           # Tâches asynchrones Celery
  /config          # Configuration de l'application
/frontend          # Application Vue.js
  /src
    /views         # Pages principales
    /components    # Composants réutilisables
    /store         # État global Vuex
    /services      # Services d'API
/tests             # Tests unitaires et d'intégration
```

## Conventions de codage

- **Backend**: PEP 8, docstrings en format Google
- **Frontend**: ESLint, Prettier, composants Vue en Single-File Components
- **Tests**: pytest avec fixtures et mocks
- **Commits**: Conventional Commits (feat, fix, docs, chore, etc.)

## Points d'entrée pour le développement

- **API principale**: `src/api/main.py`
- **Logique de planification**: `src/services/scheduling/scheduler.py`
- **Interface utilisateur principale**: `frontend/src/views/SchedulerView.vue`
- **Configuration de base de données**: `src/models/base.py`

## Règles métier clés

1. **Planification**:
   - Respecter les disponibilités des employés
   - Optimiser la couverture des postes par niveau de compétence
   - Répartir équitablement les shifts entre employés selon contrat

2. **Contraintes**:
   - Repos minimum entre deux shifts: 12h
   - Temps de travail maximum par semaine: 44h
   - Ne pas planifier un employé sur deux bars différents le même jour

## Références techniques

- Documentation FastAPI: [https://fastapi.tiangolo.com/](https://fastapi.tiangolo.com/)
- Documentation Vue.js: [https://vuejs.org/guide/introduction.html](https://vuejs.org/guide/introduction.html)
- API SQLAlchemy: [https://docs.sqlalchemy.org/](https://docs.sqlalchemy.org/) 