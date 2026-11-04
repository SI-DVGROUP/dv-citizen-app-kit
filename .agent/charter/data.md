# Données

Chaque spécification identifie les données utilisées, leur source de vérité, les utilisateurs autorisés, les opérations réalisées, les règles de conservation, la présence éventuelle de données personnelles, RH, clients, financières ou confidentielles, ainsi que les risques de duplication.

- [MUST] Ne pas dupliquer une donnée d'entreprise sans nécessité documentée.
- [MUST] Identifier la source de vérité.
- [MUST] Ne collecter et conserver que les données nécessaires au besoin métier.
- [MUST] Ne pas utiliser de données réelles sensibles dans les exemples, tests ou fixtures génériques.
- [MUST] Toute nouvelle catégorie de donnée sensible déclenche une vérification appropriée ou une escalade avant implémentation.
- [MUST] Les suppressions, imports et mises à jour de masse prévoient une protection contre les erreurs et les relances.
- [SHOULD] Prévoir l'idempotence des traitements susceptibles d'être exécutés plusieurs fois et justifier tout écart dans la spécification.


## État du template

Ce kit ne contient pas encore de données applicatives ni de modèle métier. Pour chaque projet, identifier la source de vérité propre au besoin avant de concevoir le stockage. La classification officielle, les durées de conservation et les propriétaires restent à confirmer par le propriétaire métier ou l'IT.