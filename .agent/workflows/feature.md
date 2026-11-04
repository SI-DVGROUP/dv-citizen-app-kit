# Nouvelle fonctionnalité

1. **Comprendre** : conserver la demande originale ; formuler l'objectif métier sans remplacer la demande ; identifier les utilisateurs et le résultat attendu ; relever les ambiguïtés.
2. **Vérifier le cadre** : lire les chartes ; vérifier la stack ; rechercher les specs et règles métier ; identifier données, intégrations et impacts de sécurité ; déterminer si une escalade est nécessaire.
3. **Spécifier** : créer ou mettre à jour `specs/active/YYYY-MM-DD-nom-court.md`. Si la date fiable est inconnue, utiliser un identifiant stable sans inventer de date. Utiliser `.agent/templates/specification.md`.
4. **Clarifier** : ne poser que les questions métier bloquantes, compréhensibles sans connaissances techniques et nécessaires pour ne pas inventer une règle. Les regrouper et donner un exemple utile. Ne jamais demander framework, base, package, architecture, authentification, outil de test ou stockage des secrets.
5. **Planifier** : consigner dans la spec les changements fonctionnels, données, interface, sécurité, tests, documentation et risques de régression. Le résumé destiné au Citizen reste fonctionnel.
6. **Implémenter** : réaliser le plus petit changement cohérent, respecter les conventions, réutiliser les composants disponibles, ne pas ajouter de technologie, gérer les erreurs, mettre à jour les tests et consigner les décisions.
7. **Vérifier** : exécuter les commandes disponibles de lint, typecheck, tests et build, en utilisant les commandes de référence du dépôt. Ne cocher ou annoncer que les commandes réellement exécutées. Si un échec peut être préexistant, l'établir si possible, ne pas le masquer et documenter son impact.
8. **Présenter** : décrire ce qui a changé, comment tester, l'impact d'usage, les limites et les blocages en langage simple.
9. **Faire valider** : attendre la validation fonctionnelle du Citizen. Après validation, mettre à jour la spec, la déplacer dans `specs/completed/`, et conserver les décisions durables sans bruit temporaire.

Une fonctionnalité n'est pas terminée sans validation fonctionnelle explicite.