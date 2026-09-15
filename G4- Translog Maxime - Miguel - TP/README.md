# MERIDIAN LOGISTIQUE — dossier du Groupe 4 (Translog)

**Module M2-01-4-ISMS** · Security governance and information system mapping
**Groupe 4 — Translog** · Miguel Monereo, Maxime · filiale d'instruction **MERIDIAN Logistique**
**Instance** `translog-b` (https://translog-b.lockbay.eu) · **périmètre** `MERIDIAN-LOGISTIQUE`

---

## Avancement : séances 1 à 8 closes côté dossier et côté outil

Le bloc 1 (séances 1–2, fondations) et le bloc 2 (séances 3 à 6) sont faits, livrables compris. La séance 6 est **close côté dossier** : bureau du RSSI clos (Miguel et Maxime), **TD 2** (management des tiers, lecture du contrat d'infogérance, ateliers 3-4 par écrit), **TP 1** (écosystème et scénarios saisis dans `translog-b` — 5 parties prenantes cotées, 2 critiques, 2 scénarios stratégiques, 1 scénario opérationnel), **TP 2** — livrable `D6` (fiche projet à six jalons + exigences du contrat APPLICA tracées + dispositif de surveillance + export de l'étude) et **sous-section 6** de la note. Reste le CM de la séance 6.

**La séance 7 est entièrement close : les deux TD sont rendus, les deux TP sont faits, `D7` est rédigé, les coûts sont saisis dans `translog-b`, et les deux pages du bureau du RSSI sont rendues (F19).** `Session-7/` porte les quatre emplacements constants, tous remplis.

**La séance 8 est entièrement close : le TD 1 est fait, les deux pages individuelles sont rendues (F19), les deux TP sont saisis dans `translog-b` et le livrable `D8` est rédigé.** TP 1 : 30 exigences de clauses 4-10 évaluées, 15 contrôles d'annexe A investigués, 16,1 % de couverture. TP 2 : `D8` (périmètre du SMSI, déclaration d'applicabilité, registre des exclusions, synthèse) et la sous-section 8 de la note de stratégie. **Reste** le CM (non noté). **La séance 9 n'a pas eu lieu** — son emplacement n'existe pas encore, et c'est normal à cette date.

| Séance | Thème | Livrable | Points | État |
|---|---|---|---|---|
| **S1** | Gouvernance : niveaux, acteurs, principes | **D1** Note de cadrage et gouvernance cible | 4 | ✅ **livrable assemblé**, bureau du RSSI clos *(F7)* |
| **S2** | Cartographie du SI | **D2** Cartographie de la filiale | 5 | ✅ **livrable assemblé**, Top 5 marqué dans l'instance *(F3 clos)* |
| **S3** | Choix du référentiel | **D3** Note de business case | 4 | ✅ **livrable assemblé** |
| **S4** | Audit · valeur de la certification | **D4** Rapport d'audit initial | 4 | ✅ **livrable assemblé**, bureau du RSSI clos, TP 1 et TP 2 faits |
| **S5** | Risques majeurs · EBIOS RM ateliers 1-2 | **D5** Appréciation initiale des risques | 3 | ✅ **livrable assemblé**, bureau du RSSI clos *(F12)*, ateliers 1-2 saisis dans `translog-b` |
| **S6** | Tiers et projets · EBIOS RM ateliers 3-4 | **D6** Tiers et projets | 7 | ✅ **livrable assemblé**, bureau du RSSI clos, TD 2 + TP 1 + TP 2 faits — reste le CM |
| **S7** | Traitement du risque · EBIOS RM atelier 4 + registre | **D7** Plan de traitement et risque résiduel | 5 | ✅ **livrable rédigé**, bureau du RSSI clos *(F14/F19)*, coûts saisis dans l'outil (82K €/an, 13/13 mesures) |
| **S8** | Périmètre du SMSI · business case de certification | **D8** Déclaration d'applicabilité | 2 | ✅ **livrable rédigé**, bureau du RSSI clos *(F16/F19)*, 30 exigences + 15 contrôles évalués dans l'outil (16,1 % de couverture) — reste le CM |
| S9 | Indicateurs, version finale | D9 | 3 | ⏳ séance non tenue |
| S1–S9 | — | Note de stratégie | 3 | 🔄 8 sous-sections sur 9, **toutes rédigées** |

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

