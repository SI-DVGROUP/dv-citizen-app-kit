## Architecture de référence observée

L'architecture cible est un monorepo pnpm/Turborepo :

- `apps/web` : interface Next.js/React ; réutilise le système de composants approuvé par DV Group.
- `apps/api` : API NestJS ; porte les règles métier, les gardes d'accès, les intégrations et l'accès aux données.
- `apps/mobile` : application Expo/React Native consommant l'API ; elle est présente mais n'est pas nécessaire à toutes les applications métier.
- `apps/api/prisma` : modèle PostgreSQL, migrations et graines.
- `infra/k8s` et Dockerfiles : packaging et déploiement conteneurisés.

La Web, l'API et le mobile ne partagent pas directement leurs responsabilités métier : l'API est l'autorité d'accès. La persistance observée est PostgreSQL/Prisma.

## Limites d'application au kit

Ce kit ne contient pas encore d'application ni de packages. L'architecture ci-dessus est une référence issue d'une seule application, pas une preuve d'approbation universelle. Le profil de travail envisagé pour le Citizen Dev est Web + API ; le mobile reste optionnel selon le besoin métier. La généralisation de ces choix, l'accès aux packages privés et les décisions de sécurité sont à valider par l'IT avant de créer un squelette exécutable.

Ne jamais placer de secrets ou d'identifiants d'environnement dans le template. Les décisions de stack, d'identité, de déploiement et d'intégration sont consignées dans `.agent/charter/stack.md` et `specs/active/`.