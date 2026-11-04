## Portée

Ce template ne configure ni ne déclare d'intégration externe comme active. Toute intégration d'un projet dérivé doit être approuvée pour son besoin, son propriétaire, son identité et ses données. Ne pas considérer une technologie citée dans une demande comme approuvée.

Pour chaque intégration approuvée, la spécification précisera son rôle, son emplacement, son mode d'authentification, sa configuration, les erreurs attendues, les restrictions et les données envoyées/reçues.

- [MUST] Ne pas ajouter une nouvelle API ou un nouveau service externe sans validation IT.
- [MUST] Ne pas utiliser un compte personnel comme identité technique.
- [MUST] Ne pas demander au Citizen de choisir des scopes OAuth ou des permissions techniques.
- [MUST] Documenter les données envoyées et reçues.
- [MUST] Gérer les indisponibilités et erreurs des services externes.
- [SHOULD] Éviter le couplage direct d'une règle métier à un fournisseur externe et justifier tout écart dans la spécification.