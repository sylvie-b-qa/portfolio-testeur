# Plan de test — Doctolib.fr

## Objectif
Vérifier le comportement du moteur de recherche Doctolib et du parcours
de prise de rendez-vous.

## Application
Doctolib.fr — version production (site live)

## Périmètre
- Champ Spécialité/Nom/Établissement
- Champ Lieu
- Filtres Disponibilité et Secteur
- Parcours de prise de rendez-vous

## Hors périmètre
Espace patient, gestion du profil, version mobile

## Base de test
Aucune spécification disponible. Les comportements dont le caractère voulu
ne peut pas être déterminé sont classés « À clarifier ».

## Techniques appliquées
| Technique | Élément testé | Cas de test |
|---|---|---|
| Partitions d'équivalence | Champ Spécialité | DOC-CT-01 à DOC-CT-05 |
| Analyse des valeurs limites | Champ Lieu | DOC-CT-06 à DOC-CT-07 |
| Tables de décision | Filtres Disponibilité et Secteur | DOC-CT-08 à DOC-CT-11 |
| Transitions d'état | Parcours de prise de rendez-vous | DOC-CT-12 à DOC-CT-19 |
| Test exploratoire | Ensemble du périmètre | Phase d'exploration préalable (ci-dessous) |

## Critères d'entrée
Site Doctolib.fr accessible, navigateur web opérationnel

## Critères de sortie
Tous les cas de test exécutés, anomalies documentées

## Testeur
Sylvie B - Juin 2026

## Phase d'exploration préalable

Avant de rédiger les cas de test, j'ai exploré librement le site pour
comprendre le comportement de chaque champ :

- Le champ Spécialité accepte du texte libre avec autocomplétion intelligente.
- Le champ Lieu est optionnel : Doctolib géolocalise automatiquement si laissé vide.
- Le champ Spécialité est obligatoire : un message d'erreur s'affiche si on
  clique sur Rechercher sans rien saisir.
- Les caractères spéciaux et mots inexistants affichent "Aucun résultat"
  sans cliquer sur Rechercher.
- Le champ Lieu accepte des codes postaux partiels, complets et des noms de villes.

## Livrables
- [Cas de test](./02-cas-de-test.md)
- [Rapports de défaut](./03-rapports-defaut.md)
- [Bilan — rapport de clôture des tests](./04-bilan.md)