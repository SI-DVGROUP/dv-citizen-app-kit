## Portée

Ce template ne configure aucune intégration externe opérationnelle. Le modèle de référence Entra ID/OIDC défini dans `.agent/charter/identity-and-access.md` est approuvé ; son guide détaillé est dans `docs/identity-and-access.md`. Avant la diffusion d'un scaffold prêt à l'emploi, la plateforme doit automatiser le provisionnement des paramètres et permissions standards à partir de profils préapprouvés. Toute autre intégration doit d'abord être ajoutée et approuvée dans le catalogue de la plateforme ; le Citizen ne configure pas lui-même d'accès hors catalogue.

Pour chaque intégration approuvée, la spécification précisera son rôle, son emplacement, son mode d'authentification, sa configuration, les erreurs attendues, les restrictions et les données envoyées/reçues.

- [MUST] Ne pas ajouter une nouvelle API ou un nouveau service externe hors du catalogue préapprouvé. Toute nouvelle capacité est examinée et intégrée au niveau de la plateforme avant d'être proposée aux projets ; elle ne déclenche pas une opération manuelle répétée pour chaque projet.
- [MUST] Ne pas utiliser un compte personnel comme identité technique.
- [MUST] Ne pas demander au Citizen de choisir des scopes OAuth ou des permissions techniques.
- [MUST] Documenter les données envoyées et reçues.
- [MUST] Gérer les indisponibilités et erreurs des services externes.
- [SHOULD] Éviter le couplage direct d'une règle métier à un fournisseur externe et justifier tout écart dans la spécification.