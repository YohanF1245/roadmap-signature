# Roadmap - Projet Signature

## 1. API
- [ ] Implémenter les endpoints CRUD pour les promotions
  - Tests: Validation des requêtes HTTP, gestion des erreurs, conformité des données
- [ ] Développer l'endpoint de récupération des promotions
  - Tests: Format des données (UUID/nom), pagination, performance
- [ ] Créer l'endpoint des données détaillées des promotions
  - Tests: Structure JSON, validation des snowflakes Discord, intégrité des relations

## 2. Bot Discord
### 2.1 Fonctionnalités Core
- [ ] Mettre en place la communication dans les canaux
  - Tests: Permissions, rate limiting, gestion des erreurs Discord
- [ ] Implémenter le système de messages privés
  - Tests: Délivrance des messages, gestion des DMs fermés
- [ ] Développer la gestion des fils de discussion
  - Tests: Création/fermeture des fils, permissions
- [ ] Configurer l'API HTTP listener
  - Tests: Sécurité des endpoints, validation des payloads
- [ ] Implémenter le système de fichiers (config/logs)
  - Tests: Persistance, concurrence, rotation des logs

### 2.2 Gestion des Signatures
- [ ] Créer l'interface de création des canaux signature
  - Tests: Validation des inputs, gestion des permissions
- [ ] Développer le système Staff → Apprenants
  - Tests: Sélection multiple, validation du timer, notifications
- [ ] Implémenter le système Apprenants → Staff
  - Tests: Validation des demandes, gestion du timer
- [ ] Mettre en place les notifications
  - Tests: Délivrance, format, timing

### 2.3 Configuration et Monitoring
- [ ] Implémenter le système de configuration
  - Tests: Parsing du fichier config, validation des données
- [ ] Développer le système de logging
  - Tests: Format des logs, rotation, performance
- [ ] Créer le système de gestion des états
  - Tests: Transitions d'états, persistance, concurrence

## 3. Dashboard
- [ ] Développer l'interface d'administration
  - Tests: Responsive design, accessibilité
- [ ] Implémenter la visualisation des logs
  - Tests: Filtrage, pagination, performance
- [ ] Créer l'interface de gestion des configurations
  - Tests: Validation des inputs, persistance des changements

## 4. Documentation
- [ ] Rédiger la documentation technique
  - Tests: Validation des exemples de code
- [ ] Créer le guide d'utilisation
  - Tests: Vérification des scénarios d'utilisation
- [ ] Documenter l'API
  - Tests: Validation des exemples d'appels API
