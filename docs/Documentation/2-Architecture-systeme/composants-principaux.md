# Composants Principaux

## Composants principaux

### 1. Interface utilisateur Web

- **Responsabilités** : Fournir une interface ergonomique pour la gestion des plannings
- **Technologies** : Flask, HTML, CSS, JavaScript, FullCalendar
- **Intégrations** : API REST, système de notifications

### 2. API REST

- **Responsabilités** : Exposer les fonctionnalités du système via des endpoints documentés
- **Technologies** : Flask Blueprint, JSON
- **Sécurité** : Authentification, validation des données

### 3. Services métier

- **Responsabilités** : Implémenter la logique métier et coordonner les opérations
- **Principaux services** :
    - `DatabaseService` : Gestion des opérations sur la base de données
    - `SolverService` : Interface avec le solveur de contraintes
    - `ICalendarService` : Génération et gestion des calendriers

### 4. Solveur de contraintes

- **Responsabilités** : Générer des plannings optimisés selon les contraintes spécifiées
- **Technologie** : OR-Tools (CP-SAT Solver)
- **Caractéristiques** :
    - Multi-objectif (couverture des besoins, préférences, équité)
    - Relaxation automatique des contraintes
    - Rapports d'infaisabilité pour diagnostic

### 5. Base de données

- **Responsabilités** : Stocker et gérer toutes les données de l'application
- **Technologie** : SQLite (extensible vers d'autres SGBD)
- **Entités principales** :
    - Employés et leurs préférences
    - Bars et leurs besoins en personnel
    - Plannings et shifts
    - Événements spéciaux

### 6. Générateur iCalendar

- **Responsabilités** : Produire des fichiers iCalendar (.ics) pour le partage des plannings
- **Intégrations** : Google Drive pour le stockage cloud

### 7. Services d'exportation

- **Responsabilités** : Fournir des mécanismes d'exportation vers divers formats
- **Formats supportés** : iCalendar, PDF, CSV

