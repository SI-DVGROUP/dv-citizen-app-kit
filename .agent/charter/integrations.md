## Portée

Ce template ne configure aucune intégration externe opérationnelle. Le modèle de référence Entra ID/OIDC défini dans `.agent/charter/identity-and-access.md` est approuvé ; son guide détaillé est dans `docs/identity-and-access.md`. Les paramètres et permissions d'annuaire restent provisionnés par l'IT pour chaque application. Toute autre intégration d'un projet dérivé doit être approuvée pour son besoin, son propriétaire, son identité et ses données. Ne pas considérer une technologie citée dans une demande comme approuvée hors de ce périmètre.

Pour chaque intégration approuvée, la spécification précisera son rôle, son emplacement, son mode d'authentification, sa configuration, les erreurs attendues, les restrictions et les données envoyées/reçues.

- [MUST] Ne pas ajouter une nouvelle API ou un nouveau service externe sans validation IT.
- [MUST] Ne pas utiliser un compte personnel comme identité technique.
- [MUST] Ne pas demander au Citizen de choisir des scopes OAuth ou des permissions techniques.
- [MUST] Documenter les données envoyées et reçues.
- [MUST] Gérer les indisponibilités et erreurs des services externes.
- [SHOULD] Éviter le couplage direct d'une règle métier à un fournisseur externe et justifier tout écart dans la spécification.