# FIXES — MERIDIAN Logistique (Groupe 4, Translog)

**Source de vérité** : `ISMS module common thread.pdf` — version 2, 8 septembre 2026.
**Remise** : 17 septembre 2026 · **Instance** : `translog-b` · **périmètre** : `MERIDIAN-LOGISTIQUE`.

**Portée de ce journal : les séances 1 à 3 uniquement.** Ce sont les seules tenues à ce jour. Les livrables D4 à D9 (24 points sur 40) ne sont pas en retard — leurs séances n'ont pas eu lieu. Rien dans ce fichier ne les concerne.

> La règle qui gouverne tout : *la sous-section n de la note affirme ; la séance n du dossier prouve ; l'export montre que l'objet existe dans l'outil.* Une affirmation sans pièce derrière elle ne compte pas ; une pièce dont la note ne dit rien est du travail perdu.

---

## Tableau de bord

| # | Correction | Livrable | Points en jeu | Charge | État |
|---|---|---|---|---|---|
| **F5** | Les objets de l'outil ne portent **aucun propriétaire** | tous + coefficient | multiplicateur individuel | Petite | ☐ ouvert |
| **F4** | **Erreur ReCyF** : écrit comme absent de la bibliothèque, la capture le montre présent | D3 + S3-05 | exactitude | Petite | ✅ **fait** |
| **F3** | **Top 5 des actifs critiques** absent (élément exigé de D2) — bloque aussi la sous-section 2 de la note | D2 + note | **5** | Moyenne | 🔄 **dossier fait** — reste à marquer dans l'instance |
| **F1** | D3 fait 13 pages ; la consigne dit **deux pages plus l'export** | D3 | 4 | Moyenne | ✅ **fait** |
| **F2** | D3 n'a pas d'**estimation de la charge** (élément exigé) | D3 | 4 (partagé) | Petite | ✅ **fait** |
| **F6** | Les comptes **93 / 37-8-14-34** n'ont aucune capture derrière eux | preuve D3 | exactitude | Petite | 🔄 **capture à prendre** (l'affirmation, elle, est exacte) |
| **F7** | **Bureau du RSSI** : S1 absent ; S2 et S3 collectifs et hors format | bureau du RSSI | **10** (coef. 1) | Grande | 🔄 **les quatre pages de Miguel faites** (S1→S4) — restent les quatre de Maxime |
| **F8** | Le schéma de gouvernance D1 ne porte pas de **fréquences** | D1 | 4 (partagé) | Petite | ✅ **fait** |
| **F9** | La feuille de route chiffrée S1 ne doit **pas** figurer au rendu | hygiène D1 | 0 | Triviale | ✅ **fait** |
| **F10** | **Aucune séance ne présente son livrable comme un livrable** — D1 à D3 sont enfouis dans des comptes rendus d'exercices | D1 · D2 · D3 | **13** | Moyenne | ✅ **fait** — D1, D2, D3 |
| **F11** | La note de cadrage D1 n'énonce ni **enjeux** ni **contraintes** | D1 | 4 (partagé) | Petite | ✅ **fait** |

### Séance 3 — close au dossier

`Session-3/2-Labs/D3-note-de-business-case.md` est le livrable, en deux pages et cinq sections, portant **les cinq éléments exigés** — dont l'**estimation de la charge** *(F2)* : ≈ **60 jours-homme** la première année, décomposée poste par poste, hypothèses de productivité écrites pour être contestées, et ce qu'elle ne contient pas (remédiation déjà financée, audit non chiffré). Le rapport de 13 pages reste au dossier comme pièce d'appui *(F1)*.

**L'erreur ReCyF est corrigée partout** *(F4)* : dans S3-05, où l'« absence à observer » devient une **présence** assumée avec la correction datée conservée au dossier ; dans la grille du TD S3-03, où la note d'outillage passe de 2 à 3, le total de 195 à **205**, l'écart de 35 à **25 points**, et où les deux tests de bascule sont **recalculés** (212/223 et 170/185) ; dans le rapport long et son PDF, régénéré. L'enseignement en sort renforcé plutôt qu'affaibli : **ce n'est pas l'arithmétique qui porte la recommandation, c'est la règle de veto** — une condition, pas une note.

