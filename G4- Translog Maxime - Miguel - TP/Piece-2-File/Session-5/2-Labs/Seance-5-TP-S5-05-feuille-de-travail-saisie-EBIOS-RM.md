# Feuille de travail — Séance 5, TP 1 : saisie des ateliers 1 et 2 d'EBIOS RM dans CISO Assistant

**Groupe 4 (Translog)** · instance `translog-b` (https://translog-b.lockbay.eu)
**Domaine** `MERIDIAN-LOGISTIQUE` (enfant de `Global`) · **périmètre** `MERIDIAN-LOGISTIQUE-FINAL`
**Date de saisie** : 9 septembre 2026 · **compte utilisé** : `Miguel.monereodelasota@ynov.com` (compte nominatif, jamais `admin@lockbay.eu`)
**Mode opératoire suivi** : [`PLAN-Seance-5-TP-S5-05-saisie-ateliers-1-et-2.md`](PLAN-Seance-5-TP-S5-05-saisie-ateliers-1-et-2.md)
**Matière saisie** : TD 2 (`../4-Working-notes/Seance-5-TD-S5-03-ateliers-1-et-2-EBIOS-RM.md`), quatre exercices

> **Ce fichier n'est pas un livrable.** C'est la trace de ce qui a été fait dans l'outil, et surtout de **chaque écart entre le TD sur papier et ce que l'outil accepte**. Le livrable de la séance est **D5**, assemblé au TP 2.

---

## 0. Répartition nominative de la saisie

| Objet | Saisi par |
|---|---|
| Matrice de risque, création de l'étude, cadrage (atelier 1 activité 1), liaison des 17 actifs (activité 2), rattachement de l'audit (activité 4) | Miguel Monereo |
| Six événements redoutés (atelier 1 activité 3) | Miguel Monereo |
| Cinq couples SR/OV (atelier 2, activités 1 à 3) | Miguel Monereo |
| Marquage du Top 5 dans la liste des actifs (F3) | Miguel Monereo |
| Relecture des objets et des libellés à l'écran | Maxime Batista |

Tous les objets de l'étude portent les deux auteurs (`maximebatista18@gmail.com` + `Miguel.monereodelasota@ynov.com`) hérités des actifs de la séance 2 ; l'étude elle-même a été créée sous le compte nominatif de Miguel.

---

## 1. Exercice 1 — Inventaire de l'existant

Table demandée par l'énoncé, avec le **nom exact observé à l'écran** (et non le nom supposé).

| # | Objet attendu | Présent ? | Nom exact observé |
|---|---|---|---|
| 1a | Domaine de la filiale sous revue | ✅ | `MERIDIAN-LOGISTIQUE`, *parent domain* `Global` |
| 1b | Second domaine (autre bout de la dépendance §6) | ✅ **présent, contrairement à l'hypothèse du plan** | `MERIDIAN-SANTE`, parent `Global`, description « filiale santé, quatre établissements de soins » |
| 1c | Périmètre associé à la filiale | ✅ | `MERIDIAN-LOGISTIQUE-FINAL`, domaine `MERIDIAN-LOGISTIQUE` |
| 2 | Actifs de la séance 2 | ✅ **17** | 4 primaires `LOG-PA-01` à `04` + 13 supports `LOG-SA-01` à `13` (noms exacts au §1.1) |
| 3a | Référentiel importé en séance 3 | ✅ | `International standard ISO/IEC 27001:2022`, provider ISO/IEC, domaine `Global` |
| 3b | Évaluation de conformité remplie en séance 4 | ✅ | `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, progression 9 %, périmètre `MERIDIAN-LOGISTIQUE/MERIDIAN-LOGISTIQUE-FINAL` |
| 4 | Module EBIOS RM, page `EBIOS RM studies` | ✅ **liste vide** avant la séance | — |

### 1.1 Noms exacts des 17 actifs

`LOG-PA-01` Exécution des flux logistiques · `LOG-PA-02` Maintien de la chaine du froid · `LOG-PA-03` Savoir-faire operationnel des six entrepots · `LOG-PA-04` Conformite contractuelle avec le client pharmaceutique
`LOG-SA-01` WMS (2 serveurs + BDD, site E1) · `LOG-SA-02` Scannettes d'entrepot (~300, Wi-Fi) · `LOG-SA-03` Automates de tri (E2/E3/E4) · `LOG-SA-04` Compte de service WMS-automates · `LOG-SA-05` Logiciel des sondes de temperature · `LOG-SA-06` Local serveur E1 · `LOG-SA-07` Entrepots E1-E6 · `LOG-SA-08` Chambres froides et remorques refrigerees · `LOG-SA-09` Responsable Exploitation · `LOG-SA-10` Prestataire TMA du WMS · `LOG-SA-11` Responsable Qualite (repond aux audits) · `LOG-SA-12` VLAN dedie + pare-feu d'inspection · `LOG-SA-13` **API** d'approvisionnement d'urgence

> ⚠️ **Écart de libellé n° 1** — le plan et D2 écrivent « **interface** d'approvisionnement d'urgence », l'outil affiche « **API** d'approvisionnement d'urgence ». Divergence mineure, **rien n'a été renommé** : c'est le nom de l'outil qui fait foi pour la traçabilité, et D5 doit citer les deux.

> ✅ **Écart n° 2 — le domaine `MERIDIAN-SANTE` existe**, alors que le plan du TP l'annonçait « probablement absent ». Le groupe avait donc bien instancié les deux bouts de la dépendance du §6 au niveau **domaine**. Ce qui n'existe pas, c'est la **valeur métier** de Santé comme actif primaire dans notre domaine — voir ER5 au §4. La phrase à porter dans D5 change : ce n'est pas « le second domaine manque », c'est « le domaine existe, mais la valeur métier qu'il porte n'est pas modélisée chez nous ».

**Captures** : `S5-05-ex1-inventaire-domaines.jpg`, `S5-05-ex1-inventaire-perimetres.jpg`, `S5-05-ex1-inventaire-17-actifs.jpg`, `S5-05-ex1-inventaire-audit-seance-4.jpg`, `S5-05-ex1-ebios-rm-studies-liste-vide.jpg`

---

## 2. Exercice 2 — Import de la matrice de risque

**Geste** : `Catalog` → `Libraries` → recherche `EBIOS` → import de **`4x4 risk matrix from EBIOS-RM`** (domaine `Global`).

**Pourquoi c'est bloquant** : l'outil refuse de créer une étude EBIOS RM sans matrice. Coter sans échelle ne veut rien dire ; sur ce point l'outil est plus strict que beaucoup d'organisations.

### Les trois phrases demandées par l'énoncé

1. **La case la plus élevée** est le croisement **`Certain` × `Critical`**, dans le coin supérieur droit de la grille, en rouge (`High`).
2. **La diagonale** est une bande en escalier de cellules **`Medium`** (orange/tan) qui va du coin supérieur gauche au coin inférieur droit. Elle sépare le `Low` (teal, coin inférieur gauche) du `High` (rouge, coin supérieur droit) : **c'est sur cette bande que viendra se poser le seuil d'acceptation dérivé de l'appétence** (TD 1), au TP 2. C'est le passage du tolérable à l'inacceptable.
3. **Non, les libellés ne sont pas exactement ceux de l'échelle d'exemple du guide vue au TD.** L'énoncé demandait de regarder V4 et G3 de près : le guide gradue jusqu'à « quasi-certain » là où l'outil écrit **`Certain`**, et le TD dit « grave » là où l'outil écrit **`Important`**. Ce ne sont pas les mêmes mots, c'est la même échelle.

### Libellés réels relevés à l'écran

| Axe | Libellé de l'axe | Niveaux |
|---|---|---|
| Vraisemblance (vertical) | *(non nommé à l'écran)* | `Unlikely`, `Likely`, `Very likely`, `Certain` (de bas en haut) |
| Gravité (horizontal) | ⚠️ **`Impact`** | `Minor`, `Significant`, `Important`, `Critical` |
| Croisement | — | 3 niveaux : `Low`, `Medium`, `High` |

> ⚠️ **Écart n° 3 — le mot de l'axe horizontal.** L'énoncé du TP annonce « **Consequence** », le CM et le TD disent « **gravité** », et l'instance affiche en réalité « **Impact** ». **Trois mots pour un seul concept.** Point de méthode gratuit à porter dans D5 : l'**ISO 27005 parle de conséquences** là où **EBIOS RM parle d'événements redoutés et de gravité** — et l'outil, lui, a choisi un troisième terme. Rien n'a été renommé.

> ✅ **Réserve du TD 2 levée (F12).** Le TD 2 annonçait la correspondance *mineure / significative / grave / critique* → `Minor` / `Significant` / `Important` / `Critical` comme **présumée, à vérifier à l'import**. Elle est désormais **constatée à l'écran**, mot pour mot. **Retirer le mot « présumée »** du compte rendu du TD 2 et de D5.

**Capture** : `S5-05-ex2-matrice-4x4-importee.jpg`

---

## 3. Exercice 3 — Création de l'étude et cadrage (atelier 1, activités 1, 2 et 4)

### 3.1 Paramètres de création

| Champ | Valeur saisie |
|---|---|
| **Nom** | `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1` |
| **Domaine** | `MERIDIAN-LOGISTIQUE` — **jamais le domaine racine** |
| **Matrice de risque** | `4x4 risk matrix from EBIOS-RM` (celle importée à l'exercice 2) |
| **Méthode de cotation** | **`Manual`** — surtout pas `Express` |
| **Statut** | `Planned` |

> **Pourquoi `Manual`** : la séance 7 saisira **à la main** la vraisemblance de chaque scénario opérationnel. En `Express`, l'outil la recalcule depuis les modes opératoires et **écrase la saisie**. Choix irréversible en pratique, posé juste dès maintenant.

### 3.2 Activité 1 — cadrage porté dans la description de l'étude

Les cinq paragraphes du TD 2 sont dans le champ description de l'étude : **objectif**, **finalité retenue** (étude complète des scénarios de risque, les cinq ateliers sur deux cycles — ni socle seul, ni homologation), **participants et rôles** (métier / SI / cyber / décision), **responsable de l'acceptation des risques résiduels** (la **Direction Générale du groupe**), **cycles** (stratégique 3 ans, opérationnel 1 an).

*Critère de l'énoncé tenu* : un lecteur qui ouvre l'étude dans six mois y trouve le cadrage **sans aller chercher le compte rendu du TD**.

### 3.3 Activité 2 — les 17 actifs sont **reliés**, pas recréés

Les 17 actifs de la séance 2 ont été **sélectionnés** via le champ `Assets` (bouton « sélectionner un actif »). Le bouton voisin « ajouter un actif » — le piège explicite de l'énoncé — n'a **pas** été touché. **Aucun doublon dans `Assets`** : la liste en compte toujours 17, vérifié après coup.

C'est le premier critère d'acceptation de D5 (« valeurs métier et biens supports **identiques** à ceux de la cartographie de la séance 2 »), et il se joue ici.

### 3.4 Activité 4 — socle de sécurité

L'audit de la séance 4 (`MERIDIAN - ISO/IEC 27001:2022 - initial assessment`) est **rattaché** à l'étude via « Select audit ». L'outil en dérive le socle et ses écarts.

> **Mécanisme confirmé** : bouton rose = *sélectionner* un audit existant ; bouton bleu = *importer* depuis la bibliothèque. Le principe « relier, ne pas créer » est bien supporté par l'outil, pour les audits comme pour les actifs.

> **Ce qui n'a pas de champ dans l'outil** : la table à quatre colonnes du socle du TD 2 (PSSI-cadre, guide d'hygiène ANSSI, ISO/IEC 27001:2022, obligations contractuelles du client) — l'outil ne connaît que la ligne ISO. Elle **reste la référence écrite**, dans D5. De même, la **décision de poursuite** prise au TD 2 (*poursuivre l'appréciation en intégrant la non-conformité*, plutôt que suspendre et renforcer le socle d'abord) n'a pas de champ : elle vit dans **D5, section 2**.

**Captures** : `S5-05-ex3-etude-creee-parametres.jpg`, `S5-05-ex3-activite2-17-actifs-lies.jpg`, `S5-05-ex3-summary-compteurs.jpg`

---

## 4. Exercice 4 — Les six événements redoutés (atelier 1, activité 3)

**Compteur final : `Feared events` = 6.** Tous cochés `Selected`.

| ID | Actif lié | Qualification | Gravité | Statut |
|---|---|---|---|---|
| **ER1** | `LOG-PA-01` Exécution des flux logistiques | `Availability` | **Critical** | ✅ |
| **ER2** | `LOG-PA-01` Exécution des flux logistiques | `Integrity` | **Important** | ✅ |
| **ER3** | `LOG-PA-02` Maintien de la chaine du froid | `Availability` + `Integrity` | **Critical** | ✅ |
| **ER4** | `LOG-PA-04` Conformite contractuelle | **`Proof`** | **Important** | ✅ |
| **ER5** | `LOG-PA-01` Exécution des flux logistiques ⚠️ | `Availability` | **Critical** | ✅ |
| **ER6** | `LOG-PA-02` Maintien de la chaine du froid | `Confidentiality` | **Significant** | ✅ |

Chaque fiche porte sa **justification** reprise du TD 2 (seuil de 6 h et pénalités de 12 000 €/j pour ER1 ; vecteurs TMA et compte de service pour ER2 ; audit annuel de chaîne du froid et risque sanitaire pour ER3 ; compte TMA partagé et absence de journal nominatif pour ER4 ; réapprovisionnement d'établissements de soin pour ER5 ; clause de confidentialité client pour ER6).

### 4.1 ER5 — la friction de l'exercice, tranchée et écrite

L'outil rappelle sous le champ `Assets` qu'un événement redouté se rattache aux **valeurs métier** (actifs primaires). Or la valeur métier réellement atteinte par ER5 — le **réapprovisionnement d'urgence de la pharmacie hospitalière** — **appartient à MERIDIAN Santé** (dossier de filiale, §6) et n'existe pas comme actif primaire dans notre domaine ; seuls ses biens supports (`LOG-SA-02`, `LOG-SA-12`, `LOG-SA-13`) sont chez nous.

**Décision prise et tracée dans le champ `Description` d'ER5** : rattacher ER5 à **`LOG-PA-01`**, auquel D2 rattache les trois biens supports du flux, et **écrire dans la fiche** que la valeur métier atteinte est propriété de Santé, non modélisée dans notre domaine. **Aucune cinquième valeur métier n'a été créée** — ce serait recréer un objet de cartographie hors séance 2, exactement ce que la règle du jour interdit.

C'est la limite que l'**atelier 3 (écosystème), en séance 6**, aura à lever.

> **Nuance apportée par l'exercice 1** : le domaine `MERIDIAN-SANTE` **existe** dans l'instance. Le trou n'est donc pas au niveau du domaine mais au niveau de la **valeur métier**. D5 doit le dire ainsi.

### 4.2 Ce que l'outil offre de plus que le plan

- Le champ `Qualifications` propose bien plus que les quatre du plan : `Authenticity`, `Availability`, `Confidentiality`, `Environmental`, `Financial`, `Governance`, `Human`, `Image`, `Integrity`, `Proof`… Les quatre du guide suffisent au TD, mais l'inventaire réel est à connaître.
- L'indication sous le champ `Assets` est **plus souple** que le plan ne l'annonçait : *« typically linked to business values (primary assets). Supporting assets are allowed here for flexibility »*. Le plan disait « **jamais** à un bien support » ; l'outil dit « en principe pas, mais c'est toléré ». Nous nous en sommes tenus à la règle du guide : **uniquement des actifs primaires**.

### 4.3 ER7 — non saisi aujourd'hui, et pourquoi

Le TD 2 recommande d'ajouter à D5 un septième événement pour `LOG-PA-03` (« la connaissance opérationnelle des six entrepôts est perdue », `Proof`, gravité *grave*). **Il n'a pas été saisi** : le critère de validation de l'énoncé est explicite, le compteur *Feared events* doit afficher **6**. L'arbitrage se fait au **TP 2** : si D5 adopte ER7, on l'ajoute dans l'outil dans la foulée, on recapture, et on écrit la raison de l'écart de compteur. L'ordre inverse fait rater le critère.

**Captures** : `S5-05-ex4-6-evenements-redoutes-liste.jpg`, `S5-05-ex4-ER5-detail-formulaire.jpg`

---

## 5. Exercice 5 — Les cinq couples SR/OV (atelier 2)

**Compteur final : `RO/TO couples` = 5, dont 3 sélectionnés.** Chaque couple — retenu ou non — est relié à au moins un événement redouté.

| # | Source de risque (TD 2) | Catégorie outil | Motivation | Ressources | Activité | `Selected` | ER reliés | **`Pertinence` calculée par l'outil** |
|---|---|---|---|---|---|---|---|---|
| **1** | Cybercriminel | `Organized crime` | `Strong` | `Important` | `Important` | ✅ | ER1, ER2 | **Highly relevant** |
| **2** | Attaquant passant par l'intégrateur | `Other` ⚠️ | `Significant` | `Important` | `Moderate` | ⬜ | ER1 | **Fairly relevant** |
| **3** | Initié de l'Exploitation | `Avenger` | `Significant` | `Significant` | `Low` ⚠️ | ✅ | ER2 | **Fairly relevant** |
| **4** | Concurrent | `Competitor` | `Low` ⚠️ | `Significant` | `Low` | ✅ | ER4, ER6 | **Partially relevant** ⚠️ |
| **5** | Militant / hacktiviste | `Activist` | `Low` | `Limited` ⚠️ | `Low` | ⬜ | ER3 | **Irrelevant** ⚠️ |

Chaque couple porte sa **justification écrite** dans le champ prévu, fondée sur l'**observable** (chiffres ANSSI 2025 et précédent LockBit pour le couple 1 ; contrat sans clause de réversibilité et box 4G hors supervision pour le couple 2 ; absence d'incident interne mais secret en clair pour le couple 3 ; absence de signal d'espionnage et risque juridique dissuasif pour le couple 4 ; absence de campagne ou de revendication pour le couple 5).

### 5.1 Écart n° 4 — couple 2 en `Other`, et pas en `Avenger`

L'énoncé range « le prestataire malveillant » en `Avenger`. Notre couple 2 **n'est pas l'intégrateur qui se venge** : c'est un attaquant qui **passe par** l'intégrateur — une compromission de la chaîne d'approvisionnement. `Other` est la catégorie juste, et la raison est écrite dans le champ `Justification` du couple. C'est exactement le réflexe que l'énoncé demande quand l'outil et le cas ne se recouvrent pas.

### 5.2 Écart n° 5 — les trois positions « à cheval » tranchées vers le bas

L'outil n'accepte pas « basse à moyenne ». Les trois positions à cheval du TD 2 ont été **tranchées vers le bas**, une fois pour toutes :

- couple 3, activité « basse à moyenne » → **`Low`** ;
- couple 4, motivation « basse à moyenne » → **`Low`** ;
- couple 5, ressources « basses à moyennes » → **`Limited`**.

**Parti pris assumé** : ces trois positions sont basses **sur l'observé**, et c'est l'observable qui fonde la note. Écrit une fois ici plutôt que trois fois dans l'outil.

### 5.3 Écart n° 6 — la colonne `Pertinence` diverge de la sélection, et on ne la suit pas

L'outil calcule seul la pertinence en croisant **motivation × ressources**, sur quatre niveaux, d'`Irrelevant` à `Highly relevant`. **L'activité n'entre pas dans son calcul** — d'où les écarts.

Le cas prévu par le TD 2 s'est produit exactement : le **couple 4** (motivation `Low` × ressources `Significant`) affiche **`Partially relevant`** alors qu'il est **retenu**. La raison de le retenir est ailleurs, et elle est écrite : il est le **seul** couple à atteindre `LOG-PA-04` et la confidentialité — sans lui, toute la moitié « confiance / conformité contractuelle » du métier resterait sans adversaire.

Symétriquement, le **couple 2** affiche `Fairly relevant` — plus que le couple 4 retenu — et reste **non sélectionné**.

> **La sélection n'a pas été changée pour faire plaisir à la colonne.** L'énoncé le dit mot pour mot : *la justification écrite prévaut sur le calcul de l'outil.*

### 5.4 Ce que le geste « relier même les couples non retenus » fait apparaître

Deux des événements les plus graves du dossier n'ont **aucune source de risque *retenue*** :

- **ER3** (chaîne du froid) n'est visé que par le couple **5**, non retenu. Le lien rend la première moitié du trou **visible dans l'outil**.
- **ER5** (réapprovisionnement Santé) **reste sans aucune origine**, et c'est exact : c'est d'abord un risque d'origine **accidentelle** (défaillance fournisseur, panne d'une liaison opérateur, blocage inter-filiales non résolu), mieux couvert par l'approche conformité que par les scénarios.

**Ce trou est signalé, pas bouché.** La recommandation du TD 2 — ajouter un couple « attaquant pivotant Logistique → Santé » avant l'atelier 3 — va dans D5 et dans la séance 6.

**Captures** : `S5-05-ex5-5-couples-liste-pertinence.jpg`, `S5-05-ex5-couple5-formulaire-non-retenu.jpg`

---

## 6. Ce qui n'est **pas** fait aujourd'hui, et pourquoi

Les **ateliers 3, 4 et 5 restent vides** — compteurs `Stakeholders` = 0, `Strategic scenarios` = 0, `Operational scenarios` = 0. Ce n'est pas un oubli, c'est la méthode :

- **atelier 3** (scénarios stratégiques) et **atelier 4** (scénarios opérationnels et leur vraisemblance) : **séance 6** — c'est là que l'écosystème, les prestataires et les projets entrent, et que le couple 2 (intégrateur) retrouve sa place ;
- **atelier 5** (traitement) : **séance 7**, dont la première activité, *« Generate the risk assessment »*, **créera le registre à partir de l'étude** ;
- **rien ne sera recopié** d'une séance à l'autre : c'est la même étude qui se remplit.

> *Un atelier vide parce que la méthode n'y est pas encore est un état normal ; un atelier rempli d'objets improvisés est pire qu'un atelier vide, parce qu'il a l'air fini.*

**Capture** : `S5-05-ateliers-3-4-5-vides-et-compteurs.jpg`, `S5-05-ateliers-1-a-5-vue-etude.jpg`

---

## 7. F3 — Marquage du Top 5 dans l'instance (geste en attente, fermé aujourd'hui)

Les cinq biens supports du Top 5 de D2 portent désormais l'étiquette **`Top5`** dans le champ `Labels`, visible **dans la colonne `LABELS` de la liste des actifs, sans avoir à ouvrir le fichier D2** :

| Rang D2 | Actif | Libellé outil | Étiquette |
|---|---|---|---|
| 1 | `LOG-SA-01` | WMS (2 serveurs + BDD, site E1) | ✅ `Top5` |
| 2 | `LOG-SA-04` | Compte de service WMS-automates | ✅ `Top5` |
| 3 | `LOG-SA-09` | Responsable Exploitation | ✅ `Top5` |
| 4 | `LOG-SA-05` | Logiciel des sondes de temperature | ✅ `Top5` |
| 5 | `LOG-SA-03` | Automates de tri (E2/E3/E4) | ✅ `Top5` |

> ⚠️ **Contrainte de l'outil relevée** : une étiquette doit être **alphanumérique et faire au plus 36 caractères**. Le premier essai, `Top 5 D2`, a été **refusé** (l'espace n'est pas accepté) ; l'étiquette retenue est **`Top5`**, sans espace. À citer dans D2 pour que l'étiquette du dossier et celle de l'instance coïncident.
>
> ℹ️ La barre de recherche de la liste des actifs **ne cherche pas dans les étiquettes** : le Top 5 se lit dans la colonne `LABELS`, ou se filtre via `Filters`.

**F3 est clos** : D2 affirmait « instance *et* dossier », c'est désormais vrai. Liste d'actifs recapturée dans `Session-2/3-Evidence/` (`S2-05bis-assets-list-Top5-page1..3-of-3.jpg`) et dans `Session-5/3-Evidence/` (`S5-05-F3-top5-marque-assets-page1..3.jpg`).

---

## 8. Compteurs finaux — « fini quand »

| Compteur de la carte *Summary* | Attendu | Constaté |
|---|---|---|
| `Assets` | ≥ 17 | **17** ✅ |
| `Audits` | 1 | **1** ✅ |
| `Feared events` | 6 | **6** ✅ |
| `RO/TO couples` | 5 | **5** ✅ |
| `Stakeholders` | 0 | **0** ✅ |
| `Strategic scenarios` | 0 | **0** ✅ |
| `Operational scenarios` | 0 | **0** ✅ |

Et **chaque écart entre l'outil et le TD 2 est écrit ici** plutôt que corrigé en douce.

---

## 9. Critères de validation de l'énoncé — relecture de clôture

- [x] Table d'inventaire produite, **nom exact observé** pour chaque objet ; l'écart (`MERIDIAN-SANTE` présent, `API` vs « interface ») est **signalé, rien n'a été recréé ni renommé**
- [x] Matrice « 4x4 EBIOS-RM » importée depuis la bibliothèque, **trois phrases** écrites (case la plus élevée, couleur de la diagonale, écart de libellés sur V4 et G3)
- [x] Étude créée **dans le domaine de la filiale**, jamais le domaine racine, avec la matrice et la méthode **`Manual`**
- [x] Cadrage lisible **dans la description**, sans avoir à ouvrir le compte rendu du TD
- [x] Les actifs sont **reliés**, pas recréés — **aucun doublon** dans `Assets` (17 avant, 17 après)
- [x] L'audit de la séance 4 est **rattaché** à l'étude
- [x] **6** événements redoutés, chacun avec **actif primaire + qualification + gravité + justification**, tous `Selected`
- [x] **5** couples SR/OV, **3** sélectionnés, **chacun** relié à au moins un événement redouté
- [x] Écart de `Pertinence` relevé (couples 4 et 2), **sélection inchangée**
- [x] Ateliers 3, 4 et 5 **vides**, et la raison écrite
- [x] Chaque objet créé porte un **auteur nommé** (compte nominatif, jamais `admin@lockbay.eu`)

---

## 10. Entrées pour le TP 2 et pour D5

| Ce qui sort d'ici | Où ça va |
|---|---|
| La matrice importée porte l'échelle sur laquelle le TP 2 posera le **seuil d'acceptation** dérivé de l'appétence du TD 1 | TP 2, D5 §échelles |
| Réserve du TD 2 **levée** : la correspondance des libellés de gravité est **constatée**, plus « présumée » — retirer le mot | TD 2 + D5 |
| Trois écarts de vocabulaire (`Impact` vs gravité vs conséquence · `API` vs interface · `Top5` sans espace) | D5, section méthode |
| ER5 rattaché à `LOG-PA-01` faute de valeur métier propre, **le domaine `MERIDIAN-SANTE` existant pourtant** | D5 §3 et §4, à lever en séance 6 (atelier 3) |
| ER7 non saisi, arbitrage à rendre | TP 2, puis saisie + recapture si D5 l'adopte |
| ER3 sans origine retenue, **ER5 sans aucune origine** — trou signalé, non bouché | D5 §4 + séance 6 |
| Couple 2 (intégrateur) reporté à l'atelier 3 comme **partie prenante critique de l'écosystème** | Séance 6 |
| Décision de poursuite et table du socle à quatre colonnes — **sans champ dans l'outil** | D5 §2 |
