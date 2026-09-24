# Cas de test — OWASP Juice Shop

**Légende des statuts :** Passé · À clarifier · Non exécuté

## Tableau de traçabilité

| ID | Technique | Élément couvert | Statut | Défaut lié |
|---|---|---|---|---|
| JS-CT-01 | Partitions d'équivalence | Mot en français | Passé | — |
| JS-CT-02 | Partitions d'équivalence | Mot en anglais | À clarifier | — |
| JS-CT-03 | Partitions d'équivalence | Deux mots | À clarifier | — |
| JS-CT-04 | Partitions d'équivalence | Mot inexistant | Passé | — |
| JS-CT-05 | Partitions d'équivalence | Caractères spéciaux | Passé | — |
| JS-CT-06 | Partitions d'équivalence | Champ vide | À clarifier | — |
| JS-CT-07 | Partitions d'équivalence | E-mail sans @ | Passé | — |
| JS-CT-08 | Partitions d'équivalence | E-mail sans domaine | Passé | — |
| JS-CT-09 | Partitions d'équivalence | E-mail sans extension | À clarifier | — |
| JS-CT-10 | Partitions d'équivalence | E-mail valide | Passé | — |
| JS-CT-11 | Valeurs limites | Mot de passe 4 caractères | Passé | — |
| JS-CT-12 | Valeurs limites | Mot de passe 5 caractères | Passé | — |
| JS-CT-13 | Valeurs limites | Mot de passe 40 caractères | Passé | — |
| JS-CT-14 | Valeurs limites | Mot de passe 41 caractères | Passé | — |

Les anomalies JS-BUG-01 et JS-BUG-02 ont été constatées sur la page d'inscription, en dehors des cas de test ci-dessus ([rapports de défaut](./03-rapports-defaut.md)).

---

## Partitions d'équivalence — Moteur de recherche

*La recherche se déclenche uniquement après validation par la touche Entrée.*

### JS-CT-01 — Recherche avec un mot en français
**Précondition :** Être sur la page d'accueil de Juice Shop,
champ de recherche visible

**Étapes :**
1. Cliquer sur la loupe — le champ s'agrandit
2. Saisir "pomme"
3. Appuyer sur Entrée

**Résultat attendu :** Les produits contenant le mot "pomme" s'affichent
**Résultat obtenu :** 2 résultats affichés — Jus de pomme et Marc de pommes
**Statut :** Passé

---

### JS-CT-02 — Recherche avec un mot en anglais
**Précondition :** Être sur la page d'accueil de Juice Shop,
champ de recherche visible

**Étapes :**
1. Cliquer sur la loupe — le champ s'agrandit
2. Saisir "apple"
3. Appuyer sur Entrée

**Résultat attendu :** Les produits contenant le mot "apple" s'affichent
**Résultat obtenu :** 3 résultats affichés — Jus de pomme, Marc de pommes
et Pineapple Juice. Le moteur recherche par chaîne de caractères et semble
traduire ou chercher par ingrédient.
**Statut :** À clarifier

*Note : "Pineapple" contient "apple" — résultat cohérent. "Jus de pomme"
et "Marc de pommes" sans le mot "apple" — comportement à clarifier :
traduction automatique ou recherche par ingrédient ?*

---

### JS-CT-03 — Recherche avec deux mots "Apple Juice"
**Précondition :** Être sur la page d'accueil de Juice Shop,
champ de recherche visible

**Étapes :**
1. Cliquer sur la loupe — le champ s'agrandit
2. Saisir "Apple Juice"
3. Appuyer sur Entrée

**Résultat attendu :** 0 résultat affiché car le produit "Apple Juice"
n'existe pas dans le catalogue
**Résultat obtenu :** 1 résultat affiché — Pineapple Juice. Le moteur
trouve "apple" ET "juice" dans "Pineapple Juice"
**Statut :** À clarifier

*Note : Le produit "Apple Juice" n'existe pas dans le catalogue. Le moteur
recherche par chaîne de caractères. Comportement à clarifier : la recherche
doit-elle trouver la correspondance exacte ou partielle ?*

---

### JS-CT-04 — Recherche avec un mot inexistant
**Précondition :** Être sur la page d'accueil de Juice Shop,
champ de recherche visible

**Étapes :**
1. Cliquer sur la loupe — le champ s'agrandit
2. Saisir "azerty"
3. Appuyer sur Entrée

**Résultat attendu :** Aucun produit affiché — message indiquant
l'absence de résultats
**Résultat obtenu :** Message affiché : "Aucun résultat. Essayez d'ajuster
votre recherche pour trouver ce que vous recherchez."
**Statut :** Passé

---

### JS-CT-05 — Recherche avec des caractères spéciaux
**Précondition :** Être sur la page d'accueil de Juice Shop,
champ de recherche visible

**Étapes :**
1. Cliquer sur la loupe — le champ s'agrandit
2. Saisir "@*/&"
3. Appuyer sur Entrée

**Résultat attendu :** Aucun produit affiché — message indiquant
l'absence de résultats
**Résultat obtenu :** Message affiché : "Aucun résultat. Essayez d'ajuster
votre recherche pour trouver ce que vous recherchez."
**Statut :** Passé

