# Séance 3 — TD (S3-03) : Selecting a framework and mapping tables
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN

> Enchaînement de la journée : le CM (S3-02) a dressé la carte, le TD du matin (S3-01) a caractérisé l'applicabilité NIS 2 filiale par filiale, **ce TD transforme la carte en décision** — une grille pour choisir, un tableau pour réutiliser. La version complète et argumentée sera la note de business case du TP de fin de journée (S3-06).

---

## Rappel du cas et des deux notions du TD

Jeudi. Le Comité Exécutif attend du RSSI Groupe la proposition d'**un référentiel unique** servant de colonne vertébrale à la sécurité des quatre filiales. Trois candidats sur la table : **ISO/IEC 27001:2022**, le **ReCyF**, le **Guide d'hygiène informatique de l'ANSSI**.

**Un critère de sélection** est un attribut du référentiel, **observable et comparable**, évalué AVANT de décider : est-il obligatoire pour nous ou le deviendra-t-il ; couvre-t-il notre périmètre réel, technique et organisationnel ; permet-il une preuve opposable ; existe-t-il en français et est-il maintenu ; notre outillage et nos équipes peuvent-ils le porter ; que coûte-t-il, en licences comme en effort. Mécanique : lister, pondérer, noter, et surtout **écrire la justification de chaque note** — c'est elle qui sera contestée, jamais le chiffre. Limite à connaître d'avance : **une grille pondérée ne calcule pas la bonne réponse, elle rend la délibération transparente.** Si son résultat heurte le bon sens, c'est la pondération qu'on réexamine, pas le bon sens.

**Un tableau de correspondance** (*mapping*) met en regard, ligne à ligne, les exigences d'un référentiel **source** et celles d'un référentiel **cible**, pour réutiliser ce qui est déjà fait et repérer ce qui manque. Anatomie d'une ligne réelle, tirée du jeu NIST CSF → ISO 27001 livré avec CISO Assistant (180 lignes) : **exigence source** `ID.AM-1` · **exigence cible** `A.5.9` · **relation** `intersect` · **justification** `semantic`. Deux enseignements décisifs : dans tout ce jeu, **aucune ligne ne déclare deux exigences équivalentes**, toutes disent « intersection » ; et « semantic » signifie que la correspondance est un **jugement de sens**, pas une équivalence juridique. L'ANSSI le dit elle-même en tête de son outil de comparaison, mis à disposition « à titre purement informatif et indicatif ».

> ⚠️ **Règle appliquée dans tout ce document** : un tableau de correspondance aide à comprendre et à réutiliser, il **ne transfère jamais la conformité**. Être conforme à la source ne rend pas conforme à la cible ; cela donne une avance, qui reste à prouver dans les termes de la cible.

---

## Exercice 1 — La grille de sélection du groupe MERIDIAN

### Q1. La grille complète : pondérations, notes de 0 à 3, une justification par note

**Pondérations retenues et leur justification par le contexte MERIDIAN** (somme = 100) :

| Critère | Pond. | Pourquoi ce poids, dans NOTRE contexte |
|---|---|---|
| **Caractère obligatoire, actuel ou à venir** | **30** | Le poids le plus lourd, mais pas écrasant : au moins deux filiales tomberont dans NIS 2 (Santé très probablement essentielle, Logistique essentielle ou importante — S3-01 Q3), et le RGPD s'applique déjà aux quatre. On ne choisit pas ce qui s'impose. |
| **Couverture du périmètre du groupe** | **25** | Quatre filiales aux métiers disjoints, dont un **périmètre OT** (automates, WMS, sondes) et un périmètre biomédical : un référentiel qui ne parlerait qu'au SI bureautique laisserait dehors les deux écarts de priorité 1 de notre analyse d'écart (S1-05 Ex. 1). |
| **Preuve opposable aux tiers** | **20** | Les ~30 collectivités clientes de Territoires exigent des garanties, le client pharmaceutique de Logistique a **annoncé un questionnaire de sécurité** pour son prochain audit, et Santé doit répondre à ses partenaires hébergeurs (HDS). La preuve n'est pas un luxe de communication, c'est une condition commerciale. |
| **Maturité et stabilité du texte** | **15** | Un référentiel-colonne vertébrale est une décision qu'on ne rouvre pas tous les six mois. C'est la colonne où un texte en cours de construction doit **payer** son instabilité. |
| **Outillage et charge de mise en œuvre** | **10** | Poids volontairement faible **mais non nul** : la Direction Générale exige « sans budget nouvel la première année », donc la charge compte ; mais elle ne peut pas décider de la colonne vertébrale d'un groupe de 7 550 salariés, sous peine de choisir le plus facile plutôt que le plus juste. |