`Session-3/1-CISO-desk/S3-bureau-du-RSSI-Miguel-Monereo.md` répond à la question de la séance 3.

> ⚠️ **Reste** : la capture de l'arbre déplié montrant 93 contrôles en 37 / 8 / 14 / 34 *(F6)*. L'affirmation est exacte — c'est la composition de l'annexe A de la norme — mais **nous** n'en avons pas la preuve à l'écran, et le livrable est noté sur les objets exportés.

### Séance 2 — close au dossier, reste un geste dans l'outil

`Session-2/2-Labs/D2-cartographie-MERIDIAN-LOGISTIQUE.md` est le livrable, et il porte **les huit éléments exigés** — dont le **Top 5 justifié** *(F3)* et le **processus de mise à jour**, jusqu'ici resté dans le fichier du bureau du RSSI *(F10)*. Le Top 5 est classé sur un critère **écrit avant le classement** (niveau DICT porté, portée de l'atteinte, faiblesse connue et actuelle, absence de substitution), et le document dit aussi ce qu'il **écarte** et pourquoi — local serveur, entrepôts, scannettes, prestataire de maintenance.

La sous-section 2 de la note de stratégie, que F3 bloquait, est **rédigée** : elle s'articule à la sous-section 1 (la règle des trente jours est la gouvernance appliquée au terrain) et alimente la sous-section 3, qui l'attendait.

`Session-2/1-CISO-desk/S2-bureau-du-RSSI-Miguel-Monereo.md` répond à la question de la séance 2.

> ⚠️ **Reste dans l'outil** : la consigne D2 dit « instance **et** dossier ». Les cinq actifs du Top 5 (`SA-01`, `SA-04`, `SA-09`, `SA-05`, `SA-03`) doivent être repérables dans `translog-b` sans lire le fichier, puis la liste des actifs recapturée dans `3-Evidence/`.

### Séance 1 — close, sauf la page de Maxime

`Session-1/2-Labs/D1-note-de-cadrage-et-gouvernance-cible.md` est le livrable, en deux pages : périmètre et **exclusions assumées**, **enjeux** dits en langage de mission, parties prenantes avec ce qu'elles doivent en retour, **contraintes** réelles *(F11)* ; puis schéma à trois niveaux **avec fréquences** *(F8)*, matrice de responsabilité, cinq directives codifiées, trois règles d'arbitrage. Les deux comptes rendus de TP restent à côté comme trace de méthode, et un `README` de dossier dit lequel est noté et rappelle que la feuille de route chiffrée n'est pas au rendu *(F9)*.

`Session-1/1-CISO-desk/S1-bureau-du-RSSI-Miguel-Monereo.md` répond à la question de la séance 1. **La page de Maxime reste à écrire** : la note est individuelle, deux pages semblables coûteraient aux deux auteurs. Trois angles distincts lui sont proposés dans le `README` du dossier.

Barème : D1 4 · D2 5 · D3 4 · D4 4 · D5 3 · D6 7 · D7 5 · D8 2 · D9 3 · note de stratégie 3 = **40 points**, convertis sur 20, coefficient 4 sur 10.

**Ordre de travail conseillé** : F5 et F4 d'abord — petites, et l'une des deux est une contre-vérité posée sous les yeux d'un correcteur qui dispose des mêmes captures que nous. Puis F3, le plus gros livrable. Puis F1 + F2 + F6 ensemble, qui atterrissent tous dans la même note de deux pages. Puis F7, le plus gros travail d'écriture. F8 et F9 se ferment quand on veut.

---

## F5 · Les objets de l'outil ne portent aucun propriétaire

**Preuve** : `Piece-2-File/Session-3/3-Evidence/S3-05-ex3-compliance-assessment-detail.jpg`.

