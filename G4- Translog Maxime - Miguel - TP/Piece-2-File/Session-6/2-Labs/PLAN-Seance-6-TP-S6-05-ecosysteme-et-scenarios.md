# PLAN D'ACTION — Séance 6, TP 1 : écosystème et scénarios dans CISO Assistant (atelier 3 + amorce de l'atelier 4)

**Groupe 4 (Translog)** · instance `translog-b` (https://translog-b.lockbay.eu)
**Domaine** `MERIDIAN-LOGISTIQUE` (sous-domaine de `Global`) · **périmètre** `MERIDIAN-LOGISTIQUE-FINAL`
**Étude à rouvrir** : `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1`
**Source du TP** : `../../../../S6 - Sources/TP 1/Ecosystem Analysis and Scenarios on CISO Assistant _ Lockbay Academy.pdf`
**Matière à saisir** : `../4-Working-notes/Seance-6-TD-S6-03-management-des-tiers-infogerance-ateliers-3-4.md` (TD 2, exercice 2 — la carte de dangerosité et le scénario stratégique) · `../1-CISO-desk/Seance-6-TD-S6-01-attaque-par-la-chaine-d-approvisionnement.md` (TD 1, l'inventaire des seize dépendances) · `../../Session-5/2-Labs/D5-appreciation-initiale-des-risques.md` (**D5 fait foi**)

**Ce fichier n'est pas un livrable** : c'est le mode opératoire. Le livrable de la séance 6 est **D6, tiers et projets (7 points, le plus lourd du module)**, assemblé au **TP 2** ; ce TP-ci transpose dans l'outil ce que le TD 2 a produit sur le papier, et rien d'autre.

> **Règle de la journée, avant tout clic** : *réutiliser, jamais recréer.* L'étude existe depuis la séance 5, les 17 actifs depuis la séance 2, l'audit depuis la séance 4, les 7 événements redoutés et les 5 couples SR/OV depuis la séance 5. **On rouvre la même étude et on la remplit** — l'énoncé le dit : *« this lab picks up that study, copying nothing over »*. Trois familles d'objets **nouveaux** aujourd'hui, et trois seulement : les **parties prenantes** de l'écosystème, les **scénarios stratégiques** avec leurs **chemins d'attaque**, puis un premier **scénario opérationnel**.

**Durée annoncée par l'énoncé** : 5 + 10 + 15 + 15 + 10 = **55 minutes** de saisie, hors captures.

**Compte de connexion** : compte **nominatif**, jamais `admin@lockbay.eu`. Tout objet créé aujourd'hui porte un auteur nommé — c'est la moitié du coefficient individuel. **Se répartir la saisie entre Miguel et Maxime et le noter dans la feuille de travail** (proposition : parties prenantes + cotation à l'un, scénarios stratégiques + opérationnel à l'autre, relecture croisée).

---

## 0. État des prérequis — ce qui est prêt, ce qui ne l'est pas

| Prérequis de l'énoncé | État au dossier |
|---|---|
| L'étude de la séance 5 avec ses ateliers 1 et 2 saisis | ✅ `translog-b`, compteurs vérifiés au TP 2 de la séance 5 |
| D5 — cadrage, échelles de gravité et de vraisemblance, socle, couples SR/OV, événements redoutés cotés | ✅ `../../Session-5/2-Labs/D5-appreciation-initiale-des-risques.md` |
| La cartographie de la séance 2 et sa vue écosystème | ✅ D2 + les 17 actifs dans l'instance |
| **Le TD du matin** — carte de dangerosité, parties prenantes critiques, structure d'un scénario stratégique et d'un scénario opérationnel | ✅ **TD 2 fait** : 5 parties prenantes cotées, seuil écrit, 2 critiques désignées, 1 scénario stratégique complet + 1 chemin secondaire |
| L'extrait de contrat `TMA-WMS-2021` (APPLICA Services) | ✅ `../../../../S6 - Sources/Extrait-contrat-Logistique-TMA-WMS.pdf` — sert au TD 2 et au TP 2, pas directement ici |

**Rien ne bloque : tout ce qui se saisit aujourd'hui est déjà écrit et justifié dans le TD 2.** Ce TP est une transcription, pas une invention. Si une décision nouvelle s'impose devant l'écran, elle s'**écrit dans la feuille de travail**, elle ne se prend pas en silence.

### L'état exact de l'étude avant d'ouvrir — et le seul écart à assumer

| Compteur de la carte *Summary* | Valeur attendue à l'écran | Ce que l'énoncé du TP annonce |
|---|---|---|
| `Assets` | **17** (4 primaires + 13 supports) | « the subsidiary's assets » ✅ |
| `Audits` | **1** (`MERIDIAN - ISO/IEC 27001:2022 - initial assessment`) | « one audit » ✅ |
| `Feared events` | **7** — ER1 à ER7, tous `Selected` | ⚠️ « **six** feared events » |
| `RO/TO couples` | **5**, dont **3** `Selected` (n°1, 3, 4) | « five RO/TO pairs of which three retained » ✅ |
| Ateliers 3, 4, 5 | **vides** | état attendu avant aujourd'hui ✅ |

> ⚠️ **L'écart des événements redoutés est connu, tranché et documenté — ne pas le « corriger ».** L'énoncé du TP écrit *six* parce qu'il décrit l'état de sortie du TP 1 de la séance 5 ; **ER7** (`LOG-PA-03`, perte du savoir-faire opérationnel, `Proof`, gravité `Important`) a été ajouté au **TP 2** de la séance 5, pour que le couple SR/OV n°3 (`Avenger`) cesse d'être un couple retenu sans événement redouté. La consigne de l'exercice 1 tranche elle-même : *« check that its Workshops 1 and 2 reflect **D5** […] : **D5 is authoritative** »* — et **D5 porte sept événements redoutés**. Trace : `../../Session-5/2-Labs/Seance-5-TP-S5-06-echelles-et-assemblage-D5.md` §80 et la feuille `S5-05` §4.3. **À réécrire d'une ligne dans la feuille de travail d'aujourd'hui**, pour que le correcteur trouve la raison sans la chercher.

---

## 1. Exercice 1 — Reprendre l'étude de la séance 5 (5 min)

*Ne rien ressaisir. Ouvrir, vérifier, compléter uniquement ce qui diverge de D5.*

**Geste** : menu `Risk` → `EBIOS RM` → ouvrir l'étude `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1`.

| # | Ce qui doit être vrai à l'écran | Vérifié ? | Observé |
|---|---|---|---|
| 1a | Domaine de l'étude = `MERIDIAN-LOGISTIQUE` (jamais `Global`) | | |
| 1b | Matrice = `4x4 risk matrix from EBIOS-RM` · méthode de cotation = **`Manual`** | | |
| 1c | Le cadrage (objectif, finalité, participants, accepteur des résiduels, cycles) est **dans la description** de l'étude | | |
| 1d | `Assets` = **17**, aucun doublon | | |
| 1e | `Audits` = **1**, l'auto-évaluation de la séance 4 | | |
| 1f | `Feared events` = **7**, tous `Selected`, gravités conformes à D5 §4 (ER1 `Critical`, ER2 `Important`, ER3 `Critical`, ER4 `Important`, ER5 `Critical`, ER6 `Significant`, ER7 `Important`) | | |
| 1g | `RO/TO couples` = **5**, `Selected` sur les n°**1**, **3**, **4** ; chacun relié à au moins un ER (couple 3 → **ER2 + ER7**) | | |
| 1h | Ateliers **3, 4, 5 vides** — c'est le point de départ d'aujourd'hui | | |

> **La méthode `Manual` est vérifiée maintenant, pas à l'exercice 5.** En `Express`, l'outil recalcule la vraisemblance depuis les modes opératoires et **écrase la saisie** ; la vraisemblance du scénario opérationnel de l'exercice 5 se pose à la main sur l'échelle V1-V4 de D5. Le choix a été posé juste en séance 5 : **le constater, ne pas le changer**.

**À produire** *(critère de l'énoncé)* : la page d'étude dont les compteurs affichent les actifs de la filiale, un audit, les événements redoutés et les cinq couples dont trois retenus, **identiques à D5**.

**Capture** : `S6-05-ex1-etude-reprise-compteurs.jpg` (carte *Summary* avec les quatre compteurs lisibles).

---

## 2. Exercice 2 — Saisir l'écosystème comme parties prenantes (10 min)

**Geste** : page de l'étude → **atelier 3** → activité *« Identifier les parties prenantes »* (libellé exact à relever) → bouton **+**.

**Objet étudié**, choisi et justifié au TD 2 : **`LOG-PA-01` Exécution des flux logistiques** — la valeur métier dont l'événement redouté (**ER1**) est coté le plus haut dans D5, rang 1 du Top 5 de D2, et la seule des trois valeurs cotées *Critique* visée par un couple SR/OV **retenu**.

### Les cinq parties prenantes à créer — toutes nommées au §3 ou au §6 du pack, aucune inventée

| Réf. | Nom à saisir | Catégorie (outil) | Description à coller dans la fiche |
|---|---|---|---|
| **PP1** | `APPLICA Services - TMA du WMS` | Prestataire / *Supplier* | Tierce maintenance applicative du WMS (`LOG-SA-10`), contrat `TMA-WMS-2021` du 8/11/2021, en renouvellement annuel depuis le 8/11/2025. Maintient le WMS, sa base et **l'interface d'approvisionnement d'urgence vers Santé** (art. 1-2). Intervient à distance par le réseau bureautique avec le **compte de domaine administrateur partagé `svc-applica`** et **installe les mises à jour de 22 h à 5 h sans autre formalité** (art. 3). Pack §3, §4, §5.2. |
| **PP2** | `Integrateur des automates de tri` | Prestataire / *Supplier* | Installe et maintient les automates d'E2/E3/E4 (`LOG-SA-03`). Accès distant permanent par **box 4G placée hors du réseau supervisé**, posée par l'Exploitation « pour ne plus dépendre de l'informatique ». Contrat **sans clause de réversibilité ni exigence de sécurité** ; réglages revendiqués comme propriété industrielle. Pack §2, §3, §4, §5. |
| **PP3** | `Operateur des liaisons inter-entrepots` | Prestataire / partenaire | Les cinq entrepôts hors E1 n'atteignent le WMS que par ses liaisons ; « si le lien tombe, l'entrepôt s'arrête », démontré en avril. Aucun accès logique au WMS. Pack §4. |
| **PP4** | `Client pharmaceutique - portail d'expedition` | Client | Portail d'expédition du client, **un compte par entrepôt** partagé par les équipes, hébergé chez lui, hors de notre annuaire. Audits annuels de chaîne du froid, **questionnaire de sécurité annoncé**. Pénalités de 12 000 €/jour d'arrêt. Pack §2, §3, §4. |
| **PP5** | `MERIDIAN Sante - flux de reapprovisionnement d'urgence` | Partenaire (groupe) | Consomme les mouvements de stock de nos ~300 scannettes via l'**API sur VLAN dédié + pare-feu d'inspection** (`LOG-SA-12`/`LOG-SA-13`), **seule segmentation du groupe** (constat **C7** de D4). **Flux coupé depuis trois mois** à la demande de la RSSI de Santé ; le Pharmacien chef en demande la reprise. Pack §6 ; reference pack §5.1. |

> ⛔ **Ce qui n'entre pas dans l'écosystème, et pourquoi.** Le **Responsable Exploitation**, la **DSI de la filiale** et les **six chefs d'entrepôt** sont des **biens supports** de D2 (`LOG-SA-09`, `LOG-SA-11`…) : ce sont des acteurs *internes*, pas des parties prenantes de l'écosystème. Le **fournisseur des sondes de température** et le **fournisseur de télématique** appartiennent à l'écosystème de `LOG-PA-02` (chaîne du froid), pas de l'objet étudié du jour : ils se cartographieront quand `LOG-PA-02` sera l'objet étudié. **Écrire cette phrase dans la feuille de travail** — c'est le critère « aucune inventée, toutes rattachées à l'objet étudié ».

> ⚠️ **Point de friction probable, à vérifier à l'écran.** Selon la version, la fiche *stakeholder* peut exiger de choisir une **entité** existante (objet `Third parties` / `Entities`) plutôt que de saisir un nom libre. Si c'est le cas : créer l'entité dans le domaine `MERIDIAN-LOGISTIQUE`, sous le **compte nominatif**, avec le nom exact ci-dessus, **puis** la rattacher à la partie prenante — et **noter le geste dans la feuille de travail** (c'est une divergence outil/plan, pas une erreur). Relever de même la **liste réelle des catégories** proposées et la corriger dans le tableau ci-dessus si elle diffère : *« ne rien inventer, relever ce que l'outil propose »*.

**À produire** *(critère de l'énoncé)* : **au moins quatre** parties prenantes rattachées à l'étude — nous en créons **cinq** —, chacune correspondant à un acteur nommé au §3 ou au §6, **aucune inventée**.

**Capture** : `S6-05-ex2-5-parties-prenantes-liste.jpg`.

---

## 3. Exercice 3 — Coter la dangerosité et lire la criticité (15 min)

**Geste** : ouvrir chaque partie prenante → renseigner les **quatre critères en valeur *courante*** : `Dependency`, `Penetration`, `Maturity`, `Trust`.

**Ce que l'outil fait tout seul** : il calcule la **criticité** = `dépendance × pénétration ÷ (maturité × confiance)`, chaque note allant de **0 à 4**. L'exposition (dépendance × pénétration) **augmente** la criticité, la fiabilité cyber (maturité × confiance) la **diminue**. **La dangerosité ne se calcule pas à la main : elle se justifie par les quatre notes, et le résultat se lit.**

### Les vingt notes, reprises telles quelles du TD 2

| Réf. | `Dependency` | `Penetration` | `Maturity` | `Trust` | **Criticité attendue** | `Selected` |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| **PP2 · Intégrateur automates** | **3** | **4** | **1** | **1** | **12,0** — rang 1 | ✅ |
| **PP1 · APPLICA (TMA WMS)** | **4** | **4** | **1** | **2** | **8,0** — rang 2 | ✅ |
| **PP5 · MERIDIAN Santé** | 2 | 3 | 2 | 3 | 1,0 | ⬜ |
| **PP3 · Opérateur des liaisons** | 3 | 1 | 2 | 3 | 0,5 | ⬜ |
| **PP4 · Client pharmaceutique** | 2 | 2 | 3 | 3 | 0,4 | ⬜ |

### La justification à coller dans chaque fiche — un fait du pack par note, jamais une impression

*Version courte des cinq blocs du TD 2 (§ « Justification des notes, ligne par ligne ») ; le TD 2 reste la version longue.*

- **PP1 · APPLICA** — *Dépendance 4* : seul mainteneur du WMS et de ses interfaces (contrat art. 1-2), astreinte unique voie de rétablissement (art. 4), aucune compétence interne (« le WMS, c'est l'affaire de la TMA », pack §3), système centralisé sans secours. *Pénétration 4* : compte de domaine **administrateur** `svc-applica` + accès aux partages (art. 3), accès distant par le réseau bureautique à tout moment, mises à jour 22 h-5 h « sans autre formalité », réseaux IT/OT interconnectés (**C3**) — l'accès déborde le WMS. *Maturité 1* : art. 5 « règles de l'art », aucune exigence vérifiable, pas de journalisation nominative, mises à jour sans validation ni retour arrière. *Confiance 2* : installé depuis 2021, clause de confidentialité (art. 6), liste des habilités tenue — mais « sur demande » seulement, et l'audit interne a reçu *un nom de compte, aucun nom de personne* (pack §3, §5.2).
- **PP2 · Intégrateur** — *Dépendance 3* : seul installateur-mainteneur des automates d'E2/E3/E4 (pack §2), mais E5/E6 sont manuels et E1 tient au WMS : la préparation ne s'arrête pas *entièrement* sans lui ; réglages **revendiqués comme propriété industrielle** (point de savoir unique). *Pénétration 4* : **box 4G hors réseau supervisé** sur un **réseau plat IT/OT** — l'accès « ne donne pas sur un automate, il donne sur tout » (**C3**) ; six chefs d'entrepôt appellent un technicien sur son mobile, sans vérification d'identité (pack §3). *Maturité 1* : contrat **sans réversibilité ni exigence de sécurité**, aucun journal au SOC (pack §6). *Confiance 1* : **refuse par écrit** de communiquer les réglages ; la box 4G a été posée **précisément pour contourner** la DSI.
- **PP3 · Opérateur des liaisons** — *Dépendance 3* : cinq entrepôts sur six n'atteignent le WMS que par ses liaisons (pack §4). *Pénétration 1* : transporte le flux, **aucun accès logique**. *Maturité 2 / Confiance 3* : opérateur mutualisé, pratiques de base présumées, **aucune exigence formulée** par la filiale, aucun incident propre.
- **PP4 · Client pharmaceutique** — *Dépendance 2* : portail de saisie des expéditions, repli papier existant. *Pénétration 2* : **un compte par entrepôt partagé**, hébergé chez le client, hors de notre annuaire — pivot dans les deux sens, mais **pas d'accès dans notre WMS**. *Maturité 3* : conduit des audits annuels et a **annoncé un questionnaire de sécurité** — plus mûr que la filiale. *Confiance 3* : intérêts alignés sur la continuité ; le risque, ce sont nos comptes partagés, pas son intention.
- **PP5 · MERIDIAN Santé** — *Dépendance 2* : Santé est **en aval**, nos flux ne dépendent pas d'elle. *Pénétration 3* : l'API sur VLAN dédié relie nos ~300 scannettes à son système de stocks — compromettre nos scannettes, c'est écrire dans les commandes d'une pharmacie hospitalière, et la voie est symétrique ; **flux coupé depuis trois mois**. *Maturité 2* : constats majeurs propres à Santé (pas de MFA, identifiant du SIH partagé entre neuf personnes, registre jamais remis — reference pack §3). *Confiance 3* : même groupe, mission alignée ; la coupure est un signe de **vigilance**, pas d'hostilité.

### Le seuil, écrit avant de lire les résultats

> **Une partie prenante est critique lorsque sa dangerosité est ≥ 4,0** — son exposition vaut au moins **quatre fois** la fiabilité cyber qui l'encadre. Règle de lecture jointe (réflexe de méthode du TD 1) : *accès numérique privilégié permanent à un bien support de `LOG-PA-01` **et** `maturité × confiance ≤ 4`* — « ce que le tiers peut faire est fort, et rien ne dirait que quelqu'un d'autre s'en sert ».

Le seuil sépare nettement l'observé : **{12,0 ; 8,0}** au-dessus, **{1,0 ; 0,5 ; 0,4}** en dessous. → **Cocher `Selected` sur PP2 et PP1**, et sur elles seules.

> 💡 **Si le nombre affiché diffère de nos 12,0 et 8,0.** L'énoncé pose la règle : *« si le résultat surprend, ce n'est pas la mathématique qu'il faut contester, ce sont les notes qu'il faut réexaminer et rejustifier »*. Trois causes plausibles, dans cet ordre : (1) l'échelle de l'outil **commence à 0** et un libellé peut décaler notre 1-4 — relever les libellés exacts et **noter la correspondance** ; (2) l'outil applique un **arrondi** ou une normalisation d'affichage ; (3) une note a été saisie dans la colonne *résiduelle* au lieu de la colonne *courante*. **Écrire l'écart dans la feuille de travail et conserver le classement**, qui ne dépend pas de l'arrondi : PP2 puis PP1 restent devant, très loin des trois autres.

> **Les valeurs *résiduelles* ne se saisissent pas aujourd'hui.** Elles décrivent la dangerosité **après traitement** — mesures de maîtrise du tiers, séance 7 (atelier 5). Tant qu'elles sont vides ou égales au courant, c'est **normal** : le dire dans la feuille de travail plutôt que de les remplir « pour faire propre ». Remplir un résiduel avant d'avoir décidé une mesure, c'est afficher un risque traité qui ne l'est pas.

**À produire** *(critère de l'énoncé)* : **au moins quatre** parties prenantes cotées, chaque note **justifiée en une ligne par un fait du pack**, la criticité **lue** pour chacune, et les parties prenantes critiques cochées `Selected`.

**Captures** : `S6-05-ex3-PP1-applica-4-notes-criticite.jpg`, `S6-05-ex3-PP2-integrateur-4-notes-criticite.jpg`, `S6-05-ex3-carte-dangerosite-classement.jpg` (la liste des 5, colonne criticité lisible, les 2 critiques cochées).

---

## 4. Exercice 4 — Deux scénarios stratégiques et leurs chemins d'attaque (15 min)

**Geste** : atelier 3 → activité *« Élaborer des scénarios stratégiques »* → **+** ; puis, dans chaque scénario, créer le ou les **chemins d'attaque** (*attack paths*), y **rattacher la partie prenante** et cocher `Selected` sur le chemin.

**Structure imposée par la méthode, à respecter dans chaque description** : **source de risque → événement intermédiaire *porté sur l'écosystème* → propagation → événement redouté *porté sur la valeur métier***. La **gravité ne se saisit pas** : elle s'affiche depuis l'événement redouté rattaché. La **vraisemblance n'a pas sa place ici** — elle appartient au scénario opérationnel (exercice 5).

### Scénario stratégique A — couple SR/OV **n°1** (`Organized crime`), par **PP1 · APPLICA**

*Le scénario complet du TD 2, à recopier. Objectif visé (D5 §3, à l'identique) : « chiffrer le WMS et sa base pour arrêter le flux d'expédition du groupe et obtenir une rançon sous menace d'arrêt prolongé ».*

| Champ | Contenu |
|---|---|
| **Nom** | `SS1 - Cybercriminel chiffre le WMS via la TMA (APPLICA)` |
| **Couple SR/OV** | n°**1** — Cybercriminel (`Organized crime`), *Highly relevant* |
| **Événement redouté visé** | **ER1** — `LOG-PA-01`, disponibilité, gravité **`Critical`** |
| **Gravité** | **G4 `Critical`**, **affichée depuis ER1** — ne pas la ressaisir |

**Chemin d'attaque n°1 — `Selected`, partie prenante rattachée : PP1 · APPLICA Services**

> **Source de risque** — le cybercriminel acquiert un accès initial chez APPLICA : poste d'un intervenant disposant de `svc-applica`, ou environnement de fabrication et de livraison des mises à jour (accès initiaux achetés, écosystème rançongiciel mature — D5 §3).
> **Événement intermédiaire, porté sur l'écosystème** — une charge malveillante est **embarquée dans la mise à jour du WMS** qu'APPLICA installe de 22 h à 5 h « sans autre formalité » (contrat `TMA-WMS-2021` art. 3) — **mécanisme NotPetya / M.E.Doc à l'identique** ; ou le cybercriminel **utilise directement le compte de domaine administrateur partagé `svc-applica`** par le réseau bureautique. Dans les deux cas, **l'intrusion ne se distingue pas d'une intervention légitime** (pack §3, constat **C4**).
> **Propagation** — depuis les deux serveurs et la base du WMS au site E1 (`LOG-SA-01`, `LOG-SA-06`), et par le **réseau plat IT/OT** (**C3**), la charge atteint le WMS **utilisé simultanément par les six sites** ; le compte de service `LOG-SA-04` (même secret en clair depuis 2019) élargit l'emprise vers les automates.
> **Événement redouté, porté sur la valeur métier** — **le WMS et sa base sont chiffrés ; les six entrepôts ne préparent ni n'expédient plus — ER1.** La reprise n'est **pas démontrée** (sauvegardes quotidiennes jamais restaurées, pack §5.4 ; RTO/RPO non contractualisés, D2 ; site unique sans secours). Au-delà de six heures : **40 % du volume expédié du groupe** bloqué, **12 000 €/jour** de pénalités, et l'**interface d'approvisionnement d'urgence vers Santé** (contrat art. 2) tombe avec le WMS.
> **Rien ne le détecte** — le SOC ne reçoit aucun journal du WMS (pack §6), aucune procédure d'incident n'existe (pack §5.6), aucune obligation de notification n'est à la charge d'APPLICA (contrat muet).

**Chemin d'attaque n°2 — `Selected`, partie prenante rattachée : PP2 · l'intégrateur des automates**

> Même couple SR/OV, **pivot différent** : le cybercriminel compromet l'intégrateur, entre par la **box 4G hors réseau supervisé**, atteint par le **réseau plat IT/OT** le WMS et sa base → **ER1**, même événement redouté, même gravité.
> **C'est la résolution de la mise en réserve de la séance 5** : le couple n°2 de D5 (« attaquant passant par l'intégrateur ») n'entre pas comme couple SR/OV — il entre comme **chemin d'attaque d'une partie prenante critique**, sa juste place méthodologique. **À écrire dans la description du chemin**, c'est un point de traçabilité gratuit.

### Scénario stratégique B — couple SR/OV **n°4** (`Competitor`), par **PP1 · APPLICA**

*L'énoncé demande deux des trois couples retenus. Le couple n°4 est choisi plutôt que le n°3 pour une raison de méthode : le n°3 est un **initié de l'Exploitation**, son chemin ne passe pas par l'écosystème — il partirait directement du bien support `LOG-SA-04`, et le critère de l'exercice exige **au moins un chemin par une partie prenante critique**. À écrire dans la feuille de travail ; le couple n°3 se traitera en séance 7, quand le registre complet s'ouvrira.*

| Champ | Contenu |
|---|---|
| **Nom** | `SS2 - Concurrent capte les donnees d'exploitation via la TMA (APPLICA)` |
| **Couple SR/OV** | n°**4** — Concurrent (`Competitor`), *Partially relevant* — **retenu malgré la pertinence calculée** : seul couple atteignant `LOG-PA-04` et la confidentialité (D5 §3) |
| **Événement redouté visé** | **ER4** — `LOG-PA-04`, `Proof`, gravité **`Important`** *(et **ER6**, `LOG-PA-02`, confidentialité, `Significant`, si l'outil accepte deux événements redoutés)* |
| **Gravité** | **G3 `Important`**, **affichée depuis ER4** |

**Chemin d'attaque — `Selected`, partie prenante rattachée : PP1 · APPLICA Services**

> **Source de risque** — un concurrent cherche les volumes, les tournées et les relevés de température du client pharmaceutique pour capter le marché (objectif visé de D5 §3).
> **Événement intermédiaire, porté sur l'écosystème** — il obtient l'accès par un intervenant d'APPLICA ou par un **sous-traitant d'un développement spécifique « sur devis »** (contrat art. 2), **non déclaré et non récusable** : le contrat ne porte aucune maîtrise de la sous-traitance. Le prestataire détient contractuellement les **données de stock, de commande et de température** (art. 6).
> **Propagation** — extraction depuis la base du WMS (`LOG-SA-01`) via le compte partagé `svc-applica` ; l'accès aux partages est prévu par l'article 3.
> **Événement redouté, porté sur la valeur métier** — **la filiale ne peut pas produire la preuve de qui a accédé aux données, à l'audit ou au questionnaire de sécurité annoncé par le client — ER4** ; et les données d'expédition et de température du client sont divulguées — **ER6**. Le compte étant partagé et non journalisé de façon nominative (**C4**), **l'exfiltration est indistinguable d'une intervention de maintenance** : c'est l'imputabilité, pas seulement la confidentialité, qui est atteinte.
> **Rien ne le détecte** — aucun journal nominatif, aucune remontée au SOC, liste des habilités « sur demande » seulement.

> ⚠️ **Si l'outil n'accepte qu'un seul événement redouté par scénario stratégique** : rattacher **ER4** (c'est lui qui porte la gravité la plus haute des deux et la valeur métier visée en premier par le couple), et **écrire ER6 dans la description**. Relever le comportement observé dans la feuille de travail.

**À produire** *(critère de l'énoncé)* : **deux scénarios stratégiques**, chacun avec **un chemin d'attaque `Selected` relié à une partie prenante critique**, **gravité affichée depuis l'événement redouté**.

**Captures** : `S6-05-ex4-SS1-detail-chemins.jpg`, `S6-05-ex4-SS2-detail-chemin.jpg`, `S6-05-ex4-scenarios-strategiques-liste-gravite.jpg`.

---

## 5. Exercice 5 — Amorcer l'atelier 4 : un scénario opérationnel (10 min)

**Le chemin le plus préoccupant, sans hésitation : le chemin n°1 du scénario A — la mise à jour du WMS posée par APPLICA.** Trois raisons, à écrire : il vise l'événement redouté le plus grave du dossier (**ER1**, `Critical`) ; il passe par la partie prenante dont l'**exposition** est la plus forte du groupe (16) ; et c'est le mécanisme **NotPetya**, dont le TD 1 a montré qu'il a frappé un transporteur exerçant notre métier.

**Geste** : atelier 4 → activité *« Élaborer des scénarios opérationnels »* → **+** → rattacher au **chemin d'attaque n°1 du scénario A** → cocher `Selected`.

### La description — un enchaînement d'actions élémentaires **sur les biens supports**

*Le stratégique dit **où** l'attaque passe ; l'opérationnel dit **comment**, techniquement. Séquence en quatre temps (connaître · entrer · trouver · exploiter), chaque action rattachée à un bien support nommé de D2.*

| # | Action élémentaire | Bien support |
|---|---|---|
| 1 | **Connaître** — le cybercriminel identifie APPLICA comme mainteneur du WMS de la filiale (information commerciale publique) et cible ses intervenants. | — (hors périmètre) |
| 2 | **Entrer chez le tiers** — compromission d'un poste d'intervenant disposant de `svc-applica`, ou de la chaîne de fabrication et de livraison des mises à jour d'APPLICA. | `LOG-SA-10` (TMA) |
| 3 | **Entrer chez nous** — la charge arrive **soit** par la mise à jour posée entre 22 h et 5 h sans validation ni retour arrière, **soit** par une session distante avec le compte de domaine administrateur partagé, depuis le réseau bureautique. **Aucune authentification forte** ne s'y oppose (`PSSI-CADRE-ACC-01` non appliqué, D5 §2). | `LOG-SA-01`, `LOG-SA-10` |
| 4 | **Trouver** — reconnaissance depuis les serveurs du WMS ; récupération du **secret du compte de service `LOG-SA-04`, en clair dans un fichier de configuration, identique sur les six entrepôts depuis 2019**. | `LOG-SA-01`, `LOG-SA-04` |
| 5 | **Élargir** — latéralisation par le **réseau plat IT/OT** (**C3**, non-conformité majeure) vers les automates de tri et les autres sites ; aucun cloisonnement ne borne la progression. | `LOG-SA-03`, `LOG-SA-07` |
| 6 | **Exploiter** — chiffrement de la base et des deux serveurs du WMS au site E1 ; suppression ou chiffrement des sauvegardes accessibles depuis le même réseau. Les six entrepôts s'arrêtent ; la restauration **n'a jamais été testée depuis la mise en service**. | `LOG-SA-01`, `LOG-SA-06` |
| 7 | **Rester invisible** — aucune de ces étapes n'est journalisée vers le SOC (ni WMS, ni OT, ni box 4G) ; aucune procédure d'incident n'existe ; l'intervention nocturne d'APPLICA est un événement **normal**. | SOC / `LOG-SA-10` |

### La vraisemblance, sur l'échelle V1-V4 de D5

> **V3 `Very likely`.**

**Justification, adossée au socle de sécurité et à ses limites (D5 §2)** — la définition de D5 est littérale : *« une faiblesse **connue et actuelle** rend le scénario réalisable avec les moyens courants de la source, exemples récents dans le secteur »*. Les quatre faiblesses sont **connues, actuelles et écrites** : compte de domaine partagé aux porteurs inconnus (**C4**), mises à jour posées sans validation ni retour arrière (contrat art. 3), secret de service en clair depuis 2019 (`A.5.17` non couvert), réseaux IT/OT interconnectés (**C3**) ; aucun journal ne remonte au SOC (`JRN-01` partiel), aucune MFA (`ACC-01` non appliqué), et 128 compromissions par rançongiciel ont été portées à la connaissance de l'ANSSI en 2025 (D5 §3).

**Pourquoi pas V4 `Certain`** — D5 réserve `Certain` au scénario *« qui s'est déjà réalisé dans le périmètre ou dont la réalisation ne dépend plus d'un attaquant »*. L'arrêt du WMS d'avril **n'a jamais été expliqué** : rien ne permet de l'attribuer à une attaque, et le supposer dépasserait ce que le dossier prouve. **La retenue se justifie mieux que l'excès** — et elle s'écrit.

> **La saisie est manuelle** (méthode `Manual` de l'étude, vérifiée à l'exercice 1) : l'outil ne recalcule pas cette note et ne l'écrasera pas.

**À produire** *(critère de l'énoncé)* : **au moins un scénario opérationnel** rattaché à un chemin d'attaque, avec sa description de modes opératoires et sa **vraisemblance justifiée par le socle de sécurité et ses limites**.

**Captures** : `S6-05-ex5-scenario-operationnel-detail.jpg`, `S6-05-ex5-atelier4-liste-vraisemblance.jpg`.

---

## 6. Ce qui n'est **pas** fait aujourd'hui, et pourquoi — à écrire dans la feuille de travail

- **L'atelier 4 n'est qu'amorcé** : un seul scénario opérationnel, sur le chemin le plus préoccupant. L'énoncé le dit — *« le complet est la substance de la séance 7 ; ici, la première pierre »*. Les autres chemins `Selected` attendent leur scénario opérationnel : *à chaque chemin d'attaque stratégique retenu correspond un scénario opérationnel*, la règle sera honorée en séance 7.
- **L'atelier 5 reste vide** : le traitement, c'est la séance 7, dont la première activité *« Générer l'appréciation des risques »* **créera le registre à partir de cette étude**. Rien ne sera recopié.
- **Les valeurs résiduelles des parties prenantes restent vides** : elles décrivent la dangerosité **après** les mesures de maîtrise du tiers, qui n'existent pas encore. Les remplir aujourd'hui afficherait un risque traité qui ne l'est pas.
- **Le couple SR/OV n°3 (`Avenger`) n'a pas de scénario stratégique** : son chemin ne passe pas par l'écosystème (voir l'encadré de l'exercice 4). Ce n'est pas un oubli, c'est un choix de méthode écrit.

**Capture** : `S6-05-atelier5-vide-et-compteurs.jpg` — la page d'étude, ateliers 1 à 4 remplis, atelier 5 vide. **Preuve de méthode, pas aveu.**

---

## 7. Pendant que l'instance est ouverte — un geste en attente

| Geste | Détail | Pourquoi maintenant |
|---|---|---|
| **Produire la capture du rapport d'étude manquante** | `../../Session-5/2-Labs/Seance-5-TP-S5-06-echelles-et-assemblage-D5.md` et **D5 §« preuves à l'appui »** citent `S5-06-rapport-etude-EBIOS-RM-ateliers-1-2.jpg` — **ce fichier n'est pas dans `Session-5/3-Evidence/`** (23 captures, aucune de ce nom). Générer le rapport d'étude depuis la page de l'étude et le capturer sous ce nom exact, dans `Session-5/3-Evidence/`. | **D5 affirme une pièce qui n'existe pas** : c'est exactement ce que la règle du rendu interdit (*« une affirmation sans pièce derrière elle ne compte pas »*). Le rapport contient désormais aussi les ateliers 3 et 4 — capturer **la partie ateliers 1-2** pour tenir l'affirmation de D5, ou corriger la mention dans D5. À trancher et à écrire. |

---

## 8. Ce qui sort de ce TP

| Sortie | Où | État |
|---|---|---|
| **Feuille de travail** `Seance-6-TP-S6-05-feuille-de-travail-ecosysteme-et-scenarios.md` | `Session-6/2-Labs/` | à écrire **pendant** la saisie : table de vérification de l'exercice 1, écart des 7 ER assumé, catégories réellement proposées par l'outil, criticités **lues** vs. calculées à la main, comportement du champ *feared events* d'un scénario stratégique, répartition nominative |
| **Captures** `S6-05-*.jpg` | `Session-6/3-Evidence/` | ~10 captures listées ci-dessus |
| **Objets nouveaux dans `translog-b`** | instance | **5 parties prenantes** cotées (4 notes chacune), **2 critiques `Selected`** · **2 scénarios stratégiques** · **3 chemins d'attaque `Selected`** · **1 scénario opérationnel** coté V3 |
| **Entrées pour le TP 2 — livrable D6** | D6 | la carte de dangerosité **outillée** justifie que les exigences contractuelles portent d'abord sur PP1 et PP2 ; chaque exigence de D6 se trace à un chemin d'attaque de l'exercice 4 ; le scénario opérationnel donne la mesure du « pourquoi maintenant » |
| **Entrée pour la sous-section 6 de la note** | `Piece-1-Strategy-note/` | deux parties prenantes critiques nommées, un scénario à **G4** qui relie un cybercriminel à l'arrêt du flux d'expédition **en passant par la TMA** |

**Fini quand** : l'étude contient **5 parties prenantes cotées dont 2 `Selected`**, **2 scénarios stratégiques** portant chacun un chemin `Selected` rattaché à une partie prenante critique et affichant sa gravité, **1 scénario opérationnel** rattaché et coté — et que **chaque écart entre l'outil et le TD 2 est écrit** quelque part plutôt que corrigé en douce.

---

## 9. Critères de validation de l'énoncé — la relecture avant de fermer

- [ ] L'étude de la séance 5 est **rouverte**, rien n'a été recréé ; ses compteurs reflètent **D5** (7 ER, écart avec l'énoncé **écrit**, pas corrigé)
- [ ] Méthode de cotation **`Manual`** constatée avant l'exercice 5
- [ ] **≥ 4 parties prenantes** (nous : 5), chacune correspondant à un acteur nommé du **§3 ou du §6**, **aucune inventée**, catégorie prise **parmi celles de l'outil**
- [ ] Les acteurs **internes** ont été **écartés** comme biens supports, et la raison est écrite
- [ ] **4 notes courantes** par partie prenante, **chacune adossée à un fait du pack** en une ligne
- [ ] La **criticité est lue**, pas calculée à la main ; tout écart avec 12,0 / 8,0 est **relevé et expliqué**, les notes ne sont pas ajustées pour faire tomber le résultat juste
- [ ] **Seuil écrit avant lecture** (≥ 4,0) ; **PP2 et PP1** cochées `Selected`, et elles seules
- [ ] Valeurs **résiduelles laissées vides**, raison écrite
- [ ] **2 scénarios stratégiques**, rattachés à **2 couples SR/OV retenus** (n°1 et n°4) et à leur **événement redouté**
- [ ] Chaque scénario porte **au moins un chemin d'attaque `Selected` relié à une partie prenante critique** ; le chemin distingue **événement intermédiaire (écosystème)** et **événement redouté (valeur métier)**
- [ ] **Gravité affichée depuis l'événement redouté**, jamais ressaisie à la main
- [ ] **1 scénario opérationnel** rattaché au chemin le plus préoccupant, **actions élémentaires sur les biens supports nommés**, **vraisemblance V3 justifiée par le socle et ses limites**
- [ ] **Atelier 5 vide**, et la raison écrite
- [ ] Chaque objet créé porte un **auteur nommé**
