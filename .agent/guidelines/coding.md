# Standards de développement

Ces recommandations s'appliquent au code applicatif des projets dérivés. La stack et les versions autorisées sont définies dans `.agent/charter/stack.md` ; la sécurité, l'identité et les données sont définies par les chartes correspondantes. Les exemples ci-dessous suivent TypeScript, NestJS, Next.js et PostgreSQL/Prisma, sans rendre exécutables les versions ou commandes qui ne sont pas encore approuvées dans le projet concerné.

## Principes de conception

- [MUST] Écrire le code pour qu'un autre développeur puisse comprendre et maintenir son intention.
- [MUST] Limiter chaque changement au besoin spécifié et préserver les comportements hors périmètre.
- [MUST] Donner aux variables, fonctions, types et modules des noms explicites, sans abréviations ambiguës.
- [MUST] Garder chaque fonction, classe et module centré sur une responsabilité cohérente.
- [MUST] Réutiliser les composants et utilitaires existants avant d'en créer de nouveaux.
- [SHOULD] Appliquer SOLID lorsque cela clarifie les responsabilités ; ne pas créer d'interfaces ou d'abstractions sans besoin concret.
- [SHOULD] Appliquer DRY aux règles métier réellement identiques, KISS à la solution immédiate et YAGNI aux besoins futurs non confirmés.
- [MUST] Éviter les valeurs magiques, la logique dupliquée, les dépendances circulaires, le code mort et le code commenté.
- [MUST] Ne pas imposer de limite arbitraire de lignes ; réduire l'imbrication et la complexité lorsque cela améliore la lecture.

Exemple : exprimer le contrat dans le type et garder la règle lisible.

À éviter :

```ts
type User = { isActive: boolean; email?: string | null };

function check(user: User | null) {
	if (user !== null) {
		if (user.isActive === true) {
			if (user.email !== null && user.email !== undefined) {
				return user.email.trim().length > 0;
			}
		}
	}
	return false;
}
```

Préférer :

```ts
type NotificationRecipient = { isActive: boolean; email?: string | null };

export function canReceiveNotifications(
	recipient: NotificationRecipient | null,
): boolean {
	return (
		recipient?.isActive === true &&
		typeof recipient.email === 'string' &&
		recipient.email.trim().length > 0
	);
}
```

## Architecture applicative

- [MUST] Suivre l'architecture et les frontières déjà établies dans le projet.
- [MUST] Séparer les contrats d'entrée/sortie, l'orchestration applicative, les règles métier et les détails d'infrastructure selon les besoins réels.
- [MUST] Garder les contrôleurs NestJS minces : ils valident le contrat HTTP et délèguent le cas d'usage ; ils n'implémentent pas de logique métier complexe ni d'accès direct à Prisma.
- [MUST] Garder les composants Next.js centrés sur l'interface et l'interaction. La navigation ou le masquage d'un contrôle ne constitue jamais une autorisation ; l'API reste l'autorité d'accès.
- [MUST] Valider toute donnée non fiable à la frontière du système avec les outils approuvés et ne pas confondre DTO API et modèle persistant.
- [SHOULD] Organiser les modules par domaine fonctionnel lorsque cela clarifie leur propriété et leurs dépendances ; éviter les couches génériques qui ne répondent à aucun besoin.
- [MUST] Faire communiquer les modules via des contrats explicites et éviter les dépendances circulaires.

## Conventions TypeScript

| Élément | Convention |
| --- | --- |
| Classes, types, interfaces, enums et composants React | `PascalCase` |
| Fonctions, méthodes, variables et paramètres | `camelCase` |
| Fichiers et dossiers | Convention déjà établie par le framework ou le projet |
| Constantes | `camelCase`, sauf convention existante ou noms de variables d'environnement |
| Interfaces TypeScript | Nom descriptif sans préfixe `I` |
| Fonctions asynchrones | Retourner un `Promise<T>` explicite lorsque cela clarifie un contrat public ; ne pas ajouter de suffixe `Async` systématiquement |

