# Contexte du Module Gestion Employes

## Contexte du module de gestion des employés

### Objectif

Permettre la gestion complète des profils employés, de leurs disponibilités et préférences, afin d'alimenter le solveur avec des données précises pour l'optimisation des plannings.

### Données essentielles

- **Profil employé**
    - Identification: Nom, identifiant unique
    - Qualifications: Niveau de formation (1-3)
    - Paramètres contractuels: Heures contractuelles, priorité
- **Disponibilités**
    - Disponibilités récurrentes par jour de semaine
    - Indisponibilités exceptionnelles (date, heure de début/fin, motif)
- **Préférences**
    - Niveau de préférence (-2 à +2)
    - Poids d'importance (1-10)
    - Cible de la préférence: jour, créneau horaire, date spécifique
- **Affectations aux bars**
    - Relations employé-bar autorisées

### Contraintes métier

- Un employé doit avoir au moins un niveau de formation défini
- Un employé doit être affecté à au moins un bar
- Les indisponibilités sont prioritaires sur les préférences
- Les préférences négatives fortes doivent être respectées autant que possible

### Interactions avec autres modules

- Fournit les données employés au module de planification
- Reçoit des métriques du module d'analyse
- Fournit les données de contact pour le module de communication 