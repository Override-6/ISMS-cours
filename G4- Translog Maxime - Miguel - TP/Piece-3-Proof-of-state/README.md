# Pièce 3 — Preuve d'état

**Ce qui est attendu** : *l'export daté de l'instance CISO Assistant, produit en séance 10 : ce que l'outil contenait au moment de la remise, lisible hors de l'outil.*

**État aujourd'hui : non produit, et c'est normal.** L'export se fait en séance 10, entre 8h30 et 9h15, au moment du dépôt. Ce dossier restera vide jusque-là.

## En attendant : les preuves intermédiaires

Les captures d'écran horodatées de l'instance sont rangées **avec la séance qui les a produites**, pas ici :

- `Piece-2-File/Session-2/3-Evidence/` — liste des actifs du périmètre `MERIDIAN-LOGISTIQUE`, vue d'analyse d'impact.
- `Piece-2-File/Session-3/3-Evidence/` — détail du référentiel ISO/IEC 27001:2022 (123 exigences), évaluation de conformité initiale rattachée au périmètre, recherches en bibliothèque.

## À vérifier avant de produire l'export

L'export est la pièce qui montre **qui a créé quoi**. Le coefficient individuel en dépend pour moitié. Avant de le produire :

1. Chaque objet de l'instance porte un **auteur nommé** — actifs primaires, actifs support, périmètre, évaluation de conformité.
2. L'évaluation de conformité porte un **statut** (sans quoi elle est exclue de son propre rapport : *« Detected 1 audits (0 counted, 1 excluded): Unknown »*).
3. Le **domaine** des objets reste `Global` — c'est la valeur normale. Le rattachement qui compte est le **périmètre**, `MERIDIAN-LOGISTIQUE` : ne pas confondre les deux champs.

Suivi dans `fixes.md` **F5**.
