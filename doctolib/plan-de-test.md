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

## Techniques appliquées
- Partitions d'équivalence
- Analyse des valeurs limites
- Tables de décision
- Transitions d'état
- Test exploratoire

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
