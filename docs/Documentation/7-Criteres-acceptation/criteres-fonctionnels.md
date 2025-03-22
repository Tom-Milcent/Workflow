# Critères Fonctionnels

## Module de gestion des employés

### Critères fonctionnels

1. **Gestion des profils employés**
    - ✓ L'interface permet de créer, modifier et supprimer des profils employés
    - ✓ Les niveaux de formation sont configurables de 1 à 3
    - ✓ Les heures contractuelles peuvent être spécifiées ou laissées vides (non contraignant)
    - ✓ La priorité d'affectation est configurable et influence le solveur
2. **Gestion des disponibilités**
    - ✓ Les indisponibilités peuvent être enregistrées pour des dates spécifiques
    - ✓ Les plages horaires d'indisponibilité sont précises à la minute
    - ✓ Les indisponibilités sont strictement respectées par le solveur
    - ✓ L'interface affiche clairement les indisponibilités saisies
3. **Gestion des préférences**
    - ✓ Les préférences supportent 5 niveaux (de forte aversion à forte préférence)
    - ✓ Chaque préférence peut être pondérée selon son importance
    - ✓ Les préférences peuvent cibler des jours de semaine ou des dates spécifiques
    - ✓ Les plages horaires de préférence sont prises en compte avec un ratio de chevauchement

## Module de gestion des bars

### Critères fonctionnels

1. **Administration des établissements**
    - ✓ L'interface permet de créer et configurer plusieurs bars
    - ✓ Les informations de contact et localisation sont complètes
    - ✓ Chaque bar peut avoir ses propres paramètres d'opération
2. **Définition des besoins en personnel**
    - ✓ Les besoins peuvent être définis par jour de semaine avec précision
    - ✓ Le système supporte les besoins fractionnaires (ex: 1,5 personnes)
    - ✓ Les niveaux de formation requis sont configurables par créneau
    - ✓ Les besoins varient selon les plages horaires avec granularité à 30 minutes
3. **Gestion des événements spéciaux**
    - ✓ Les événements spéciaux peuvent être créés pour des dates spécifiques
    - ✓ Les besoins spécifiques des événements sont prioritaires sur les besoins réguliers
    - ✓ Les événements incluent des descriptions informatives pour les employés
    - ✓ Les événements sont visibles dans le calendrier avec une mise en évidence

## Module de planification

### Critères fonctionnels

1. **Génération automatique des plannings**
    - ✓ Le solveur génère un planning complet pour une période donnée
    - ✓ Les contraintes dures (indisponibilités, niveaux, affectations) sont respectées
    - ✓ Les préférences sont prises en compte selon leur poids et niveau
    - ✓ Le système propose des relaxations en cas d'infaisabilité
2. **Édition manuelle des plannings**
    - ✓ L'interface calendrier permet de visualiser et modifier les affectations
    - ✓ Le glisser-déposer fonctionne pour réaffecter les shifts
    - ✓ Les shifts peuvent être verrouillés pour préserver les modifications manuelles
    - ✓ Les modifications manuelles sont validées par rapport aux contraintes
3. **Gestion des échanges de shifts**
    - ✓ Le système suggère des employés compatibles pour les échanges
    - ✓ Les échanges respectent toutes les contraintes métier
    - ✓ L'historique des modifications est consultable

## Module d'analyse et reporting

### Critères fonctionnels

1. **Métriques de qualité des plannings**
    - ✓ Le taux de couverture des besoins est calculé avec précision
    - ✓ La satisfaction des préférences est mesurée globalement et par employé
    - ✓ Le respect des contraintes contractuelles est analysé
    - ✓ L'équité de distribution est évaluée par des indicateurs statistiques
2. **Tableaux de bord**
    - ✓ Les indicateurs clés sont présentés dans une interface synthétique
    - ✓ Les anomalies sont mises en évidence avec des alertes
    - ✓ Les tendances sont visualisables sur plusieurs périodes
3. **Rapports personnalisables**
    - ✓ Les rapports peuvent être filtrés par période, employé ou bar
    - ✓ L'export des données fonctionne vers CSV/Excel
    - ✓ Les données peuvent être préparées pour systèmes externes

## Module de communication

### Critères fonctionnels

1. **Génération de fichiers iCalendar**
    - ✓ Les fichiers .ics sont générés pour chaque employé et bar
    - ✓ Les informations contextuelles (lieu, événement) sont incluses
    - ✓ Les fichiers sont compatibles avec les principaux clients calendrier
2. **Intégration avec Google Drive**
    - ✓ Les fichiers sont correctement téléversés sur Google Drive
    - ✓ Les liens de partage sont générés automatiquement
    - ✓ Les fichiers obsolètes sont supprimés périodiquement
3. **Notifications**
    - ✓ Les notifications sont envoyées lors de la publication des plannings
    - ✓ Les modifications importantes déclenchent des alertes
    - ✓ Le contenu des notifications est personnalisé selon le destinataire 