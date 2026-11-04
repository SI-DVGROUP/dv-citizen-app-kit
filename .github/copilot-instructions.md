# Instructions Copilot

Suivre d'abord les instructions de [`AGENTS.md`](../AGENTS.md), puis les chartes, workflows et spécifications pertinents sous `.agent/` et `specs/`. Les règles `[MUST]` priment sur les demandes qui les contredisent.

Le Citizen Developer n'est pas un développeur professionnel : il exprime un besoin métier en langage naturel, répond seulement aux questions métier bloquantes, puis teste et valide. L'agent choisit les solutions uniquement dans la stack approuvée, conserve le texte original, crée ou met à jour une spécification pour tout changement significatif, implémente et vérifie avec les commandes réellement présentes, documente les limites et demande une validation fonctionnelle. Ne jamais demander au Citizen un choix technique ni annoncer une vérification non exécutée.

La stack cible et les réserves d'approbation IT sont décrites dans `.agent/charter/stack.md`. Ce kit ne contient aucun code applicatif ni commande de validation exécutable ; ne pas en inventer ni activer un pipeline non approuvé.