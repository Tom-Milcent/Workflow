# Matrices De Dependances

## Dépendances entre modules fonctionnels

|Module|Dépend de|Impact des modifications|
|---|---|---|
|Interface Web|API REST, Services métier|Moyen|
|API REST|Services métier, Base de données|Élevé|
|Services métier|Base de données, Solveur|Très élevé|
|Solveur|Services métier (configuration)|Moyen|
|Base de données|-|Très élevé|
|Générateur iCalendar|Services métier, Base de données|Faible|
|Exportation|Base de données, Services métier|Faible|

## Dépendances entre entités de données

|Entité|Dépend de|Impact des modifications|
|---|---|---|
|Employee|-|Élevé|
|Bar|-|Élevé|
|EmployeePreference|Employee|Moyen|
|EmployeeUnavailability|Employee|Moyen|
|BarRequirement|Bar|Moyen|
|SpecialEvent|Bar|Moyen|
|EmployeeBarAssignment|Employee, Bar|Élevé|
|Shift|Employee, Bar, SpecialEvent (optionnel)|Très élevé|
|Schedule|Shift|Élevé|

## Dépendances techniques

|Composant|Dépendances externes|Criticité|
|---|---|---|
|Flask|Werkzeug, Jinja2|Critique|
|OR-Tools|Python API|Critique|
|SQLite|-|Critique|
|FullCalendar|JavaScript, jQuery|Moyenne|
|iCalendar|Bibliothèque ics|Moyenne|
|Google Drive API|google-api-python-client|Faible|
|Celery|Redis, Broker|Faible|

## Dépendances chronologiques de développement

|Phase|Prérequis|Blocage potentiel|
|---|---|---|
|Base de données|-|Critique pour tout|
|Services métier|Base de données|Critique pour API et UI|
|Solveur|Services métier (partiel)|Critique pour planning|
|API REST|Services métier|Bloque l'interface web|
|Interface web|API REST|-|
|Génération iCalendar|Services métier, planning fonctionnel|-|
|Reporting|Planning fonctionnel, métriques|-| 