- [MUST] Respecter le mode strict TypeScript configuré par le projet.
- [MUST] Préférer `unknown` avec validation/narrowing à `any` ; toute exception à cette règle doit être locale et justifiée.
- [MUST] Maintenir les contrats publics et types proches de leur frontière d'usage ; éviter les types fourre-tout partagés sans propriétaire clair.
- [SHOULD] Rendre explicite le type de retour des fonctions exportées lorsque l'inférence masque un contrat important.
- [MUST] Suivre les conventions de fichiers imposées par Next.js, NestJS et les outils présents dans le manifeste réel du projet.

## API, données et erreurs

- [SHOULD] Utiliser des routes REST nommées comme des ressources au pluriel et les méthodes HTTP selon leur sémantique, par exemple `/api/users`.
- [MUST] Exposer des DTO adaptés à chaque opération ; ne pas sérialiser directement les modèles Prisma ou entités internes.
- [MUST] Documenter les contrats d'API avec le mécanisme OpenAPI adopté par le projet lorsqu'il est configuré.
- [MUST] Ne jamais ignorer silencieusement une exception et ne pas utiliser une exception pour un résultat métier attendu.
- [MUST] Traduire les erreurs au niveau approprié en réponses cohérentes et compréhensibles, sans détail interne, secret ou donnée personnelle inutile.
- [MUST] Utiliser les transactions pour les écritures qui doivent rester cohérentes ensemble.
- [MUST] Modifier le schéma de données au moyen des migrations versionnées du projet ; ne pas modifier manuellement un environnement partagé.
- [SHOULD] Ajouter contraintes, index et pagination en fonction des invariants métier et des requêtes réellement nécessaires.
- [MUST] Sélectionner uniquement les colonnes utiles et éviter les accès N+1 ; mesurer avant d'entreprendre une optimisation plus complexe.

## Sécurité, journalisation et dépendances

- [MUST] Suivre `.agent/charter/security.md`, `.agent/charter/identity-and-access.md` et `.agent/charter/data.md` ; cette guideline ne peut pas réduire leurs exigences.
- [MUST] Ne jamais committer de secret, mot de passe, jeton, certificat privé ou fichier `.env` réel.
- [MUST] Vérifier les autorisations côté serveur pour chaque opération protégée et appliquer le moindre privilège.
- [MUST] Traiter les erreurs et journaux sans exposer de détails sensibles ; ne pas journaliser de mots de passe, jetons ou réponses complètes de services externes.
- [SHOULD] Utiliser des logs structurés, les niveaux adaptés et les identifiants de corrélation déjà prévus par le projet.
- [MUST] Réutiliser les dépendances de la stack approuvée ; toute nouvelle dépendance doit être nécessaire, maintenue et compatible avec la politique du projet.
- [MUST] Utiliser le gestionnaire de paquets et le lockfile réellement présents ; ne pas inventer une commande pour un kit qui n'a pas encore de manifest.

## Tests et livraison

- [MUST] Tester les règles métier, les résultats limites et les erreurs pertinentes au niveau où ils sont définis.
- [SHOULD] Ajouter un test de non-régression pour un défaut corrigé et des tests d'intégration pour les frontières importantes (API, persistance, services autorisés).
- [MUST] Rendre les tests déterministes et ne jamais utiliser de données sensibles ou de production dans les fixtures.
- [MUST] Exécuter uniquement les contrôles réellement définis dans les manifests et scripts du projet ; indiquer ceux qui n'ont pas pu être exécutés.
- [MUST] Mettre à jour la documentation affectée et suivre le workflow de revue du projet avant intégration.
- [MAY] Ajouter un commentaire qui explique une contrainte ou une décision non évidente ; ne pas paraphraser le code.

## Vérification de fin

Avant de présenter un changement, vérifier que le besoin est respecté, que les responsabilités et autorisations restent au bon niveau, que les erreurs sont traitées, que les tests et contrôles disponibles ont été exécutés, et que la documentation correspond au comportement réel. Ne pas déclarer une vérification réussie sans l'avoir exécutée.