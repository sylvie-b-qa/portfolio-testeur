# Cas de test — OWASP Juice Shop

## Partitions d'équivalence — Moteur de recherche

*La recherche se déclenche uniquement après validation par la touche Entrée.*

### CT-018 — Recherche avec un mot en français
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

### CT-019 — Recherche avec un mot en anglais
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

### CT-020 — Recherche avec deux mots "Apple Juice"
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

### CT-021 — Recherche avec un mot inexistant
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

### CT-022 — Recherche avec des caractères spéciaux
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

### CT-023 — Recherche avec le champ vide
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

## Partitions d'équivalence — Formulaire d'inscription

### CT-024 — Inscription avec un email sans @
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

### CT-025 — Inscription avec un email sans domaine
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

### CT-026 — Inscription avec un email sans extension
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

### CT-027 — Inscription avec un email valide
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

### CT-028 — Mot de passe trop court (moins de 5 caractères)
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

### CT-029 — Mot de passe valide (entre 5 et 40 caractères)
**Précondition :** Avoir cliqué sur "Compte", "Se connecter"
puis "Pas encore client"

**Étapes :**
1. Cliquer dans le champ "E-mail"
2. Saisir "sylvie.test@test.com"
3. Cliquer dans le champ "Mot de passe"
4. Saisir "00000" (5 caractères)
5. Cliquer hors du champ

**Résultat attendu :** Message en bleu affiché : "Votre mot de passe
doit contenir au moins 5-40 caractères"
**Résultat obtenu :** Message en bleu affiché : "Votre mot de passe
doit contenir au moins 5-40 caractères"
**Statut :** Passé

---

### CT-030 — Mot de passe trop long (plus de 40 caractères)
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
