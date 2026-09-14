# Séance 7 — TP · livrable D7 (5 points)

**État : rien n'est encore produit ici.** Les deux TD de la séance sont rendus ; les deux TP ne sont pas
faits. Ce dossier reste vide jusqu'à ce qu'ils le soient — un vide documenté vaut mieux qu'un vide qui passe
pour un oubli.

| Fichier attendu | Rôle | Noté |
|---|---|---|
| `PLAN-Seance-7-TP-S7-05-atelier4-et-registre.md` | Le mode opératoire du TP 1, écrit **avant** la saisie (format des séances 4, 5 et 6) | trace de méthode |
| `Seance-7-TP-S7-05-feuille-de-travail-atelier4-et-registre.md` | La feuille de travail du TP 1 : scénarios opérationnels, vraisemblances justifiées, registre, résiduels, **note d'écart** | trace de méthode |
| **`D7-plan-de-traitement-et-risque-residuel.md`** | **Le livrable D7** — plan de traitement priorisé sur trois ans, fiches d'acceptation, demandes de dérogation | ✅ **5 points** |
| `Seance-7-TP-S7-06-acceptations-et-derogations.md` | La feuille de travail du TP 2 si D7 déborde | trace de méthode |

---

## TP 1 — Atelier 4 détaillé et registre de risques dans `translog-b`

**Source** : `../../../../S7 - Sources/TP 1/Atelier 4 détaillé et Registre de risques dans CISO Assistant _ Lockbay Academy.pdf`

Quatre étapes, et **rien ne se recrée** : l'étude ouverte en séance 5 et enrichie en séance 6 est le support.

1. **Décliner les chemins d'attaque en scénarios opérationnels** (25 min) — au minimum les **deux** qui
   passent par les parties prenantes critiques (l'intégrateur des automates, dangerosité 12,0 ; APPLICA,
   8,0). Chaque étape nomme un **bien support de l'inventaire de la séance 2** et dit ce qui s'y oppose
   aujourd'hui : mesure du socle, cloisonnement, authentification, journalisation, ou **rien**. Un bien
   support absent de l'inventaire est un **trou de cartographie à noter**, pas un objet à inventer.
   *État de départ* : 1 scénario opérationnel existe déjà (séance 6, `Very likely`, `High`) pour SS1 ; SS2
   n'en a pas encore.
2. **Estimer la vraisemblance maillon par maillon** (20 min) — V1 à V4, **échelle de D5 telle quelle**.
   L'étape qui oppose le **plus de résistance** commande la note de l'ensemble. La justification cite un
   signal vérifiable : un écart de l'audit de la séance 4, une pratique observée, la maturité et la
   confiance cotées à l'atelier 3, un incident public comparable. *Piège* : coter au vu de la gravité.
3. **Constituer le registre** (25 min) — atelier 5, activité 1, **généré une seule fois**. L'outil y ajoute
   les **événements redoutés sans scénario** (chez nous : ER3 chaîne du froid et ER5 réapprovisionnement
   Santé, signalés dans D5) — à coter à leur tour. Aucun scénario sans décision ; chaque réduction porte
   mesure, **porteur pris dans la carte du pouvoir du pack §3** et échéance ; chaque acceptation, sa
   motivation, son réexamen et l'instance signataire. **Le contrôle qualité de l'outil passé au vert fait
   partie du livrable.**
4. **Coter le risque résiduel** (20 min) — **après la décision, jamais avant**. L'outil refuse un résiduel
   supérieur au niveau actuel : ce refus est une règle de méthode, pas une gêne. Confronter chaque résiduel
   à la ligne d'acceptation ; ceux qui restent au-dessus vont en renforcement ou en **dérogation motivée**.

> **La note d'écart fait partie du livrable** : ce que l'outil a fait découvrir et que le brouillon ne
> contenait pas, plus les libellés d'écran divergents. Les séances 5 et 6 en ont produit six et deux — c'est
> le passage le plus convaincant en soutenance.

## TP 2 — Plan de traitement, risque résiduel (D7) et note de stratégie

**Source** : `../../../../S7 - Sources/TP 2/Plan de traitement, risque résiduel (D7) et Note de stratégie _ Lockbay Academy.pdf`

### Les quatre exigences d'acceptation de D7, vérifiées une par une