**Où va quel TD — la confusion à ne pas refaire.** Le **TD 1** de chaque séance est *« Le point du RSSI »* /
*« The CISO's Desk »* : sa note collective va dans **`1-CISO-desk/`**, numérotée `S{n}-01`, à côté des deux
pages individuelles qu'elle nourrit. Le **TD 2** de l'après-midi va dans **`4-Working-notes/`**, numéroté
`S{n}-03`. Les deux TP sont `S{n}-05` et `S{n}-06`, dans `2-Labs/`. Cette numérotation est celle des séances 1
à 6 ; la séance 7 y a été ramenée le 14 septembre 2026 (`fixes.md` **F14**).

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

### Séance 4 — Audit initial *(D4)* ✅
- `1-CISO-desk/` — **les deux pages rendues** (Miguel et Maxime, angles distincts) à partir du TD 1 *« La valeur de la certification ISO 27001 »*. `fixes.md` F7 est clos, 8 pages sur 8.
- `4-Working-notes/Seance-4-TD-S4-03-gradation-des-constats.md` — **TD 2 fait** : les huit constats du cycle d'audit groupe gradés (conforme / non-conformité majeure ou mineure / observation), justifiés par l'exigence et l'étendue de l'écart, jamais par la gravité ressentie ; les deux gradations discutables (C6, C8) argumentées des deux côtés. Préalable du TP 1.
- `2-Labs/` — **TP 1 fait** : `PLAN-Seance-4-TP-S4-05-auto-evaluation.md` (le mode opératoire) et `Seance-4-TP-S4-05-feuille-de-travail-auto-evaluation.md` (**la feuille de travail** — cadrage, mapping des statuts, les douze exigences justifiées, les quatre mesures SMART, synthèse par thème, lecture de maturité, biais assumé). Dans `translog-b` : les douze exigences retenues portent un statut (0 couvert · 2 partiels · 9 non couverts · 1 non évalué assumé, A.6.3), et quatre mesures appliquées (deux corrections, deux actions correctives) sont créées, rattachées à leur exigence, avec propriétaire nominatif et échéance. **TP 2 fait** : `D4-rapport-d-audit-initial.md` (**le livrable**, six sections — cadrage, synthèse, constats gradués, recommandations, plan d'action correctif, angles morts) et `Seance-4-TP-S4-06-exercice1-cadrage-homologation-WMS-et-exercice3-recommandations.md` (fiche de cadrage de l'homologation du WMS, trois recommandations bâclées réparées). Dans `translog-b` : un objet *Follow-up* porte les trois constats gradés par le TD 2 (C3, C4 en non-conformité majeure, C7 conforme sur son flux), chacun rattaché aux mesures correctives concernées. Aucun objet des séances 2/3 recréé ou renommé.
- `3-Evidence/` — cinq captures : `S4-05-*.jpg` (l'évaluation des exigences, le détail de A.8.22, les quatre mesures appliquées, le taux de conformité après saisie) et `S4-06-ex2-follow-up-findings-C3-C4-C7.png` (le suivi outillé des trois constats).

### Séance 5 — Appréciation initiale des risques *(D5)* ✅
- `2-Labs/D5-appreciation-initiale-des-risques.md` — **le livrable** : cadrage de l'étude, socle de sécurité (PSSI-cadre, guide d'hygiène, ISO 27001, obligations client), **3 couples source de risque / objectif visé** retenus sur 5, **7 événements redoutés** cotés, échelles de gravité et de vraisemblance dans les termes du groupe, **seuil d'acceptation** posé sur la grille 4×4. Feuilles de travail S5-05 (saisie ateliers 1-2) et S5-06 (échelles, assemblage) à côté.
- `1-CISO-desk/` — la page S5 de Maxime rendue (appétence au risque) ; **la page S5 de Miguel reste due** *(F12)*. Note collective du TD 2 (ateliers 1-2 d'EBIOS RM) en `4-Working-notes/`.
- `3-Evidence/` — 24 captures : matrice 4×4 importée, étude créée en méthode `Manual`, 17 actifs reliés, audit rattaché, 7 événements redoutés, 5 couples SR/OV, ateliers 3-4-5 vides à ce stade, rapport d'étude ateliers 1-2.
- Dans `translog-b` : l'**étude EBIOS RM** ouverte, ateliers 1 et 2 saisis (D5 fait foi).

### Séance 6 — Tiers et projets *(D6)* ✅
- `2-Labs/D6-tiers-et-projets.md` — **le livrable (7 points, le plus lourd du module)**, deux pièces cohérentes : **fiche projet** (reprise sécurisée du flux d'approvisionnement d'urgence Logistique→Santé, six jalons M1-M6 à critère de passage démontré par un fait, trois régimes, propriétaire ultime unique par jalon, points d'arbitrage) et **exigences de sécurité du contrat d'infogérance du WMS** (APPLICA Services, `TMA-WMS-2021`) — cinq familles, formulation vérifiable, justification tracée à un scénario stratégique / un écart de l'audit S4 / un silence du contrat ; + dispositif de surveillance du tiers. Complété par l'export de l'étude EBIOS RM (écosystème coté, scénarios stratégiques). Feuilles de travail S6-05 (TP 1) et S6-06 (TP 2) à côté ; TD 2 en `4-Working-notes/`.
- `1-CISO-desk/` — **les deux pages rendues** (Miguel sur la case vide de la détection, Maxime sur « le pivot est signé, pas piraté ») + la note collective du TD 1 (seize dépendances tierces). `fixes.md` F13.
- `3-Evidence/` — 13 captures : TP 1 (étude reprise, 5 parties prenantes et criticités, notes de PP1/PP2, 2 scénarios stratégiques et 3 chemins, scénario opérationnel, atelier 5 vide) + TP 2 (rapport de l'étude ateliers 3-4, liste écosystème avec les 2 critiques `Selected`).
- Dans `translog-b` : atelier 3 complet (5 parties prenantes cotées, 2 `Selected` : intégrateur 12, APPLICA 8), 2 scénarios stratégiques (SS1 `Critical`, SS2 `Important`), 1 scénario opérationnel (`High`).

### Séance 7 — Traitement du risque *(D7)* ✅ close
- `1-CISO-desk/Seance-7-TD-S7-01-chiffrer-le-cout-de-l-inaction.md` — **TD 1 fait** : la note collective des trois questions guidées. Les références de coût de l'exposé (Mærsk 250-300 M$, Norsk Hydro ~800 M NOK, Equifax ≥ 575 M$, France Travail 5 M€, IBM 3,85 M€ / 4,44 M$ / 241 jours) rattachées **une par une** aux trois familles de scénarios du registre, y compris la ligne « aucune référence ne colle » assumée pour la malveillance interne ; l'argument d'investissement pour le scénario d'indisponibilité, en fourchette aux quatre termes, avec les quatre **données à demander au Directeur Financier** nommées ; les trois objections et leurs réponses. **Les deux pages individuelles sont rendues** (F19) — `S7-bureau-du-RSSI-Miguel-Monereo.md` et `S7-bureau-du-RSSI-Maxime.md`, angles distincts.
- `4-Working-notes/Seance-7-TD-S7-03-matrices-de-cotation-et-options-de-traitement.md` — **TD 2 fait, réécrit au gabarit des séances 5 et 6** : rappel du cas · cadrage des deux notions (matrice de cotation, ligne d'acceptation — avec ce qu'elles *ne font pas*, et le « pourquoi 4×4 et non 5×5 ») · les trois manipulations à reconnaître, chacune rattachée à l'endroit où elle apparaît dans la journée · les quatre scénarios du groupe cotés sur les deux axes avec les échelles de D5 **reprises telles quelles** (A `High`, B `High`, C `High`, D `Medium`), chaque note adossée à un **signal vérifiable** et assortie de son **« pourquoi pas le niveau au-dessus »**, le scénario le plus débattu (B) et ce qui changerait sa cotation · la ligne d'acceptation défendue contre la proposition du Directeur de la Logistique (veto suspensif `ARB-01`, 72 h), la réponse au comité en trois phrases, **qui signe et pourquoi ce n'est ni le RSSI ni le directeur de filiale** · les quatre options de traitement (réduire · réduire · réduire + transférer · **accepter formellement**), **porteurs pris dans la carte du pouvoir du pack §3** — l'avenant contractuel au Directeur de la filiale, les comptes de domaine à la DSI, le réseau industriel au Responsable Exploitation —, la portée réelle de l'assurance cyber sur A en deux colonnes, l'acceptation de D aux cinq éléments · « ce qui entre dans la suite de la journée » · auto-évaluation en huit critères. Matière directe du registre (TP 1) et de `D7` (TP 2).
- `2-Labs/PLAN-Seance-7-TP-S7-05-atelier4-et-registre.md` — **le mode opératoire du TP 1, écrit avant la saisie** (format des séances 4, 5 et 6) : l'état exact de l'étude à vérifier avant d'ouvrir · les **deux scénarios opérationnels** qui manquent (`AP.02` de SS1 par l'intégrateur, `AP.01` de SS2 par APPLICA), chacun en kill chain de sept maillons nommant un bien support **et ce qui s'y oppose aujourd'hui** · les **vraisemblances lues sur le maillon le plus résistant** — V3 pour l'intégrateur (« sept maillons, sept fois *rien* »), **V2** pour le concurrent, qui n'a pas l'accès : le portefeuille hiérarchise au lieu de tout coter pareil · les **8 lignes attendues du registre** (3 scénarios + ER2, ER3, ER5, ER6, ER7) avec option, porteur pris dans la carte du pouvoir §3, et échéance · les **résiduels visés** et ce que chaque mesure change · la **note d'écart déjà amorcée** sur deux trous de cartographie certains (la liaison 4G de l'intégrateur et les liaisons opérateur entre E1 et E2-E6, traversées par les scénarios et absentes de l'inventaire) · les critères de validation et les dix captures.
- `2-Labs/Seance-7-TP-S7-05-feuille-de-travail-atelier4-et-registre.md` — **TP 1 fait dans `translog-b`**, feuille de travail remplie à l'observé. Les deux scénarios opérationnels saisis conformes au plan (`Very likely`/`High` et `Likely`/`Medium`). **Écart n°1** : l'activité 1 de l'atelier 5 n'a généré que **6 lignes**, pas 8 — ER2 et ER6 figurent dans la liste *Feared events* d'un scénario stratégique sans en être le *Focused feared event*, l'outil les considère donc déjà couverts ; créés explicitement pour tenir l'exigence 1 de D7 (aucun risque sans décision), **8 lignes au total**. Les 8 décisions prises (6 réductions, 2 acceptations formelles), mesures et résiduels cotés **après** décision : six résiduels `Medium` (conforme au chiffre anticipé par le plan), un `Low` inchangé (ER6, aucune mesure), un cas d'école où la mesure joue sur la **gravité** et non la vraisemblance (ER7). Contrôle qualité — trouvé sous `X-rays → Risk assessments`, pas sur la page du registre — passé de 1 bucket rouge (8 constats, résiduel non coté) à zéro. **Écart n°2, le plus net de la séance** : contrairement à ce qu'annonçaient l'énoncé et le plan, **l'outil n'a pas refusé** un résiduel délibérément saisi au-dessus du niveau actuel (`Certain × Critical` sur ER3, actuel `Medium`) — l'enregistrement a réussi sans blocage ni avertissement ; capturé, puis corrigé. Note d'écart complète : les deux trous de cartographie couverts par une mesure d'inventaire (`PT-13`), les libellés divergents (le contrôle qualité vit dans `X-rays`, le statut `Transfered` porte une faute d'orthographe de l'outil), les champs sans équivalent (`Assigned to` n'accepte que des comptes de l'instance — les rôles du pack §3 vivent en texte dans les justifications ; aucun champ pour l'instance signataire ni la date de réexamen d'une acceptation — ils vivront dans `D7`). Dix captures produites, aucune empreinte dupliquée.
- `2-Labs/D7-plan-de-traitement-et-risque-residuel.md` — **le livrable D7 (5 points)**. Plan de traitement de 13 mesures **organisé par décision et non par scénario** — cinq décisions de direction (deux avenants contractuels, une acceptation formalisée signée Direction Générale sur la chaîne du froid, une acceptation simple sur la divulgation client, le pilotage du projet de reprise du flux Santé), huit d'exécution dont deux mesures **transversales** comptées une seule fois au budget (comptes nommés + MFA ; segmentation IT/OT, la plus coûteuse du plan). **Sept fiches d'acceptation** (six résiduels `Medium` formalisés, une `Low` simple), signées **Direction Générale du groupe** — jamais « accepté par le RSSI » — et **zéro dérogation à demander, écrit et justifié** : aucun résiduel ne dépasse `Medium`. Coût annuel **≈ 82 000 €**, confirmé dans `translog-b` (82K €/an lus dans l'aperçu budgétaire du *Plan d'action*, 13/13 mesures, après rattachement d'une `PT-13` retrouvée orpheline), mis en face de la fourchette du coût de l'inaction du TD 1 (12 000 € pour un seul jour d'arrêt, plusieurs millions en ordre de grandeur pour l'incident abouti). Table de rapprochement à ISO/IEC 27001:2022, mesure par mesure, pour la déclaration d'applicabilité de la séance 8. Les deux acceptations formelles (ER3, ER6) sont créées comme objets `Risk acceptances` dans l'outil.
- `3-Evidence/` — **dix captures S7-05** (TP 1), aucun doublon d'empreinte : compteurs avant saisie, scénarios opérationnels et détail d'OS2, vraisemblances justifiées d'OS2/OS3, registre généré à 8 lignes, options/porteurs/échéances, contrôle qualité au vert, résiduels cotés, et la tentative de résiduel supérieur acceptée par l'outil sans refus, plus les trois captures `S7-06-…` du TP 2 (coûts d'une mesure, aperçu budgétaire, rapport d'étude).

> **Réserve de forme sur la séance 7** : la note du **TD 1** est encore rédigée sans accents, là où tout le reste du dossier est en français accentué. Le TD 2 ne l'est plus depuis sa réécriture du 14 septembre. Aucun point n'en dépend (matière de travail, non notée), mais le contraste se voit maintenant entre les deux notes de la même séance — reprise à faire à la main avant la remise (`fixes.md` **F14**).

### Séance 8 — Périmètre du SMSI *(D8)* ✅ close
- `1-CISO-desk/Seance-8-TD-S8-01-le-business-case-de-la-certification.md` — **TD 1 fait, relu (F16)** : la note collective des cinq questions guidées du cas *« The Certification Business Case »*. La clause du client pharmaceutique décomposée en trois exigences emboîtées, deux lectures de la « démarche documentée équivalente » (stricte : D3+D4+D7 déjà documentables ; large : écartée, le client vient d'annoncer un questionnaire) ; six audiences pour ce que le certificat prouverait (client pharmaceutique ; MERIDIAN Santé, client interne donné par le §6 ; Direction Générale et actionnaires ; Audit Interne du holding ; filiales et équipes ; régulateur avec nuance) et quatre limites pour ce qu'il ne prouverait pas (réglementaire, sécurité réelle, périmètre, fraîcheur/vivacité) ; un **périmètre de certification proposé** — MERIDIAN Logistique d'abord, les services du client pharmaceutique (chaîne du froid et flux WMS des entrepôts E1 et E4, `LOG-PA-02`/`LOG-PA-04` de D2) — avec la **réserve honnête** qu'E4 est à la fois dédié au client pharmaceutique et équipé d'automates de tri sur le réseau non cloisonné du constat C3 de D4, à exclure explicitement tant que la segmentation IT/OT (`PT-03` de D7) n'est pas faite ; la décision en trois phrases demandée au Comité Exécutif, sans date de certificat ni coût improvisé (le seul montant cité, 82 000 €/an, est celui déjà arrêté par D7).
- `1-CISO-desk/S8-bureau-du-RSSI-Maxime.md` — **page individuelle de Maxime** : angle sur la tension d'E4, à la fois dédié au client pharmaceutique et porteur des automates non cloisonnés (C3) — deux façons de la découvrir (devant l'auditeur de certification, ou écrite par nous), une seule choisie. Recommandation : inscrire dans `D8` une **exclusion écrite et datée** de l'automatisation d'E4 jusqu'à la segmentation IT/OT (`PT-03`, 14/06/2027), reprise en une phrase dans la réponse écrite au client.
- `1-CISO-desk/S8-bureau-du-RSSI-Miguel-Monereo.md` — **page individuelle de Miguel** (F19) : angle sur le silence qui coûte plus cher que l'anticipation — le questionnaire du client est annoncé, pas reçu, et attendre ses questions laisse son calendrier commander le nôtre. Ancré sur la phrase du pack §3 sur les relevés de température sans réponse possible aujourd'hui, à laquelle `PT-10` répond si elle est engagée avant la visite du client.
- `2-Labs/PLAN-Seance-8-TP-S8-05-evaluation-clauses-et-SoA.md` et `Seance-8-TP-S8-05-feuille-de-travail-evaluation-et-SoA.md` — **TP 1 fait dans `translog-b`** : les 30 exigences des clauses 4 à 10 évaluées (2 conformes, 8 non conformes, 20 partiellement conformes), la déclaration d'applicabilité marquée sur 15 contrôles d'annexe A investigués (12 de la séance 4, 3 du CM, 5 communs — 11 non conformes, 3 partiellement conformes, 1 exclusion `A.8.28` justifiée en trois lignes). **Écart d'outil trouvé et corrigé** : le champ Observation n'enregistrait rien au premier passage (mode aperçu par défaut, champ caché) ; les 23 observations concernées reprises via le vrai champ d'édition. Quatre captures dans `3-Evidence/`.
- `2-Labs/D8-declaration-d-applicabilite.md` — **le livrable D8 (2 points), TP 2**. Deux périmètres distingués — le SMSI de la filiale entière (six entrepôts, quatre valeurs métier, treize biens supports, six exclusions, quatre interfaces) et le périmètre visé pour la première certification, plus étroit (chaîne du froid et flux WMS d'E1/E4, hors automatisation d'E4) — avec un test du tiers dedans/dehors ; déclaration d'applicabilité, **16,1 % de couverture** affichée en tête, cohérence croisée vérifiée dans les deux sens avec D4 (aucun orphelin sur les écarts majeurs `C3`/`C4`) et D7 (chaque risque réduit mène à un contrôle retenu sauf ER7, dont l'ancrage `A.5.37` reste à investiguer ; trois contrôles inclus — `A.5.24`, `A.6.3`, `A.7.4` — encore sans mesure de traitement, signalés) ; registre des exclusions repris tel que saisi ; synthèse pour la direction en dix lignes. **Sous-section 8 de la note de stratégie rédigée** dans le même mouvement. *(Note : une seconde version de ce livrable, écrite en parallèle, a été retirée le 15 septembre pour n'en garder qu'une — voir `2-Labs/README.md`.)*
- Reste : le CM (*ISO/IEC 27001:2022, architecture et rôle de la direction*, non noté). La séance 8 ne comporte pas de TD 2 (`S8 - Sources/` ne contient que CM, TD 1, TP 1, TP 2).

> **Réserve héritée de `fixes.md` F17** : les renvois de `D8` vers `PT-02`/`PT-03`/`PT-06` (D7) ne referment pas l'écart de dates avec `M1`/`M2`/`M4` (D4) sur les mêmes contrôles — décrit et laissé ouvert, arbitrage d'auteur toujours dû avant `D9`.

---

## Le point à ne pas perdre de vue

La note individuelle passe par **deux** portes, et l'une d'elles est dans l'outil : le coefficient individuel (0,85 · 0,95 · 1,05 · 1,15) s'appuie à parts égales sur la **question individuelle en soutenance** et sur la **traçabilité nominative dans l'instance — chaque objet créé porte un propriétaire**. Cette seconde porte est désormais fermée : l'évaluation de conformité porte auteurs et statut, et les 17 actifs portent un propriétaire assigné. Voir `fixes.md` F5.