**La grille notée** (0 = ne répond pas, 3 = répond pleinement) :

| Critère | Pond. | ISO/IEC 27001:2022 | ReCyF | Guide d'hygiène |
|---|---|---|---|---|
| Caractère obligatoire | 30 | **1** — norme volontaire ; ne devient contraignante que par le contrat, ce qui arrive déjà (clients de Territoires) | **3** — destiné à devenir le référentiel de contrôle de l'ANSSI : ses objectifs de sécurité seront **fixés par décret** (art. 14 du projet de loi) | **1** — force juridique nulle ; opposable seulement comme état de l'art invoqué par un juge, un assureur ou un client |
| Couverture du périmètre | 25 | **3** — 93 mesures, 4 thèmes (organisationnel, humain, physique, technologique) + clauses de management : couvre le SI, l'OT et le pilotage, sur un périmètre que l'on déclare | **2** — 20 objectifs taillés pour les entités NIS 2 : ne dit rien d'**Éducation**, hors champ (S3-01 Q3), et ses objectifs 16 à 20 ne visent que les entités essentielles | **1** — 42 mesures d'hygiène généralistes, faibles sur la gouvernance de groupe et sur l'industriel |
| Preuve opposable | 20 | **3** — **le seul des trois** menant à une certification par tierce partie, sur un périmètre écrit noir sur blanc | **1** — aucune certification ; l'entité qui applique ses moyens acceptables pourra s'en prévaloir **devant l'ANSSI**, pas devant une collectivité cliente aujourd'hui | **1** — son outil de suivi en annexe ne produit qu'une **auto-déclaration** |
| Maturité et stabilité | 15 | **3** — édition 2022, norme internationale maintenue, ~1 000 organismes certifiés en France fin 2023 (AFNOR/ISO Survey), soit trois fois plus qu'en 2019 | **1** — version de travail diffusée depuis le **17 mars 2026**, objectifs non encore fixés par décret : le texte peut bouger jusqu'aux textes d'application | **2** — stable, mais c'est la **v2 de 2017** : stable par immobilité autant que par maturité |
| Outillage et charge | 10 | **2** — s'importe nativement dans CISO Assistant (constaté au TP S2-05), mais l'ISMS des clauses 4 à 10 et l'audit de certification sont une charge réelle | **3** — gratuit, 20 objectifs, et **bibliothèque native dans l'instance** (vérifié à l'écran le 8 sept. 2026) : la charge de mise en œuvre est la plus légère des trois | **3** — gratuit, 42 mesures, deux niveaux (standard / renforcé) et son propre outil de suivi : utilisable dès demain matin |
| **Total pondéré (sur 300)** | **100** | **230** | **205** | **135** |

> ⚠️ **Correction du 8 septembre 2026.** La note d'outillage du ReCyF était de **2**, justifiée par un « outillage encore incertain ». La capture `S3-05-ex4-library-search-ReCyF-FOUND-see-note.jpg` montre que le référentiel **est présent nativement** dans la bibliothèque de l'instance. La note passe à **3**, le total de 195 à **205**. Le classement ne bascule pas ; les tests de sensibilité ci-dessous sont recalculés en conséquence.

*Détail du calcul — ISO : 30+75+60+45+20 · ReCyF : 90+50+20+15+**30** · Guide : 30+25+20+30+30.*

**Lecture** : ISO/IEC 27001 devance le ReCyF de **25 points sur 300**, et le Guide d'hygiène est distancé de près de 100. Le Guide gagne la seule colonne de la charge et perd toutes les autres : **c'est un point de départ, pas une colonne vertébrale de groupe.**

### Q2. Le critère qui mérite un droit de veto plutôt qu'une pondération

**La couverture du périmètre.** Une moyenne pondérée **compense** — c'est sa fonction — or certains critères **ne se compensent pas**. Un référentiel qui ignorerait les obligations sectorielles de Santé (HDS) ou le périmètre OT de Logistique resterait **disqualifiant même noté 3 partout ailleurs** : c'est la différence entre une **note** et une **condition**.

La règle de veto que nous inscrivons en tête de la grille, avant toute note :

> *Est écarté, quelle que soit sa note pondérée, tout référentiel ne permettant pas de couvrir simultanément : les obligations sectorielles de Santé (HDS), le périmètre industriel de Logistique (automates, WMS, chaîne du froid), et une filiale hors champ NIS 2 (Éducation).*

Appliquée aux trois candidats, elle change une chose et une seule, mais elle la change avant le calcul : **le ReCyF ne peut pas être la colonne vertébrale du groupe**, parce qu'il n'a rien à dire d'une filiale qui n'est pas une entité NIS 2 — et Éducation, 900 salariés et 45 000 comptes, ne cesse pas d'exister parce qu'elle est hors annexes. Ce n'est pas sa note de 205 qui l'écarte, c'est une condition qu'il ne remplit pas. La nuance est capitale pour le ComEx : nous n'écartons pas le ReCyF comme *mauvais*, nous l'écartons comme *colonne vertébrale*, et nous le gardons comme référentiel de **veille active** (cf. exercice 3).

**Le piège symétrique, explicitement évité** : confondre « note faible » et « condition non remplie ». Le ReCyF a une note faible en preuve opposable — cela se compense. Il ne couvre pas une filiale sur quatre — cela ne se compense pas.

### Q3. Analyse de sensibilité : à quelle condition le classement bascule-t-il ?

L'écart à combler est de **25 points**. Le ReCyF ne devance ISO que sur **un** critère, le caractère obligatoire (3 contre 1). Deux tests de bascule :

| Test | Manipulation | Résultat | Lecture |
|---|---|---|---|
| **Transfert de pondération** | Faire passer « caractère obligatoire » de 30 à **39** et « maturité » de 15 à **6** | ISO **212**, ReCyF **223** → **bascule** | Il faut toujours déplacer **9 points sur 100**, soit près d'un tiers du poids du critère déjà le plus lourd, ET réduire la stabilité du texte à presque rien : c'est un **changement de doctrine**, pas un réglage fin. Mais depuis la correction du 8 sept., la bascule est plus large (11 points au lieu de 1) — l'arithmétique protège moins qu'on ne le croyait. |
| **Suppression d'un critère** | Retirer purement et simplement « preuve opposable » (20 points) | ISO **170**, ReCyF **185** → **bascule** | Ce test dit ce qui protège réellement notre recommandation : **les clients de Territoires et le questionnaire du client pharma**. Si le ComEx juge la preuve accessoire, il choisit un autre référentiel — et il doit le dire explicitement. |

**Ce que cette sensibilité enseigne** — et la correction du 8 septembre l'a rendu plus vrai, pas moins : **ce n'est pas la grille qui porte la recommandation, c'est la règle de veto.** Les deux tests basculent désormais plus largement, et l'écart de base n'est plus que de 25 points. Si notre choix ne tenait qu'à l'arithmétique, il serait fragile. Il tient à une **condition** — couvrir une filiale hors champ NIS 2 — que le ReCyF ne remplit pas quelle que soit sa note. La recommandation reste **robuste sans être inattaquable**, et elle repose sur deux jugements de contexte que le ComEx **doit valider explicitement** : que la preuve opposable aux tiers compte, et que la stabilité du texte compte. Les deux scénarios seront présentés dans la note de business case (S3-06), conformément au réflexe attendu : *une analyse qui ne teste pas sa propre bascule est une mise en scène, pas une analyse.*

---

## Exercice 2 — Trois exigences, trois correspondances

*Rappel du piège annoncé : la tentation de cocher « équivalence » partout où les sujets se ressemblent. **La relation se juge sur ce que les textes EXIGENT, pas sur ce dont ils parlent.***

### Exigence A — ANSSI, jeu d'exigences NIS 2, réf. `1.1-EI/EE`

> *« L'entité liste l'ensemble de ses activités et services, y compris les activités et services qui ne correspondent pas aux critères pour lesquels l'entité constitue une entité importante ou essentielle »*, et pour chaque entrée, identifie **un propriétaire** et liste **les systèmes d'information qui la supportent**.

**1. Correspondance côté ISO/IEC 27001:2022** — l'exigence touche **les deux blocs**, et c'est là toute sa subtilité :
- **Clauses 4 à 10** (management) : la clause 4, *contexte de l'organisation*, pour la partie « lister ses activités et services » et la détermination du domaine d'application.
- **Annexe A, thème organisationnel** : `A.5.9` *Inventaire des informations et autres actifs associés* (l'inventaire opérationnel **avec propriétaire**), avec un appui de `A.5.12` sur la classification.

**2. Verdict : intersection** — et certainement pas équivalence. Ce que la source exige et que la cible n'exige pas : lister **AUSSI les activités hors critères d'applicabilité**. Formulé d'une phrase, c'est un renversement complet de logique : **ISO permet de choisir son périmètre ; NIS 2 interdit de le choisir.** Un ISMS certifié sur le seul WMS de Logistique serait parfaitement conforme à ISO et ne dirait rien de l'exigence A.

**3. Ce que MERIDIAN a déjà** :
- **S2-03** (valeurs métier et biens supports de Logistique) : les 4 valeurs métier et leurs biens supports des trois natures répondent **à la lettre** au « liste les systèmes d'information qui la supportent ».
- **S2-05** (saisie dans CISO Assistant) : les mêmes objets typés, avec propriétaires et *security targets*, dans un référentiel unique — l'exigence demande un inventaire tenu, pas un tableur.
- **S2-01 Q5** (règle de gouvernance) : *« chaque filiale tient son inventaire dans le référentiel commun, avec un propriétaire nommé pour chaque actif ; tout élément découvert en dehors est rattaché ou traité sous trente jours »* — la règle de tenue est écrite.
- **Ce qui manque** : le **propriétaire par activité** (nous avons des propriétaires par actif) — la matrice RACI de **S1-05 Ex. 2** permet de le compléter en une réunion ; et surtout, côté Logistique, les **systèmes d'information supportant** les activités hors critères (entreposage sous température dirigée, télématique de la flotte, paie/comptabilité hébergées chez le holding) — c'est-à-dire exactement la lacune des **plages d'adresses IP** identifiée en S3-01 Q5, avec la box 4G de l'intégrateur hors réseau supervisé.

### Exigence B — ReCyF, objectif de sécurité n° 2

> Mise en œuvre d'un **cadre de gouvernance de la sécurité numérique** : une organisation, des rôles et responsabilités, des processus de gestion de la conformité, et une politique de sécurité des systèmes d'information.

**1. Correspondance côté ISO/IEC 27001:2022** — la plus directe des trois, du côté des **clauses de management** : clause 5 *leadership* (5.2 politique, **5.3 rôles, responsabilités et autorités**), clause 6 *planification*, clause 9 *évaluation des performances* pour la gestion de la conformité ; avec un **débordement** sur le thème organisationnel de l'annexe A pour les politiques (`A.5.1` politiques de sécurité de l'information, `A.5.2` fonctions et responsabilités).

**2. Verdict : intersection forte.** C'est le cas qui donne tout son sens au *moyen acceptable de conformité* vu au CM : **le ReCyF lui-même accepte un ISMS certifié ISO/IEC 27001:2022 comme démonstration de CET objectif**, « sur les systèmes d'information couverts par la certification ». Deux bornes, et elles sont l'essentiel : **un objectif sur vingt**, et **le seul périmètre du certificat**.

**3. Ce que MERIDIAN a déjà** :
- **S1-05 Ex. 2** : l'organisation (instances + rôles sur l'appétence au risque), la **matrice RACI** à propriétaire unique par ligne, les **5 directives codifiées** `[PSSI-CADRE-ACC-01]` à `[PSSI-CADRE-COR-01]`, les **3 règles d'arbitrage** `[ARB-01/02/03]` → les points « organisation » et « rôles et responsabilités » sont couverts à l'essentiel.
- **S1-06 Ex. 1** : la note de cadrage (but, périmètre, prérogatives, contreparties, limites) — le mandat écrit qui manque à beaucoup d'organisations.
- **Ce qui manque** : la **PSSI-cadre** n'existe qu'à l'état d'embryon (cinq directives codifiées, pas une politique complète), et surtout **les processus de gestion de la conformité n'existent pas** — aucun de nos livrables n'organise la mesure récurrente de l'écart. C'est précisément ce que l'outil GRC portera (TP S3-05), et c'est la raison pour laquelle l'importer n'est pas une formalité technique.

