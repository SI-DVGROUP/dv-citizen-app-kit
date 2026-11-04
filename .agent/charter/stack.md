# Stack technique

## Profil cible

DV Citizen Starter définit un socle TypeScript en monorepo. Le profil comprend une application Web, une API et une base relationnelle ; le mobile est optionnel selon le besoin métier. Le kit ne contient pas encore de manifests ni de code applicatif : aucune commande de build, test ou démarrage n'est exécutable ici.

| Composant | Technologie cible | Rôle et statut |
| --- | --- | --- |
| Runtime | Node.js `24.20.0` | Runtime des applications et images conteneurisées |
| Langages | TypeScript ; JavaScript ESM pour la configuration | TypeScript `6.0.0-beta` est une préversion ; validation IT requise avant d'en faire le standard stable |
| Monorepo | pnpm `10.15.0`, Turborepo `2.5.6` | Workspaces et orchestration des applications |
| Web | Next.js `16.3.0`, React `19.2.x`, Tailwind CSS `4.1.x` | Interface métier Web |
| UI | Système de composants partagé DV Group, icônes Lucide | Accès au registre et composants autorisés à confirmer par l'IT |
| API | NestJS `12`, TypeScript ESM, Express | Règles métier, contrôle des autorisations, services et accès aux données |
| Validation des entrées | Zod, class-validator, class-transformer | Validation aux frontières de confiance selon le standard retenu |
| Données | PostgreSQL `18.6`, Prisma `7.10.0` et adaptateur PostgreSQL | Stockage relationnel ; versions exactes à confirmer avant initialisation |
| Identité | Microsoft Entra ID via OIDC | Modèle de référence validé ; tenant, App Registration, permissions et données autorisées sont provisionnés par l'IT pour chaque application |
| Mobile (optionnel) | Expo `57`, React Native `0.86.3`, Expo Router | Client natif si le besoin métier le justifie ; builds gérés par EAS après approbation |
| Tests API/Web | Vitest `5`, tests NestJS, Supertest `7`, Testing Library, jsdom | Tests automatisés des services, routes et composants |
| Tests mobile | Jest `29`, jest-expo | À utiliser uniquement si l'application mobile est retenue |
| Qualité | Oxlint, Prettier, TypeScript strict | Lint, format et vérification de types |
| Build | Turborepo, images Docker multi-stage | Build coordonné des workspaces et conteneurs |
| Développement local | Docker Compose avec PostgreSQL | Environnement local à configurer dans le template |
| Hébergement cible | Conteneurs, GHCR et Kubernetes/Kustomize | À confirmer par l'IT pour ce template |
| CI/CD | GitHub Actions et Jenkins | Choix et responsabilités à confirmer ; aucun pipeline n'est activé ici |
| Secrets | Variables d'environnement et magasin de secrets géré | À définir avec l'IT ; aucun secret réel dans le dépôt |
| Observabilité | OpenTelemetry, Pino, Sentry ; performance avec k6 | À confirmer comme standards avant d'ajouter les dépendances |

## Commandes cibles

Après création des manifests, les commandes prévues sont `pnpm install --frozen-lockfile`, `pnpm dev`, `pnpm build`, `pnpm test`, `pnpm lint`, `pnpm typecheck` et `pnpm format:check`. Les tâches de données envisagées sont `pnpm db:generate`, `pnpm db:migrate` et `pnpm db:seed`. Elles ne sont pas exécutables dans le kit tant que les scripts correspondants n'y sont pas créés.

## Décisions restantes

- [MUST] Confirmer une version stable de TypeScript et les versions exactes des outils avant de qualifier le socle de stable.
- [MUST] Confirmer l'accès au système de composants partagé et à son registre pour tous les forks.
- [MUST] Choisir et documenter un mécanisme CI/CD unique ou des rôles non redondants avant activation.
- [MUST] Confirmer l'identité d'entreprise, l'hébergement, la gestion des secrets et l'observabilité applicables.
- [MUST] Utiliser TLS et des certificats valides sur tous les échanges réseau ; ne jamais désactiver leur validation.
- [MUST] Ne pas intégrer d'identifiants d'application, noms d'environnement, domaines, URL ou paramètres propres à un déploiement.

## Règles d'évolution

- [MUST] Ne pas introduire un autre langage, framework, stockage, fournisseur d'identité, hébergement ou outil CI/CD sans validation IT.
- [MUST] Réutiliser les composants et services partagés autorisés pour le projet concerné.
- [SHOULD] Préférer une extension de l'architecture validée à l'ajout d'une nouvelle couche ; justifier tout écart dans la spécification.
- [MUST] Si un besoin ne peut pas être réalisé avec la stack formellement validée, arrêter la partie concernée et créer une fiche dans `specs/blocked/`.
- [MUST] Ne pas inventer de technologie, commande, configuration ou approbation absente des décisions validées.