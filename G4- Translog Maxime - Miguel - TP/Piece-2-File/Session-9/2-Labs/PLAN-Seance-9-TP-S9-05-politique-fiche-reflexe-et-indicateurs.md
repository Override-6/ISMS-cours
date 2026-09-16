# PLAN — Séance 9, TP 1 (S9-05) : section de PSSI, fiche réflexe, indicateurs et tableau de bord

**Mode opératoire écrit avant la saisie**, au format des plans des séances 4 à 8. Instance `translog-b`,
domaine `MERIDIAN-LOGISTIQUE`, périmètre `MERIDIAN-LOGISTIQUE-FINAL`.
**Source** : `../../../../S9 - Sources/TP 1/Workshop in the tool_ PSSI, quick-reaction sheet, indicators and dashboard _ Lockbay Academy.pdf`
(énoncé ; corrigé replié dans la page, non consulté).

> **Ce que ce fichier est, et n'est pas.** Il décide **avant la saisie** le contenu des trois documents et
> des sept indicateurs, sourcé sur `D1` à `D8` et sur le pack de filiale. Il ne porte **aucune valeur lue
> dans l'outil** : les relevés du jour, les compteurs et les captures vont dans la feuille de travail
> `Seance-9-TP-S9-05-feuille-de-travail-*.md`, à remplir pendant la séance. Le livrable reste `D9-…`.

---

## 0. Les cinq règles de rédaction, à appliquer aux trois documents

Rappelées par l'énoncé avant la première ligne, et vérifiables une par une à la relecture :

1. **Une règle est une obligation vérifiable** — sujet identifiable, verbe d'obligation, critère de
   vérification. *« Les mots de passe doivent être robustes »* n'est pas une règle, c'est une humeur.
2. **Toute règle a un propriétaire et une preuve.** Si l'on ne peut dire ni qui répond de la règle, ni quel
   enregistrement démontre son application, ce qui est écrit est un espoir.
3. **Verbes mous interdits** — *« veiller à »*, *« s'efforcer de »*, *« dans la mesure du possible »* : un
   auditeur les lit comme des clauses d'échappement, un juriste aussi.
4. **Une phrase, une règle.** Trois obligations et une exception dans la même phrase produisent des débats
   d'interprétation.
5. **Tout document cite son fondement** — la section de PSSI cite le risque ou le contrôle retenu qui la
   justifie, la procédure cite la règle qu'elle décline, la fiche réflexe cite la procédure qu'elle
   condense. Un document qui ne sait pas nommer son étage supérieur est un orphelin.

**Le test du tableau « avant / après » de l'énoncé, transposé chez nous** : la colonne de droite ne contient
presque que des règles **que le groupe possède déjà** (`COR-01` 14 jours, `ACC-02` revue trimestrielle,
`INC-01` 2 heures). L'atelier n'invente pas d'obligations, il apprend à écrire celles que `D1` a posées.

---

## 1. Exercice 1 — la section « gestion des vulnérabilités » de la PSSI-cadre (20 min)

**À produire** : la section, **une page au plus**, saisie dans l'outil en document de type **Policy**,
référence `PSSI-VUL`, domaine du groupe, *content source* **Authored**, reliée sous *Relations* au contrôle
appliqué qui porte le traitement des vulnérabilités — chez nous **`PT-01`** (recette formalisée avant toute
mise à jour du WMS, échéance 14/12/2026).

### 1.1 Étape préalable imposée — citer, ne pas paraphraser

L'énoncé l'exige explicitement : **lire dans l'instance, avant d'écrire**, le statut et la justification que
la déclaration d'applicabilité porte sur le contrôle de gestion des vulnérabilités techniques, et **citer
cette justification** dans l'item « objet et fondement » plutôt que de la reconstituer de mémoire.

L'état écrit au dossier, à confronter à l'observation réelle de l'instance :

