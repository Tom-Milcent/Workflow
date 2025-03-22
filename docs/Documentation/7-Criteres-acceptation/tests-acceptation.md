# Tests Acceptation

## Scénarios de tests d'acceptation

### Module de gestion des employés

1. **TA-EMP-001: Création et modification d'un profil employé**
   - **Préconditions**: Accès au module de gestion des employés
   - **Actions**:
     1. Créer un nouveau profil avec toutes les informations requises
     2. Modifier le niveau de formation et les heures contractuelles
     3. Enregistrer les modifications
   - **Résultat attendu**: Le profil est créé puis modifié avec succès, les données sont correctement enregistrées

2. **TA-EMP-002: Gestion des indisponibilités**
   - **Préconditions**: Existence d'un profil employé
   - **Actions**:
     1. Ajouter plusieurs indisponibilités pour différentes dates
     2. Visualiser le calendrier des indisponibilités
     3. Supprimer une indisponibilité
   - **Résultat attendu**: Les indisponibilités sont correctement enregistrées, affichées et peuvent être supprimées

### Module de gestion des bars

1. **TA-BAR-001: Configuration des besoins en personnel**
   - **Préconditions**: Existence d'un bar dans le système
   - **Actions**:
     1. Définir les besoins pour chaque jour de la semaine
     2. Spécifier des niveaux de formation différents selon les créneaux
     3. Configurer un besoin fractionnaire (1,5 personnes)
   - **Résultat attendu**: Les besoins sont correctement enregistrés et visibles dans le planning

2. **TA-BAR-002: Création d'un événement spécial**
   - **Préconditions**: Existence d'un bar avec des besoins standards
   - **Actions**:
     1. Créer un événement pour une date spécifique
     2. Définir des besoins supérieurs aux besoins standards
     3. Vérifier l'impact sur le planning
   - **Résultat attendu**: L'événement est visible dans le calendrier et ses besoins remplacent les besoins standards

### Module de planification

1. **TA-PLN-001: Génération automatique de planning**
   - **Préconditions**: Configuration complète des employés et des bars
   - **Actions**:
     1. Définir une période de 2 semaines
     2. Lancer la génération automatique
     3. Vérifier le respect des contraintes
   - **Résultat attendu**: Un planning complet est généré en respectant toutes les contraintes dures

2. **TA-PLN-002: Édition manuelle et verrouillage de shifts**
   - **Préconditions**: Existence d'un planning généré
   - **Actions**:
     1. Modifier manuellement plusieurs affectations
     2. Verrouiller certains shifts
     3. Regénérer le planning
   - **Résultat attendu**: Les shifts verrouillés sont préservés lors de la regénération

### Module d'analyse et reporting

1. **TA-REP-001: Génération et filtrage de rapports**
   - **Préconditions**: Existence d'un planning validé
   - **Actions**:
     1. Générer un rapport de couverture des besoins
     2. Filtrer par période et par bar
     3. Exporter au format CSV
   - **Résultat attendu**: Le rapport est généré, filtré et exporté correctement

2. **TA-REP-002: Analyse des métriques de satisfaction**
   - **Préconditions**: Planning avec préférences employés
   - **Actions**:
     1. Accéder au tableau de bord de satisfaction
     2. Identifier les employés les moins satisfaits
     3. Analyser les causes des insatisfactions
   - **Résultat attendu**: Le système identifie correctement les problèmes de satisfaction

### Module de communication

1. **TA-COM-001: Génération et partage des calendriers**
   - **Préconditions**: Existence d'un planning validé
   - **Actions**:
     1. Générer les fichiers iCalendar
     2. Partager via Google Drive
     3. Vérifier l'accès aux fichiers partagés
   - **Résultat attendu**: Les fichiers sont générés et accessibles via les liens de partage

2. **TA-COM-002: Envoi de notifications**
   - **Préconditions**: Modification d'un planning publié
   - **Actions**:
     1. Effectuer un changement de dernière minute
     2. Confirmer le changement
     3. Vérifier l'envoi des notifications
   - **Résultat attendu**: Les notifications sont envoyées uniquement aux personnes concernées

