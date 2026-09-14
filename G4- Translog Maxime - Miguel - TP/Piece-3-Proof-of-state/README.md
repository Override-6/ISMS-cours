# Pièce 3 — Preuve d'état

**Ce qui est attendu** : *l'export daté de l'instance CISO Assistant, produit en séance 10 : ce que l'outil contenait au moment de la remise, lisible hors de l'outil.*

**État aujourd'hui : non produit, et c'est normal.** L'export se fait en séance 10, entre 8h30 et 9h15, au moment du dépôt. Ce dossier restera vide jusque-là.

## En attendant : les preuves intermédiaires

Les captures d'écran horodatées de l'instance sont rangées **avec la séance qui les a produites**, pas ici :

- `Piece-2-File/Session-2/3-Evidence/` — **6 captures** : liste des actifs du périmètre `MERIDIAN-LOGISTIQUE` (dont le Top 5 étiqueté), vue d'analyse d'impact.
- `Piece-2-File/Session-3/3-Evidence/` — **16 captures** : détail du référentiel ISO/IEC 27001:2022 (123 exigences, arbre de l'annexe A déplié en 37/8/14/34), évaluation de conformité rattachée au périmètre et portant auteurs + statut, 17 actifs avec propriétaires assignés, recherches en bibliothèque.
- `Piece-2-File/Session-4/3-Evidence/` — **5 captures** : auto-évaluation des douze exigences, mesures appliquées, taux de conformité, suivi outillé des trois constats gradés (*Follow-up*).
- `Piece-2-File/Session-5/3-Evidence/` — **24 captures** : matrice 4×4 importée, étude EBIOS RM créée, 17 actifs reliés, 7 événements redoutés, 5 couples SR/OV, rapport d'étude ateliers 1-2.
- `Piece-2-File/Session-6/3-Evidence/` — **13 captures** : écosystème coté (5 parties prenantes, 2 critiques `Selected`), 2 scénarios stratégiques et 3 chemins d'attaque, 1 scénario opérationnel, rapport d'étude ateliers 3-4.
- `Piece-2-File/Session-7/3-Evidence/` — **vide** : le TP 1 de la séance 7 n'a pas encore eu lieu. Les onze captures attendues y sont listées et nommées d'avance.

## À vérifier avant de produire l'export

L'export est la pièce qui montre **qui a créé quoi**. Le coefficient individuel en dépend pour moitié. Avant de le produire :

1. Chaque objet de l'instance porte un **auteur nommé** — actifs primaires, actifs support, périmètre, évaluation de conformité.
2. L'évaluation de conformité porte un **statut** (sans quoi elle est exclue de son propre rapport : *« Detected 1 audits (0 counted, 1 excluded): Unknown »*).
3. Le **domaine** des objets est `MERIDIAN-LOGISTIQUE`, un sous-domaine propre enfant du domaine racine `Global` ; le **périmètre** est `MERIDIAN-LOGISTIQUE-FINAL`, à l'intérieur de ce sous-domaine. Ne pas confondre les deux champs, et ne pas supposer que le domaine affiché est littéralement `Global` sans l'avoir vérifié sur l'objet *(précision apportée à la séance 4 ; une première rédaction de cette page disait `Global`, c'était imprécis)*.
4. Le **registre de risques** de la séance 7 et son plan de traitement sont dans l'étude, avec les coûts *build*/*run* saisis sur chaque mesure appliquée — c'est ce que l'aperçu budgétaire du *Plan d'action* additionne.

Suivi dans `fixes.md` **F5** (clos) et **F14**.
