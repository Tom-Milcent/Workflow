# Decisions Techniques

## Flux de données

1. **Création du planning** :
    - Saisie des contraintes et paramètres via l'interface web
    - Transmission à l'API puis aux services métier
    - Génération du planning via le solveur
    - Stockage en base de données
    - Affichage des résultats à l'utilisateur
2. **Partage du planning** :
    - Sélection des options de partage via l'interface
    - Génération des fichiers iCalendar
    - Export vers Google Drive
    - Distribution des liens de partage
3. **Analyse des métriques** :
    - Récupération des données de planning depuis la base
    - Calcul des indicateurs de performance
    - Présentation via l'interface utilisateur

