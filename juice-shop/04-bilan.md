# Bilan — Rapport de clôture des tests — OWASP Juice Shop

## Résumé
Session de test pratique réalisée en juin 2026 sur OWASP Juice Shop (version locale),
portant sur le moteur de recherche et le formulaire d'inscription.
Complétée en septembre 2026 par l'ajout de JS-CT-13.

## Métriques

| Indicateur | Valeur |
|---|---|
| Cas de test conçus | 14 |
| Cas de test exécutés | 14 |
| Passés | 10 |
| À clarifier | 4 (JS-CT-02, JS-CT-03, JS-CT-06, JS-CT-09) |
| Rapports de défaut | 2 (JS-BUG-01, JS-BUG-02) |
| Anomalies distinctes | 6 (4 cas à clarifier + 2 défauts) |

## Couverture

| Technique | Couverture |
|---|---|
| Analyse des valeurs limites (2 valeurs) — mot de passe 5 à 40 caractères | 4 valeurs limites sur 4 (4, 5, 40, 41) — 100 % |

## Évaluation par rapport au plan
- Critère de sortie « tous les cas de test exécutés » : **atteint**.
- Critère de sortie « anomalies documentées » : **atteint**.

## Écarts par rapport au plan
- JS-CT-13 (40 caractères) a été ajouté pour compléter l'analyse des valeurs limites.

## Obstacles
- Aucune spécification disponible : 4 comportements n'ont pas pu être tranchés et sont classés « À clarifier ».

## Anomalies non résolues
- JS-BUG-01 — Incohérence entre la règle affichée (5 caractères minimum) et les conseils (8 caractères minimum)
- JS-BUG-02 — Le compteur de caractères affiche 0/20 au lieu de 0/40
- JS-CT-02 — "apple" remonte des produits sans le mot "apple"
- JS-CT-03 — "Apple Juice" remonte "Pineapple Juice" : correspondance exacte ou partielle attendue ?
- JS-CT-06 — Champ de recherche vide : tout le catalogue s'affiche
- JS-CT-09 — E-mail sans extension accepté