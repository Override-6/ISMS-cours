# Feuille de travail — Séance 9, TP 1 (S9-05) : PSSI, fiche réflexe, procédure, indicateurs et tableau de bord

**Remplie à l'observé**, après saisie réelle dans `translog-b` (domaine `MERIDIAN-LOGISTIQUE`, périmètre
`MERIDIAN-LOGISTIQUE-FINAL`). Deux modes opératoires existaient pour cette séance, écrits **indépendamment**
avant la saisie par les deux membres du groupe : `PLAN-Seance-9-TP-S9-05-pssi-procedure-fiche-reflexe-indicateurs.md`
(Maxime, six indicateurs) et `PLAN-Seance-9-TP-S9-05-politique-fiche-reflexe-et-indicateurs.md` (Miguel, sept
indicateurs). Les exercices 1 à 3 convergent presque au mot près entre les deux plans ; l'exercice 4 diverge
sur le jeu d'indicateurs — **fusionné**, décision explicite de Maxime (« reprendre les meilleurs indicateurs
des deux plans »), détaillée en §4.

---

## 1. Exercice 1 — Section « gestion des vulnérabilités » de la PSSI-cadre — fait

Document **`PSSI-VUL`**, type *Policy*, domaine `MERIDIAN-LOGISTIQUE`, saisi conforme au plan : cinq règles
`PSSI-CADRE-VUL-01` à `05` (`VUL-01` reprend `COR-01` littéralement — correctif critique sous 14 jours ;
`VUL-02` reprend `PT-01` — recette + avenant avant toute mise à jour du WMS ; `VUL-03` à `VUL-05` couvrent
inventaire, qualification à 5 jours ouvrés, contrôle trimestriel). L'objet et fondement **cite** la
justification retenue dans D8 §2.2 pour `A.8.8` (*« directive `COR-01` de D1, non mesurée ; mises à jour du
WMS non maîtrisées ; scénario OS1 »*) plutôt que de la paraphraser — étape préalable exigée par l'énoncé,
vérifiée à l'écran (`S9-05-PSSI-VUL-in-review.png`). Dérogation `ARB-03` (48 h, RSSI Groupe) reprise pour
tout dépassement de `VUL-01`.

**Publication : réserve tenue, non levée.** L'outil ne bloque pas techniquement l'auto-validation (aucun
message d'erreur constaté au clic sur *Approve* par l'auteur), mais la convention du dossier depuis la
séance 3 est qu'un auteur ne valide pas son propre texte. Miguel n'étant pas connecté pendant l'exécution de
ce TP, le document reste **`In review`, v1**, auteur Maxime, en attente de la revue croisée de Miguel avant
la remise.

## 2. Exercice 2 — Procédure de revue trimestrielle des comptes à privilèges — fait (optionnel)

Document **`PRO-PRIV`**, type *Procedure*, six étapes numérotées, cas limite du compte partagé `svc-applica`
(`LOG-SA-04`, C4, `PT-02`) nommé explicitly et couvert jusqu'à sa fermeture au 14/01/2027. Rôle « Contrôle »
tenu par le RSSI Groupe **par défaut**, réserve écrite : la filiale n'a pas de RSSI (D8, clause 5.3).
Statut identique à l'exercice 1 : `In review`, même réserve de validation croisée
(`S9-05-PRO-PRIV-in-review.png`).

## 3. Exercice 3 — Fiche réflexe « suspicion de rançongiciel », site E1 — fait, test à blanc non tenu

