# ISMS — MERIDIAN Logistique · Groupe 4 (Translog)

**Module M2-01-4-ISMS** — *Security governance and information system mapping*
**Groupe 4 « Translog »** · Miguel Monereo, Maxime · filiale d'instruction **MERIDIAN Logistique**
**Instance** `translog-b` (https://translog-b.lockbay.eu) · **périmètre** `MERIDIAN-LOGISTIQUE`
**Remise : 17 septembre 2026** · dernière mise à jour du dépôt : **8 septembre 2026**

> **La règle qui gouverne tout le rendu :**
> *la sous-section n de la note **affirme** ; la séance n du dossier **prouve** ; l'export **montre** que l'objet existe dans l'outil.*
> Une affirmation sans pièce derrière elle ne compte pas ; une pièce dont la note ne dit rien est du travail perdu.

---

## 1. Où nous en sommes, en un coup d'œil

**Séances tenues : 4 sur 9, la séance 5 est la prochaine à ouvrir.** Tout ce qui relève des séances 5 à 9 n'est pas « en retard » — ces séances n'ont pas eu lieu.

| Bloc noté | Poids | Acquis aujourd'hui | Reste |
|---|---|---|---|
| **Livrables D1→D9** | 40 pts → /20, **coef. 4** | **17 pts** assemblés (D1 4 · D2 5 · D3 4 · D4 4) | D5→D9 = 20 pts, séances non tenues |
| **Note de stratégie** (pièce 1) | 3 pts (inclus dans les 40) | 4 sous-sections sur 9, **toutes rédigées** | 5 sous-sections, une par séance restante |
| **Bureau du RSSI** | 10 pts, **coef. 1**, **individuel** | ✅ **8 pages sur 8** (Miguel + Maxime, S1→S4) | rien — F7 clos |
| **Coefficient individuel** | ×0,85 / 0,95 / 1,05 / 1,15 | ✅ traçabilité nominative confirmée (auteurs + statut) | — |
| **Preuve d'état** (pièce 3) | support | captures intermédiaires par séance | export final, produit en **séance 10** |

### Détail par séance

| Séance | Thème | Livrable | Pts | Dossier | Instance |
|---|---|---|---|---|---|
| **S1** | Gouvernance : niveaux, acteurs, principes | **D1** Note de cadrage et gouvernance cible | 4 | ✅ assemblé | — (instance ouverte en S2) |
| **S2** | Cartographie du SI | **D2** Cartographie de la filiale | 5 | ✅ assemblé | ⬜ **Top 5 à marquer** |
| **S3** | Choix du référentiel | **D3** Note de business case | 4 | ✅ assemblé | ✅ auteurs + statut |
| **S4** | Audit · valeur de la certification | **D4** Rapport d'audit initial | 4 | ✅ assemblé, bureau du RSSI clos | ✅ auto-évaluation + suivi des constats |
| S5 | Risques majeurs | D5 | 3 | ⏳ | — |
| S6 | Tiers et projets | D6 | 7 | ⏳ | — |
| S7 | Traitement du risque | D7 | 5 | ⏳ | — |
| S8 | Périmètre du SMSI | D8 | 2 | ⏳ | — |
| S9 | Indicateurs, version finale | D9 | 3 | ⏳ | — |

---

## 2. Ce qui est **fait**

### Les quatre livrables existent, nommés, autonomes, au format exigé

| Livrable | Fichier | Ce qu'il porte |
|---|---|---|
| **D1** | `…/Session-1/2-Labs/D1-note-de-cadrage-et-gouvernance-cible.md` | Deux pages : périmètre et exclusions assumées, enjeux, parties prenantes, contraintes réelles · gouvernance à trois niveaux **avec fréquences**, matrice RACI, 5 directives codifiées, 3 règles d'arbitrage |
| **D2** | `…/Session-2/2-Labs/D2-cartographie-MERIDIAN-LOGISTIQUE.md` | Les **8 éléments exigés** : valeurs métier, biens supports, DICT, dépendances inter-filiales, **Top 5 justifié**, lacunes assumées, processus de mise à jour |
| **D3** | `…/Session-3/2-Labs/D3-note-de-business-case.md` | Deux pages, 5 sections, les **5 éléments exigés** dont l'**estimation de charge** (≈ 60 jours-homme la 1re année, poste par poste) |
| **D4** | `…/Session-4/2-Labs/D4-rapport-d-audit-initial.md` | Six sections imposées : cadrage (auto-évaluation, sans indépendance, assumée), synthèse pour décision, **constats gradués** (C3/C4 majeurs, C7 conforme sur son flux, + écarts complémentaires de l'auto-évaluation), recommandations tracées, plan d'action correctif (M1-M4), angles morts |

### Corrections passées (journal complet : [`fixes.md`](G4-%20Translog%20Maxime%20-%20Miguel%20-%20TP/fixes.md))

- **F10** — les livrables sont désormais *présentés* comme des livrables, plus enfouis dans des comptes rendus de TP. **13 pts débloqués.**
- **F11 / F8** — D1 énonce enfin ses **enjeux** et ses **contraintes** ; chaque instance de gouvernance porte une **fréquence**.
- **F1 / F2** — D3 ramenée à **deux pages** ; le rapport de 13 pages requalifié en pièce d'appui ; **estimation de charge** ajoutée.
- **F4** — **erreur ReCyF corrigée** dans les 4 fichiers concernés : le référentiel est *présent* en bibliothèque, contrairement à ce qu'on écrivait. Grille recalculée (ReCyF 195 → **205**, écart 35 → **25 pts**), deux tests de bascule refaits. La recommandation ne bouge pas — elle tient sur la **règle de veto**, pas sur l'arithmétique.
- **F9** — la feuille de route chiffrée S1 est conservée mais **sortie du rendu** (c'est le sujet du rattrapage).
- **F7 (clos)** — les **huit pages du bureau du RSSI** (Miguel + Maxime, S1 à S4) sont écrites, chacune individuelle, chacune close par une recommandation à la direction, chacune avec un angle distinct de son binôme.
- **Séance 4 close en entier** — bureau du RSSI (les deux pages S4, à partir du TD 1 *« La valeur de la certification ISO 27001 »* : Miguel sur le découplage des deux demandes client/Direction Générale, Maxime sur l'effet interne de l'échéance externe), auto-évaluation outillée (TP 1) et rapport d'audit initial **D4** (TP 2, six sections, trois constats gradés suivis dans l'instance).
- **F3 (moitié)** — le Top 5 est au dossier, classé sur un critère écrit *avant* le classement, et la **sous-section 2 de la note de stratégie qu'il bloquait est rédigée**.

### Preuves déjà au dossier

- `Session-2/3-Evidence/` — liste des actifs (2 captures), vue d'analyse d'impact.
- `Session-3/3-Evidence/` — 16 captures : détail du référentiel (**123 exigences**, dont l'arbre annexe A déplié en 37/8/14/34), évaluation rattachée au périmètre et portant désormais auteurs + statut, liste des 17 actifs avec propriétaires assignés, recherches en bibliothèque (guide d'hygiène ANSSI, DORA, HDS v2.0, RGS 2.0 Annexe B2, ReCyF).
- `Session-4/3-Evidence/` — 5 captures : auto-évaluation des douze exigences, mesures appliquées, taux de conformité, et le suivi outillé des trois constats gradés (*Follow-up*) créé dans `translog-b`.

---

## 3. Ce qui **manque** — les prochains objectifs, dans l'ordre

### 🔴 Avant la remise du 17 septembre — 1 chantier

| # | Objectif | Où ça se passe | Qui | Enjeu | Charge |
|---|---|---|---|---|---|
| **1** | **F3 · Marquer le Top 5 dans l'instance** — `SA-01`, `SA-04`, `SA-09`, `SA-05`, `SA-03` repérables sans lire le fichier, puis liste d'actifs recapturée dans `Session-2/3-Evidence/` | instance `translog-b` | les deux | **D2 dit « instance *et* dossier »** — 5 pts | Moyenne |

> ⚠️ **Ce dernier chantier se fait dans le navigateur**, sur `translog-b`. Aucun fichier de ce dépôt ne le résout : la saisie se fait dans l'outil, puis on rapatrie les captures.

**F7 · Bureau du RSSI — clos.** Les huit pages (Miguel + Maxime, S1 à S4) sont écrites, une par étudiant et par séance, chacune individuelle et close par une recommandation à la direction ; le détail des angles retenus est dans `fixes.md`.

**F6 · Capture de l'annexe A dépliée — clos.** `Session-3/3-Evidence/S3-05-ex2bis-framework-detail-annexA-4themes-expanded.png` montre l'arbre déplié : **93** contrôles en **37 / 8 / 14 / 34**, conforme à l'affirmation déjà écrite dans D3.

**F5 · Nommer les propriétaires — clos.** Authors confirmés sur l'évaluation de conformité et sur les **17 actifs** (`Assigned to`), statut posé (`In progress`) : le rapport de référentiel compte désormais l'audit (« 1 counted, 0 excluded »). Trois nouvelles captures dans `Session-3/3-Evidence/`.

### ⏳ Au fil des séances 5 à 9 — le rythme à tenir

Chaque séance produit **trois choses**, et il n'y en a jamais eu d'autres :

1. **Le livrable `Dn`** dans `Session-n/2-Labs/`, nommé, autonome, au format que la consigne exige.
2. **La sous-section n de la note de stratégie**, dans `Piece-1-Strategy-note/`, qui s'**articule** aux précédentes — c'est le critère de notation, pas le contenu — et **rien ne s'y supprime jamais** : une contradiction s'amende d'une phrase datée au journal.
3. **Une page du bureau du RSSI par étudiant** dans `Session-n/1-CISO-desk/`, close par une recommandation à la direction.

Plus les **captures** dans `Session-n/3-Evidence/` dès qu'un objet est créé ou modifié dans l'instance.

| Séance | Livrable attendu | Pts |
|---|---|---|
| S5 | **D5** — risques majeurs | 3 |
| S6 | **D6** — tiers et projets *(le plus lourd du module)* | **7** |
| S7 | **D7** — traitement du risque | 5 |
| S8 | **D8** — périmètre du SMSI | 2 |
| S9 | **D9** — indicateurs + **version close de la note de stratégie** | 3 |
| **S10** | **Pièce 3** — export daté de l'instance, 8h30–9h15, au dépôt | support |

**Budget de pages de la note** : 3 à 5 pages de texte (3 est la cible). Quatre sous-sections écrites ≈ **2 pages** — la marge se resserre mais tient, la contrainte mordra vers S6/S7 et se traitera en resserrant la **nouvelle** sous-section, jamais en supprimant une précédente.

---

## 4. Comment ce dépôt est rangé

```
ISMS/
├── README.md                         ← vous êtes ici : état d'avancement et prochains objectifs
├── ISMS module common thread.pdf     ← LA source de vérité (v2, 8 sept. 2026) : consignes et barème
│
├── G4- Translog Maxime - Miguel - TP/ ← 🎯 LE RENDU
│   ├── fixes.md                       ← journal détaillé des corrections (F1→F11)
│   ├── README.md                      ← notice du rendu
│   ├── 0-Reference/                   ← dossier de filiale reçu + supports de cadrage
│   │
│   ├── Piece-1-Strategy-note/         ← PIÈCE 1 · la note de stratégie, 9 sous-sections
│   ├── Piece-2-File/                  ← PIÈCE 2 · le dossier, une séance par dossier
│   │   └── Session-1|2|3|4/
│   │       ├── 1-CISO-desk/           ← bureau du RSSI — 1 page/étudiant · 10 pts, individuel
│   │       ├── 2-Labs/                ← le livrable Dn · barème des livrables
│   │       ├── 3-Evidence/            ← captures de l'instance CISO Assistant
│   │       └── 4-Working-notes/       ← TD 2 et notes d'étude · non noté
│   └── Piece-3-Proof-of-state/        ← PIÈCE 3 · export de l'instance (séance 10) — vide, normal
│
├── Seance-1/, Seance-2/, Seance-3/   ← supports de cours reçus (CM / TD / TP), par séance
├── S2 - Sources/, S3 - Sources/,     ← mêmes supports, export Lockbay Academy
│   S4 - Sources/                        (S1 à S4 désormais complètes)
├── Correction/                        ← version française du support S4 TD 1
├── 00-Reference/                      ← dossier de référence MERIDIAN + accès à l'instance
└── .FIRST_TP-backup-20260908-115436/ ← état du dossier avant la réorganisation du 8 sept. (archive)
```

**Par où commencer**, selon ce qu'on cherche :

| Je cherche… | J'ouvre |
|---|---|
| Ce qu'il reste à faire | ce README, section 3 |
| Le détail d'une correction | `G4- .../fixes.md` |
| Le document que lit un directeur général | `Piece-1-Strategy-note/MERIDIAN-strategy-note.md` |
| Le livrable noté d'une séance | `Piece-2-File/Session-n/2-Labs/Dn-*.md` |
| La consigne exacte et le barème | `ISMS module common thread.pdf` |

---

## 5. Conventions à ne pas perdre

- **Instance** `translog-b`. Domaine ≠ périmètre : le **domaine** des objets de la filiale est `MERIDIAN-LOGISTIQUE` (un sous-domaine propre, enfant du domaine racine `Global` — vérifié dans `Domains`), et le **périmètre** est `MERIDIAN-LOGISTIQUE-FINAL`, à l'intérieur de ce sous-domaine. Ne pas confondre les deux, et ne pas supposer que le domaine affiché est littéralement `Global` sans l'avoir vérifié sur l'objet.
- **Chaque objet créé dans l'instance porte un auteur nommé.** C'est la moitié du coefficient individuel, l'autre moitié étant la question individuelle en soutenance.
- **La note de stratégie est en français** et ne mélange pas les langues. Le dossier (pièce 2) peut être dans l'autre langue, la consigne l'autorise.
- **Un livrable ne se cache pas dans un compte rendu.** Il porte son nom `Dn-…`, il est autonome, il tient le format exigé ; les comptes rendus de TP restent à côté comme trace de méthode.
- **Rien ne se supprime dans la note de stratégie.** Une sous-section qui en contredit une précédente l'amende d'une phrase datée au journal des amendements.