---

### JS-CT-06 — Recherche avec le champ vide
**Précondition :** Être sur la page d'accueil de Juice Shop,
champ de recherche visible

**Étapes :**
1. Cliquer sur la loupe — le champ s'agrandit
2. Ne rien saisir
3. Appuyer sur Entrée

**Résultat attendu :** Comportement à clarifier. Option A : message
d'erreur "Veuillez saisir un mot clé". Option B : affichage de tous
les produits si comportement voulu.
**Résultat obtenu :** 46 résultats affichés — la liste complète des
produits s'affiche sur plusieurs pages (15 par page)
**Statut :** À clarifier

*Note : Comportement différent de Doctolib qui bloquait avec un message
d'erreur sur champ vide. Sans specs, impossible de déterminer si afficher
tout le catalogue est voulu.*

---

## Partitions d'équivalence — Formulaire d'inscription (champ E-mail)

### JS-CT-07 — Inscription avec un email sans @
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test"
3. Cliquer dans le champ "Mot de passe" pour quitter le champ email

**Résultat attendu :** Un message d'erreur s'affiche indiquant que
l'adresse mail n'est pas valide
**Résultat obtenu :** Un message d'erreur s'affiche indiquant que
l'adresse mail n'est pas valide
**Statut :** Passé

---

### JS-CT-08 — Inscription avec un email sans domaine
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test@"
3. Cliquer dans le champ "Mot de passe" pour quitter le champ email

**Résultat attendu :** Un message d'erreur s'affiche indiquant que
l'adresse mail n'est pas valide
**Résultat obtenu :** Un message d'erreur s'affiche indiquant que
l'adresse mail n'est pas valide
**Statut :** Passé

---

### JS-CT-09 — Inscription avec un email sans extension
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test@test"
3. Cliquer dans le champ "Mot de passe" pour quitter le champ email

**Résultat attendu :** Un message d'erreur s'affiche indiquant que
l'adresse mail n'est pas valide
**Résultat obtenu :** Aucun message d'erreur — l'email "sylvie.test@test"
est accepté comme valide par le formulaire
**Statut :** À clarifier

*Note : Un email sans extension (.com, .fr...) n'est pas techniquement
valide. Sans specs, impossible de déterminer si ce comportement est voulu.*

---

### JS-CT-10 — Inscription avec un email valide
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test@test.com"
3. Cliquer dans le champ "Mot de passe" pour quitter le champ email

**Résultat attendu :** Adresse valide — pas de message d'erreur
**Résultat obtenu :** Adresse valide — pas de message d'erreur
**Statut :** Passé

---

## Analyse des valeurs limites — Mot de passe

*Règle affichée par l'application : 5 à 40 caractères. Analyse à 2 valeurs :
4 et 5 (borne basse), 40 et 41 (borne haute).*

### JS-CT-11 — Mot de passe trop court (moins de 5 caractères)
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test@test.com"
3. Cliquer dans le champ "Mot de passe"
4. Saisir "0000" (4 caractères)
5. Cliquer hors du champ

**Résultat attendu :** Message en rouge affiché : "Votre mot de passe
doit contenir au moins 5-40 caractères"
**Résultat obtenu :** Message en rouge affiché : "Votre mot de passe
doit contenir au moins 5-40 caractères"
**Statut :** Passé

---

### JS-CT-12 — Mot de passe valide (entre 5 et 40 caractères)
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test@test.com"
3. Cliquer dans le champ "Mot de passe"
4. Saisir "00000" (5 caractères)
5. Cliquer hors du champ

**Résultat attendu :** Message affiché dans la couleur de l'interface
(pas en rouge) : "Votre mot de passe doit contenir au moins 5-40 caractères"
**Résultat obtenu :** Message affiché dans la couleur de l'interface
(pas en rouge) : "Votre mot de passe doit contenir au moins 5-40 caractères"
**Statut :** Passé

---

### JS-CT-13 — Mot de passe à la limite haute (40 caractères)
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test@test.com"
3. Cliquer dans le champ "Mot de passe"
4. Saisir 40 caractères : "0000000000000000000000000000000000000000"
5. Cliquer hors du champ

**Résultat attendu :** Message affiché dans la couleur de l'interface
(pas en rouge) : "Votre mot de passe doit contenir au moins 5-40 caractères"
**Résultat obtenu :** Message affiché dans la couleur de l'interface
(pas en rouge) : "Votre mot de passe doit contenir au moins 5-40 caractères"
**Statut :** Passé

---

### JS-CT-14 — Mot de passe trop long (plus de 40 caractères)
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test@test.com"
3. Cliquer dans le champ "Mot de passe"
4. Saisir 41 caractères : "00000000000000000000000000000000000000000"
5. Cliquer hors du champ

**Résultat attendu :** Message en rouge affiché : "Votre mot de passe
doit contenir au moins 5-40 caractères"
**Résultat obtenu :** Message en rouge affiché : "Votre mot de passe
doit contenir au moins 5-40 caractères"
**Statut :** Passé