| Contrôle | État constaté (D8 §2.2) | Justification du maintien, telle que D8 la porte |
|---|---|---|
| **`A.8.8`** — Gestion des vulnérabilités techniques | **Non conforme** | *« Directive `COR-01` de D1, non mesurée ; mises à jour du WMS non maîtrisées ; scénario `OS1` »* — traitement : `PT-01`, 14/12/2026 |

> **Point de vigilance F22.** `D8` §2.4 signale que le rapprochement `A.8.8` ↔ `PT-01` est **une lecture de
> D8**, absente du tableau mesure ↔ exigence de `D7` §6 — la correction de `D7` §6 est le chantier inscrit à
> la séance 9. Si elle est faite avant ce TP, la relation à poser dans l'outil devient directe ; sinon, la
> poser quand même et noter l'écart dans la feuille de travail.

Les deux autres fondements que la section doit nommer :

- **Le constat d'audit** : `D4` §3.2 relève `A.8.8` **non couvert** — *« `COR-01` (correctif sous 14 jours) :
  ni mesuré ni mesurable, mises à jour décidées par la TMA sans préavis »*, sur les actifs `SA-01` (WMS) et
  `SA-03` (automates de tri).
- **Le risque du registre** : `OS1`, le chiffrement du WMS par la voie de la tierce maintenance —
  `Very likely × Critical` = `High` avant traitement (`D7` §2).

### 1.2 Le gabarit imposé, rempli avant saisie

| Item du gabarit | Ce que nous y mettons |
|---|---|
| **Objet et fondement** | Ce que couvre la section — la qualification, la correction et la traçabilité des vulnérabilités techniques sur les systèmes de la filiale, mises à jour du WMS comprises. Ce qui la fonde : la justification de `A.8.8` **citée verbatim** depuis l'instance, le constat de `D4` §3.2, et le scénario `OS1` du registre de `D7`. |
| **Règles** | **Cinq règles**, numérotées dans la codification du groupe — détail en §1.3. |
| **Responsabilités** | Par rôle, aligné sur la matrice RACI de `D1` : le **DSI de filiale** porte `COR-01` (propriétaire de la règle) ; le **Responsable SI de la filiale** — *qui ne porte pas le titre de RSSI*, pack §3 — exécute l'inventaire et la recette ; le **RSSI Groupe** valide les dérogations sous `ARB-03` ; le **Directeur de la filiale** porte l'avenant contractuel qui rend la recette opposable à la tierce maintenance (`PT-01`). |
| **Dérogations** | Circuit `ARB-03` de `D1` : toute dérogation à la PSSI-cadre est **validée par le RSSI Groupe sous 48 heures**, datée et bornée. *« Une dérogation sans circuit devient un droit acquis. »* |
| **Application et preuve** | L'indicateur qui mesure la section — **`IND-07`** (voir §3) — et l'enregistrement qui sert de preuve : le **procès-verbal de recette** de chaque mise à jour du WMS, conservé par le Responsable SI de la filiale, exigible par l'Audit Interne du holding. |

### 1.3 Les cinq règles, écrites au format « obligation vérifiable »

*Deux viennent du corps de règles existant (`COR-01`, `ARB-03`), trois sont ajoutées par l'analyse — comme
l'énoncé le demande : le délai des correctifs critiques et le circuit de dérogation que le groupe possède
déjà, **plus** l'inventaire des systèmes couverts et la qualification des vulnérabilités.*

