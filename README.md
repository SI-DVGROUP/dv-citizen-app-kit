# DV Citizen Starter

Template de gouvernance pour les projets DV Group Citizen Development. Le Citizen Developer décrit son besoin, répond éventuellement à quelques questions métier, puis teste et valide le résultat. Les agents prennent en charge la spécification, les choix techniques conformes au cadre approuvé, l'implémentation, les vérifications disponibles et la documentation.

## Démarrer

Consulter [le guide de démarrage](docs/getting-started.md), puis décrire le besoin métier en langage naturel. Les règles destinées aux agents se trouvent dans [AGENTS.md](AGENTS.md) et `.agent/` ; le cycle de vie des demandes est décrit dans `specs/`.

Le [standard des comptes, rôles et de Microsoft Entra ID](docs/identity-and-access.md) décrit le modèle identité et accès validé ; les paramètres propres à chaque application sont provisionnés par l'IT.

## État de ce dépôt

La stack cible et les décisions encore ouvertes sont décrites dans `.agent/charter/stack.md`. Le kit ne contient pas encore de squelette applicatif exécutable. La validation des versions, de l'identité, des composants partagés et du mécanisme CI/CD reste à faire par l'IT ; voir `specs/active/` et `specs/blocked/`.

La CI du kit n'est pas activée. Aucun secret réel n'est inclus.