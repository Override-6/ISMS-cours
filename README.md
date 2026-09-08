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

**Séances tenues : 3 sur 9, la séance 4 est ouverte** (le bureau du RSSI S4 est fait, le TP reste à venir). Tout ce qui relève des séances 5 à 9 n'est pas « en retard » — ces séances n'ont pas eu lieu.

| Bloc noté | Poids | Acquis aujourd'hui | Reste |
|---|---|---|---|
| **Livrables D1→D9** | 40 pts → /20, **coef. 4** | **13 pts** assemblés (D1 4 · D2 5 · D3 4) | D4→D9 = 24 pts, séances non tenues |
| **Note de stratégie** (pièce 1) | 3 pts (inclus dans les 40) | 3 sous-sections sur 9, **toutes rédigées** | 6 sous-sections, une par séance restante |
| **Bureau du RSSI** | 10 pts, **coef. 1**, **individuel** | Miguel : **4 pages sur 4** (S1→S4) | Maxime : **4 pages sur 4 à écrire** |
| **Coefficient individuel** | ×0,85 / 0,95 / 1,05 / 1,15 | — | **à sécuriser** : traçabilité nominative dans l'instance |
| **Preuve d'état** (pièce 3) | support | captures intermédiaires par séance | export final, produit en **séance 10** |

### Détail par séance

| Séance | Thème | Livrable | Pts | Dossier | Instance |
|---|---|---|---|---|---|
| **S1** | Gouvernance : niveaux, acteurs, principes | **D1** Note de cadrage et gouvernance cible | 4 | ✅ assemblé | — (instance ouverte en S2) |
| **S2** | Cartographie du SI | **D2** Cartographie de la filiale | 5 | ✅ assemblé | ⬜ **Top 5 à marquer** |
| **S3** | Choix du référentiel | **D3** Note de business case | 4 | ✅ assemblé | ⬜ **auteurs + statut** |
| **S4** | Audit · valeur de la certification | **D4** | 4 | 🔄 bureau du RSSI S4 fait (Miguel) · **D4 à produire** | — |
| S5 | Risques majeurs | D5 | 3 | ⏳ | — |
| S6 | Tiers et projets | D6 | 7 | ⏳ | — |
| S7 | Traitement du risque | D7 | 5 | ⏳ | — |
| S8 | Périmètre du SMSI | D8 | 2 | ⏳ | — |
| S9 | Indicateurs, version finale | D9 | 3 | ⏳ | — |

---

## 2. Ce qui est **fait**

### Les trois livrables existent, nommés, autonomes, au format exigé

| Livrable | Fichier | Ce qu'il porte |
|---|---|---|
| **D1** | `…/Session-1/2-Labs/D1-note-de-cadrage-et-gouvernance-cible.md` | Deux pages : périmètre et exclusions assumées, enjeux, parties prenantes, contraintes réelles · gouvernance à trois niveaux **avec fréquences**, matrice RACI, 5 directives codifiées, 3 règles d'arbitrage |
| **D2** | `…/Session-2/2-Labs/D2-cartographie-MERIDIAN-LOGISTIQUE.md` | Les **8 éléments exigés** : valeurs métier, biens supports, DICT, dépendances inter-filiales, **Top 5 justifié**, lacunes assumées, processus de mise à jour |
| **D3** | `…/Session-3/2-Labs/D3-note-de-business-case.md` | Deux pages, 5 sections, les **5 éléments exigés** dont l'**estimation de charge** (≈ 60 jours-homme la 1re année, poste par poste) |

### Corrections passées (journal complet : [`fixes.md`](G4-%20Translog%20Maxime%20-%20Miguel%20-%20TP/fixes.md))

