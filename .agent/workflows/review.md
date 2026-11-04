# Revue

Vérifier la conformité à la spécification, la stack, la sécurité, les autorisations, les données, la gestion des erreurs, les dépendances, les tests, la documentation, l'expérience utilisateur, l'accessibilité de base, l'absence de secrets, de code mort évident, de contournement et de changements injustifiés hors périmètre.

Classer chaque constat :

- **BLOCKING** : interdit de considérer le travail comme terminé (notamment toute violation d'une règle `[MUST]`).
- **WARNING** : le travail peut fonctionner, mais un risque subsiste et doit être expliqué.
- **SUGGESTION** : amélioration facultative.

Ne pas transformer une préférence stylistique mineure en blocage. Citer le comportement ou la règle concernée et les éléments observables. Ne pas affirmer qu'un contrôle a été exécuté sans l'avoir exécuté.