### Exigence C — Guide d'hygiène, mesure 4

> Identifier les **informations et serveurs les plus sensibles** et **maintenir un schéma du réseau**.

**1. Correspondance côté ISO/IEC 27001:2022** — **Annexe A, thème organisationnel** : `A.5.9` (inventaire) et `A.5.12` (classification). L'inventaire et la topologie relèvent des **mesures**, pas du management : c'est le test proposé par l'énoncé — *la mesure organise-t-elle le pilotage, ou déploie-t-elle un contrôle ?* Ici, elle déploie un contrôle. *(Le schéma réseau alimente ensuite les mesures du thème technologique — `A.8.20` sécurité des réseaux, `A.8.22` cloisonnement — mais il n'en est pas une lui-même.)*

**2. Verdict : intersection** avec ISO, **et intersection avec l'exigence A** — et c'est le point qui méritait d'être écrit : **les correspondances se composent, mais chaque recouvrement est partiel et les pertes s'additionnent**. Le « schéma réseau simplifié » du guide est **moins exigeant** que l'inventaire complet de l'exigence A : *une organisation conforme à C n'a pas fini A.*

**3. Ce que MERIDIAN a déjà** : S2-03 et S2-05 identifient les actifs sensibles et les **serveurs du WMS à E1** (2 serveurs + base, dans un local au fond de l'atelier de maintenance, climatisation défaillante). **Ce qui manque, et c'est le plus embarrassant du TD : il n'existe aucun schéma réseau de Logistique.** Réseaux IT et OT interconnectés sans cloisonnement (constat 1 du diagnostic), box 4G de l'intégrateur hors du réseau supervisé, ~300 scannettes en Wi-Fi. **Des trois exigences examinées, la plus modeste est la seule que nous ne satisfaisons pas** — et c'est le chantier déjà inscrit à 24 mois dans notre feuille de route (S1-06 Ex. 2).

### Récapitulatif à l'anatomie du TD (4 champs par ligne)

| Exigence source | Exigence cible (ISO/IEC 27001:2022) | Relation | Justification |
|---|---|---|---|
| `NIS2 1.1-EI/EE` — activités, services, propriétaires, SI supports | Clause 4 (contexte) **+** `A.5.9` | **intersect** | *semantic* — la source impose de lister **hors** périmètre d'applicabilité ; la cible autorise à borner son périmètre |
| `ReCyF Obj. 2` — cadre de gouvernance | Clauses 5, 6, 9 **+** `A.5.1`, `A.5.2` | **intersect** (forte) | *semantic* — reconnue par le ReCyF comme moyen acceptable, borné à **un** objectif et au **périmètre du certificat** |
| `Hygiène mesure 4` — actifs sensibles + schéma réseau | `A.5.9`, `A.5.12` | **intersect** | *semantic* — le schéma « simplifié » de la source est moins exigeant que l'inventaire de `NIS2 1.1`, avec lequel il s'intersecte aussi |

*Aucune ligne ne porte « equivalence » — comme dans les 180 lignes du jeu livré avec l'outil.*

### Q4. Conclusion en deux phrases : « nous serons conformes NIS 2 puisque nous appliquons ISO 27001 »

> **L'affirmation est fausse au sens strict** : la doctrine officielle tient en une ligne — **aucune présomption générale de conformité** (FAQ NIS 2 de l'ANSSI : « l'obtention d'une certification ISO 27001 ne permet pas, en elle-même, une conformité à NIS 2 »), mais **un moyen acceptable, borné à un objectif et à un périmètre** (ReCyF, objectif 2, « sur les systèmes d'information couverts par la certification »). **Le cas A suffit à le démontrer** : ISO laisse l'organisation choisir le périmètre de son ISMS, là où NIS 2 exige de lister jusqu'aux activités **hors** critères d'applicabilité — un groupe certifié sur sa seule filiale la mieux tenue aurait donc un certificat impeccable et **n'aurait rien prouvé** sur les trois autres.

---

## Exercice 3 — La recommandation en dix lignes au Comité Exécutif

> **Recommandation du RSSI Groupe — référentiel de sécurité du groupe MERIDIAN**
>
> Nous recommandons **ISO/IEC 27001:2022** comme référentiel colonne vertébrale des quatre filiales. Deux arguments le désignent dans la grille : il est le **seul candidat couvrant l'intégralité du périmètre du groupe**, filiales dans le champ NIS 2 comme filiale hors champ, systèmes de gestion comme environnements industriels ; et il est le **seul menant à une preuve opposable à un tiers**, exigence déjà posée par les collectivités clientes de Territoires et par le questionnaire de sécurité annoncé par le client pharmaceutique de Logistique. Ce choix **ne délivre à lui seul aucune conformité réglementaire** : le RGPD, l'exigence HDS de Santé et le RGS de Territoires continuent de s'appliquer indépendamment, et la future conformité NIS 2 se démontrera devant les objectifs du **ReCyF**, dont une certification ne couvrirait que l'objectif de gouvernance, sur le seul périmètre certifié. Nous traitons ce reste par trois moyens : une **veille active** sur le ReCyF et la loi Résilience, un **tableau de correspondance** tenu à jour pour que chaque effort ISO soit réutilisé au titre de NIS 2, et l'application immédiate du **Guide d'hygiène** là où l'urgence l'impose, à commencer par le cloisonnement IT/OT de Logistique. **Décision demandée au Comité Exécutif : approuver ISO/IEC 27001:2022 comme référentiel de groupe et mandater le RSSI Groupe pour arrêter, filiale par filiale, le périmètre de son déploiement.**

### Vérification des contraintes de l'exercice

| Contrainte | Vérification |
|---|---|
| **Dix lignes au plus** | Le paragraphe tient en dix lignes rédigées, sans titre ni liste — format « lu à voix haute en comité ». |
| **Deux arguments décisifs tirés de la grille** | Couverture du périmètre (25) et preuve opposable (20) — soit exactement les deux critères dont le test de sensibilité a montré qu'ils portent la recommandation. |
| **Ce que le choix ne couvre PAS, et comment le reste est traité** | Dit explicitement : ni RGPD, ni HDS, ni RGS, ni conformité NIS 2 automatique ; traité par veille ReCyF + tableau de correspondance + guide d'hygiène en mesure d'urgence. |
| **Une décision demandée** | Dernière phrase : approuver le référentiel **et** mandater sur le périmètre — parce qu'un référentiel approuvé sans périmètre ne s'applique nulle part. |
| **Vraie que la loi soit promulguée dans 3 ou 18 mois** | Aucune date, aucun engagement de calendrier, aucune affirmation sur l'état du droit français : le ReCyF y est nommé comme référentiel à suivre, pas comme obligation en vigueur. |
| **Ne promet aucune conformité qu'aucun texte n'accorde** | La troisième phrase énonce l'inverse d'une promesse : elle **retire** la conformité réglementaire du bénéfice attendu. |

---

## Ce que nous n'affirmons pas (et pourquoi c'est volontaire)

1. **« Le ReCyF est un mauvais référentiel. »** Il est le mieux placé sur le seul critère qui pèse 30 points, et il deviendra le référentiel de contrôle de l'ANSSI. Nous l'écartons comme **colonne vertébrale**, sur une condition de couverture, pas sur une note.
2. **« La grille a tranché. »** Elle a rendu la délibération transparente ; le test de sensibilité montre qu'une doctrine différente sur la preuve opposable inverserait le classement. Le ComEx tranche, la grille documente.
3. **« Nous sommes en avance grâce aux séances 1 et 2. »** Sur l'exigence A nous avons l'essentiel, sur l'exigence B il manque toute la gestion de la conformité, et sur l'exigence C — la plus simple des trois — nous n'avons **rien** : pas de schéma réseau.

---

## Auto-évaluation (grille officielle du TD)

| Critère | Notre niveau atteint |
|---|---|
| **Grille (ex. 1)** | Cinq pondérations justifiées **une par une** par le contexte MERIDIAN (Santé essentielle probable, ~30 collectivités de Territoires, contrainte « sans budget nouveau »), et **une justification écrite pour chacune des 15 notes** — jamais un chiffre nu |
| **Veto et sensibilité (ex. 1)** | Un critère disqualifiant identifié (couverture du périmètre), rédigé en **règle de veto placée avant le calcul**, avec la distinction explicite note faible / condition non remplie ; **deux** tests de bascule chiffrés (transfert de 9 points ; suppression du critère de preuve) et leur interprétation |
| **Correspondances (ex. 2)** | Trois verdicts qualifiés, **aucune « équivalence »**, bloc ISO et thème d'annexe désignés pour chacun, livrables S1/S2 cités précisément (S1-05 Ex. 2, S1-06 Ex. 1, S2-01 Q5, S2-03, S2-05), et récapitulatif rendu à l'anatomie à 4 champs du TD |
| **Conclusion (ex. 2)** | Doctrine « pas de présomption, un moyen borné » reformulée **et adossée au cas A**, avec la formule qui la porte : ISO laisse choisir le périmètre, NIS 2 interdit de le choisir |
| **Recommandation (ex. 3)** | Dix lignes, deux arguments issus de la grille, lacunes assumées et traitées, décision demandée en dernière phrase, **aucune promesse de conformité automatique**, aucune date opposable |

*Chaque case vise la colonne « Excellent » de la grille officielle — à confronter en séance avec le corrigé de référence du module.*
