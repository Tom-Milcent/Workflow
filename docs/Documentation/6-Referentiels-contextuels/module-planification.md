# Contexte du Module Planification

## Contexte du module de planification

### Objectif

Générer des plannings optimisés respectant l'ensemble des contraintes et permettant un ajustement manuel lorsque nécessaire.

### Données essentielles

- **Paramètres de génération**
    - Période de planification (début/fin)
    - Options de relaxation des contraintes
    - Facteur d'échelle pour les besoins fractionnaires
- **Contraintes dures**
    - Indisponibilités des employés
    - Niveaux de formation requis
    - Affectations aux bars autorisées
    - Non-chevauchement des shifts pour un même employé
- **Objectifs d'optimisation**
    - Couverture des besoins en personnel
    - Respect des préférences des employés
    - Équité de la distribution du travail
    - Respect des heures contractuelles
    - Minimisation des transitions entre sous-créneaux
- **Shifts générés**
    - Assignation employé-bar-créneau
    - Statut (confirmé, en attente, etc.)
    - Verrouillage (pour préserver les modifications manuelles)

### Contraintes métier

- Tous les shifts doivent respecter les contraintes dures
- La couverture des besoins est prioritaire sur les préférences
- Les shifts verrouillés doivent être préservés lors des regénérations
- Le planning doit minimiser les écarts aux heures contractuelles

### Interactions avec autres modules

- Utilise les données des modules employés et bars
- Alimente le module d'analyse avec les plannings générés
- Fournit les données au module de communication pour partage 