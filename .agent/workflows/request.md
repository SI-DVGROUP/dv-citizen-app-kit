# Router une demande

L'agent choisit le workflow ; le Citizen n'a pas à le sélectionner.

## Classification

Classer la demande comme nouvelle fonctionnalité, correction d'anomalie, clarification fonctionnelle, modification documentaire, maintenance technique ou demande nécessitant une escalade. Une demande peut combiner plusieurs catégories ; traiter chaque partie selon son workflow et ses blocages.

## Étapes obligatoires

1. Conserver le texte original, sans correction silencieuse.
2. Rechercher une spécification correspondante dans `specs/active/`, `specs/completed/` et `specs/blocked/`.
3. Rechercher les règles métier existantes et les décisions applicables.
4. Rechercher les impacts sur utilisateurs, données, sécurité, autorisations, intégrations et documentation.
5. Classifier et appliquer le workflow adapté sous `.agent/workflows/`.
6. Communiquer en langage simple, sans demander de choix technique.

Si une précision métier est réellement bloquante, poser une question concise et concrète. En cas de contrainte `[MUST]` insoluble, documenter dans `specs/blocked/` et escalader.