Document **`FR-RANCON`**, type *Other* (aucun type « fiche réflexe » natif dans l'outil), site **E1** retenu
pour les trois raisons du plan (local serveur unique du WMS, entrepôt pharmaceutique, aucun automate — isole
le risque WMS sans mélanger IT/OT). Trois blocs saisis : actions immédiates (déconnexion réseau, jamais
extinction ; exercice du droit d'isolement `ARB-02` par le DSI de la filiale à défaut de RSSI ; nomination du
point de contact unique — comble le vide documenté depuis la séance 3), alertes (RSSI Groupe sous 2 h
`INC-01`, SOC, direction de la filiale, APPLICA informée **après** mise en sécurité seulement), interdits
(jamais éteindre, jamais payer sans validation DG, jamais restaurer avant capture forensique — RTO
**inconnu**, `PT-04` encore ouvert, jamais de contact technique hors circuit nommé). `S9-05-FR-RANCON-in-review.png`.

**Écart assumé, à corriger avant remise** : le **test à blanc chronométré en binôme** (Step 5 de l'énoncé —
une minute, montre en main, un lecteur qui récite les quatre premières actions sans relire) est un exercice
qui suppose deux personnes réellement présentes l'une avec l'autre ; il n'a **pas** été mené pendant cette
exécution outillée. **Reste dû, par Maxime et Miguel eux-mêmes**, avant la remise du 17 septembre.

## 4. Exercice 4 — Indicateurs et tableau de bord — fait, fusion des deux plans

### 4.1 Pourquoi une fusion, et pas l'un des deux plans tel quel

Le plan de Maxime posait six indicateurs dont **deux** calculables le jour même dans l'instance
(`IND-05` constats critiques sans plan daté, `IND-06` segmentation IT/OT) ; les quatre autres (couverture
PSSI-cadre, obsolescence, délai de détection, respect du délai de notification) dépendaient de données
groupe ou d'incidents réels **hors `translog-b`**, donc posés en `Draft` sans valeur. Le plan de Miguel,
écrit indépendamment, posait sept indicateurs dont **six** calculables le jour même, tous ancrés sur des
objets déjà présents dans l'instance (D7 §6, D8 §2.4, le registre de risques) plutôt que sur des données à
venir. Sur le critère même que l'énoncé retient — *« au moins un indicateur calculable aujourd'hui »*, dépassé
par les deux plans mais bien plus largement par celui de Miguel — le jeu de Miguel est le plus fort, à une
exception près : aucun des deux plans de Miguel ne portait un indicateur de **délai de détection**, alors que
c'est l'un des deux indicateurs directement issus du TD 1 de la matinée (candidat 5 du cas) et l'objet même
d'un des deux angles du bureau du RSSI de la séance. D'où la fusion, tranchée par Maxime : **les sept
indicateurs de Miguel repris quasiment tels quels, plus un huitième de détection**, plutôt que de choisir un
plan contre l'autre ou de les juxtaposer sans arbitrage.

### 4.2 Table de correspondance — ce qui est gardé, ce qui est abandonné, et pourquoi

| Indicateur retenu | Origine | Devenir des indicateurs de l'autre plan couvrant la même idée |
|---|---|---|
| `IND-01` Couverture de la déclaration d'applicabilité (16,1 %) | Miguel | Remplace l'`IND-01` de Maxime (couverture PSSI-cadre) — donnée groupe non disponible dans l'instance ; `IND-01` de Miguel se lit directement dans D8 |
| `IND-02` Écarts de conformité sans mesure de traitement (20 %) | Miguel | Recouvre l'intention de l'`IND-05` de Maxime (constats critiques sans plan daté) avec une base plus large — tous les écarts retenus, pas seulement les deux majeurs C3/C4 |
| `IND-03` Restaurations du WMS testées sur douze mois (0) | Miguel | Nouveau — c'est l'indicateur que le pack de filiale désigne nommément (§5), absent des deux plans jusqu'à la lecture de Miguel |
| `IND-04` Segmentation réseau IT/OT (0/6) | Miguel | Reprend l'`IND-06` de Maxime (même mesure `PT-03`), en comptage par entrepôt plutôt qu'en pourcentage — plus lisible pour un Comité qui doit voir « combien de sites restent » |
| `IND-05` Risques résiduels au-dessus du seuil d'acceptation (0 %) | Miguel | Nouveau — lit directement le registre de risques de D7 §1 |
| `IND-06` Accès TMA par compte nominatif (0 %) | Miguel | Nouveau — lit `PT-02` et le constat C4 |
| `IND-07` Respect du délai de notification à 2 h, `INC-01` (Draft) | Miguel | Recouvre l'`IND-04` de Maxime (même directive) ; gardé en `Draft`/« non mesuré » plutôt qu'une valeur inventée — c'est l'angle de la page individuelle de Miguel |
| `IND-08` Délai moyen de détection des incidents (Draft) | Maxime | Seul ajout au jeu de Miguel — aucun des deux plans de Miguel ne le portait ; recouvre l'`IND-03` de Maxime, gardé en `Draft` pour la même raison que `IND-07` |
| — | Maxime, abandonné | `IND-01` (couverture PSSI-cadre) et `IND-02` (obsolescence du parc) — aucune donnée dans l'instance à ce jour, remplacés par des indicateurs calculables |

Aucune valeur n'a été inventée pour combler `IND-07`/`IND-08` : les deux restent `Draft`, affichés
**« non mesuré »** dans la description plutôt que laissés vides — l'argument même de la page de Miguel
(« une case vide se lit comme une case verte »), désormais prouvé dans l'outil plutôt qu'écrit seulement sur
la page individuelle.

### 4.3 Exécution outillée

Saisie faite par scripts Python (`playwright.sync_api`, environnement `uv` isolé, Chromium installé sans
`--with-deps` faute de droits root) pour les opérations répétitives (8 définitions × 8 instances × 6
échantillons datés × 8 tuiles de tableau de bord), et par les outils MCP Playwright pour les vérifications
visuelles et les deux derniers correctifs de texte. Résultat final vérifié par compte de lignes après chaque
phase (8/8 à chaque fois) :

- **8 metric definitions** (`Metrics → Metric definitions`) : chaque description préfixée par sa nature —
  `[Compliance]`, `[Risk]` ou `[Operations]` — case *higher is better* décochée sur les trois comptes qui
  doivent baisser (`IND-02`, `IND-05`, `IND-08` en heures) ou rester à zéro (`IND-06` visé à 100 % donc
  cochée). `S9-05-metric-definitions-huit-indicateurs.png`.
- **8 metric instances**, une par définition, description au format formule + source + seuil + fréquence +
  destinataire + objectif de la note surveillé (repris du gabarit de plan), `Assigned to` renseigné. Statut
  **Active** pour `IND-01` à `IND-06`, **Draft** pour `IND-07`/`IND-08`. `S9-05-metric-instances-huit-lignes.png`
  et le détail complet d'une fiche, `S9-05-IND-04-fiche-detail.png` (formule, source `PT-03`, cible 6/6,
  seuil d'alerte, destinataire Comité Exécutif, objectif suivi sous-sections 7 et 8, échantillon daté).
- **6 échantillons datés du 16/09/2026** sur les instances actives, chacun avec une observation sourcée :
  `IND-01` 16,1 % (D8, 15/93 contrôles investigués), `IND-02` 20 % (3 orphelins sur 15 investigués), `IND-03`
  0 (D1/pack §5, aucune restauration jamais testée), `IND-04` 0/6 (`PT-03` non démarré), `IND-05` 0 %
  (aucune ligne du registre D7 au-dessus du seuil `Medium` sans traitement daté), `IND-06` 0 % (`PT-02` non
  démarré, comptes partagés toujours en place).
- **Tableau de bord `TDB-COMEX`** reconstruit : description à jour (huit indicateurs, note de fusion des deux
  plans), tuile de période resserrée (« Huit indicateurs, pas un de plus »), **huit cartes KPI ordonnées par
  poids de décision** (`IND-03`, `IND-04`, `IND-06` en tête — rouges mais avec un plan daté ; puis `IND-02`,
  `IND-05` ; puis `IND-01` ; puis `IND-07`, `IND-08` en `Draft`/non mesuré), tuile de fermeture « Messages et
  décisions demandées » (trois points numérotés : les trois indicateurs rouges-mais-planifiés, les écarts
  orphelins de `IND-02`, le choix délibéré de ne pas afficher `IND-07`/`IND-08` comme conformes).
  `S9-05-dashboard-fusionne-final.png`.

### 4.4 Écarts d'outil rencontrés, et comment ils ont été tenus

- **Boutons de suppression, deux comportements différents.** Sur les tuiles du tableau de bord, le bouton de
  suppression porte un attribut `title="Delete"`. Sur les listes de métriques (*Metric definitions*,
  *Metric instances*), le bouton équivalent porte `data-testid="tablerow-delete-button"` et
  `aria-label="Delete"`, **sans** attribut `title`. Un premier script ciblant `title="Delete"` sur les deux
  types d'écran a silencieusement échoué à supprimer les anciennes lignes (aucune erreur levée, la boucle de
  suppression comptait 0 bouton trouvé et passait à la ligne suivante) — six définitions et six instances de
  l'ancien jeu à six indicateurs sont restées en double aux côtés des huit nouvelles pendant un temps. **Reprise
  complète** : script final (`final_clean_build.py`) qui supprime **sans condition** toutes les lignes des
  deux listes avant de tout recréer, avec vérification du compte (0 puis 8) à chaque étape plutôt que de
  patcher l'état intermédiaire.
