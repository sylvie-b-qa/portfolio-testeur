# Rapports de défaut - OWASP Juice Shop

## BUG-003 — Incohérence entre la règle affichée (5 caractères minimum) et les conseils (8 caractères minimum) pour le mot de passe

**Date :** 19/06/2026
**Application :** OWASP Juice Shop
**Testeur :** Sylvie B
**Sévérité :** Mineur
**Priorité :** Basse

**Étapes pour reproduire :**
1. Aller sur Juice Shop, cliquer sur "Compte"
   puis "Se connecter" puis "Pas encore client"
2. Observer le message sous le champ "Mot de passe" :
   "Votre mot de passe doit contenir au moins 5-40 caractères"
3. Observer la section conseils sur la même page :
   elle indique "votre mot de passe doit contenir au moins 8 caractères"

**Résultat obtenu :** Deux règles contradictoires s'affichent sur la même
page. Message principal : minimum 5 caractères. Section conseils :
minimum 8 caractères.

**Résultat attendu :** Une seule règle cohérente affichée partout
sur la page.

**Impact utilisateur :** L'utilisateur ne sait pas quelle règle respecter
pour créer son mot de passe. Risque de confusion et d'échecs répétés
lors de l'inscription.

**Statut :** Nouveau

---

## BUG-004 — Le compteur de caractères affiche 0/20 au lieu de 0/40 pour le champ mot de passe

**Date :** 19/06/2026
**Application :** OWASP Juice Shop
**Testeur :** Sylvie B
**Sévérité :** Mineur
**Priorité :** Basse

**Étapes pour reproduire :**
1. Aller sur Juice Shop, cliquer sur "Compte"
   puis "Se connecter" puis "Pas encore client"
2. Observer le compteur affiché sous le champ "Mot de passe"

**Résultat obtenu :** Le compteur affiche "0/20" alors que la règle
annoncée est un maximum de 40 caractères.

**Résultat attendu :** Le compteur devrait afficher "0/40" pour être
cohérent avec la règle affichée de 40 caractères maximum.

**Impact utilisateur :** L'utilisateur pense être limité à 20 caractères
alors que la limite réelle est 40. Risque de confusion sur la longueur
maximale autorisée.

**Statut :** Nouveau
