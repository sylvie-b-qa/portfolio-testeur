# Plan de test - OWASP Juice Shop

## Objectif
Vérifier le comportement du moteur de recherche et du formulaire
d'inscription de l'application OWASP Juice Shop.

## Application
OWASP Juice Shop - application web volontairement vulnérable, publiée par
l'OWASP pour les formations à la sécurité. Utilisée ici comme support de
tests fonctionnels.
Version locale : http://localhost:3000
Interface en français pour l'ensemble des tests

## Périmètre
- Moteur de recherche (barre de recherche)
- Formulaire d'inscription (email, mot de passe)

## Hors périmètre
- Panier et tunnel d'achat
- Espace administrateur
- Tests de sécurité

## Base de test
Aucune spécification disponible. Les comportements dont le caractère voulu
ne peut pas être déterminé sont classés « À clarifier ».

## Techniques appliquées
| Technique | Élément testé | Cas de test |
|---|---|---|
| Partitions d'équivalence | Moteur de recherche | JS-CT-01 à JS-CT-06 |
| Partitions d'équivalence | Champ E-mail | JS-CT-07 à JS-CT-10 |
| Analyse des valeurs limites | Champ Mot de passe | JS-CT-11 à JS-CT-14 |
| Test exploratoire | Ensemble du périmètre | Phase d'exploration préalable (ci-dessous) |

## Critères d'entrée
Application Juice Shop accessible sur http://localhost:3000

## Critères de sortie
Tous les cas de test exécutés, anomalies documentées

## Testeur
Sylvie B - Juin 2026

## Phase d'exploration préalable

Avant de rédiger les cas de test, j'ai exploré librement
l'application pour comprendre son comportement :

- La recherche se déclenche uniquement après validation
  par la touche Entrée
- Le champ vide affiche les 46 produits du catalogue
  (15 par page)
- Le moteur recherche par chaîne de caractères -
  "apple" retourne aussi "pomme" et "Pineapple Juice"
- La langue peut être changée mais certains articles
  restent en anglais
- Le formulaire d'inscription contient des incohérences
  sur les règles du mot de passe

## Livrables
- [Cas de test](./02-cas-de-test.md)
- [Rapports de défaut](./03-rapports-defaut.md)
- [Bilan — rapport de clôture des tests](./04-bilan.md)