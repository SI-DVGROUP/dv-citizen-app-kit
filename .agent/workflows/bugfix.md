# Correction d'anomalie

1. Conserver exactement la description originale de l'anomalie.
2. Identifier le comportement attendu et le comportement observé à partir des informations disponibles.
3. Identifier les conditions de reproduction et rechercher la règle métier applicable.
4. Reproduire le problème si possible ; ne jamais prétendre l'avoir reproduit sans l'avoir fait.
5. Créer une spécification ou mettre à jour celle qui correspond ; ajouter un test de non-régression lorsque pertinent.
6. Corriger la cause plutôt que masquer le symptôme, sans modifier le comportement métier non concerné.
7. Exécuter les vérifications disponibles et documenter précisément les résultats.
8. Expliquer simplement la correction et faire valider le résultat par le Citizen.

Ne pas demander au Citizen d'analyse technique. Les questions autorisées portent sur ce qu'il faisait, ce qu'il attendait, ce qui s'est produit, un exemple de donnée non sensible, et l'étendue des utilisateurs concernés.