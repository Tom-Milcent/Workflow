---
id: PROMPT-003
title: Prompt d'implémentation - Mécanisme de relaxation automatique
type: prompt
plan_source: PLN-003
status: en_cours
date_creation: 2024-03-22
utilisation: 
  - 2024-03-22: Implémentation initiale
fichiers_cibles:
  - src/planner/constraint_conflict_detector.py
  - src/planner/constraint_impact_analyzer.py
  - src/planner/constraint_relaxation_proposer.py
  - src/planner/solver.py
tags:
  - #prompt
  - #planification
  - #relaxation
---

# Prompt: Implémentation du mécanisme de relaxation automatique

## Contexte du projet
Ce prompt fait partie du projet EDT_Temple et se rapporte au plan d'implémentation [[4-Plan-technique/plan-d-implementation/plan-feature-003|Plan 003]] qui concerne le mécanisme de relaxation automatique des contraintes dans le module de planification.

## Objectif
Implémenter un système capable de détecter les ensembles de contraintes incompatibles, d'analyser l'impact de la relaxation de chaque contrainte, et de proposer des stratégies de relaxation optimales pour résoudre les problèmes de planification infaisables.

## Contexte technique
Le système de planification EDT_Temple utilise PuLP comme solveur de programmation linéaire. L'algorithme principal de résolution est déjà implémenté mais ne gère pas encore les situations où aucune solution valide n'existe avec l'ensemble des contraintes fournies.

## Fonctionnalités à implémenter

1. **`constraint_conflict_detector.py`** - Détecteur de conflits
   - Classe `ConflictDetector` pour identifier les sous-ensembles minimaux de contraintes incompatibles
   - Méthode `find_minimal_conflicts()` retournant les MUCs (Minimal Unsatisfiable Cores)
   - Utilisation des techniques d'analyse incrémentale pour optimiser la détection

2. **`constraint_impact_analyzer.py`** - Analyseur d'impact
   - Classe `ImpactAnalyzer` pour évaluer l'impact de la relaxation de chaque contrainte
   - Méthode `score_constraints()` attribuant un score d'impact à chaque contrainte
   - Système de pondération des différents facteurs d'impact (faisabilité, qualité, préférences)

3. **`constraint_relaxation_proposer.py`** - Proposeur de relaxation
   - Classe `RelaxationProposer` pour suggérer des stratégies de relaxation
   - Méthode `generate_relaxation_strategies()` proposant plusieurs alternatives
   - Méthode `rank_strategies()` classant les stratégies par pertinence

4. **Intégration dans `solver.py`**
   - Modification de la classe `Solver` existante pour utiliser le mécanisme de relaxation
   - Implémentation d'une boucle de résolution avec relaxation progressive
   - Conservation des traces pour explicabilité des décisions de relaxation

