# Citizen Development

## Parcours du Citizen Developer

1. Décrire le besoin en langage naturel.
2. Répondre, si nécessaire, à quelques questions métier simples et bloquantes.
3. Tester le résultat et le valider fonctionnellement.

L'agent lit les règles, identifie les impacts métier et les données, choisit uniquement dans le cadre technique approuvé, tient à jour une spécification, réalise les changements, exécute les contrôles disponibles et explique le résultat sans jargon.

## Responsabilités

Le Citizen confirme le besoin et les règles métier, puis valide le résultat. L'agent gère l'analyse technique, l'implémentation, les tests et la documentation dans le dépôt applicatif du projet. L'équipe plateforme définit et maintient le cadre commun ; elle n'intervient pas manuellement dans les développements standards.

## Voie standard autonome

Le Citizen développe les features et fixtures dans le dépôt applicatif du projet, en utilisant la stack et les capacités préapprouvées. Les changements standards peuvent être codés, lancés et testés localement sans ticket, approbation au cas par cas ou opération manuelle de l'équipe plateforme.

Les capacités accessibles sont limitées à un catalogue préapprouvé et appliquées avec des permissions minimales. Si un besoin sort de ce catalogue, il est identifié comme une capacité à ajouter au produit plateforme, pas comme une tâche manuelle à faire réaliser par le Citizen ou un blocage à traiter au fil de chaque projet. Les travaux qui ne dépendent pas de cette capacité peuvent continuer avec des données fictives et des services simulés, sans présenter la simulation comme une intégration réelle.

Ce dépôt est un kit de gouvernance et de documentation, pas un squelette applicatif exécutable. Les commandes de développement et les fixtures appartiennent au dépôt applicatif du projet. L'accès à un système réel, une capacité hors catalogue ou la livraison en environnement partagé peut nécessiter un traitement distinct ; cela ne doit pas bloquer les features indépendantes réalisables localement.

## Spécifications

Les demandes et décisions sont suivies dans `specs/`. Les questions métier restent explicites ; les choix techniques ne sont pas délégués au Citizen. Une fonctionnalité n'est terminée qu'après validation fonctionnelle.