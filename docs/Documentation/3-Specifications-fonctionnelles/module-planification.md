---
id: SPEC-240322-001
title: Spécification du module de planification
type: specification
status: validé
version: 1.0
date_creation: 2024-03-22
date_modification: 2024-03-22
auteur: Thomas
modules:
  - planification
  - solver
implements:
  - REQ-001
  - REQ-002
implemented_by:
  - PLN-001
  - PLN-002
  - PLN-003
tags:
  - #spec
  - #planification
  - #priorité-haute
---

# Spécification du module de planification

## Résumé

Le module de planification est responsable de la génération optimisée d'emplois du temps en tenant compte de multiples contraintes et préférences. Il constitue le cœur algorithmique du système EDT_Temple.

## Contexte

La génération d'emplois du temps optimisés est un problème complexe de satisfaction de contraintes qui nécessite une approche algorithmique sophistiquée. Ce module doit pouvoir générer des plannings qui respectent les contraintes dures (indisponibilités, qualifications) tout en optimisant les contraintes souples (préférences, équité).

## Exigences fonctionnelles

### 1. Modélisation des contraintes

1.1. **Contraintes dures (obligatoires)**
   - Respect des indisponibilités des employés
   - Respect des qualifications requises pour chaque poste
   - Respect du nombre minimum d'employés par créneau
   - Respect des temps de repos entre shifts

1.2. **Contraintes souples (optimisées)**
   - Minimisation des changements d'établissements dans une même journée
   - Respect des préférences de créneaux horaires
   - Distribution équitable de la charge de travail
   - Minimisation des shifts isolés

### 2. Algorithme de résolution

2.1. **Approche primaire**
   - Utilisation d'un solveur de programmation par contraintes
   - Formulation du problème comme un problème d'optimisation linéaire
   - Intégration d'un mécanisme d'évaluation multi-critères

2.2. **Mécanisme de relaxation**
   - Détection automatique des ensembles de contraintes infaisables
   - Proposition de relaxations intelligentes des contraintes
   - Priorisation des contraintes à relaxer selon leur importance

### 3. Interface de planification

3.1. **API de génération**
   - Endpoint de génération de planning avec paramètres configurables
   - Suivi de l'état d'avancement de la génération
   - Récupération des résultats et des métriques

3.2. **Mécanismes d'ajustement**
   - Interface pour ajustements manuels post-génération
   - Vérification de la validité des modifications manuelles
   - Optimisation locale après modifications manuelles

### 4. Visualisation et exportation

4.1. **Visualisation**
   - Représentation calendaire des plannings générés
   - Vue par employé et par établissement
   - Indication visuelle des violations de contraintes

4.2. **Exportation**
   - Format iCalendar pour intégration avec agendas personnels
   - Format CSV pour exploitation dans des outils externes
   - PDF pour impression et distribution physique

## Modèle de données

### Entités principales

- **Créneau** (Slot)
  - Date
  - Heure début
  - Heure fin
  - Établissement
  - Poste de travail
  - Employé assigné

- **Contrainte** (Constraint)
  - Type (dure/souple)
  - Poids (pour contraintes souples)
  - Paramètres spécifiques
  - Fonction de vérification

- **Solution** (Solution)
  - Ensemble de créneaux assignés
  - Score d'optimalité
  - Liste des contraintes violées
  - Métriques de qualité

### Relations

- Une solution contient plusieurs créneaux assignés
- Chaque créneau est associé à un employé et un établissement
- Chaque contrainte s'applique à un ou plusieurs créneaux

## Contraintes et limitations

- Le temps de génération doit rester raisonnable (< 10 minutes pour 100 employés)
- La solution doit pouvoir fonctionner avec des ressources matérielles limitées
- Le module doit pouvoir traiter jusqu'à 500 employés et 50 établissements

## Plans d'implémentation

Cette spécification est implémentée par les plans suivants:

- [[4-Plan-technique/plan-d-implementation/plan-feature-001|PLN-001: Implémentation du modèle de contraintes]]
- [[4-Plan-technique/plan-d-implementation/plan-feature-002|PLN-002: Algorithme de résolution principal]]
- [[4-Plan-technique/plan-d-implementation/plan-feature-003|PLN-003: Mécanisme de relaxation automatique]]

## Critères d'acceptation

- Génération d'un planning valide pour 50 employés en moins de 5 minutes
- Taux de satisfaction des contraintes souples > 85%
- Détection et proposition de relaxation pour 100% des ensembles de contraintes infaisables
- Validation des plans générés par un panel d'utilisateurs test

## Documentation associée

- [[2-Architecture-systeme/architecture-module-planification|Architecture du module de planification]]
- [[3-Specifications-fonctionnelles/algorithme-planification|Algorithme de planification]]
- [[3-Specifications-fonctionnelles/relaxation-contraintes|Relaxation de contraintes]]
- [[7-Criteres-acceptation/metriques-qualite-planning|Métriques de qualité des plannings]]