Ce qui est bon : nom `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, périmètre `Global/MERIDIAN-LOGISTIQUE`, référentiel ISO/IEC 27001:2022, vierge, créée le 9/7/2026 à 14h03.
Ce qui est vide : **Authors, Reviewers, Status, Description, ID**.

**Pourquoi cela coûte des points.** Le coefficient individuel — 0,85 / 0,95 / 1,05 / 1,15, appliqué **aux deux** composantes collectives (livrables coef. 4, soutenance coef. 3) — repose sur deux éléments de poids égal, dont le premier est *« la traçabilité nominative dans l'outil, où chaque objet créé porte un propriétaire »*.

Second symptôme : le rapport de référentiel affiche *« Detected 1 audits (0 counted, 1 excluded): Unknown 1 »* — faute de statut, notre évaluation est exclue de son propre rapport.

> **Correction du 8 septembre 2026** : une version antérieure de cette fiche demandait aussi de remplacer le domaine `Global` par `MERIDIAN-LOGISTIQUE`. **C'était une erreur**, reprise d'une convention de notre propre S2-05 qui confondait deux champs : dans CISO Assistant, le **domaine** est le dossier organisationnel — `Global` y est la valeur normale — et c'est le **périmètre** (`MERIDIAN-LOGISTIQUE`) qui porte le rattachement noté. **Ne pas toucher au domaine.**

**Fini quand** : auteurs renseignés sur l'évaluation **et** sur tous les actifs, statut posé pour que l'audit soit compté par son propre rapport, puis nouvelles captures dans `Session-3/3-Evidence/`. Le domaine reste `Global`.

> ⚠️ **Travail dans l'outil, pas dans les fichiers.** Ces champs se règlent dans le navigateur sur `translog-b`. Je peux fournir la liste champ par champ ; la saisie vous revient.

---

## F4 · L'affirmation sur le ReCyF est contredite par nos propres preuves

**Preuve** : `Piece-2-File/Session-3/3-Evidence/S3-05-ex4-library-search-ReCyF-FOUND-see-note.jpg` — le référentiel est **présent** dans la bibliothèque : fournisseur **ANSSI**, id `ReCyF`, *« RECYF : RÉFÉRENTIEL CYBER France – Version 2.5 du 17/03/2026 »*, built-in, langue française, date de publication **2026-07-09**, « Showing 1 to 1 of 1 ».

**Ce qui le contredit**

| Emplacement | Texte erroné |
|---|---|
| `Session-3/2-Labs/…S3-05…md`, Ex. 4 | *« Recherché dans la liste : **introuvable**, et c'est **normal**… cette version est antérieure à la publication du ReCyF »* — ainsi que toute la leçon « l'outil a un millésime » bâtie dessus |
| `Session-3/2-Labs/MERIDIAN-business-case…md`, §II.3 | *« No library in the group instance: the tool's build predates the framework's March 2026 publication »* |
| idem, §III.1 provenance | *« ReCyF does not appear in the instance's library, and that is normal »* |

**Effet sur la recommandation : aucun.** Si la note d'outillage du ReCyF passe de 2 à 3, son total va de 195 à **205** contre **230** pour ISO — l'écart se resserre de 35 à 25 mais ne bascule pas. La règle de veto l'écarte toujours comme **colonne vertébrale** sur la couverture, indépendamment de la note.

**Fini quand** : l'Ex. 4 de S3-05 est réécrit autour de ce qui est réellement à l'écran ; les deux passages de la note de business case sont corrigés ; l'analyse de sensibilité dit 25 et non 35, et pourquoi cela tient toujours.

---

## F3 · Le Top 5 des actifs critiques est absent

**La consigne**

> **D2** Cartographie de la filiale : valeurs métier, biens supports, besoins DICT, dépendances inter-filiales, **top 5 justifié des actifs critiques**, lacunes assumées, processus de mise à jour. — Instance et dossier · **5 points**

**Où nous en sommes.** La seule mention dans nos fichiers est un renvoi en avant, `Session-2/2-Labs/…S2-05…md` ligne 112 : *« Ce point de sortie sert directement d'entrée au prochain TP (S2-06, extraction du Top 5). »* Le Top 5 lui-même a été produit en plénière et, comme notre propre S3-06 l'admet, *« ne figure pas dans le dossier écrit de notre groupe »*.

**Double conséquence.** C'est le plus gros livrable des trois séances (5 points) **et** cela bloque la **sous-section 2 de la note de stratégie**, qui reste à écrire — d'autant que la sous-section 3, déjà rédigée, s'y articule explicitement (*« les actifs critiques cessent d'être une liste et deviennent un objet d'évaluation »*). Une sous-section qui renvoie à une pièce absente ne compte pas.

**Fini quand** : cinq actifs critiques tirés de notre propre inventaire `LOG-PA` / `LOG-SA`, chacun justifié d'une phrase adossée aux notations DICT de S2-03, présents dans `Session-2/2-Labs/` **et** dans l'instance ; puis la sous-section 2 de la note rédigée.

---

## F1 · D3 fait 13 pages, la consigne en demande deux

**La consigne**

> **D3** Note de business case : qualification réglementaire, choix argumenté du référentiel, options écartées, matrice de correspondance, estimation de la charge. — **Deux pages plus l'export** · 4 points

**Où nous en sommes.** `Session-3/2-Labs/MERIDIAN-business-case-framework-selection.md` (et son PDF) font 13 pages. Ce format répondait à une commande passée avant que cette consigne soit disponible. Il est **hors format en tant que D3**.

**Pourquoi ce n'est pas perdu.** La pièce 2 est libre de forme et veut les TP de chaque séance : le rapport long y a sa place comme pièce d'appui de la séance 3, celle qui prouve les affirmations de la note de deux pages.

**Fini quand** : une note D3 de deux pages strictes portant les cinq éléments exigés, plus l'export ; le rapport de 13 pages requalifié en pièce d'appui de séance 3.

---

## F2 · D3 n'a pas d'estimation de la charge

**Absence confirmée** — aucune occurrence de *charge de travail / workload / jours-homme / ETP / person-day* dans tout le dossier.

Ce n'est **pas** le chiffrage de certification déjà écrit au §III.2 du rapport long : celui-ci diffère un **prix**. La consigne demande un **effort** — ce que le travail va prendre en jours-homme.

**Fini quand** : une estimation de charge avec sa base explicite — évaluation initiale sur les 123 exigences importées, collecte des preuves par filiale, travail d'arrêt du périmètre — exprimée en jours-homme, chaque hypothèse nommée.

---

## F6 · Les comptes 93 / 37-8-14-34 n'ont aucune preuve derrière eux

`Session-3/3-Evidence/S3-05-ex2-framework-detail-123-requirements-annexA-4themes.jpg` confirme **123** exigences associées et les deux blocs (`core - Clauses`, `annex-a - Statement of Applicability`) avec les quatre thèmes A.5 / A.6 / A.7 / A.8 — mais l'arbre est **replié**, donc aucun compte par thème n'est visible.

S3-05 et la note de business case affirment pourtant **93** et **37 / 8 / 14 / 34** comme des faits.

**Fini quand** : soit une capture arbre déplié montrant les comptes, soit l'affirmation ramenée à ce que la preuve soutient.

---

## F7 · Le bureau du RSSI : format et auteur

**La consigne**

> Le bureau du RSSI est écrit : **chaque étudiant** répond, en **une page au plus**, à la question du jour transposée à sa filiale, et **clôt par une recommandation adressée à sa direction** ; c'est la seule note individuelle courant sur les neuf séances.

Barème : justesse et pertinence 4 · posture RSSI, une page tenue, recommandation explicite 3 · écriture lisible par un dirigeant non technique 3 = **10 points, coefficient 1**.

**Les trois questions**

| Séance | Question du jour | Notre fichier | Problème |
|---|---|---|---|
| S1 | De quoi un conseil d'administration a-t-il réellement besoin de son RSSI ? | *aucun* | **Absente.** Le TD S1-03 rangé en `4-Working-notes/` porte sur les principes structurants — autre sujet |
| S2 | Pourquoi tout inventaire d'actifs est-il faux, et qu'en fait-on ? | `Session-2/1-CISO-desk/…S2-01…md` | Bon sujet, mais collectif et long |
| S3 | Sommes-nous dans le champ de NIS 2, et à quel titre ? | `Session-3/1-CISO-desk/…S3-01…md` | Bon sujet, mais collectif et **199 lignes** contre une page |
| S4 | Que vaut une certification ISO 27001, et que répond-on au tiers qui l'exige ? | `Session-4/1-CISO-desk/S4-…-Miguel-Monereo.md` | ✅ page de Miguel rendue ; **celle de Maxime reste à écrire** |

Tous portent l'en-tête *« Réponses du Groupe 4 »* — collectif, là où la note est **individuelle**. Le fond est là ; le format et l'auteur ne le sont pas.

**Fini quand** : une page par étudiant et par séance — Miguel et Maxime séparément, **huit pages en tout à ce jour** (S1 à S4) — chacune close par une recommandation explicite à la direction.

> ⚠️ **Décision à prendre avant de commencer** : c'est la seule note individuelle, vous ne pouvez donc pas rendre la même page. Qui prend quelle séance, ou chacun écrit-il les trois de son côté ?

---

## F8 · Le schéma de gouvernance D1 ne porte pas de fréquences

**La consigne** : *« schéma de gouvernance à trois niveaux avec les instances, leurs **fréquences** et la nature des décisions »*.

**Où nous en sommes** : `Session-1/2-Labs/…S1-05…md` section 1 donne instance / rôle en gouvernance / rôle sur l'appétence. La seule cadence de tout le fichier est `[PSSI-CADRE-ACC-02]`, une revue trimestrielle des privilèges — une directive, pas une fréquence de réunion. Aucune instance ne porte de fréquence.

**Fini quand** : une fréquence par instance (Conseil d'Administration, Direction Générale, Comité Exécutif, reporting du RSSI Groupe), cohérente avec la revue trimestrielle déjà promise dans la note de cadrage.

---

## F9 · La feuille de route chiffrée ne fait pas partie du rendu

**La consigne**

> La feuille de route pluriannuelle chiffrée de la séance 1 est conservée par le groupe mais **ne fait pas partie du rendu** : elle est le sujet du rattrapage. La note de cadrage, elle, reste en séance 1 du dossier comme preuve de gouvernance.

`Session-1/2-Labs/…S1-06…md` Exercice 2 est la feuille de route et son budget. À conserver, mais à ne pas présenter comme livrable de séance 1. Les axes budgétaires restent légitimement **cités** par la note de business case comme l'enveloppe dans laquelle la décision s'inscrit.

**Fini quand** : la séance 1 met en avant la note de cadrage et la gouvernance cible ; la feuille de route est clairement identifiée comme matière conservée.

---

## F10 · Aucune séance ne présente son livrable comme un livrable

**Le problème est structurel, et il porte sur les trois séances à la fois.** Le barème note **D1, D2, D3**. Or aucun fichier du dossier ne s'appelle D1, D2 ou D3, et aucun n'est le livrable : ce sont des comptes rendus d'exercices, qui *contiennent* le livrable quelque part.

| Livrable | Format exigé | Où il se trouve réellement |
|---|---|---|
| **D1** | Note de cadrage **et** gouvernance cible — **deux pages, document** | **Éclaté sur deux fichiers** : la note de cadrage est l'Exercice 1 de `…S1-06…md`, la gouvernance cible est l'Exercice 2 de `…S1-05…md`. Aucun des deux n'est un document de deux pages ; les deux sont des comptes rendus avec consignes, corrigés et auto-évaluation |
| **D2** | Instance et dossier — pas de limite de pages | `…S2-05…md` est le plus proche d'un livrable propre. Mais le **processus de mise à jour** exigé par D2 ne s'y trouve pas : il est dans le fichier du bureau du RSSI (`…S2-01…md`, la règle des trente jours) |
| **D3** | **Deux pages plus l'export** | La note de deux pages est l'Exercice 1 de `…S3-06…md`, noyée entre la revue par les pairs et l'auto-évaluation — et un rapport de 13 pages lui fait concurrence dans le même dossier |

**Pourquoi cela coûte cher.** Un correcteur qui ouvre `Session-1/2-Labs/` cherche « le document de deux pages » et trouve deux comptes rendus de TP. Le travail est fait ; il n'est pas *présenté*. C'est 13 points de livrables qui dépendent d'un rangement, pas d'une rédaction supplémentaire.

**Fini quand** : chaque séance porte un fichier livrable nommé, autonome, au format exigé — `D1-note-de-cadrage-et-gouvernance-cible.md`, `D2-cartographie-MERIDIAN-LOGISTIQUE.md`, `D3-note-de-business-case.md` — les comptes rendus d'exercices restant à côté comme trace de méthode.

---

## F11 · La note de cadrage n'énonce ni enjeux ni contraintes

**La consigne D1** : *« périmètre, **enjeux**, parties prenantes, **contraintes** »*.

**Où nous en sommes** : la note de cadrage de `…S1-06…md` a cinq sections — but, périmètre, prérogatives, contreparties, limites.

| Élément exigé | Correspondance | État |
|---|---|---|
| Périmètre | « Périmètre » — 4 filiales, division mutualisée, flux inter-filiales | ✅ |
| Parties prenantes | « Contreparties » — DG, ComEx, CA, Auditeur interne | ✅ |
| Enjeux | « But » donne la raison de créer le poste, pas les enjeux de la filiale | ⚠️ mince |
| Contraintes | « Limites » sont les exclusions du **mandat** du RSSI, pas les contraintes d'exercice | ❌ absent |

Les contraintes réelles existent pourtant dans le dossier et ne sont écrites nulle part dans la note : RSSI nommé depuis six semaines, **sans prédécesseur, sans PSSI, sans budget consolidé**, et l'exigence de la Direction Générale de **ne pas engager de budget nouveau la première année**.

**Fini quand** : la note de cadrage porte une section « enjeux » adossée à la mission de la filiale et une section « contraintes » reprenant celles qui sont déjà établies au dossier — sans les confondre avec les limites du mandat, qui restent utiles et distinctes.

---

## Vérifié bon — ne pas rouvrir

- **123 exigences** importées, deux blocs, quatre thèmes d'annexe A — capture à l'appui.
- **Évaluation créée, vierge, rattachée à `MERIDIAN-LOGISTIQUE`**, datée du 9/7/2026 — capture à l'appui ; vierge est l'état correct à ce stade.
- **Captures de bibliothèque** pour le guide d'hygiène, DORA, HDS v2.0 et RGS 2.0 Annexe B2 — le tri et les « options écartées » de D3 sont prouvés.
- **Listes d'actifs** (2 captures) et vue d'analyse d'impact pour D2.
- **Qualification réglementaire** (élément 1 de D3) traitée filiale par filiale, les deux lectures conservées pour Logistique.
- **Matrice de correspondance** (élément 4 de D3) présente, anatomie à quatre champs, aucune ligne « equivalence ».
- **Note de stratégie** : sous-sections 1 et 3 rédigées et assemblées en pièce 1 ; budget de 3 à 5 pages intact.
- **Structure du dossier** : trois pièces séparées, séances identifiables, bureau du RSSI et TP distingués dans chacune.

---

## Journal

| Date | Action |
|---|---|
| 8 sept. 2026 | Dossier réorganisé en trois pièces ; note de stratégie assemblée en pièce 1 ; neuf corrections ouvertes. Sauvegarde de l'état antérieur : `.FIRST_TP-backup-20260908-115436`. |
| 8 sept. 2026 | Audit de la pièce 2 : deux corrections supplémentaires ouvertes (**F10** livrables non présentés comme tels, **F11** enjeux et contraintes absents du cadrage). |
| 8 sept. 2026 | **Séance 1 corrigée** : livrable `D1` assemblé en deux pages (F10, F11, F8), bureau du RSSI de Miguel écrit (F7 partiel), feuille de route sortie du rendu (F9). Reste la page de Maxime. |
| 8 sept. 2026 | **Séance 2 corrigée** : livrable `D2` assemblé avec le **Top 5 justifié** et le processus de mise à jour (F3, F10), bureau du RSSI S2 de Miguel écrit (F7), **sous-section 2 de la note de stratégie débloquée et rédigée**. Reste le marquage du Top 5 dans l'instance. |
| 8 sept. 2026 | **Séance 4 ouverte** : bureau du RSSI S4 de Miguel écrit à partir du TD 1 « La valeur de la certification ISO 27001 » — mécanique en trois maillons, arbitrage de périmètre, mise au point NIS 2, réponse au client pharmaceutique (F7). Reste la page de Maxime, ainsi que le TP et le livrable D4. |
| 8 sept. 2026 | **Séance 3 corrigée** : livrable `D3` en deux pages avec estimation de charge (F1, F2, F10), **erreur ReCyF corrigée dans les quatre fichiers concernés et arithmétique de la grille recalculée** (F4), bureau du RSSI S3 de Miguel écrit (F7). Restent la capture de l'annexe A (F6) et les objets de l'outil (F5). |
