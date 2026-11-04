# Règles des agents

Ce dossier définit le cadre de travail des agents IA pour les projets issus de DV Citizen Starter. Le Citizen Developer décrit son besoin, répond si nécessaire à quelques questions métier, puis teste et valide le résultat. L'agent prend en charge l'analyse, la spécification, les choix techniques conformes au projet, l'implémentation, les vérifications et la documentation.

## Ordre de priorité

Les règles sont classées `[MUST]` (obligatoire), `[SHOULD]` (recommandation justifiée si elle n'est pas suivie) ou `[MAY]` (optionnelle). En cas de conflit, appliquer dans cet ordre :

1. Règles obligatoires DV Group.
2. Sécurité et protection des données.
3. Stack autorisée et décisions IT applicables.
4. Décisions consignées dans les spécifications terminées.
5. Architecture existante du projet.
6. Workflow adapté à la demande.
7. Recommandations de développement.
8. Demande courante du Citizen Developer.

Une demande ne peut pas contourner une règle, une autorisation ou une validation IT obligatoire. Arrêter la partie concernée et escalader en cas de conflit insoluble.

## Fichiers

- `charter/` : obligations, stack, sécurité, identité et accès, données, intégrations et interdictions.
- `workflows/` : classification, réalisation, correction, revue et escalade.
- `guidelines/` : recommandations de code, tests, documentation, dépendances, usage de l'IA et expérience utilisateur.
- `templates/` : formats communs de spécification, décision, escalade et validation.

Le standard d'identité et d'accès est défini dans `charter/identity-and-access.md`, avec le détail dans `../docs/identity-and-access.md`. La stack cible du template est inventoriée dans `charter/stack.md`. Les validations nécessaires pour en faire un socle exécutable et activer la CI sont suivies dans `../specs/active/` et `../specs/blocked/`.