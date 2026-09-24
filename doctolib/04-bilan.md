# Bilan — Rapport de clôture des tests — Doctolib.fr

## Résumé
Session de test pratique réalisée en juin 2026 sur Doctolib.fr (site en production),
portant sur le moteur de recherche et le parcours de prise de rendez-vous.

## Métriques

| Indicateur | Valeur |
|---|---|
| Cas de test conçus | 19 |
| Cas de test exécutés | 17 |
| Passés | 14 |
| À clarifier | 3 (DOC-CT-07, DOC-CT-09, DOC-CT-17) |
| Non exécutés | 2 (DOC-CT-13, DOC-CT-16) |
| Anomalies distinctes | 3 |
| dont avec rapport de défaut | 2 (DOC-BUG-01, DOC-BUG-02) |

## Couverture

| Technique | Couverture |
|---|---|
| Tables de décision | 4 règles sur 4 — 100 % |
| Transitions d'état (transitions valides) | 6 transitions sur 8 — 75 % |

## Évaluation par rapport au plan
- Critère de sortie « tous les cas de test exécutés » : **non atteint** (DOC-CT-13 et DOC-CT-16 restent à exécuter).
- Critère de sortie « anomalies documentées » : **atteint**.

## Écarts par rapport au plan
- Le champ Lieu s'est révélé ne pas être un champ code postal strict (il accepte des codes partiels et des noms de villes).

## Obstacles
- Aucune spécification disponible : 3 comportements n'ont pas pu être tranchés et sont classés « À clarifier ».

## Anomalies non résolues
- DOC-BUG-01 — Repli silencieux sur la géolocalisation lors de la saisie d'un code postal invalide
- DOC-BUG-02 — Des établissements non médicaux apparaissent dans une recherche "Médecin généraliste"
- DOC-CT-17 — Destination du bouton "Étape précédente" depuis la page de connexion

## Leçons apprises
- Mon hypothèse de départ sur le champ Lieu (codes postaux à 5 chiffres uniquement)
  était fausse : le champ accepte aussi des codes partiels et des noms de villes.
  L'explorer avant de concevoir les cas de test m'a permis d'ajuster l'analyse
  des valeurs limites.
- En l'absence de spécifications, j'ai formulé les résultats attendus incertains
  sous forme d'options (A/B) et classé ces cas « À clarifier » plutôt que de
  conclure à un défaut.