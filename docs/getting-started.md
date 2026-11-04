1. Créez le dépôt du projet dans l'organisation approuvée par DV Group à partir de ce template.
2. Conservez `AGENTS.md`, `.agent/`, `specs/` et les règles de sécurité.
3. Faites confirmer par l'IT les points marqués **À valider** dans `.agent/charter/stack.md`, notamment la version stable du langage, l'identité, les composants partagés et la CI/CD. Ne demandez pas au Citizen de choisir ces technologies.
4. Tant que le kit ne contient pas les manifests de l'application, n'exécutez pas les commandes pnpm de référence : elles sont documentées dans `.agent/charter/stack.md` mais ne sont pas installées ici.
5. Décrivez le besoin métier en langage naturel. L'agent choisit le workflow, conserve la demande et crée une spécification.
6. Répondez uniquement aux questions métier bloquantes.
7. Testez le parcours livré et consignez votre validation dans la spécification.

Le kit actuel est un socle de gouvernance et de documentation, pas encore un squelette applicatif exécutable. La création de ce squelette dépend des validations IT consignées dans `specs/active/`.