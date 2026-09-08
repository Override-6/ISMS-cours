# MERIDIAN LOGISTIQUE — dossier du Groupe 4 (Translog)

**Module M2-01-4-ISMS** · Security governance and information system mapping
**Groupe 4 — Translog** · Miguel Monereo, Maxime · filiale d'instruction **MERIDIAN Logistique**
**Instance** `translog-b` (https://translog-b.lockbay.eu) · **périmètre** `MERIDIAN-LOGISTIQUE`

---

## Avancement : séances 1 à 3 sur 9, séance 4 en cours (TP 1 fait)

Le bloc 1 (séances 1–2, fondations) et la première séance du bloc 2 (séance 3, choix du référentiel) sont faits, livrables compris. La séance 4 est **en cours** : le bureau du RSSI y est clos (Miguel et Maxime), et le **TP 1 — auto-évaluation dans CISO Assistant — est fait** (les douze exigences retenues sont saisies dans `translog-b`, les quatre mesures appliquées sont créées, la feuille de travail est rédigée). Reste le **TP 2**, qui écrit le livrable `D4` (rapport d'audit initial) à partir de cette matière. **Les séances 5 à 9 n'ont pas encore eu lieu** — les emplacements correspondants n'existent donc pas encore dans ce dossier, et c'est normal à cette date.

| Séance | Thème | Livrable | Points | État |
|---|---|---|---|---|
| **S1** | Gouvernance : niveaux, acteurs, principes | **D1** Note de cadrage et gouvernance cible | 4 | ✅ **livrable assemblé**, bureau du RSSI clos *(F7)* |
| **S2** | Cartographie du SI | **D2** Cartographie de la filiale | 5 | ✅ **livrable assemblé** — reste le marquage dans l'instance *(F3)* |
| **S3** | Choix du référentiel | **D3** Note de business case | 4 | ✅ **livrable assemblé** |
| **S4** | Audit · valeur de la certification | **D4** | 4 | 🔄 bureau du RSSI clos, **TP 1 fait** (auto-évaluation, douze exigences + quatre mesures dans l'instance) — **TP 2 et livrable `D4` à venir** |
| S5–S9 | Risque, tiers, traitement, SMSI, indicateurs | D5 à D9 | 20 | ⏳ séances non tenues |
| S1–S9 | — | Note de stratégie | 3 | 🔄 3 sous-sections sur 9, **toutes rédigées** |

**Barème des livrables : 40 points** (D1 4 · D2 5 · D3 4 · D4 4 · D5 3 · D6 7 · D7 5 · D8 2 · D9 3 · note 3), convertis sur 20, coefficient 4 sur 10.
**Remise : 17 septembre 2026.**

👉 **Les corrections en cours sont suivies dans [`fixes.md`](fixes.md).**

---

## Comment ce dossier est rangé

Le rendu se compose de **trois pièces**, et l'arborescence les sépare :

```
Piece-1-Strategy-note/     ← PIÈCE 1 · la note de stratégie, 9 sous-sections
Piece-2-File/              ← PIÈCE 2 · le dossier, une séance par dossier
Piece-3-Proof-of-state/    ← PIÈCE 3 · l'export daté de l'instance (séance 10)
0-Reference/               ← matière première reçue (dossier de filiale, supports)
fixes.md                   ← journal des corrections à passer avant remise
```

**La règle qui relie les trois** : *la sous-section n de la note affirme ; la séance n du dossier prouve ; l'export montre que l'objet existe dans l'outil.* Une affirmation sans pièce derrière elle ne compte pas ; une pièce dont la note ne dit rien est du travail perdu.

### Dans chaque séance

La consigne exige que les séances soient **séparées et identifiables**, et que chacune contienne **le bureau du RSSI** et **les TP**. D'où quatre emplacements constants :

| Dossier | Contenu | Noté ? |
|---|---|---|
| `1-CISO-desk/` | Le bureau du RSSI — TD 1, **une page par étudiant**, individuel, clos par une recommandation à la direction | ✅ 10 pts, coef. 1, **individuel** |
| `2-Labs/` | Le livrable de la séance, D1 à D9 | ✅ barème des livrables |
| `3-Evidence/` | Les captures de l'instance CISO Assistant qui prouvent l'état des objets | ✅ support du livrable |
| `4-Working-notes/` | TD 2 et notes d'étude — matière de travail, non notée en tant que telle | ➖ |

---

## Ce que contient chaque séance aujourd'hui

### Séance 1 — Gouvernance cible *(D1)* ✅
- `2-Labs/D1-note-de-cadrage-et-gouvernance-cible.md` — **le livrable**, deux pages : périmètre et exclusions, enjeux, parties prenantes, contraintes ; schéma de gouvernance à trois niveaux avec fréquences, matrice RACI, cinq directives codifiées, trois règles d'arbitrage. Les comptes rendus S1-05 et S1-06 restent à côté comme trace de méthode.
- `1-CISO-desk/` — **les deux pages rendues** (Miguel et Maxime, angles distincts). Voir `fixes.md` F7.
- `3-Evidence/` — vide, et c'est correct : l'instance n'a été ouverte qu'en séance 2.
- La feuille de route chiffrée reste consultable en S1-06 mais **ne fait pas partie du rendu** — c'est écrit dans le `README` de `2-Labs/`.

### Séance 2 — Cartographie *(D2)* ✅
- `2-Labs/D2-cartographie-MERIDIAN-LOGISTIQUE.md` — **le livrable**, les huit éléments exigés : valeurs métier, biens supports, DICT, dépendances inter-filiales, **Top 5 justifié**, lacunes assumées, processus de mise à jour. Le compte rendu S2-05 reste à côté comme trace de méthode.
- `1-CISO-desk/` — **les deux pages rendues** (Miguel et Maxime, angles distincts). Voir `fixes.md` F7.
- `3-Evidence/` — liste des actifs (2 captures), vue d'analyse d'impact.
- ⚠️ Le Top 5 doit encore être **repérable dans l'instance**, pas seulement au dossier. Voir `fixes.md` F3.

### Séance 3 — Choix du référentiel *(D3)* ✅
- `2-Labs/D3-note-de-business-case.md` — **le livrable**, deux pages, cinq sections, les cinq éléments exigés dont l'**estimation de la charge** (≈ 60 jours-homme la première année). Le rapport long de 13 pages reste à côté comme pièce d'appui.
- `1-CISO-desk/` — **les deux pages rendues** (Miguel et Maxime, angles distincts). Voir `fixes.md` F7.
- `3-Evidence/` — 16 captures : détail du référentiel (123 exigences, dont l'arbre annexe A déplié), évaluation rattachée au périmètre et portant désormais auteurs + statut, liste des 17 actifs avec propriétaires assignés, recherches en bibliothèque.
- ✅ L'**erreur sur le ReCyF est corrigée** dans les quatre fichiers concernés, et l'arithmétique de la grille recalculée (ReCyF 205, écart 25 points). ✅ La capture de l'annexe A dépliée est faite (93 en 37/8/14/34) — voir `fixes.md` F6.

### Séance 4 — Audit · valeur de la certification *(D4)* 🔄
- `1-CISO-desk/` — **les deux pages rendues** (Miguel et Maxime, angles distincts) à partir du TD 1 *« La valeur de la certification ISO 27001 »*. `fixes.md` F7 est clos, 8 pages sur 8.
- `4-Working-notes/Seance-4-TD-S4-03-gradation-des-constats.md` — **TD 2 fait** : les huit constats du cycle d'audit groupe gradés (conforme / non-conformité majeure ou mineure / observation), justifiés par l'exigence et l'étendue de l'écart, jamais par la gravité ressentie ; les deux gradations discutables (C6, C8) argumentées des deux côtés. Préalable du TP 1.
- `2-Labs/` — **TP 1 fait** : `PLAN-Seance-4-TP-S4-05-auto-evaluation.md` (le mode opératoire) et `Seance-4-TP-S4-05-feuille-de-travail-auto-evaluation.md` (**la feuille de travail** — cadrage, mapping des statuts, les douze exigences justifiées, les quatre mesures SMART, synthèse par thème, lecture de maturité, biais assumé, et les deux listes qui alimenteront le TP 2). Dans `translog-b` : les douze exigences retenues portent un statut (0 couvert · 2 partiels · 9 non couverts · 1 non évalué assumé, A.6.3), et quatre mesures appliquées (deux corrections, deux actions correctives) sont créées, rattachées à leur exigence, avec propriétaire nominatif et échéance. Aucun objet des séances 2/3 recréé ou renommé.
- `3-Evidence/` — quatre captures `S4-05-*.jpg` : l'évaluation d'une exigence saisie, le détail de A.8.22 (non couvert, justification), les quatre mesures appliquées avec propriétaire et échéance, le taux de conformité après saisie.
- Reste à faire : le **TP 2**, qui écrit le livrable `D4-rapport-d-audit-initial.md` (six sections imposées) à partir de cette feuille de travail, et la 4ᵉ sous-section de la note de stratégie.

---

## Le point à ne pas perdre de vue

La note individuelle passe par **deux** portes, et l'une d'elles est dans l'outil : le coefficient individuel (0,85 · 0,95 · 1,05 · 1,15) s'appuie à parts égales sur la **question individuelle en soutenance** et sur la **traçabilité nominative dans l'instance — chaque objet créé porte un propriétaire**. Cette seconde porte est désormais fermée : l'évaluation de conformité porte auteurs et statut, et les 17 actifs portent un propriétaire assigné. Voir `fixes.md` F5.
