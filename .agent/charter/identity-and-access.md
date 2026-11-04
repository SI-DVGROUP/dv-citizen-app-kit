# Identité et contrôle d'accès

Cette charte est le résumé normatif du standard identité et accès validé pour le kit. Le guide détaillé, les diagrammes et l'exemple de synchronisation sont dans [`docs/identity-and-access.md`](../../docs/identity-and-access.md).

## Modèle des identités

- [MUST] Séparer `Account`, l'identité d'accès, de `User`, la personne métier. Les objets métier référencent `User`, jamais `Account`.
- [MUST] Utiliser Microsoft Entra ID via OIDC pour le SSO de tous les comptes ordinaires. Chaque application possède un unique compte administrateur local, exclu de la synchronisation ; ne créer aucun autre compte local.
- [MUST] Relier une identité externe avec une clé stable contextualisée par tenant/émetteur. Ne jamais associer des comptes à partir de la seule adresse e-mail.
- [MUST] Créer au premier login SSO le `Account` lié à un `User` déjà provisionné et actif. Refuser les identités absentes du périmètre de provisionnement ou désactivées.
- [MUST] Attribuer les rôles à `Account` via `AccountRole`. Les données métier restent associées à `User`.

## Rôles et mappings

- [MUST] Chaque application utilise les rôles standards Administrateur, Utilisateur et Visiteur ; les permissions précises sont définies par les fonctionnalités et le moindre privilège.
- [MUST] Utiliser `UserMapping` pour définir le périmètre de provisionnement des personnes et `RoleMapping` pour relier les groupes Entra aux rôles de l'application.
- [MUST] Comparer les identifiants stables de groupes contextualisés par tenant ; ne pas dépendre de leur nom affiché.
- [MUST] Recalculer les rôles issus des mappings à partir des appartenances actuelles et retirer les attributions devenues obsolètes sans effacer celles d'autres sources autorisées.
- [MUST] Si un compte reste autorisé mais n'a aucun rôle mappé, lui attribuer Visiteur ; un compte ou un `User` désactivé n'obtient aucun accès.

## Synchronisation et révocation

- [MUST] Appliquer les changements destructifs uniquement après une synchronisation complète et vérifiée. Une erreur, une réponse partielle ou une indisponibilité ne doit jamais provoquer une désactivation massive.
- [MUST] Désactiver le `User` et ses comptes lorsqu'il sort de tous les groupes configurés pour le provisionnement ; préserver ses données métier, relations et historiques.
- [MUST] Réactiver un utilisateur désactivé lorsqu'il réintègre un groupe de provisionnement, après une synchronisation complète réussie, puis recalculer ses rôles.
- [MUST] Empêcher tout accès d'un compte ou utilisateur désactivé, même depuis une session ou un jeton antérieur, par un contrôle d'autorisation côté serveur.
- [MUST] Auditer les changements d'accès et les résultats de synchronisation sans journaliser de mot de passe, secret, jeton ni profil complet inutile.

## Configuration et responsabilité IT

- [MUST] Permettre l'administration de la configuration des fournisseurs depuis l'espace dédié autorisé, avec validation, journal d'audit et possibilité de retour arrière ; son application ne nécessite pas une nouvelle livraison.
- [MUST] Stocker les secrets hors de la base applicative et du dépôt ; seule une référence protégée au mécanisme de secrets approuvé peut être configurée.
- [MUST] L'IT provisionne et reste propriétaire des tenants, App Registrations, identités techniques, permissions Entra/Graph, attributs autorisés et paramètres propres à chaque application.
- [MUST] Appliquer le moindre privilège, TLS avec validation de certificat, et les règles de `.agent/charter/security.md` et `.agent/charter/integrations.md`.
- [MUST] Ne jamais inventer un tenant, une permission, un secret, une portée ou une configuration d'environnement. Le Citizen ne choisit pas les permissions techniques.
