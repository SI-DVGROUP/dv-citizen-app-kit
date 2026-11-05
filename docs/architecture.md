## Architecture de référence observée

L'architecture cible est un monorepo pnpm/Turborepo :

- `apps/web` : interface Next.js/React ; réutilise le système de composants approuvé par DV Group.
- `apps/api` : API NestJS ; porte les règles métier, les gardes d'accès, les intégrations et l'accès aux données.
- `apps/mobile` : application Expo/React Native consommant l'API ; elle est présente mais n'est pas nécessaire à toutes les applications métier.
- `apps/api/prisma` : modèle PostgreSQL, migrations et graines.
- `infra/k8s` et Dockerfiles : packaging et déploiement conteneurisés.

La Web, l'API et le mobile ne partagent pas directement leurs responsabilités métier : l'API est l'autorité d'accès. La persistance observée est PostgreSQL/Prisma.

## Limites d'application au kit

Ce dépôt documente une architecture de référence observée ; il ne contient pas le code applicatif. Le Citizen réalise les features et fixtures dans le dépôt applicatif du projet, en respectant les choix approuvés. Le développement local et les tests ne doivent pas dépendre de l'accès à une intégration réelle ou de la livraison en environnement partagé. Le mobile reste optionnel selon le besoin métier.

Ne jamais placer de secrets ou d'identifiants d'environnement dans le template. Les décisions de stack, d'identité, de déploiement et d'intégration sont consignées dans `.agent/charter/stack.md` et `specs/active/`.