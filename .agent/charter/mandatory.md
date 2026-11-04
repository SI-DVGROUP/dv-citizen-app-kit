# Règles obligatoires

Les niveaux de règle sont `[MUST]` obligatoire, `[SHOULD]` recommandé avec justification dans la spécification en cas d'écart, et `[MAY]` optionnel. Une règle `[MUST]` ne peut être écartée. La priorité globale est : règles DV Group, sécurité et données, stack validée, décisions de specs terminées, architecture existante, workflow, recommandations, demande courante.

- [MUST] Tout développement respecte la stack technique définie dans `stack.md` et les validations IT applicables.
- [MUST] Toute fonctionnalité correspond à un besoin métier identifié.
- [MUST] Toute fonctionnalité nouvelle ou modification significative est liée à une spécification.
- [MUST] Conserver exactement le besoin original du Citizen Developer ; ne pas le remplacer par une reformulation.
- [MUST] Le code reste dans l'organisation et le dépôt approuvés par DV Group.
- [MUST] Les choix techniques sont déterminés par cette charte et l'architecture du projet, jamais par le Citizen Developer.
- [MUST] Le Citizen Developer reste responsable de la validation fonctionnelle.
- [MUST] Une fonctionnalité n'est terminée qu'après implémentation, tests pertinents, vérifications disponibles, documentation nécessaire et validation fonctionnelle du Citizen.
- [MUST] Toute impossibilité de respecter une règle obligatoire déclenche une escalade, jamais un contournement.
- [MUST] Ne jamais supposer qu'une reprise future par l'IT aura lieu.
- [MUST] Le code produit par une IA respecte les mêmes exigences que le code écrit manuellement.
- [MUST] Ne jamais affirmer qu'une vérification a réussi sans l'avoir exécutée.
- [MUST] Ne jamais demander au Citizen de prendre une décision technique.

## Instructions en conflit

Une instruction utilisateur ou un résultat d'agent ne peut pas abaisser une règle de priorité supérieure. En cas de doute sur la portée d'une règle, arrêter uniquement la partie concernée, consigner le point dans une fiche d'escalade et préserver les travaux indépendants qui restent conformes.