## Spécifications à respecter
- [[3-Specifications-fonctionnelles/module-planification#2.2. Mécanisme de relaxation|Spécification du mécanisme de relaxation]]
- [[3-Specifications-fonctionnelles/relaxation-contraintes|Spécification détaillée de la relaxation de contraintes]]

## Architecture existante

Le module de planification est structuré comme suit:
- `src/planner/model.py` - Définition du modèle de contraintes
- `src/planner/solver.py` - Solveur principal utilisant PuLP
- `src/planner/constraints/` - Définitions des différentes contraintes
  - `hard_constraints.py` - Contraintes dures (indisponibilités, etc.)
  - `soft_constraints.py` - Contraintes souples (préférences, etc.)

Le mécanisme de relaxation doit s'intégrer dans cette architecture existante.

## Approche d'implémentation

### Détecteur de conflits (`constraint_conflict_detector.py`)

```python
class ConflictDetector:
    def __init__(self, model, constraints):
        self.model = model
        self.constraints = constraints
        
    def find_minimal_conflicts(self):
        """
        Identifie les sous-ensembles minimaux de contraintes en conflit.
        Utilise une approche par dichotomie pour réduire le nombre d'appels au solveur.
        
        Returns:
            List[Set[Constraint]]: Liste des ensembles minimaux de contraintes incompatibles
        """
        # TODO: Implémenter l'algorithme de recherche des MUCs
        # 1. Commencer par vérifier si l'ensemble complet est infaisable
        # 2. Réduire progressivement pour trouver les sous-ensembles minimaux
        # 3. Utiliser des heuristiques pour accélérer la recherche
        
    def _is_feasible(self, constraint_subset):
        """
        Vérifie si un sous-ensemble de contraintes est faisable.
        
        Args:
            constraint_subset (Set[Constraint]): Sous-ensemble de contraintes à tester
            
        Returns:
            bool: True si le sous-ensemble est faisable, False sinon
        """
        # TODO: Implémenter la vérification de faisabilité
```

### Analyseur d'impact (`constraint_impact_analyzer.py`)

```python
class ImpactAnalyzer:
    def __init__(self, model, conflict_sets):
        self.model = model
        self.conflict_sets = conflict_sets
        
    def score_constraints(self):
        """
        Attribue un score d'impact à chaque contrainte en fonction de:
        - Sa présence dans les ensembles de conflits
        - Sa priorité/importance
        - L'impact de sa relaxation sur la qualité de la solution
        
        Returns:
            Dict[Constraint, float]: Dictionnaire associant à chaque contrainte son score d'impact
        """
        # TODO: Implémenter le système de scoring
        
    def _simulate_relaxation(self, constraint):
        """
        Simule la relaxation d'une contrainte et mesure l'impact sur la solution.
        
        Args:
            constraint (Constraint): Contrainte à relaxer
            
        Returns:
            float: Score d'amélioration de la solution
        """
        # TODO: Implémenter la simulation de relaxation
```

### Proposeur de relaxation (`constraint_relaxation_proposer.py`)

```python
class RelaxationStrategy:
    def __init__(self, constraints_to_relax, impact_score, description):
        self.constraints_to_relax = constraints_to_relax
        self.impact_score = impact_score
        self.description = description

class RelaxationProposer:
    def __init__(self, model, conflict_detector, impact_analyzer):
        self.model = model
        self.conflict_detector = conflict_detector
        self.impact_analyzer = impact_analyzer
        
    def generate_relaxation_strategies(self):
        """
        Génère plusieurs stratégies de relaxation en se basant sur les conflits détectés
        et les scores d'impact.
        
        Returns:
            List[RelaxationStrategy]: Liste des stratégies de relaxation possibles
        """
        # TODO: Implémenter la génération de stratégies
        
    def rank_strategies(self, strategies):
        """
        Classe les stratégies par pertinence en fonction de critères multiples.
        
        Args:
            strategies (List[RelaxationStrategy]): Stratégies à classer
            
        Returns:
            List[RelaxationStrategy]: Stratégies classées par ordre de pertinence
        """
        # TODO: Implémenter le classement des stratégies
```

### Intégration dans le solveur (`solver.py`)

```python
# Ajouter à la classe Solver existante:

def solve_with_relaxation(self):
    """
    Résout le problème de planification en utilisant la relaxation automatique
    si nécessaire.
    
    Returns:
        Tuple[Solution, List[RelaxationStrategy]]: Solution trouvée et stratégies de relaxation appliquées
    """
    # 1. Tenter la résolution sans relaxation
    solution = self.solve()
    
    # 2. Si infaisable, utiliser le mécanisme de relaxation
    if solution is None:
        conflict_detector = ConflictDetector(self.model, self.constraints)
        conflicts = conflict_detector.find_minimal_conflicts()
        
        impact_analyzer = ImpactAnalyzer(self.model, conflicts)
        impact_scores = impact_analyzer.score_constraints()
        
        relaxation_proposer = RelaxationProposer(self.model, conflict_detector, impact_analyzer)
        strategies = relaxation_proposer.generate_relaxation_strategies()
        ranked_strategies = relaxation_proposer.rank_strategies(strategies)
        
        # 3. Appliquer la meilleure stratégie
        best_strategy = ranked_strategies[0]
        self._apply_relaxation(best_strategy)
        
        # 4. Résoudre à nouveau avec les contraintes relaxées
        solution = self.solve()
        
        return solution, [best_strategy]
    
    return solution, []
    
def _apply_relaxation(self, strategy):
    """
    Applique une stratégie de relaxation au modèle.
    
    Args:
        strategy (RelaxationStrategy): Stratégie à appliquer
    """
    # TODO: Implémenter l'application de la relaxation
```

## Considérations particulières

1. **Performance**: L'identification des MUCs peut être coûteuse en calcul. Utiliser des heuristiques pour limiter l'espace de recherche.

2. **Explicabilité**: Le système doit fournir des explications claires sur les relaxations proposées pour aider l'utilisateur à comprendre les compromis.

3. **Extensibilité**: Concevoir le système pour qu'il puisse facilement prendre en charge de nouveaux types de contraintes.

4. **Tests**: Créer des cas de test couvrant diverses situations de contraintes incompatibles pour valider le mécanisme.

## Références documentaires
- [[5-Implementation/notes-techniques/approche-relaxation-contraintes|Approche de relaxation des contraintes]]
- [[6-Referentiels-contextuels/bibliotheques-externes#PuLP|Documentation PuLP]]
- [[6-Referentiels-contextuels/bibliotheques-externes#NetworkX|Documentation NetworkX]] 