- **Confirmation de suppression** : modale intégrée à l'application (`data-testid="delete-confirm-button"`),
  pas une boîte de dialogue native du navigateur — aucun gestionnaire `page.on("dialog")` nécessaire.
- **Champs date/heure (`datetime-local`)** peu fiables à la saisie clavier séquentielle (un cas observé où
  « 09/16/2026 » saisi caractère par caractère a produit « 09/12/2026 »). Fixé en écrivant directement la
  valeur via le setter natif de `HTMLInputElement` puis en déclenchant les événements `input`/`change`.
- **Pagination** : les listes affichent 10 lignes par défaut ; avec 14 lignes en état transitoire (6
  anciennes + 8 nouvelles), les dernières restaient invisibles sans sélectionner « 50 » dans le sélecteur
  *Show entries*.
- **Navigation vers le détail d'une instance** : cliquer sur la ligne n'ouvre pas fiablement la page de
  détail (comportement de SPA peu clair). Fixé en lisant l'attribut `href` du lien *View* de la ligne puis en
  y naviguant directement (`page.goto`).

## 5. Correction mécanique portée hors du TP, mais due à cette séance (`fixes.md` F22 §3)

`D8` §2.4 rapprochait déjà `PT-02` de `A.5.15` et `PT-01` de `A.8.8`, en le signalant explicitement comme une
**lecture de D8 non répercutée dans D7 §6**, avec la note *« correction due dans D7 §6 en séance 9 »*. Le
tableau mesure ↔ exigence de `D7-plan-de-traitement-et-risque-residuel.md` §6 a été complété en conséquence
(`A.5.15` ajouté à la ligne `PT-02`, `A.8.8` ajouté à la ligne `PT-01`), et le tableau des orphelins de `D8`
§2.4 mis à jour pour refléter que les deux contrôles ne sont plus orphelins. C'est une correction mécanique
(la cible était déjà écrite et justifiée dans D8, il ne manquait que le report), pas un arbitrage — à la
différence des quatre écarts de fond suivants, laissés intacts.

