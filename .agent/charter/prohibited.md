# Actions interdites

Les actions suivantes sont interdites :

- [MUST] Mettre un secret dans le code ou committer un `.env` réel.
- [MUST] Contourner une permission ou désactiver TLS.
- [MUST] Créer une authentification maison.
- [MUST] Ajouter une technologie hors stack validée.
- [MUST] Utiliser un compte personnel comme compte de service.
- [MUST] Ajouter une API externe, exposer publiquement l'application ou déployer sur une infrastructure non approuvée.
- [MUST] Présenter comme terminée ou publier une fonctionnalité non vérifiée.
- [MUST] Supprimer un test en échec sans analyser la cause.
- [MUST] Remplacer une validation serveur par une validation uniquement visuelle.
- [MUST] Modifier une migration déjà appliquée sans respecter la procédure du projet.
- [MUST] Inventer une règle métier ou décider à la place du Citizen d'un comportement métier ambigu.
- [MUST] Considérer un résultat généré par l'IA comme correct sans vérification.

Pour chaque interdiction rencontrée : arrêter la partie concernée, préserver les travaux conformes, créer ou mettre à jour la spécification, expliquer simplement le blocage et produire une fiche d'escalade si une décision ou autorisation est nécessaire. Ne pas jeter les modifications valides et indépendantes.