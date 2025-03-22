# Critères Non Fonctionnels

## Module de gestion des employés

### Critères non fonctionnels

1. **Performance**
    - ✓ Le chargement de la liste des employés prend moins de 1 seconde pour 100 employés
    - ✓ La sauvegarde des modifications est confirmée en moins de 2 secondes
2. **Utilisabilité**
    - ✓ L'interface est intuitive et ne nécessite pas de formation approfondie
    - ✓ Les formulaires incluent une validation en temps réel
    - ✓ Les messages d'erreur sont explicites et orientés solution
3. **Fiabilité**
    - ✓ Les données sont validées avant sauvegarde pour éviter les incohérences
    - ✓ Les opérations critiques demandent confirmation

## Module de gestion des bars

### Critères non fonctionnels

1. **Performance**
    - ✓ La génération des créneaux pour une semaine prend moins de 5 secondes
    - ✓ L'affichage des besoins en personnel est actualisé en temps réel
2. **Utilisabilité**
    - ✓ L'interface de définition des besoins est visuelle et intuitive
    - ✓ Les conflits entre besoins réguliers et événements sont clairement signalés
    - ✓ Les opérations en masse sont possibles pour configuration rapide
3. **Fiabilité**
    - ✓ Les modifications des besoins n'affectent pas les plannings déjà validés
    - ✓ Le système détecte et signale les configurations incohérentes

## Module de planification

### Critères non fonctionnels

1. **Performance**
    - ✓ La génération d'un planning pour 20 employés sur 2 semaines prend moins de 60 secondes
    - ✓ Le solveur utilise efficacement les ressources CPU/mémoire
    - ✓ L'interface reste réactive pendant le processus de génération
2. **Utilisabilité**
    - ✓ L'état d'avancement de la génération est clairement indiqué
    - ✓ Les modifications manuelles sont immédiatement visibles
    - ✓ Le système fournit des explications sur les décisions d'affectation
3. **Fiabilité**
    - ✓ Les shifts verrouillés ne sont jamais modifiés lors des regénérations
    - ✓ Les erreurs du solveur sont gérées avec des messages explicites
    - ✓ Le système peut récupérer d'une interruption pendant la génération

## Module d'analyse et reporting

### Critères non fonctionnels

1. **Performance**
    - ✓ Les métriques sont calculées en moins de 5 secondes pour un mois de planning
    - ✓ Les tableaux de bord se chargent en moins de 3 secondes
2. **Utilisabilité**
    - ✓ Les métriques sont présentées de manière visuelle et compréhensible
    - ✓ La navigation entre différentes vues est intuitive
    - ✓ Les rapports sont facilement personnalisables
3. **Fiabilité**
    - ✓ Les calculs statistiques sont vérifiés et validés
    - ✓ Les métriques sont recalculées automatiquement après modification du planning

## Module de communication

### Critères non fonctionnels

1. **Performance**
    - ✓ La génération des fichiers iCalendar prend moins de 10 secondes pour 50 employés
    - ✓ L'envoi des notifications est réalisé en moins de 30 secondes
2. **Utilisabilité**
    - ✓ Les liens de partage sont faciles à copier et distribuer
    - ✓ L'interface de gestion des notifications est intuitive
    - ✓ Les fichiers générés s'ouvrent correctement sur tous les appareils
3. **Fiabilité**
    - ✓ Le système vérifie l'intégrité des fichiers générés
    - ✓ Les erreurs de communication sont gérées avec des mécanismes de reprise
    - ✓ Les tentatives d'envoi échouées sont enregistrées et signalées 