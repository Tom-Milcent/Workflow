---
title: "Templates de prompts pour Cursor"
created: {{date}}
modified: {{date}}
type: guidance
---

# Templates de prompts pour Cursor

Ce document contient des templates de prompts pour utiliser efficacement Cursor avec le projet EDT_Temple.

## Prompt de développement de fonctionnalité

```
Je travaille sur la fonctionnalité [ID_FONCTIONNALITÉ] du module [NOM_MODULE] dans le projet EDT_Temple. Voici les spécifications:

[COPIER LA SECTION PERTINENTE DE LA SPÉCIFICATION]

Je dois implémenter cette fonctionnalité dans [FICHIER] en suivant l'architecture existante. Les fonctionnalités similaires déjà implémentées se trouvent dans [FICHIERS_SIMILAIRES].

Aide-moi à:
1. Analyser les spécifications
2. Créer une structure de code adaptée
3. Implémenter la fonctionnalité en respectant les conventions du projet
```

## Prompt de revue de code

```
Peux-tu examiner le code suivant pour le projet EDT_Temple:

[CODE À EXAMINER]

Ce code implémente [DESCRIPTION]. Vérifie:
1. La conformité avec les conventions PEP 8 (Python) / ESLint (JS)
2. Les problèmes potentiels de performance
3. La sécurité et la gestion des erreurs
4. La lisibilité et maintenabilité
5. La couverture de test nécessaire
```

## Prompt pour optimisation d'algorithme

```
J'ai besoin d'optimiser l'algorithme de planification dans EDT_Temple. Voici le code actuel:

[CODE ACTUEL]

Les problèmes identifiés sont:
1. Performances lentes avec plus de X employés
2. Ne prend pas en compte la contrainte [CONTRAINTE]
3. Utilisation mémoire excessive

Aide-moi à optimiser cet algorithme en conservant la logique métier mais en améliorant les performances.
```

## Prompt pour création de test

```
Je dois créer des tests pour la fonctionnalité [ID_FONCTIONNALITÉ] du module [NOM_MODULE]. Voici le code à tester:

[CODE À TESTER]

Aide-moi à:
1. Identifier les scénarios de test principaux
2. Créer des tests unitaires avec pytest
3. Préparer les mocks nécessaires
4. Définir les assertions appropriées
```

## Prompt pour debug

```
J'ai un bug dans le module [NOM_MODULE] du projet EDT_Temple. Voici le code:

[CODE PROBLÉMATIQUE]

L'erreur que je reçois est:
[MESSAGE D'ERREUR]

Contexte:
- Cette fonction est appelée depuis [CONTEXTE_APPEL]
- Les données d'entrée typiques sont [DONNÉES_ENTRÉE]
- Le comportement attendu est [COMPORTEMENT_ATTENDU]

Aide-moi à identifier et corriger ce bug.
```

## Prompt pour intégration de composants

```
Je dois intégrer le module [MODULE_A] avec le module [MODULE_B] dans EDT_Temple. 

Spécifications du module A:
[SPÉCIFICATIONS_A]

Spécifications du module B:
[SPÉCIFICATIONS_B]

Points d'intégration requis:
1. [POINT_INTÉGRATION_1]
2. [POINT_INTÉGRATION_2]

Propose une approche d'intégration respectant l'architecture existante et les principes de découplage.
```

## Prompt pour refactoring

```
J'ai besoin de refactoriser cette partie du code dans le module [NOM_MODULE]:

[CODE_À_REFACTORISER]

Problèmes identifiés:
1. [PROBLÈME_1]
2. [PROBLÈME_2]

Objectifs du refactoring:
- Améliorer la maintenabilité
- Réduire la complexité cyclomatique
- Faciliter les tests

Propose une version refactorisée qui respecte les conventions du projet.
``` 