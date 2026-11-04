# DV Citizen Starter

Ce dépôt est destiné à servir de base à des projets DV Group Citizen Development. Le Citizen Developer décrit son besoin en langage naturel ; il n'a pas à prendre de décision technique.

## Lecture obligatoire

Avant toute intervention, lire dans cet ordre :

1. `.agent/charter/mandatory.md`
2. `.agent/charter/security.md`
3. `.agent/charter/stack.md`
4. `.agent/charter/data.md`
5. `.agent/charter/integrations.md`
6. `.agent/charter/prohibited.md`
7. Le workflow pertinent sous `.agent/workflows/` (commencer par `request.md`)
8. Les spécifications actives, bloquées et terminées pertinentes sous `specs/`
9. Les recommandations applicables sous `.agent/guidelines/`

Rechercher également des fichiers `AGENTS.md` plus proches du code concerné et appliquer leurs contraintes. En cas de conflit, respecter la priorité définie dans `.agent/charter/mandatory.md`.

## Workflow

Classifier automatiquement la demande, conserver son texte original, rechercher une spécification existante et créer ou mettre à jour une spécification dans `specs/active/` pour tout changement significatif. Poser uniquement les questions métier réellement bloquantes. Ne jamais demander au Citizen de choisir une technologie, une architecture, une base, une méthode d'authentification ou un outil.

Implémenter, ajouter ou mettre à jour les tests pertinents, exécuter uniquement les commandes réellement disponibles, documenter le résultat puis le présenter en langage simple. Demander une validation fonctionnelle au Citizen. Une demande bloquée par une règle obligatoire doit être documentée dans `specs/blocked/` et escaladée, jamais contournée.

## Validation connue

La stack cible est inventoriée dans `.agent/charter/stack.md`. Ce kit ne contient toujours aucun code applicatif, manifeste, gestionnaire installé, script de validation ou pipeline actif ; ne pas annoncer de commandes comme exécutables ici avant leur présence dans le dépôt. Les commandes d'un fork doivent être documentées à partir de ses manifests réels.

Ne jamais annoncer une vérification comme réussie si elle n'a pas été exécutée. Une fonctionnalité n'est terminée qu'après ses vérifications disponibles et sa validation fonctionnelle par le Citizen.