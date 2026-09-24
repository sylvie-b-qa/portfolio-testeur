# Portfolio testeur logiciel

**Sylvie B — Candidate ISTQB CTFL v4.0**

## Qui je suis

En reconversion vers le test logiciel après 15 ans d'expérience dans
l'administratif, j'ai réalisé que je possédais déjà les compétences clés
du métier : la rigueur, l'analyse et la curiosité. Il ne me manquait que
le cadre technique.

## Projets

### Doctolib.fr — Session de test pratique (Juin 2026)

Application des techniques du syllabus ISTQB CTFL v4.0 sur le moteur de
recherche et le parcours de prise de rendez-vous.

- 19 cas de test conçus, 17 exécutés (partitions d'équivalence, analyse des
  valeurs limites, tables de décision, transitions d'état)
- 3 anomalies à clarifier, dont 2 ont fait l'objet d'un rapport de défaut
- Bilan : rapport de clôture des tests

[Voir le détail du projet](./doctolib/)

---

### OWASP Juice Shop — Session de test pratique (Juin 2026)

Application des techniques du syllabus ISTQB CTFL v4.0 sur le moteur de
recherche et le formulaire d'inscription de cette application web
volontairement vulnérable, publiée par l'OWASP.

- 14 cas de test conçus et exécutés (partitions d'équivalence, analyse des
  valeurs limites)
- 4 anomalies à clarifier
- 2 rapports de défaut
- Bilan : rapport de clôture des tests

[Voir le détail du projet](./juice-shop/)

---

## Organisation du dépôt

Chaque projet contient les mêmes documents, à lire dans l'ordre :

1. **Plan de test** — objectif, périmètre, techniques, critères d'entrée et de sortie
2. **Cas de test** — avec un tableau de traçabilité en tête
3. **Rapports de défaut**
4. **Bilan** — rapport de clôture des tests (métriques, couverture, anomalies non résolues)

Les identifiants sont préfixés par projet : `DOC-` pour Doctolib, `JS-` pour Juice Shop
(ex. DOC-CT-01 pour un cas de test, JS-BUG-01 pour un défaut).

## Techniques appliquées

- Partitions d'équivalence
- Analyse des valeurs limites
- Tables de décision
- Transitions d'état
- Test exploratoire (phase d'exploration préalable à la conception)

## Certification en cours

ISTQB Certified Tester Foundation Level v4.0 (CTFL) : en préparation, passage envisagé en octobre 2026