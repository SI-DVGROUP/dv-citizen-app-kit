Aucun script de test n'est présent dans ce kit. La stack cible est définie dans `.agent/charter/stack.md`; les commandes ne seront exécutables qu'après création des manifests correspondants. Ne jamais annoncer un contrôle comme exécuté avant de l'avoir lancé.
# Tests

- [MUST] Ajouter ou mettre à jour les tests correspondant au comportement modifié selon les capacités du projet.
- [MUST] Utiliser les outils et commandes déjà déclarés ; ne pas introduire un outil de test sans validation requise.
- [MUST] Ne pas supprimer ou affaiblir un test pour faire disparaître un échec sans analyser et documenter la cause.
- [MUST] Ne pas utiliser de données réelles sensibles dans les tests.
- [SHOULD] Vérifier le scénario nominal, les entrées invalides, les droits, les doublons/réexécutions et les dépendances indisponibles lorsque le comportement les concerne.
- [MUST] Consigner les commandes exactes exécutées, leur résultat et les contrôles non exécutés.

Aucun outil ni script de test n'a été détecté dans le dépôt initial ; leur choix est **À valider par l'IT** avec la stack.