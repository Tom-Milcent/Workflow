# Vue Generale

## Vue d'ensemble

Le système EDT_Temple repose sur une architecture modulaire en couches qui sépare clairement les responsabilités et permet une évolution indépendante des composants.

## Diagramme conceptuel de l'architecture


`┌─────────────────┐    ┌─────────────────┐     ┌─────────────────┐
│                               │    │                                 │        │                              │
│  Interface Web       │◄─►│   API REST           │◄─►│  Services               │
│  (Flask/HTML)        │    │  (Flask)                    │         │  métier                  │
│                               │    │                               │          │                               │
└─────────────────┘    └─────────────────┘          └────────┬────────┘
                                                       │
                                                       ▼
       ┌─────────────────┐                              ┌─────────────────────┐
       │                               │                              │                                      │
       │  Solveur                 │◄─────────────►│       Base de données    │
       │  (OR-Tools)            │                              │  (SQLite)                        │
       │                               │                              │                                      │
       └─────────────────┘                              └─────────────────────┘
              │                                                  │
              │                                                  │
              ▼                                                ▼
       ┌─────────────────┐               ┌─────────────────────┐
       │                               │               │                                      │
       │  Générateur           │               │  Service                        │
       │  iCalendar              │               │  d'exportation              │
       │                               │               │                                      │
       └─────────────────┘               └─────────────────────┘`

