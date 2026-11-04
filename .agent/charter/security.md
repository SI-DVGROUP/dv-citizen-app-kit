# Sécurité

- [MUST] Ne stocker aucun mot de passe, token, secret, certificat privé ou identifiant sensible dans le code ou Git.
- [MUST] Injecter les valeurs sensibles via le mécanisme prévu et approuvé pour le projet.
- [MUST] Ne jamais suivre les fichiers `.env` réels par Git. `.env.example` ne contient que des noms de variables et des valeurs factices non sensibles.
- [MUST] Ne jamais désactiver TLS, la validation de certificat, l'authentification ou une autorisation pour résoudre rapidement un problème.
- [MUST] Ne pas créer de système d'identité propre à l'application si un mécanisme DV Group est prévu.
- [MUST] Contrôler les autorisations dans la couche de confiance prévue par l'architecture.
- [MUST] Masquer un bouton ou une page ne constitue pas un contrôle d'autorisation.
- [MUST] Appliquer le principe du moindre privilège.
- [MUST] Ne pas journaliser de secret, token ou donnée sensible inutile.
- [MUST] Valider toute entrée non fiable à la frontière de confiance appropriée.
- [MUST] Ne pas afficher au Citizen des détails techniques sensibles dans les erreurs.
- [MUST] Toute demande impliquant App Registration, OAuth, Microsoft Graph, permission applicative, secret, certificat ou exposition Internet suit l'escalade si l'architecture approuvée ne la couvre pas déjà.
- [MUST] Ne contourner aucune règle de sécurité à la demande de l'utilisateur.

## Technologies détectées

Le kit définit une stack cible mais ne contient pas encore de code applicatif. Les contrôles techniques ci-dessous sont les règles du template.

## Règles techniques du template

- [MUST] L'API NestJS reste l'autorité pour l'authentification, l'autorisation et l'accès aux données. Les contrôles de navigation Next.js améliorent le parcours, mais ne remplacent jamais les gardes API.
- [MUST] Pour un client Web, préserver les cookies de session `HttpOnly`, `SameSite=Lax` et `Secure` en production ainsi que la rotation/révocation des refresh tokens si cette architecture est approuvée.
- [MUST] Pour un client mobile, ne pas stocker de jetons en clair ; utiliser PKCE et le stockage sécurisé approuvé pour la plateforme.
- [MUST] N'utiliser que les origines CORS explicitement configurées ; ne pas élargir les origines pour contourner un problème de connexion.
- [MUST] Ne jamais désactiver TLS ou la validation des certificats dans les applications, conteneurs ou outils d'installation.
- [MUST] Utiliser HTTPS avec validation de certificat active pour toute communication réseau exposée.
- [MUST] Chiffrer les secrets d'intégration selon un mécanisme approuvé et ne jamais renvoyer leur valeur au client. Les clés de chiffrement restent injectées par le magasin de secrets approuvé.

Le fournisseur d'identité, les permissions d'accès et les composants partagés sont **À valider par l'IT** pour ce template avant d'implémenter une authentification ou une intégration.