## 6. Ce qui n'a pas été tranché ici — quatre arbitrages de `fixes.md` F17, à décider par les deux auteurs

Le `README.md` de `2-Labs/` signale deux chantiers hérités pour cette séance : la correction de `D7` §6 (faite,
§5 ci-dessus) et le règlement des écarts de fond de F17. **Ces derniers n'ont pas été tranchés** : ce journal
les décrit et les laisse volontairement intacts, précisément parce que chacun est une décision d'auteur, pas
une correction mécanique. Pour mémoire (détail complet dans `fixes.md`, section F17) :

- **(a)** trois mesures de `D4` datées différemment de leur équivalent `D7` sur le même contrôle
  (`M1`/`PT-03`, `M2`/`PT-06`, `M4`/`PT-02`) — à trancher mesure par mesure : même mesure (amendement croisé)
  ou mesures distinctes (renvoi explicite).
- **(b)** le titre du dirigeant de la filiale, « Directeur » dans cinq pièces contre « Directrice Générale »
  dans deux — le poids des pièces penche vers « Directeur de la filiale ».
- **(c)** les porteurs de `M2`/`M4` dans `D4` sont des noms d'étudiants (« Maxime + Miguel ») plutôt que des
  rôles de la carte du pouvoir.
- **(e)** les six jalons de `D6` ne portent aucune date propre (le 14/09/2027 vit dans `D7`, pas dans `D6`).