| # | Exigence | Ce qu'elle ferme |
|---|---|---|
| **1** | **Aucun risque du registre sans décision** | la porte du **risque orphelin** — identifié, coté, puis laissé sans suite |
| **2** | **Tout résiduel qui dépasse l'appétence de la séance 5 porte une dérogation motivée** | la porte de l'**acceptation implicite** — un résiduel inacceptable porté par personne |
| **3** | **Cotations cohérentes avec les échelles de D5, jamais recréées** | la porte de la **cotation opportuniste** — qui change d'échelle quand le résultat déplaît |
| **4** | **Chaque risque porte son option, ses mesures, son responsable, son échéance et son résiduel coté** | la traçabilité de bout en bout |

### Le gabarit du plan de traitement

Organisé **par décision, pas par scénario** — un comité arbitre des décisions. Les mesures qui traitent
plusieurs risques à la fois se regroupent : ce sont les meilleures. Ce qui relève d'une **décision de
direction** (engager un budget, renoncer à une activité, accepter un risque) est séparé visiblement de ce
qui relève de l'**exécution**.

| Décision et risque visé | Mesure | Porteur et échéance | Coût (build, run, amortissement, annuel) | Effet sur la cotation |
|---|---|---|---|---|

**La charge se saisit dans l'outil**, sur chaque mesure appliquée, section *Coût* : build = « Coût fixe » +
« Jours-personnes nécessaires pour la mise en œuvre » ; run = « Coût fixe » annuel + « Jours-personnes
nécessaires annuellement » ; puis la « Durée d'amortissement (années) » du build. Taux journalier de
l'instance : **500 € par défaut** (*Paramètres → Général → Paramètres financiers*), **à laisser tel quel**.
L'onglet *Plan d'action* donne le **total dans son aperçu budgétaire** — et ce total se met **en face de la
fourchette du coût de l'inaction du matin** (`../1-CISO-desk/Seance-7-TD-S7-01-…`) : c'est l'arbitrage promis
au Directeur Financier. Là où le dossier ne donne rien, coût fixe à zéro et jours-personnes estimés
suffisent, **en le disant**.

### Acceptations et dérogations

- **Acceptation simple — cinq éléments** : le risque tel qu'il est coté · la raison de l'accepter ·
  l'instance qui accepte · la date · l'échéance de réexamen.
- **Dérogation — les cinq, plus trois** : pourquoi le traitement supplémentaire n'est pas engagé · ce qu'il
  faudrait pour l'engager · à quelle condition la dérogation tomberait.
- **L'instance** : une acceptation se signe **au niveau où l'appétence a été fixée** (chez nous la Direction
  Générale du groupe, D1 et D5 §1), une dérogation à ce niveau ou au-dessus — **jamais** un directeur de
  filiale sur un risque de groupe. S'il n'y a aucune dérogation à demander, **l'écrire et dire pourquoi**.
- **La phrase à ne jamais écrire** : *« Risque accepté par le RSSI. »*

### Sous-section 7 de la note de stratégie

Trois choses suffisent : la **position du groupe sur l'acceptabilité du risque**, les **décisions
structurantes** prises ce jour, et **ce qui reste ouvert avec l'échéance** à laquelle ce sera tranché. Rien
ne se supprime dans les sous-sections 1 à 6 ; si l'appétence de la séance 5 ne résiste pas aux cotations du
jour, elle s'**amende** d'une phrase datée au journal des amendements. Budget : 3 à 5 pages de texte, six
sous-sections ≈ 3 pages — la septième se rédige serré.

### Ce qui s'emporte vers la séance 8

La déclaration d'applicabilité (D8) justifiera l'inclusion de **chaque mesure du référentiel** par un risque
de D7 ou par une exigence légale ou contractuelle. Donc, **à vérifier avant de rendre D7** : chaque mesure du
plan est formulée de façon à pouvoir être rapprochée d'une exigence d'ISO/IEC 27001:2022 (le référentiel
retenu en séance 3). *« Renforcer la sécurité des accès »* ne se rapproche de rien ; *« supprimer les comptes
d'administration partagés au profit de comptes nominatifs tracés »* se rattache à `A.5.16`/`A.8.2` et se
vérifie.

---

**Deux points de vigilance, constants depuis la séance 1.** Le livrable, c'est `D7-…` : autonome, nommé, au
format exigé ; les feuilles de travail restent à côté comme trace de méthode, jamais à sa place. Et chaque
objet créé ou modifié dans `translog-b` se capture dans `../3-Evidence/` — c'est la moitié du coefficient
individuel.
