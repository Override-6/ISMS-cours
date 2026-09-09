# PLAN D'ACTION — Séance 5, TP 1 : saisie des ateliers 1 et 2 d'EBIOS RM dans CISO Assistant

**Groupe 4 (Translog)** · instance `translog-b` (https://translog-b.lockbay.eu)
**Domaine** `MERIDIAN-LOGISTIQUE` (sous-domaine de `Global`) · **périmètre** `MERIDIAN-LOGISTIQUE-FINAL`
**Source du TP** : `../../../../S5 - Sources/TP 1/Inputting Workshops 1 and 2 into CISO Assistant _ Lockbay Academy.pdf`
**Matière saisie** : `../4-Working-notes/Seance-5-TD-S5-03-ateliers-1-et-2-EBIOS-RM.md` (TD 2, les quatre exercices) et `../1-CISO-desk/Seance-5-TD-S5-01-appetence-au-risque.md` (TD 1, l'appétence)

**Ce fichier n'est pas un livrable** : c'est le mode opératoire. Le livrable de la séance 5 est **D5, le dossier d'appréciation initiale**, assemblé au **TP 2** ; ce TP-ci transpose dans l'outil ce que le TD 2 a produit sur le papier, et rien d'autre.

> **Règle de la journée, avant tout clic** : *réutiliser, jamais recréer.* Les 4 valeurs métier et les 13 biens supports existent depuis la séance 2, le référentiel depuis la séance 3, l'audit depuis la séance 4. On les **relie** à l'étude. Le bouton « ajouter un actif » de l'atelier 1 activité 2 est le piège explicite de l'énoncé : il crée un doublon, et le doublon est le début de la divergence entre l'outil et la réalité.

**Durée annoncée** : 10 + 10 + 15 + 20 + 25 = **80 minutes** de saisie, hors captures.

---

## 0. État des prérequis — ce qui est prêt, ce qui ne l'est pas

| Prérequis de l'énoncé | État au dossier |
|---|---|
| Le cadrage de l'étude (objectif, participants, cycles, accepteur des résiduels) | ✅ TD 2, exercice 1 |
| Les six événements redoutés cotés en gravité | ✅ TD 2, exercice 2 |
| La table du socle de sécurité | ✅ TD 2, exercice 3 |
| Les cinq couples SR/OV évalués, trois retenus | ✅ TD 2, exercice 4 |
| L'appétence du matin (elle porte le seuil d'acceptation) | ✅ TD 1 — mais le **seuil sur la grille** est un exercice du **TP 2**, pas d'aujourd'hui |
| Les objets des séances 2, 3, 4 dans `translog-b` | ✅ *a priori* — c'est précisément ce que l'exercice 1 va **prouver**, objet par objet |

**Rien ne bloque.** La page S5 du bureau du RSSI de Miguel (`fixes.md` F12) est une note individuelle : elle ne conditionne pas ce TP.

**Deux gestes en attente qui se ferment bien pendant que l'instance est ouverte** — voir §7 : le marquage du **Top 5** dans la liste des actifs (`fixes.md` **F3**) et la recapture de la liste d'actifs pour `Session-2/3-Evidence/`.

**Compte de connexion** : compte **nominatif**, jamais `admin@lockbay.eu`. Tous les objets créés aujourd'hui — une étude, six événements redoutés, cinq couples — porteront un auteur nommé : c'est la moitié du coefficient individuel, et c'est aussi ce qui permettra de dire en soutenance qui a saisi quoi. **Se répartir la saisie entre Miguel et Maxime et le noter dans la feuille de travail.**

---

## 1. Exercice 1 — L'inventaire de l'existant (10 min)

*Prouver que le socle est là **avant** d'entrer quoi que ce soit. Relever pour chaque objet le **nom exact observé à l'écran**, pas le nom qu'on croit lui avoir donné.*

| # | Objet attendu (énoncé) | Où le chercher dans l'outil | Nom attendu au dossier | Présent ? | Nom exact observé |
|---|---|---|---|---|---|
| 1a | Le **domaine** de la filiale sous revue, créé en séance 2 | `Organisation` → `Domains` | `MERIDIAN-LOGISTIQUE` — *Parent domain* = `Global` | à relever | |
| 1b | Le **second domaine**, celui qui porte l'autre bout de la dépendance inter-filiales du §6 | `Organisation` → `Domains` | `MERIDIAN-SANTE` | ⚠️ **probablement absent** — voir encadré | |
| 1c | Le **périmètre** associé à la filiale | `Organisation` → `Perimeters` | `MERIDIAN-LOGISTIQUE-FINAL`, dans le sous-domaine ci-dessus | à relever | |
| 2 | Les **actifs de la séance 2** : valeurs métier et biens supports, dépendance §6 comprise | `Organisation` → `Assets` | **17 actifs** : 4 primaires (`LOG-PA-01` à `04`) + 13 supports (`LOG-SA-01` à `13`), dont `SA-02`, `SA-12`, `SA-13` qui portent le flux vers Santé | à relever | |
| 3a | Le **référentiel** importé en séance 3 | `Catalog` → `Frameworks` | ISO/IEC 27001:2022 — **123 exigences**, 93 contrôles d'annexe A en 37/8/14/34 | à relever | |
| 3b | L'**évaluation de conformité** créée avec lui, **remplie** en séance 4 | `Compliance` → `Audits` | `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, statut *In progress*, 12 exigences renseignées | à relever | |
| 4 | Le **module EBIOS RM** | menu `Risk` → `EBIOS RM` → page `EBIOS RM studies` | **liste vide** — c'est l'état attendu avant aujourd'hui | à relever | |

> ⚠️ **Le domaine `MERIDIAN-SANTE` n'a jamais été créé dans `translog-b`.** Le groupe n'a instancié que le sous-domaine de sa filiale d'instruction ; l'autre bout de la dépendance du §6 vit dans le dossier (D2, §« dépendance inter-filiales ») et dans les biens supports `SA-02` / `SA-12` / `SA-13`, qui sont **chez nous**, mais pas comme domaine.
> **Ne pas le créer en réaction.** L'énoncé est explicite : *« si un objet manque, ne le recréez pas silencieusement : notez-le, signalez-le, et continuez le TP avec ce qui existe. Un manque dans l'outil est une information de gouvernance, pas un obstacle personnel. »* Le porter tel quel dans la feuille de travail, et en tirer la phrase qui va dans D5 : l'étude porte sur un flux inter-filiales dont **un seul bout est modélisé**, ce qui est exactement la limite que la séance 6 (atelier 3, écosystème) aura à lever.

**À produire** : la table ci-dessus remplie, colonnes « Présent ? » et « Nom exact observé » — c'est la table à quatre lignes que demande l'énoncé, ici détaillée en sept parce que la ligne 1 en porte trois objets distincts.

**Capture** : `S5-05-ex1-inventaire-domaines-perimetres.png`, `S5-05-ex1-inventaire-17-actifs.png`, `S5-05-ex1-ebios-rm-studies-liste-vide.png`.

---

## 2. Exercice 2 — Importer la matrice de risque (10 min)

**Pourquoi c'est bloquant** : l'outil **refuse** de créer une étude EBIOS RM sans matrice de risque. Coter sans échelle ne veut rien dire, et sur ce point l'outil est plus strict que beaucoup d'organisations. C'est la première phrase à écrire dans la feuille de travail.

**Geste** : `Catalog` → `Libraries` → recherche `EBIOS` → importer **« 4x4 risk matrix from EBIOS-RM »** *(libellé de l'énoncé ; le TP 2 la désigne « Matrice 4x4 EBIOS-RM » — relever le libellé réel à l'écran et noter la différence, ne rien renommer)*.

Puis **ouvrir la matrice et la regarder vraiment** — c'est l'échelle de tout le reste du module :

| Axe | Attendu | À relever |
|---|---|---|
| Vraisemblance | 4 niveaux, **V1 « Peu vraisemblable »** → **V4 « Certain »** | |
| Conséquence | 4 niveaux, **G1 « Mineure »** → **G4 « Critique »** | |
| Croisement | 3 niveaux de risque : **Faible / Moyen / Élevé** | |

> **Le mot que l'outil a choisi** : « **Conséquence** », là où le guide et le TD disent « **gravité** ». Même concept, vocabulaire dédoublé — et c'est un excellent rappel : l'**ISO 27005 parle de conséquences** là où **EBIOS RM parle d'événements redoutés et de gravité**. À écrire dans la feuille de travail, c'est un point de méthode gratuit.

**À produire — trois phrases** (l'énoncé les demande explicitement) :

1. **Quelle case porte le risque le plus élevé** → attendu : le croisement **V4 × G4**, coin de la grille.
2. **De quelle couleur est la diagonale** → à relever à l'écran, et dire ce que cela signifie : la diagonale porte le passage du tolérable à l'inacceptable, c'est sur elle que le **seuil d'acceptation du TP 2** viendra se poser.
3. **Les libellés sont-ils exactement ceux de l'échelle d'exemple du guide vue au TD ?** L'énoncé prévient : *« regardez de près les niveaux V4 et G3 avant de répondre »*. Réponse attendue : **non, pas exactement** — le guide gradue jusqu'à « quasi-certain » là où l'outil écrit **« Certain »**, et le TD dit **« grave »** là où l'outil écrit **« Important »**. Ce ne sont pas les mêmes mots, c'est la même échelle.

> ✅ **Ceci ferme une réserve ouverte au TD 2** (F12). Le TD 2 annonçait la correspondance *mineure / significative / grave / critique* → *Minor / Significant / Important / Critical* comme **présumée, à vérifier à l'import de la matrice au TP 1**. L'énoncé du TP la confirme mot pour mot à l'exercice 4 : `mineure = Minor`, `significative = Significant`, `grave = Important`, `critique = Critical`. **Constater à l'écran, puis retirer le mot « présumée » du TD 2 et de D5.**

**Capture** : `S5-05-ex2-matrice-4x4-importee.png` (la grille complète, axes lisibles).

---

## 3. Exercice 3 — Créer l'étude et poser le cadrage — atelier 1, activités 1, 2 et 4 (15 min)

**Geste** : menu `Risk` → `EBIOS RM` → bouton **+** en haut à droite de la liste.

### 3.1 Les quatre champs de création

| Champ | Valeur à saisir | Pourquoi |
|---|---|---|
| **Nom** | `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1` | Convention imposée : *« Étude EBIOS RM MERIDIAN - [filiale sous revue] et [dépendance du §6] - cycle 1 »*. Les exemples de l'énoncé (« Santé et approvisionnement d'urgence », « Territoires et annuaire commun du pôle ») donnent le format du titre court de la dépendance — le nôtre est le **réapprovisionnement d'urgence de Logistique vers Santé** (D2, §6 du pack) |
| **Domaine** | `MERIDIAN-LOGISTIQUE` | **Jamais le domaine racine.** L'énoncé le dit, et `fixes.md` porte déjà la trace d'une confusion domaine/périmètre corrigée en séance 4 : le domaine est `MERIDIAN-LOGISTIQUE`, enfant de `Global` ; le périmètre `MERIDIAN-LOGISTIQUE-FINAL` est autre chose |
| **Matrice de risque** | celle importée à l'exercice 2 | C'est **le geste qui attache l'étude à une échelle** — sans lui, pas d'étude |
| **Méthode de cotation** | **`Manual`** — surtout pas `Express` | La séance 7 saisira **à la main** la vraisemblance de chaque scénario opérationnel. En `Express`, l'outil la **recalcule** depuis les modes opératoires et **écrase la saisie**. Choix irréversible en pratique : le poser juste maintenant |

Une fois l'étude créée, sa page affiche les **cinq ateliers et leurs activités**. Les trois activités du jour sont dans l'**atelier 1**.

### 3.2 Activité 1 — « Définir le cadre de l'étude » : la description

*À coller dans le champ description de l'activité 1. Un lecteur qui ouvre l'étude dans six mois doit y trouver le cadrage **sans aller chercher le compte rendu du TD**.*

> **Objectif de l'étude** — Apprécier et traiter les risques numériques pesant sur MERIDIAN Logistique et sur son flux d'approvisionnement d'urgence vers MERIDIAN Santé — premier cycle d'une démarche de groupe — pour éclairer les décisions de traitement de la Direction Générale et matérialiser sur la grille le seuil d'acceptation dérivé de l'appétence fixée au bureau du RSSI.
>
> **Finalité retenue** — étude complète des scénarios de risque (les cinq ateliers, sur les deux cycles), en vue du traitement et du pilotage. Ce n'est ni un socle seul (atelier 1 isolé), ni une homologation : le cadrage d'homologation du WMS produit en séance 4 en est un sous-ensemble, pas l'objet.
>
> **Participants et rôles** — Responsable Exploitation de Logistique, en appui du Responsable Qualité et chaîne du froid (**métier** : ce que valent les flux des six entrepôts et la chaîne du froid) ; DSI de la filiale, 3 personnes, sans titre de RSSI (**SI** : ce que le SI permet — angle mort acté : ni l'OT, ni la télématique, ni la box 4G de l'intégrateur) ; RSSI Groupe, le groupe de travail (**cyber** : état de la menace, couverture partielle du SOC, constats gradés de l'audit de séance 4) ; Directrice Générale du groupe, représentée en séance par le Directeur de la filiale Logistique pour ce qui engage la filiale (**décision**).
>
> **Responsable de l'acceptation des risques résiduels** — la **Direction Générale du groupe**. La gouvernance de la séance 1 en fait la seule instance qui fixe l'appétence (le Conseil d'Administration l'approuve, le RSSI Groupe la propose sans la fixer) ; accepter le risque résiduel en est la face opérationnelle.
>
> **Cycles** — cycle **stratégique : 3 ans** (l'étude entière et les scénarios stratégiques) ; cycle **opérationnel : 1 an** (les scénarios opérationnels, revus à la lumière des incidents, des vulnérabilités nouvelles et de l'évolution des modes opératoires). Référence : recommandation du guide EBIOS RM pour l'homologation de sécurité, citée au CM de la séance 5.

### 3.3 Activité 2 — « Définir le périmètre métier et technique » : relier, ne rien créer

Sur la page de l'activité 2, le bouton **« sélectionner un actif »** ouvre la liste des actifs existants. **Cocher les 17 actifs de la séance 2**, dépendance inter-filiales comprise :

| Valeurs métier (actifs primaires) | Biens supports (actifs supports) |
|---|---|
| `LOG-PA-01` Exécution des flux logistiques · `LOG-PA-02` Maintien de la chaîne du froid · `LOG-PA-03` Savoir-faire opérationnel des six entrepôts · `LOG-PA-04` Conformité contractuelle avec le client pharmaceutique | `SA-01` WMS · `SA-02` scannettes · `SA-03` automates de tri · `SA-04` compte de service WMS↔automates · `SA-05` logiciel des sondes · `SA-06` local serveur E1 · `SA-07` entrepôts E1–E6 · `SA-08` chambres froides et remorques · `SA-09` Responsable Exploitation · `SA-10` TMA du WMS · `SA-11` Responsable Qualité · `SA-12` VLAN + pare-feu d'inspection · `SA-13` interface d'approvisionnement d'urgence |

> ⛔ **Le bouton voisin « ajouter un actif » est à laisser tranquille** : il en créerait un nouveau. *Ne rien créer, ne rien renommer, relier.* C'est le premier critère d'acceptation de D5 (« valeurs métier et biens supports **identiques** à ceux de la cartographie de la séance 2 »), et il se joue ici, pas au TP 2.

### 3.4 Activité 4 — « Déterminer le socle de sécurité » : ancrer

Rattacher à l'étude l'**audit de la séance 4** — l'évaluation de conformité `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`. L'outil en **dérive** le socle et ses écarts. La table à quatre colonnes du TD 2 (PSSI-cadre, guide d'hygiène ANSSI, ISO/IEC 27001:2022, obligations contractuelles du client) **reste la référence écrite** — l'outil ne connaît que la ligne ISO — et ses écarts retenus deviennent des données d'entrée de l'étude.

*Rappel à porter dans la feuille de travail* : la **décision de poursuite** prise au TD 2 — *poursuivre l'appréciation en intégrant la non-conformité*, plutôt que suspendre et renforcer le socle d'abord — n'a pas de champ dans l'outil. Elle vit dans D5, section 2.

**À produire** : l'étude créée et visible dans la liste des études du domaine, cadrage dans la description, actifs reliés, audit rattaché ; la carte **« Summary »** de la page d'étude affiche les compteurs **Assets** et **Audits**.

**Captures** : `S5-05-ex3-etude-creee-parametres.png` (nom, domaine, matrice, méthode `Manual`), `S5-05-ex3-activite1-cadrage.png`, `S5-05-ex3-activite2-17-actifs-lies.png`, `S5-05-ex3-summary-compteurs.png`.

---

## 4. Exercice 4 — Les six événements redoutés — atelier 1, activité 3 (20 min)

**Geste** : page de l'étude → atelier 1 → activité 3 **« Identifier les événements redoutés »** → bouton **+** de la liste, **une ligne du TD 2 à la fois**.

Champs du formulaire : `ID`, `Name`, `Description`, `Gravity`, `Justification`, `Assets`, `Qualifications`, case **`Selected`**.

**Correspondance de gravité, confirmée par l'énoncé** : `mineure = Minor` · `significative = Significant` · **`grave = Important`** · `critique = Critical`.
**Qualifications** : `Availability` (disponibilité), `Integrity` (intégrité), `Confidentiality` (confidentialité), **`Proof`** — c'est le mot de l'outil pour la **traçabilité**, qu'il n'emploie pas.

| ID | Nom (valeur métier atteinte + besoin touché) | Actif à lier | Qualification | Gravity | Justification (champ `Justification`) | Selected |
|---|---|---|---|---|---|---|
| **ER1** | Le flux d'expédition du groupe est interrompu — WMS ou liaison inter-entrepôts indisponible, les six entrepôts ne préparent plus | `LOG-PA-01` | `Availability` | **Critical** | Un arrêt > 6 h bloque 40 % du volume expédié du groupe ; pénalités contractuelles de 12 000 €/jour ; aggravation : la reprise n'est pas démontrée — sauvegardes quotidiennes jamais restaurées depuis la mise en service. **Seuil** : Critical à partir de 6 h d'interruption non planifiée ; en deçà, ou sur arrêt planifié hors pointe, Important | ✅ |
| **ER2** | Les données de préparation et de stock du WMS sont altérées — les entrepôts expédient des commandes fausses sans le savoir | `LOG-PA-01` | `Integrity` | **Important** | Erreurs d'expédition en cascade, y compris vers Santé ; vecteurs : mise à jour TMA de nuit non contrôlée, compte de service en clair ; partiellement détectable et rattrapable, pas de risque vital direct | ✅ |
| **ER3** | La chaîne du froid est rompue ou ses relevés sont faussés sur un entrepôt pharma (E1/E4) | `LOG-PA-02` | `Availability` + `Integrity` | **Critical** | Manquement direct aux engagements du client pharmaceutique et à l'audit annuel de chaîne du froid ; **personnes** : risque sanitaire pour le patient final ; image | ✅ |
| **ER4** | La filiale ne peut pas produire la preuve de qui accède aux relevés de température et aux systèmes, à l'audit annuel ou au questionnaire de sécurité du client | `LOG-PA-04` | **`Proof`** | **Important** | Échec probable de l'audit / du questionnaire annoncé → risque de perte du contrat ; compte de la TMA partagé, porteurs inconnus, aucun journal nominatif — le Responsable Qualité « ne pourra pas répondre » | ✅ |
| **ER5** | Le réapprovisionnement d'urgence de la pharmacie hospitalière de MERIDIAN Santé n'est plus assuré — flux scannettes → interface → VLAN indisponible, il l'est déjà depuis trois mois | ⚠️ voir encadré | `Availability` | **Critical** | **Personnes** : réapprovisionnement d'urgence d'établissements de soin ; missions inter-filiales ; le Pharmacien chef de Santé : « on gère avec des commandes manuelles, ça ne tiendra pas l'hiver » | ✅ |
| **ER6** | Les données de température et d'expédition du client pharmaceutique sont divulguées — accès non maîtrisé chez un fournisseur hors supervision | `LOG-PA-02` | `Confidentiality` | **Significant** | Violation d'une clause de confidentialité client ; image ; pas de donnée de santé nominative directe — la confidentialité n'est jamais notée « très important » dans D2 | ✅ |

> ⚠️ **ER5 — la seule vraie friction de l'exercice, à décider avant de saisir.** L'outil rappelle sous le champ qu'un événement redouté **se rattache à une valeur métier, jamais à un bien support**. Or la valeur métier « réapprovisionnement d'urgence » **appartient à MERIDIAN Santé** (D2, §6) : elle n'existe pas comme actif primaire dans `translog-b`, seuls ses biens supports (`SA-02`, `SA-12`, `SA-13`) sont chez nous.
> **Décision recommandée** : rattacher ER5 à **`LOG-PA-01`** — les trois biens supports du flux y sont rattachés dans D2 — et **écrire dans la description** que la valeur métier réellement atteinte est propriété de Santé, non modélisée dans notre domaine. **Ne pas créer une cinquième valeur métier** pour l'occasion : ce serait recréer un objet de cartographie hors séance 2, exactement ce que la règle du jour interdit.
> C'est le même manque que la ligne 1b de l'exercice 1, vu de l'autre bout : à signaler dans la feuille de travail, à porter dans D5, et à lever en séance 6 quand l'atelier 3 ouvrira l'écosystème.

> **ER7 — le septième événement redouté, à ne pas saisir aujourd'hui.** Le TD 2 recommande d'ajouter à D5 un événement pour `LOG-PA-03` (« la connaissance opérationnelle des six entrepôts est perdue », `Proof`, gravité *grave*), la valeur métier laissée de côté par la table de départ. **Le critère de validation de l'énoncé est explicite : le compteur « Feared events » doit afficher 6.** Saisir les six, terminer le TP, puis **arbitrer au TP 2** : si D5 adopte ER7, l'ajouter dans l'outil dans la foulée, recapturer, et écrire la raison de l'écart de compteur. L'ordre inverse fait rater le critère.

**À produire** : six événements redoutés dans la liste de l'activité 3, chacun avec son actif, sa qualification, sa gravité et sa justification ; compteur **« Feared events » = 6**.

**Captures** : `S5-05-ex4-6-evenements-redoutes-liste.png`, `S5-05-ex4-ER1-detail.png` (une fiche ouverte, tous champs remplis, pour prouver la profondeur de saisie).

---

## 5. Exercice 5 — Les cinq couples SR/OV — atelier 2 (25 min)

**Geste** : page de l'étude → atelier 2 → activité 1 **« Identifier les sources de risque et les objectifs visés »** → bouton **+**, **un couple candidat du TD 2 à la fois, cinq en tout**. Le formulaire est découpé selon les **trois activités** de l'atelier — c'est exactement l'ordre de l'exercice 4 du TD.

### 5.1 Activité 1 — Identifier : la source et l'objectif

Catégories de l'outil : `State`, `Organized crime`, `Terrorist`, `Activist`, `Competitor`, `Amateur`, `Avenger`, `Pathological`, `Other`.
Deux correspondances données par l'énoncé : **le cybercriminel se saisit en `Organized crime`** ; **l'employé ou le prestataire malveillant en `Avenger`**, catégorie du guide pour l'initié.

| # | Source de risque (TD 2) | Catégorie outil | Objectif visé — formulé en **résultat obtenu aux dépens du groupe** |
|---|---|---|---|
| **1** | Cybercriminel | `Organized crime` | Chiffrer le WMS et sa base, arrêter le flux d'expédition du groupe et obtenir une rançon sous menace d'arrêt prolongé |
| **2** | Attaquant passant par l'intégrateur des automates | `Other` ⚠️ | Atteindre le réseau industriel et les automates via la box 4G non supervisée, et prendre la main sur les réglages |
| **3** | Initié de l'Exploitation, mécontent ou partant | `Avenger` | Altérer les données de préparation et de stock via le compte de service en clair connu de tous, et emporter le savoir-faire opérationnel non écrit |
| **4** | Concurrent | `Competitor` | Obtenir les données d'exploitation et les données du client pharmaceutique (volumes, tournées, relevés) pour capter le marché |
| **5** | Militant / hacktiviste | `Activist` | Interrompre publiquement l'activité d'un entrepôt ou exposer une défaillance de la chaîne du froid pour nuire à l'image du groupe et de son client |

> ⚠️ **Couple 2 — `Other` et non `Avenger`, et le dire.** L'énoncé range « le prestataire malveillant » en `Avenger`. Notre couple 2 n'est pas l'intégrateur qui se venge : c'est un attaquant qui **passe par** l'intégrateur — compromission de la chaîne d'approvisionnement. `Other` est la catégorie juste, avec une phrase de justification dans le champ prévu. **Différence à noter dans la feuille de travail** : c'est le réflexe que l'énoncé demande quand l'outil et le cas ne se recouvrent pas exactement.

> **Piège rappelé par le TD** : l'objectif visé est un **résultat**, jamais la motivation. *« Se faire de l'argent »* n'est pas un objectif visé — c'est ce qui pousse la source.

### 5.2 Activité 2 — Évaluer : motivation, ressources, activité

Échelles de l'outil : **motivation** (`Very low`, `Low`, `Significant`, `Strong`) · **ressources** (`Limited`, `Significant`, `Important`, `Unlimited`) · **niveau d'activité** (`Very low`, `Low`, `Moderate`, `Important`).
Correspondance donnée par l'énoncé avec les trois positions du TD : `bas = Low / Limited` · `moyen = Significant / Moderate` · `haut = Strong / Important`.

| # | TD 2 (bas/moyen/haut) | Motivation | Ressources | Activité | Justification de l'activité (champ `Justification`) — **l'observable** |
|---|---|---|---|---|---|
| **1** | haute / hautes / haute | `Strong` | `Important` | `Important` | 128 compromissions par rançongiciel portées à la connaissance de l'ANSSI en 2025 ; secteur logistique/santé régulièrement ciblé (Centre Hospitalier Sud Francilien, 2022, LockBit) |
| **2** | moyenne / hautes / moyenne | `Significant` | `Important` | `Moderate` | Contrat sans clause de réversibilité ni exigence de sécurité ; l'intégrateur qualifie déjà les réglages de « propriété industrielle » (position écrite, pack §3) ; box 4G hors réseau supervisé |
| **3** | moyenne / moyennes / basse à moyenne | `Significant` | `Significant` | `Low` ⚠️ | Aucun incident interne connu à ce jour — d'où `Low` sur l'**observé** ; mais aucune procédure de départ et un accès trivial (secret en clair connu de toute l'Exploitation), ce qui justifie de retenir le couple malgré une activité basse |
| **4** | basse à moyenne / moyennes / basse | `Low` ⚠️ | `Significant` | `Low` | Aucun signal d'espionnage concurrentiel observé ; données dispersées, aucune tentative constatée ; risque juridique dissuasif |
| **5** | basse / basses à moyennes / basse | `Low` | `Limited` ⚠️ | `Low` | Aucune campagne ni revendication visant la filiale ou son client ; surface technique exposée mais pas de ciblage observé |

> ⚠️ **Les trois « à cheval » du TD 2 doivent devenir une valeur unique** : l'outil n'accepte pas « basse à moyenne ». **Trancher vers le bas et justifier** — c'est le choix honnête, parce que ces trois positions sont basses **sur l'observé** et que c'est l'observable qui fonde la note. Écrire ce parti pris une fois dans la feuille de travail plutôt que trois fois dans l'outil.

### 5.3 Activité 3 — Sélectionner, et relier aux événements redoutés

**Cocher `Selected` sur les couples 1, 3 et 4. Laisser 2 et 5 décochés.** Puis **relier chaque couple — sélectionné ou non — aux événements redoutés qu'il vise** :

| # | `Selected` | Événements redoutés à relier | Motif (une phrase, pour D5) |
|---|---|---|---|
| **1** | ✅ | **ER1**, **ER2** | Pertinence la plus élevée, l'événement le plus grave de la filiale, menace de référence du secteur |
| **2** | ⬜ | **ER1** | Redouble `LOG-PA-01` déjà porté par le couple 1 ; sa finalité relève d'un risque de dépendance qui se traite au contrat et sera repris comme **partie prenante critique de l'écosystème en séance 6, atelier 3** — c'est sa juste place méthodologique |
| **3** | ✅ | **ER2** | Catégorie d'origine distincte (initié), seul couple atteignant `LOG-PA-03`, jeu d'événements différent du couple 1 |
| **4** | ✅ | **ER4**, **ER6** | Seul couple atteignant `LOG-PA-04` et la confidentialité — sans lui, toute la moitié « confiance / conformité contractuelle » du métier resterait sans adversaire |
| **5** | ⬜ | **ER3** | Le plus bas sur les trois critères, aucune activité observable ; conservé en veille pour sa cible symbolique — et c'est **le seul rattachement qui donne une origine à ER3** |

> **Ce que le geste « relier même les couples non retenus » fait apparaître.** Deux des événements les plus graves du dossier — **ER3** (chaîne du froid) et **ER5** (réapprovisionnement Santé) — n'ont **aucune source de risque *retenue***. Le lien du couple 5 vers ER3 rend la première moitié du trou visible dans l'outil ; **ER5 reste sans aucune origine**, et c'est exact : c'est d'abord un risque d'origine **accidentelle** (défaillance du fournisseur, panne d'une liaison opérateur, blocage inter-filiales non résolu), mieux couvert par l'approche conformité que par les scénarios. **Le signaler, ne pas forcer la sélection pour boucher le trou** ; la recommandation du TD 2 — ajouter un couple « attaquant pivotant Logistique → Santé » avant l'atelier 3 — va dans D5 et dans la séance 6.

### 5.4 La colonne `Pertinence` — la lire, ne pas lui obéir

L'outil calcule seul la pertinence en croisant **motivation × ressources**, sur quatre niveaux, d'`Irrelevant` à `Highly relevant`. Elle peut **différer d'un cran** de la pertinence du TD, **parce que l'activité n'entre pas dans son calcul**.

**Attendu chez nous** : le couple **4** (motivation `Low` × ressources `Significant`) affichera une pertinence basse alors qu'il est **retenu** — c'est le cas prévu par le TD 2 (« malgré une pertinence modérée »), et la raison de le retenir est ailleurs : il est le **seul** à couvrir `LOG-PA-04` et la confidentialité.

> **Relever l'écart dans la feuille de travail, et ne pas changer la sélection pour faire plaisir à la colonne. La justification écrite prévaut sur le calcul de l'outil** — l'énoncé le dit mot pour mot.

**À produire** : cinq couples dans la liste de l'atelier 2, **trois sélectionnés**, chacun relié à au moins un événement redouté ; compteur **« RO/TO pairs » = 5**.

**Captures** : `S5-05-ex5-5-couples-liste-pertinence.png` (la colonne `Pertinence` doit être lisible), `S5-05-ex5-couple1-detail-evaluation.png`, `S5-05-ex5-couple4-pertinence-vs-selection.png`.

---

## 6. Ce qui n'est **pas** fait aujourd'hui, et pourquoi — à écrire dans la feuille de travail

Les **ateliers 3, 4 et 5 restent vides**. Ce n'est pas un oubli, c'est la méthode :

- **atelier 3** (scénarios stratégiques) et **atelier 4** (scénarios opérationnels et leur vraisemblance) : **séance 6** — c'est là que l'écosystème, les prestataires et les projets entrent, et que le couple 2 (intégrateur) retrouve sa place ;
- **atelier 5** (traitement) : **séance 7**, dont la première activité, *« Générer l'appréciation des risques »*, **créera le registre à partir de l'étude** ;
- **rien ne sera recopié** d'une séance à l'autre : c'est la même étude qui se remplit.

> *« Un atelier vide parce que la méthode n'y est pas encore est un état normal ; un atelier rempli d'objets improvisés est pire qu'un atelier vide, parce qu'il a l'air fini. »*

**Capture** : `S5-05-ateliers-3-4-5-vides.png` — la page d'étude montrant les cinq ateliers, les deux premiers remplis, les trois suivants vides. C'est une **preuve de méthode**, pas un aveu.

---

## 7. Pendant que l'instance est ouverte — deux gestes en attente (F3)

| Geste | Détail | Pourquoi maintenant |
|---|---|---|
| **Marquer le Top 5 des actifs** | `SA-01`, `SA-04`, `SA-09`, `SA-05`, `SA-03` repérables **sans lire le fichier** D2 — préfixe dans le libellé, étiquette, ou champ dédié selon ce que la version offre | `fixes.md` **F3**, ouvert depuis le 8 septembre. D2 affirme « instance *et* dossier » : 5 points en dépendent |
| **Recapturer la liste d'actifs** | remplacer/compléter `Session-2/3-Evidence/S2-05-assets-list-page1-of-2.jpg` et `page2-of-2.jpg` | La capture actuelle est antérieure au marquage ; elle ne prouve pas ce que D2 affirme |

---

## 8. Ce qui sort de ce TP

| Sortie | Où | État |
|---|---|---|
| **Feuille de travail** `Seance-5-TP-S5-05-feuille-de-travail-saisie-EBIOS-RM.md` | `Session-5/2-Labs/` | à écrire pendant la saisie — table de l'exercice 1 remplie, les trois phrases de l'exercice 2, les écarts relevés (domaine `MERIDIAN-SANTE` absent, ER5 sans valeur métier propre, couple 2 en `Other`, pertinence du couple 4, positions « à cheval » tranchées), répartition nominative de la saisie |
| **Captures** `S5-05-*.png` | `Session-5/3-Evidence/` | ~11 captures listées ci-dessus |
| **Objets dans `translog-b`** | instance | 1 étude, cadrage, 17 actifs reliés, 1 audit rattaché, 6 événements redoutés, 5 couples SR/OV dont 3 retenus |
| **Réserve du TD 2 levée** | `Seance-5-TD-S5-03-…md` + D5 | retirer le mot « présumée » sur la correspondance des libellés de gravité, constatée à l'écran |
| **Entrées pour le TP 2** | D5 | la matrice importée porte l'échelle sur laquelle le TP 2 posera le **seuil d'acceptation** ; les signalements (ER5, ER7, couples secondaires) entrent en sections 3 et 4 de D5 |

**Fini quand** : les trois compteurs de la carte *Summary* disent la vérité — **Assets ≥ 17**, **Audits = 1**, **Feared events = 6**, **RO/TO pairs = 5** — et que chaque écart entre l'outil et le TD 2 est **écrit** quelque part plutôt que corrigé en douce.

---

## 9. Critères de validation de l'énoncé — la relecture avant de fermer

- [ ] Table d'inventaire produite, **nom exact observé** pour chaque objet ; l'objet manquant est **signalé, pas recréé**
- [ ] Matrice « 4x4 EBIOS-RM » importée depuis la bibliothèque, **trois phrases** écrites (case la plus élevée, couleur de la diagonale, écart de libellés sur V4 et G3)
- [ ] Étude créée **dans le domaine de la filiale**, jamais le domaine racine, avec la matrice et la méthode **`Manual`**
- [ ] Cadrage lisible **dans la description**, sans avoir à ouvrir le compte rendu du TD
- [ ] Les actifs sont **reliés**, pas recréés — aucun doublon dans `Assets`
- [ ] L'audit de la séance 4 est **rattaché** à l'étude
- [ ] **6** événements redoutés, chacun avec **actif primaire + qualification + gravité + justification**, tous `Selected`
- [ ] **5** couples SR/OV, **3** sélectionnés, **chacun** relié à au moins un événement redouté
- [ ] Écart de `Pertinence` relevé, **sélection inchangée**
- [ ] Ateliers 3, 4 et 5 **vides**, et la raison écrite
- [ ] Chaque objet créé porte un **auteur nommé**