*(le point (d) — correspondance des niveaux de risque — a déjà été fermé par F18 ; le point (f) est sans
gravité, en attente de `PT-13`.)*

## 7. Captures produites, réconciliées avec la liste prévue par `3-Evidence/README.md`

Neuf captures produites, préfixe `S9-05-` — le tableau ci-dessous fait correspondre chacune à ce que la liste
initiale attendait :

| Capture produite | Couvre |
|---|---|
| `S9-05-PSSI-VUL-in-review.png` | Document `PSSI-VUL` publié en revue, cinq règles visibles, citation de la justification A.8.8 |
| `S9-05-PRO-PRIV-in-review.png` | Document `PRO-PRIV`, exercice optionnel |
| `S9-05-FR-RANCON-in-review.png` | Fiche réflexe, trois blocs visibles |
| `S9-05-documents-liste-trois-objets.png` / `S9-05-documents-manage-view-trois-objets.png` | Vue liste et vue gestion des trois documents ensemble |
| `S9-05-metric-definitions-huit-indicateurs.png` | Les huit définitions (attendu : sept — le jeu fusionné en porte huit, §4.2) |
| `S9-05-metric-instances-huit-lignes.png` | Les huit instances, valeurs et statuts |
| `S9-05-IND-04-fiche-detail.png` | Gabarit complet d'une fiche (formule, source, cible, échantillon daté) — répond au point « détail d'une instance complète » de la liste initiale |
| `S9-05-dashboard-fusionne-final.png` | Le tableau de bord `TDB-COMEX`, page entière, daté — la maquette de `D9` |

**Non couvert par une capture dédiée, à ne pas laisser dans l'angle mort** : la relation explicite `PSSI-VUL`
→ `PT-01` (le document ne porte pas de section *Relations* structurée dans cette version de l'outil ; la
citation de `PT-01` est **textuelle**, dans la règle `VUL-02`, visible sur la capture du document lui-même) ;
le statut `Draft` isolé de `IND-07` (visible sur `S9-05-metric-instances-huit-lignes.png`, ligne `IND-07`,
colonne *Status*, sans capture dédiée).

## 8. Ce qui reste dû

- **Revue croisée des trois documents par Miguel** (`Approve` ou `Request changes` sous son propre compte) —
  aucun des trois n'est publié en version validée à ce jour, tous restent `In review`.
- **Test à blanc en binôme de `FR-RANCON`**, chronométré, à mener réellement par Maxime et Miguel (§3).
- **Les quatre arbitrages de F17** (§6) — décision des deux auteurs, pas une correction que cette feuille
  peut prendre à leur place.
- **Le livrable `D9`** (`D9-politique-procedures-et-indicateurs.md`, 3 points) et la **sous-section 9 de la
  note de stratégie** — objet du TP 2 (S9-06), non commencé.
- **TP 2** : vérification du jeu d'indicateurs contre les cinq questions du Comité, capture tuile par tuile
  datée, rédaction de la sous-section 9.
- **La réserve de longueur de la page S9 de Miguel** (832 mots contre un maximum d'une page) — reliquat F19,
  à traiter dans la passe unique sur les dix-huit pages du bureau du RSSI, hors périmètre de ce TP.
