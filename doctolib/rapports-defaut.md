# Rapports de défaut — Doctolib.fr

## BUG-001 — Repli silencieux sur la géolocalisation lors de la saisie d'un code postal invalide

**Date :** 06/06/2026
**Application :** Doctolib.fr
**Testeur :** Sylvie B
**Sévérité :** Mineur
**Priorité :** Basse

**Étapes pour reproduire :**
1. Ouvrir doctolib.fr
2. Cliquer sur le champ "Lieu"
3. Saisir un code postal à 6 chiffres : "699600"
4. Observer le comportement de l'autocomplétion

**Résultat obtenu :** Seule l'option "Autour de moi" s'affiche. Aucun message d'erreur ni indication à l'utilisateur que sa saisie est invalide. Le système se replie silencieusement sur la géolocalisation.

**Résultat attendu :** Comportement à clarifier. Option A : afficher un message "Code postal invalide". Option B : si le repli est voulu, l'indiquer clairement à l'utilisateur.

**Impact utilisateur :** Faible. L'utilisateur obtient des résultats près de chez lui par défaut. Risque : il ne comprend pas pourquoi sa recherche géographique précise est ignorée.

**Statut :** À clarifier

---

## BUG-002 — Des établissements non médicaux apparaissent dans une recherche "Médecin généraliste"

**Date :** 06/06/2026
**Application :** Doctolib.fr
**Testeur :** Sylvie B
**Sévérité :** Mineur
**Priorité :** Basse

**Étapes pour reproduire :**
1. Saisir "Médecin généraliste" dans le champ Spécialité et "69960" dans le champ Lieu
2. Cliquer sur "Rechercher"
3. Observer les résultats et scroller pour voir tous les types d'établissements affichés

**Résultat obtenu :** Des établissements autres que des médecins généralistes apparaissent : pharmacies (Pharmacie de l'Europe, Pharmacie du Village), maisons de santé, centres d'imagerie, angiologues, cabinets médicaux.

**Résultat attendu :** Comportement à clarifier. Option A : seuls les médecins généralistes s'affichent. Option B : si l'élargissement est voulu, l'indiquer clairement à l'utilisateur.

**Impact utilisateur :** Faible. L'élargissement peut aider l'utilisateur à trouver des soins de proximité, mais sans indication claire cela peut créer de la confusion.

**Statut :** À clarifier