| # | Règle | Propriétaire | Preuve |
|---|---|---|---|
| **VUL-01** | Tout correctif qualifié de critique est appliqué **sous 14 jours calendaires** à compter de sa publication par l'éditeur ; tout dépassement est couvert par une dérogation validée sous 48 heures. *(décline `PSSI-CADRE-COR-01` et `ARB-03`)* | DSI de filiale | Horodatage de publication et horodatage d'application, par système |
| **VUL-02** | Chaque système de la filiale figure à l'inventaire des systèmes couverts, avec son éditeur, sa version et son propriétaire ; tout système découvert hors inventaire y est rattaché **sous 30 jours**. *(décline la règle de tenue de `D2` §8, déjà appliquée par `PT-13`)* | DSI de filiale | Inventaire daté dans `translog-b` — 17 actifs à propriétaire nommé |
| **VUL-03** | Toute vulnérabilité publiée est qualifiée **sous 5 jours ouvrés** en critique, importante ou mineure, selon l'exposition du système et le besoin de sécurité de la valeur métier qu'il porte ; la qualification est écrite et porte un nom. | Responsable SI de la filiale | Fiche de qualification, une par vulnérabilité qualifiée critique |
| **VUL-04** | **Aucune mise à jour du système de gestion d'entrepôt n'est déployée en production sans procès-verbal de recette signé** par la filiale ; le prestataire de tierce maintenance notifie toute mise à jour **au moins 5 jours ouvrés** avant déploiement. *(rend `PT-01` opposable ; ferme le maillon « mise à jour déployée sans recette » d'`OS1`)* | Directeur de la filiale *(avenant)* · Responsable SI *(recette)* | Procès-verbal de recette, avenant au contrat `TMA-WMS-2021` |
| **VUL-05** | Le taux de correctifs critiques appliqués dans le délai est relevé **chaque trimestre** et présenté au Comité sécurité groupe ; un relevé impossible faute de donnée est déclaré **« non mesuré »**, jamais compté comme conforme. | RSSI Groupe | Relevé trimestriel, fiche de l'indicateur `IND-07` |

> **Pourquoi VUL-05 existe.** `D4` écrit que `COR-01` est *« ni mesuré ni mesurable »*. Une section qui
> poserait le délai sans poser la mesure reproduirait exactement le défaut qu'elle prétend corriger — et
> c'est le point que la page S9 de Miguel généralise : **une case vide se lit trop facilement comme une case
> verte**. La règle du « non mesuré » déclaré est la réponse de rédaction à cet angle.

### 1.4 Marche à suivre dans l'outil

1. *Governance* → *Documents* → *New document* : référence **`PSSI-VUL`**, nom de la section, type
   **Policy**, domaine du groupe, *content source* **Authored**.
2. *Relations* : lier **`PT-01`** (et `PT-13` si l'outil accepte plusieurs contrôles appliqués).
3. Rédiger item par item sur le gabarit du §1.2, les cinq règles du §1.3.
4. **Test de l'auditeur, règle par règle** : *un tiers peut-il déterminer, sans interroger l'auteur, qui est
   en faute et sur quelle preuve ?* Si non, la règle est réécrite, pas commentée.
5. **Publier** : soumettre la révision à l'autre membre du groupe, qui valide. **L'outil interdit à un auteur
   de valider son propre texte** — c'est la règle du CM : un document sans validation n'engage personne.
   Exporter la version 1 publiée en **PDF** pour le dossier.

> **Répartition nominative** *(moitié du coefficient individuel)* : `PSSI-VUL` est **rédigée par l'un**,
> **validée par l'autre** ; `FR-RANCON` s'écrit dans l'autre sens. Chaque document porte donc un auteur et un
> validateur distincts et nommés.

---

## 2. Exercice 3 — la fiche réflexe « suspicion de rançongiciel » (15 min)

*L'exercice 2 (procédure `PRO-PRIV` de revue trimestrielle des privilèges, `ACC-02`) est **optionnel** et se
fait en temps projet encadré, après `D9` : il n'est pas exigé pour le dossier. À ne traiter que si les sept
indicateurs et le tableau de bord sont finis.*

**Ce qu'est une fiche réflexe**, au sens du module : **une seule page, affichable au mur**, qui dit à une
personne sous stress quoi faire dans les premières minutes d'un événement grave, avant l'arrivée des
spécialistes. Ni politique ni procédure : le condensé d'urgence d'une procédure, écrit pour être exécuté par
quelqu'un qui ne l'a jamais lue au calme, la nuit, un jour férié.

**À produire** : la fiche pour **un site de MERIDIAN Logistique**, dans l'outil en document de type **Other**
(aucun type « fiche réflexe » n'existe), référence **`FR-RANCON`**, domaine du groupe, reliée sous
*Relations* au contrôle de sauvegarde ou de réponse à incident du plan de traitement — chez nous **`PT-04`**
(test de restauration du WMS, 14/11/2026) et, à défaut, `PT-07` (raccordement des journaux au SOC).

### 2.1 Le site retenu, et pourquoi

**Le site E1.** Choisi sur la carte du pouvoir (§3) et sur ce qui franchit la frontière (§6) du pack :
E1 héberge **les deux serveurs du WMS et sa base**, ainsi que **le local serveur unique de la filiale** ; il
est l'un des deux entrepôts servant le client pharmaceutique ; et c'est de lui que part **le flux de
réapprovisionnement d'urgence vers MERIDIAN Santé**, la seule dépendance inter-filiales de §6 — donc le seul
flux sur lequel le droit d'isolement d'urgence `ARB-02` a un objet.

### 2.2 Les trois blocs, décidés avant saisie

*Une liste numérotée par bloc dans l'éditeur. Chaque interdit porte sa raison en quelques mots : un interdit
inexpliqué se viole sous stress.*

**Bloc 1 — Gestes immédiats** *(les cinq premières minutes)*

1. **Ne pas éteindre.** Débrancher le **câble réseau** du poste ou du serveur concerné ; laisser la machine
   allumée.
2. **Noter l'heure** — heure exacte du premier signe constaté, et ce qui a été vu. *C'est le premier geste
   d'une chronologie ; l'arrêt d'avril 2026 n'en a jamais eu.*
3. **Appeler le Responsable SI de la filiale**, ligne directe, puis le Responsable Exploitation. Si aucun ne
   répond en 10 minutes, appeler le **RSSI Groupe** directement.
4. **Demander l'isolement du flux de réapprovisionnement d'urgence vers MERIDIAN Santé.** Le droit
   d'isolement d'urgence sur un flux inter-filiales en cas de compromission confirmée est `ARB-02` de `D1` ;
   il est porté par le **RSSI de filiale** — et **MERIDIAN Logistique n'en a pas** : le pack §3 décrit un
   *« Responsable SI de la filiale, qui ne porte pas le titre de RSSI, trois personnes »*. **Tant que ce
   porteur n'est pas nommé, la fiche désigne le Responsable SI de la filiale, avec escalade immédiate au RSSI
   Groupe** — et c'est une décision à faire trancher, pas un détail de rédaction.
5. **Ne rien annoncer au client pharmaceutique** sans décision du Directeur de la filiale.

**Bloc 2 — Alertes à donner** *(les deux premières heures)*

1. **RSSI Groupe — sous 2 heures**, obligation ferme : `PSSI-CADRE-INC-01` de `D1`. Canaux **dans cet ordre**
   : téléphone mobile, puis ligne fixe, puis courriel avec accusé. *L'heure de chaque tentative est notée.*
2. **Directeur de la filiale** — il décide de l'information du client pharmaceutique et de l'arrêt éventuel
   de l'exploitation *(pack §3 : budget, contrats et clients sont sa décision)*.
3. **Responsable Qualité et chaîne du froid** — si des relevés de température sont touchés : l'atteinte se
   paie au contrat et à l'audit annuel du client.
4. **RSSI de MERIDIAN Santé** — dès que l'isolement du flux est décidé, parce que la coupure les concerne.
5. **Prestataire de tierce maintenance** — **en dernier**, et seulement pour l'informer : il est l'un des
   chemins d'attaque identifiés (`AP.01`), il n'est pas le premier appel.

**Bloc 3 — Interdits** *(chacun avec sa raison)*

1. **Ne pas éteindre la machine** — l'extinction détruit la mémoire vive, où se trouve parfois la seule copie
   de la clé de chiffrement.
2. **Ne pas redémarrer, ne pas « réparer »** — un redémarrage peut déclencher la phase de chiffrement.
3. **Ne pas restaurer une sauvegarde avant accord du RSSI Groupe** — une restauration sur un réseau encore
   compromis se fait rechiffrer, et **aucune restauration du WMS n'a jamais été testée** (pack §5).
4. **Ne pas payer, ne pas répondre au message de rançon** — c'est une décision de direction, jamais de site.
5. **Ne pas prévenir le client ni les réseaux sociaux** — la communication externe appartient au Directeur de
   la filiale.
6. **Ne pas effacer le message de rançon ni les fichiers chiffrés** — ce sont les seules preuves.

### 2.3 Marche à suivre dans l'outil, et le test imposé

1. *Governance* → *Documents* → *New document* : référence **`FR-RANCON`**, type **Other**, domaine du
   groupe ; les trois blocs en trois listes numérotées dans l'éditeur.
2. **Test en binôme, exigé par l'énoncé** : l'autre membre lit la fiche **en une minute, montre en main**,
   puis raconte ce qu'il ferait. *Ce qu'il raconte mal, la fiche le dit mal — on corrige la fiche, pas le
   lecteur.* **Consigner le résultat du test dans la feuille de travail** : c'est la preuve que l'étape a eu
   lieu.
3. **Publier après validation** par le binôme qui a fait passer le test, puis **exporter le PDF** : une fiche
   réflexe vit imprimée à côté du poste, pas seulement dans l'outil.

---

## 3. Exercice 4 — les indicateurs et le tableau de bord (25 min)

### 3.1 Le gabarit de `D9`, non négociable — un item vide est un indicateur rejeté

| Item | Exigence | Où il vit dans l'outil |
|---|---|---|
| **Nom et nature** | Un nom sans jargon, et sa nature : conformité, risque ou opérations | *Metric definition* : référence, nom, la nature **en tête de la description** |
| **Définition** | Ce que l'indicateur mesure, en une phrase qu'un membre du Comité comprend seul | *Metric definition* : description |
| **Formule** | Le calcul exact : numérateur, dénominateur, unité, règles d'inclusion et d'exclusion | *Metric instance* : **première ligne** de la description |
| **Source de données** | D'où viennent les valeurs, avec le propriétaire de la lecture | *Metric instance* : description + **`Assigned to`** |
| **Seuil** | La cible, le seuil d'alerte, et ce que son franchissement déclenche | *Definition* : cible par défaut et case *higher is better* ; *instance* : valeur cible, seuil dans la description |
| **Fréquence** | Le rythme de relevé, et de présentation s'il diffère | *Metric instance* : *collection frequency* |
| **Destinataire** | Qui le reçoit, et la décision qu'il éclaire pour lui | *Metric instance* : description + **l'objectif de la note de stratégie surveillé** |
| **Valeur du jour** | La valeur à la date du TP, avec le comptage qui la justifie | *Metric instance* : **un échantillon daté**, sa valeur, son observation |

**Les deux règles de composition, qui sont les critères d'acceptation du livrable** : le jeu **mêle les trois
natures** (conformité, risque, opérations) ; **chaque indicateur est rattaché explicitement à un objectif de
la note de stratégie** — un indicateur qui ne surveille aucun objectif est un chiffre orphelin, si bien
construit soit-il. Et **au moins un indicateur doit être calculable le jour même** avec les pièces du
dossier : c'est la preuve que le jeu n'est pas un vœu d'outillage futur.

### 3.2 Le jeu retenu — sept indicateurs

*Matière première, telle que l'énoncé la désigne : les KRI et KPI du tableau de bord de la séance 1 ; les
indicateurs promis par les documents écrits ce matin ; **le trou dans le filet** — l'avancement de la
segmentation chez Logistique, qu'aucun chiffre ne surveillait ; et les réserves de `D7` et `D8`.*

| Réf. | Indicateur | Nature | Objectif de la note surveillé | Calculable aujourd'hui | Statut à saisir |
|---|---|---|---|---|---|
| **`IND-01`** | Couverture de la déclaration d'applicabilité | Conformité | **§8** — périmètre du SMSI | ✅ `D8` | `Active` |
| **`IND-02`** | Écarts de conformité sans mesure de traitement | Conformité | **§8** et **§4** — état des lieux | ✅ `D8` §2.4 | `Active` |
| **`IND-03`** | Restaurations du WMS testées sur douze mois | Opérations | **§7** — point ouvert « RTO réel » | ✅ pack §5 | `Active` |
| **`IND-04`** | Avancement de la séparation des réseaux bureautique et industriel | Risque | **§7** et **§8** — l'exclusion d'E4 tombe à cette date | ✅ `D7` | `Active` |
| **`IND-05`** | Risques résiduels au-dessus du seuil d'acceptation | Risque | **§5** — seuil d'acceptation | ✅ `D7` §2 | `Active` |
| **`IND-06`** | Accès de la tierce maintenance ouverts par compte nominatif | Risque | **§6** — tiers et projets | ✅ pack §3 | `Active` |
| **`IND-07`** | Respect du délai de notification `INC-01` | Opérations | **§1** — gouvernance et directives | ❌ **non mesurable à ce jour** | **`Draft`** |

**Couverture des trois natures** : conformité `IND-01`/`IND-02` · risque `IND-04`/`IND-05`/`IND-06` ·
opérations `IND-03`/`IND-07`. **Six des sept sont calculables aujourd'hui** — très au-delà du minimum d'un
seul qu'exige l'énoncé.

### 3.3 Les sept fiches, remplies avant saisie

*La valeur du jour est écrite ici telle que le dossier la donne ; elle **se relit dans l'outil ou dans la
pièce citée avant d'être saisie**, et c'est la feuille de travail qui fait foi.*

| Réf. | Formule | Source · propriétaire de la lecture | Cible | Seuil d'alerte · ce qu'il déclenche | Fréquence | Destinataire · décision éclairée | Valeur du jour, et son comptage |
|---|---|---|---|---|---|---|---|
| **`IND-01`** | Contrôles d'annexe A investigués ÷ 93 contrôles de l'annexe A. *Inclus : tout contrôle portant un résultat autre que « non évalué », exclusion comprise. Exclus : les clauses 4 à 10.* | Évaluation `MERIDIAN - ISO/IEC 27001:2022 - initial assessment` dans `translog-b` · RSSI Groupe | **100 %** au cycle 3 · **50 %** au cycle 2 | **< 20 %** → programmer l'investigation des huit contrôles désignés par `D8` §2.4 | Trimestrielle | Comité sécurité groupe · l'effort d'investigation à financer | **16,1 %** — 15 ÷ 93 (`D8` §2.1) |
| **`IND-02`** | Contrôles retenus, non conformes ou partiels, **qu'aucune mesure du plan de traitement ne porte** ÷ contrôles retenus investigués. | `D8` §2.4 vis-à-vis de `D7` §6 · RSSI Groupe | **0 %** | **> 0 %** → inscrire chaque orphelin au plan de traitement ou l'accepter formellement | Trimestrielle | Comité sécurité groupe · ouvrir une mesure ou signer une acceptation | **20 %** — 3 ÷ 15 (`A.5.24`, `A.6.3`, `A.7.4`) |
| **`IND-03`** | Nombre de restaurations complètes du WMS et de sa base **testées et documentées** sur les douze derniers mois. *Une restauration partielle ou non documentée ne compte pas.* | Pack de filiale §5, puis procès-verbal de test de `PT-04` · DSI de filiale | **≥ 1 par an** | **0** → financer le test de restauration sans attendre le cycle budgétaire | Annuelle, relevé trimestriel | Direction Générale · la borne haute du coût de l'inaction reste indéterminée tant qu'il vaut 0 | **0** — aucune restauration depuis la mise en service (pack §5) |
| **`IND-04`** | Entrepôts dont les réseaux bureautique et industriel sont séparés, recette prononcée ÷ **6** entrepôts. | Recette de `PT-03` · DSI de filiale | **6 / 6** au **14/06/2027** | **< 6/6 après le 14/06/2027** → l'exclusion de l'automatisation d'E4 du périmètre de certification **ne tombe pas** ; réexamen au Comité Exécutif | Trimestrielle | Comité Exécutif · tenir ou reporter la date de certification | **0 / 6** — aucune segmentation recettée (`D7` §1, `C3` de `D4`) |
| **`IND-05`** | Lignes du registre dont le **risque résiduel** est au-dessus du seuil d'acceptation ÷ lignes du registre. *Seuil : `High` inacceptable (`D5`).* | Registre de `translog-b` · RSSI Groupe | **0 %** | **> 0 %** → traiter avant toute mise en production, ou faire signer une acceptation formelle | Trimestrielle | Direction Générale · le seuil de la sous-section 5 tient ou non | **0 %** — 0 ÷ 8 (`D7` §2 : 6 `Medium`, 2 `Low`) |
| **`IND-06`** | Accès du prestataire de tierce maintenance ouverts par **compte nominatif avec authentification forte** ÷ accès du prestataire ouverts. | Annuaire de domaine, puis recette de `PT-02` · DSI de filiale | **100 %** au **14/01/2027** | **< 100 %** → suspendre les accès non nominatifs ou faire acter une dérogation `ARB-03` | Trimestrielle | Directeur de la filiale · l'avenant contractuel et la suspension des accès | **0 %** — le compte de domaine `svc-applica` est partagé, **nombre de porteurs inconnu** (pack §3, `C4` de `D4`) |
| **`IND-07`** | Incidents majeurs notifiés au RSSI Groupe **en moins de 2 heures** ÷ incidents majeurs déclarés. | Chronologie d'incident produite par la procédure à écrire (`A.5.24`) · Responsable SI de la filiale | **100 %** | **< 100 %** → exiger une dérogation formelle et bornée sous `ARB-03` | Par incident, présenté trimestriellement | Comité sécurité groupe · escalader ou borner le manquement | **Non mesuré — aucune procédure d'incident, donc aucun dénominateur.** À afficher *« non mesuré à ce jour »*, **jamais** comme une conformité |

> **Pourquoi `IND-07` est saisi en `Draft` et affiché quand même.** C'est exactement l'argument de la page S9
> de Miguel : sur un tableau de bord binaire, **une case vide se lit comme une case verte**. L'énoncé prévoit
> le statut `Draft` *« pour les indicateurs dont la source reste à ouvrir »* — nous l'utilisons, et la tuile
> du tableau de bord porte la mention explicite plutôt qu'un blanc.
>
> **Pourquoi le taux de sensibilisation n'est pas dans le jeu.** C'est l'argument de la page S9 de Maxime :
> `A.6.3` est coté **non conforme faute de toute preuve** (`D8` §2.2) et **n'a jamais produit de mesure** —
> il n'existe chez nous ni numérateur ni dénominateur. Le réintégrer une fois le programme de sensibilisation
> écrit, avec sa méthode de calcul rendue explicite. **Le doublon arbitré** : `IND-02` et un éventuel
> indicateur « constats d'audit non résolus à 30 jours » éclairent la même décision ; `IND-02` est retenu, sa
> source (`D8` §2.4 face à `D7` §6) étant la plus fiable des deux.

### 3.4 Marche à suivre dans l'outil

1. **Définir** : *Metrics* → *Metric definitions* → *Add*. Référence `IND-01` et suivantes, nom **sans
   jargon**, description **commençant par la nature** (KPI ou KRI) puis ce que le chiffre mesure, domaine du
   groupe, catégorie *Quantitative*, unité *Count* ou *Percentage*, cible par défaut, *provider* au nom du
   groupe. **Case *higher is better* décochée** pour tout compte qui doit baisser — chez nous `IND-02` et
   `IND-05`.
2. **Instancier** : *Metrics* → *Metric instances* → *Add*. Même référence, la définition choisie, le domaine
   ; dans la description, **la formule et la source** *(les deux items qui tuent)*, le seuil d'alerte et ce
   qu'il déclenche, le destinataire et la décision éclairée, **l'objectif de la note de stratégie surveillé**
   ; *collection frequency*, valeur cible, et **le propriétaire de la lecture dans `Assigned to`**.
   Statut **`Active`** pour `IND-01` à `IND-06`, **`Draft`** pour `IND-07`.
3. **Relever la valeur du jour** des six calculables : ouvrir l'instance, *Add a sample*, horodatage du jour,
   la valeur, et **dans l'observation le comptage qui la justifie — numérateur, dénominateur, document
   d'origine**. Le piège de cette étape n'est pas la paresse, c'est **la fausse précision** : une formule qui
   a l'air exacte et dont personne ne sait où vit le dénominateur.
4. **Tableau de bord** : *Metrics* → *Dashboards* → *Add*. Référence, nom, domaine, et **dans la description
   la période couverte et la règle de lecture**. Puis *Edit layout* : une carte KPI par indicateur via *Add
   custom metric* (dernière valeur **et** cible) ; une ou deux vues natives via *Add builtin metric* — chez
   nous la **répartition des résultats de l'évaluation** et la **répartition des options de traitement du
   registre** ; une tuile texte en haut pour la période, une tuile texte en bas pour **les messages et les
   décisions demandées**.
5. **Ordonner les tuiles par importance de décision, pas par famille technique** — le Comité lit de haut en
   bas et s'arrête quand on l'interrompt. Ordre proposé : `IND-03`, `IND-04`, `IND-06`, `IND-05`, `IND-01`,
   `IND-02`, `IND-07`.
6. **Contrôle de cohérence de bout en bout** : chaque tuile correspond à un indicateur, chaque indicateur à
   une définition **et** à un objectif de la note, **aucun chiffre de la page ne sort de nulle part**. Puis
   **capture datée** de la page — c'est la maquette de `D9`, et elle est exigée au dossier.

---

## 4. Ce qui sort de ce TP, et où cela va

| Produit | Destination |
|---|---|
| `PSSI-VUL` (Policy, publiée, PDF) · `FR-RANCON` (Other, publiée, PDF) | `translog-b` + export dans `../3-Evidence/` |
| 7 définitions + 7 instances d'indicateurs, 6 relevés datés | `translog-b` |
| Le tableau de bord du Comité, **capturé daté** | `../3-Evidence/S9-05-tableau-de-bord-date.jpg` |
| Les valeurs lues, les écarts d'outil, le résultat du test en binôme de `FR-RANCON` | `Seance-9-TP-S9-05-feuille-de-travail-*.md` |
| **Le livrable `D9`** — politique sur le gabarit imposé, une procédure, une fiche réflexe, 5 à 8 indicateurs avec formule, source, seuil, fréquence et destinataire | `D9-politique-procedures-et-indicateurs.md` *(TP 2)* |
| **La sous-section 9 de la note de stratégie**, qui referme le document sur lui-même | `../../Piece-1-Strategy-note/MERIDIAN-strategy-note.md` *(TP 2)* |

**Deux points de vigilance, constants depuis la séance 1.** Le livrable, c'est `D9-…` : autonome, nommé, au
format exigé, **un seul par séance** ; les feuilles de travail et ce plan restent à côté comme trace de
méthode. Et **chaque objet créé dans `translog-b` porte un auteur nommé** — c'est la moitié du coefficient
individuel, l'autre moitié étant la question individuelle en soutenance.
