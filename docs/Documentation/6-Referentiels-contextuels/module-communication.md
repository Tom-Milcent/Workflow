# Contexte du Module Communication

## Contexte du module de communication

### Objectif

Faciliter le partage des plannings avec les employés via des formats standardisés et accessibles, automatiser les notifications importantes.

### Données essentielles

- **Calendriers générés**
    - Fichiers iCalendar par employé et par bar
    - Période couverte
    - Métadonnées événements (lieu, description)
- **Paramètres de partage**
    - Méthode de partage (lien Google Drive, email, etc.)
    - Destinataires
    - Permissions d'accès
- **Notifications**
    - Type (publication, modification, rappel)
    - Destinataire(s)
    - Contenu et format

### Contraintes métier

- Les calendriers doivent être générés uniquement pour les plannings confirmés
- Les fichiers obsolètes doivent être nettoyés automatiquement
- Les événements spéciaux doivent être inclus avec leurs détails
- Les modifications de dernière minute doivent déclencher des notifications

### Interactions avec autres modules

- Utilise les données du module de planification
- Intègre les informations contextuelles des modules employés et bars
- Se connecte aux services externes (Google Drive) 