- **F10** — les livrables sont désormais *présentés* comme des livrables, plus enfouis dans des comptes rendus de TP. **13 pts débloqués.**
- **F11 / F8** — D1 énonce enfin ses **enjeux** et ses **contraintes** ; chaque instance de gouvernance porte une **fréquence**.
- **F1 / F2** — D3 ramenée à **deux pages** ; le rapport de 13 pages requalifié en pièce d'appui ; **estimation de charge** ajoutée.
- **F4** — **erreur ReCyF corrigée** dans les 4 fichiers concernés : le référentiel est *présent* en bibliothèque, contrairement à ce qu'on écrivait. Grille recalculée (ReCyF 195 → **205**, écart 35 → **25 pts**), deux tests de bascule refaits. La recommandation ne bouge pas — elle tient sur la **règle de veto**, pas sur l'arithmétique.
- **F9** — la feuille de route chiffrée S1 est conservée mais **sortie du rendu** (c'est le sujet du rattrapage).
- **F7 (moitié)** — les **trois pages du bureau du RSSI de Miguel** sont écrites, une par séance, chacune close par une recommandation à la direction.
- **Séance 4 amorcée** — le bureau du RSSI S4 de Miguel est écrit à partir du TD 1 *« La valeur de la certification ISO 27001 »* : mécanique de la certification, arbitrage de périmètre, mise au point NIS 2 et réponse au client pharmaceutique.
- **F3 (moitié)** — le Top 5 est au dossier, classé sur un critère écrit *avant* le classement, et la **sous-section 2 de la note de stratégie qu'il bloquait est rédigée**.

### Preuves déjà au dossier

- `Session-2/3-Evidence/` — liste des actifs (2 captures), vue d'analyse d'impact.
- `Session-3/3-Evidence/` — 12 captures : détail du référentiel (**123 exigences**), évaluation rattachée au périmètre, recherches en bibliothèque (guide d'hygiène ANSSI, DORA, HDS v2.0, RGS 2.0 Annexe B2, ReCyF).

---

## 3. Ce qui **manque** — les prochains objectifs, dans l'ordre

### 🔴 Avant la remise du 17 septembre — 4 chantiers

| # | Objectif | Où ça se passe | Qui | Enjeu | Charge |
|---|---|---|---|---|---|
| **1** | **F5 · Nommer les propriétaires** — renseigner *Authors* sur l'évaluation de conformité **et sur tous les actifs**, poser un **statut** sur l'évaluation, puis recapturer | instance `translog-b` | les deux | **le coefficient individuel** (×0,85 → ×1,15 sur *toutes* les notes collectives) | Petite |
| **2** | **F3 · Marquer le Top 5 dans l'instance** — `SA-01`, `SA-04`, `SA-09`, `SA-05`, `SA-03` repérables sans lire le fichier, puis liste d'actifs recapturée dans `Session-2/3-Evidence/` | instance `translog-b` | les deux | **D2 dit « instance *et* dossier »** — 5 pts | Moyenne |
| **3** | **F6 · Capture de l'annexe A dépliée** — montrer **93** contrôles en **37 / 8 / 14 / 34**, ou ramener l'affirmation à ce que la preuve soutient | instance → `Session-3/3-Evidence/` | les deux | exactitude de D3 | Petite |
| **4** | **F7 · Les quatre pages du bureau du RSSI de Maxime** — S1, S2, S3 **et S4**, **une page chacune**, individuelles, closes par une recommandation à la direction | dossier | **Maxime** | **10 pts, coef. 1** | Grande |

> ⚠️ **Chantiers 1, 2 et 3 = travail dans le navigateur**, sur `translog-b`. Aucun fichier de ce dépôt ne les résout : la saisie se fait dans l'outil, puis on rapatrie les captures.

**Les quatre questions du bureau du RSSI, pour Maxime :**

| Séance | Question du jour |
|---|---|
| S1 | De quoi un conseil d'administration a-t-il réellement besoin de son RSSI ? |
| S2 | Pourquoi tout inventaire d'actifs est-il faux, et qu'en fait-on ? |
| S3 | Sommes-nous dans le champ de NIS 2, et à quel titre ? |
| S4 | Que vaut une certification ISO 27001, et que répond-on au tiers qui l'exige ? |

C'est la **seule note individuelle** du module : les deux pages d'une même séance ne peuvent pas se ressembler. Des angles distincts sont proposés dans le `README` de chaque dossier `1-CISO-desk/`.

### ⏳ Au fil des séances 4 à 9 — le rythme à tenir

Chaque séance produit **trois choses**, et il n'y en a jamais eu d'autres :

1. **Le livrable `Dn`** dans `Session-n/2-Labs/`, nommé, autonome, au format que la consigne exige.
2. **La sous-section n de la note de stratégie**, dans `Piece-1-Strategy-note/`, qui s'**articule** aux précédentes — c'est le critère de notation, pas le contenu — et **rien ne s'y supprime jamais** : une contradiction s'amende d'une phrase datée au journal.
3. **Une page du bureau du RSSI par étudiant** dans `Session-n/1-CISO-desk/`, close par une recommandation à la direction.

Plus les **captures** dans `Session-n/3-Evidence/` dès qu'un objet est créé ou modifié dans l'instance.

| Séance | Livrable attendu | Pts |
|---|---|---|
| **S4** | **D4** — audit / état des lieux · *bureau du RSSI S4 déjà fait ; reste le TP, le livrable et la sous-section 4 de la note* | 4 |
| S5 | **D5** — risques majeurs | 3 |
| S6 | **D6** — tiers et projets *(le plus lourd du module)* | **7** |
| S7 | **D7** — traitement du risque | 5 |
| S8 | **D8** — périmètre du SMSI | 2 |
| S9 | **D9** — indicateurs + **version close de la note de stratégie** | 3 |
| **S10** | **Pièce 3** — export daté de l'instance, 8h30–9h15, au dépôt | support |

**Budget de pages de la note** : 3 à 5 pages de texte (3 est la cible). Trois sous-sections écrites ≈ **1 ½ page** — la marge est intacte, la contrainte mordra vers S6/S7 et se traitera en resserrant la **nouvelle** sous-section, jamais en supprimant une précédente.

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
│   S4 - Sources/                        (S4 : séance en cours)
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

- **Instance** `translog-b`, **périmètre** `MERIDIAN-LOGISTIQUE`. Le **domaine** reste `Global` — c'est sa valeur normale dans CISO Assistant. Domaine ≠ périmètre : c'est le **périmètre** qui porte le rattachement noté.
- **Chaque objet créé dans l'instance porte un auteur nommé.** C'est la moitié du coefficient individuel, l'autre moitié étant la question individuelle en soutenance.
- **La note de stratégie est en français** et ne mélange pas les langues. Le dossier (pièce 2) peut être dans l'autre langue, la consigne l'autorise.
- **Un livrable ne se cache pas dans un compte rendu.** Il porte son nom `Dn-…`, il est autonome, il tient le format exigé ; les comptes rendus de TP restent à côté comme trace de méthode.
- **Rien ne se supprime dans la note de stratégie.** Une sous-section qui en contredit une précédente l'amende d'une phrase datée au journal des amendements.
