# Plan de test — OWASP Juice Shop

## Objectif
Vérifier le comportement du moteur de recherche et du formulaire 
d'inscription de l'application OWASP Juice Shop.

## Application
OWASP Juice Shop — application volontairement défectueuse, 
conçue pour s'entraîner au test logiciel.
Version locale : http://localhost:3000

## Périmètre
- Moteur de recherche (barre de recherche)
- Formulaire d'inscription (email, mot de passe)

## Hors périmètre
- Panier et tunnel d'achat
- Espace administrateur
- Tests de sécurité

## Techniques appliquées
- Partitions d'équivalence
- Rédaction de rapports de défaut
- Test exploratoire

## Critères d'entrée
Application Juice Shop accessible sur http://localhost:3000

## Critères de sortie
Tous les cas de test exécutés, anomalies documentées

## Testeur
Sylvie B — Juin 2026

## Phase d'exploration préalable

Avant de rédiger les cas de test, j'ai exploré librement 
l'application pour comprendre son comportement :

- La recherche se déclenche uniquement après validation
  par la touche Entrée
- Le champ vide affiche les 46 produits du catalogue
  (15 par page)
- Le moteur recherche par chaîne de caractères —
  "apple" retourne aussi "pomme" et "Pineapple Juice"
- La langue peut être changée mais certains articles
  restent en anglais
- Le formulaire d'inscription contient des incohérences
  sur les règles du mot de passe
