# Comprendre le dossier — la logique de bout en bout

**Module M2-01-4-ISMS** · *Gouvernance de la sécurité et cartographie du SI*
**Groupe 4 « Translog »** · Miguel Monereo, Maxime · filiale d'instruction **MERIDIAN Logistique**
**Instance** `translog-b` · **périmètre** `MERIDIAN-LOGISTIQUE` · **remise** 17 septembre 2026

---

## À quoi sert ce document, et ce qu'il n'est pas

Le dépôt contient déjà trois documents de pilotage, et ce n'en est pas un quatrième :

| Document | Répond à |
|---|---|
| `README.md` | **Où en est-on ?** — état d'avancement, ce qui reste, points en jeu |
| `G4-…/fixes.md` | **Qu'a-t-on corrigé ?** — journal des 23 corrections, F1 à F23 |
| `DELIVERABLE/questions.md` | **Que demande-t-on ?** — résumé fidèle des énoncés, séance par séance |
| **ce document** | **Pourquoi ?** — la logique qui relie tout : ce que chaque séance reçoit, décide, produit et transmet |

Il s'adresse à quelqu'un qui ouvre le dossier sans l'avoir construit : un correcteur, un binôme qui reprend
le travail, ou nous-mêmes dans deux semaines. Il ne remplace aucune pièce : il explique **pourquoi chaque
pièce existe** et **pourquoi elle est là plutôt qu'ailleurs**.

---

# 1. Le dispositif — comprendre les règles du jeu avant le jeu

## 1.1 Ce que le module demande vraiment

Dix séances, un cas, une méthode. Le module ne note pas des connaissances : il note **un dossier de
gouvernance cohérent**, produit par accumulation, séance après séance. La source de vérité unique est
`ISMS module common thread.pdf` (version 2, 8 septembre 2026) — tout le reste du dépôt en découle.

La fiction est la suivante : MERIDIAN est un groupe de services de **7 700 salariés** en quatre filiales —
Santé (3 200), Logistique (2 800), Éducation (900), Territoires (650) — plus un holding de 150 personnes.
Chaque groupe de travail tient le rôle du RSSI d'une filiale ; le RSSI Groupe est joué par l'enseignant.
**Deux groupes travaillent sur la même filiale à partir des mêmes données** — ce qui dit l'essentiel de la
notation : *il n'y a pas de bonne réponse unique, seulement des décisions argumentées et traçables, ou pas.*

Nous sommes le groupe 4, sur **MERIDIAN Logistique**.

> **Une subtilité de cadrage à ne pas rater.** La séance 1 se joue **au niveau du groupe** : `D1` est une
> note de cadrage émise par le *RSSI Groupe* à destination des instances du groupe, et son périmètre couvre
> les quatre filiales. À partir de la séance 2, le dossier se resserre sur **Logistique** et n'en sort plus.
> Ce n'est pas une incohérence : on pose d'abord la gouvernance qui arbitre, ensuite on descend sur le
> terrain qu'elle gouverne.

## 1.2 Trois pièces, et pourquoi trois plutôt qu'une

| Pièce | Ce que c'est | Pourquoi elle existe séparément |
|---|---|---|
| **Pièce 1** — la note de stratégie | Un PDF, 9 sous-sections (une par séance), 3 à 5 pages de texte | C'est **le document qu'un directeur général lit**. Il n'a ni le temps ni le besoin d'ouvrir le dossier technique |
| **Pièce 2** — le dossier | 9 séances séparées, forme et langue libres | C'est **ce que l'auditeur vérifie**. Il veut la pièce derrière l'affirmation |
| **Pièce 3** — la preuve d'état | Export daté de l'instance CISO Assistant, produit en séance 10 | C'est **ce qui prouve que l'objet existe vraiment** ailleurs que dans un document Word |

Trois pièces parce qu'il y a **trois lecteurs**, et le fil rouge le dit en toutes lettres : *la direction qui
décide, l'auditeur qui vérifie, le successeur qui reprend.* Un seul document ne peut pas servir les trois
sans trahir au moins deux d'entre eux.

## 1.3 La règle qui gouverne absolument tout

> **La sous-section *n* de la note affirme ; la séance *n* du dossier prouve ; l'export montre que l'objet
> existe dans l'outil.**
>
> Une affirmation sans pièce derrière elle ne compte pas. Une pièce dont la note ne dit rien est du travail
> perdu.

Cette phrase est citée en tête du `README.md`, de `fixes.md` et de la note de stratégie. Ce n'est pas une
formule : c'est **le critère de correction déguisé en principe**, et il explique presque toutes les
décisions d'organisation du dépôt.

Deux conséquences pratiques qu'on retrouve partout :

1. **Chaque sous-section de la note porte, en annexe, le renvoi vers les pièces qui la prouvent.** L'annexe
   ne compte pas au budget de pages — c'est exactement pour cela qu'elle a été créée (correction **F18**).
2. **Toute affirmation non prouvée est un écart, même si elle est vraie.** C'est ce qu'a trouvé la relecture
   **F20** : la sous-section 1 renvoyait à une « charte de gouvernance » que `D1` ne contenait pas. La
   charte a été écrite, pas l'affirmation supprimée.

## 1.4 La seconde règle : rien ne se réinvente

Le fil rouge l'écrit : *« la cartographie de la séance 2 alimente l'audit de la séance 4, qui alimente
l'analyse de risque, qui alimente la déclaration d'applicabilité. »*

C'est la contrainte la plus structurante du module, et celle qui fait la différence entre un dossier qui
tient et neuf devoirs juxtaposés. Elle est vérifiable : à chaque séance, on peut demander *« d'où vient cet
objet ? »* et la réponse doit être un objet d'une séance antérieure, pas une invention du jour.

## 1.5 Comment tout cela est noté

| Composante | Format | Portée | Coef. |
|---|---|---|---|
| **Bureau du RSSI**, écrit | 1 page par séance, S1 à S9 · 10 pts | **Individuel** | 1 |
| **Quiz**, neuf | 13-15 questions, 45 min · chacun coef. 2/9 | **Individuel** | 2 |
| **Livrables D1→D9 + note de stratégie** | 40 pts convertis sur 20 | Groupe, individualisé | **4** |
| **Soutenance finale** | 18 min + 12 min de questions · 30 pts | Groupe, individualisé | **3** |

Note du module = (1 × bureau + 2 × quiz + 4 × livrables + 3 × soutenance) / 10.

**Le coefficient individuel** (0,85 / 0,95 / 1,05 / 1,15) module la part collective. Il repose sur deux
éléments de poids égal : **la traçabilité nominative dans l'outil** — chaque objet créé porte un auteur — et
**la question individuelle en soutenance**. Les coefficients d'un groupe font 1 en moyenne : *ce qu'un
étudiant gagne, l'autre le perd.* C'est pourquoi le dépôt insiste autant sur les auteurs nommés (correction
**F5**) et sur des pages du bureau du RSSI **à angles distincts** entre les deux binômes (**F7**).

Le barème des livrables, qui explique pourquoi certaines séances ont reçu plus d'effort que d'autres :

`D1` 4 · `D2` 5 · `D3` 4 · `D4` 4 · `D5` 3 · **`D6` 7** · `D7` 5 · `D8` 2 · `D9` 3 · note 3 = **40 points**.

---

# 2. Le cas — les faits têtus dont tout découle

Toute l'analyse du dossier repose sur une poignée de faits donnés dans le dossier de filiale. Ils reviennent
à chaque séance, et savoir les reconnaître suffit à comprendre 80 % des décisions prises.

| Le fait | Où il resurgit |
|---|---|
| Le **WMS** (logiciel de gestion d'entrepôt) est centralisé sur **un seul site**, E1, sans secours | `D2` rang 1 du Top 5 · `D5` événement le plus grave · `D7` mesures · `D8` périmètre |
| Un arrêt du WMS de plus de **six heures bloque 40 % du volume expédié du groupe** | Partout — c'est le chiffre qui parle au ComEx |
| Les **sauvegardes n'ont jamais été restaurées** depuis la mise en service | `D2` lacune · `D5` vraisemblance · `D7` point ouvert « RTO réel » · `D9` `IND-03` |
| Le **compte de service WMS ↔ automates** a le **même mot de passe sur six entrepôts depuis 2019**, en clair dans un fichier | `D2` rang 2 · `D4` constat majeur · `D5` chemin d'attaque |
| Les réseaux **bureautique et industriel ne sont pas cloisonnés** ; l'intégrateur est raccordé par une **liaison 4G hors supervision** | `D2` rang 5 · `D4` constat `C3` · `D7` mesure `PT-03` · `D8` exclusion d'E4 |
| Le **SOC du groupe ne reçoit aucun journal** du WMS, des automates ni de la 4G | `D2` arbitrage DICT · `D6` bureau du RSSI de Miguel |
| Le **client pharmaceutique** impose des audits annuels et **12 000 €/jour** de pénalités d'arrêt | `D2` valeur métier `PA-04` · `D7` coût de l'inaction · `D8` périmètre de certification |
| Le **flux de réapprovisionnement d'urgence Logistique → Santé est bloqué depuis 3 mois** | `D1` enjeu de gouvernance · `D2` dépendance inter-filiales · `D6` fiche projet |
| Le **contrat de tierce maintenance du WMS** (APPLICA) n'offre ni réversibilité, ni droit d'audit, ni comptes nominatifs — et se **renouvelle en novembre 2026** | `D4` constat `C4` · `D6` exigences contractuelles · `D7` avenants |
| Le **savoir-faire des six entrepôts n'est écrit nulle part** — il tient dans une personne | `D2` rang 3 du Top 5 · `D5` scénario interne |

**Le fil rouge de tout le dossier tient en une phrase** : *des fondations documentées, une application non
prouvée, des angles morts nommés.* C'est la formule de la sous-section 4 de la note, et c'est le diagnostic
que la soutenance porte au comité.

---

# 3. L'anatomie d'une séance — pourquoi le dossier est rangé ainsi

Chaque séance suit le même rythme, et ce rythme explique la structure des dossiers.

| Moment | Ce qui s'y passe | Où ça atterrit dans le dossier |
|---|---|---|
| **CM** (matin) | Théorie, illustrée sur **TRAMONTANE**, une entreprise qui n'est jamais notre cas | *(non noté ; notes d'étude)* |
| **TD 1 — « Le bureau du RSSI »** | La question du jour, transposée à notre filiale. **Écrit, une page max, clos par une recommandation à la direction** | `Session-n/1-CISO-desk/` — la note collective `Sn-01` **et** une page par étudiant |
| **TD 2** | Exercice dirigé qui prépare la matière du TP | `Session-n/4-Working-notes/` — numéroté `Sn-03` |
| **TP 1** (après-midi) | Saisie dans **CISO Assistant**, l'outil GRC | `Session-n/2-Labs/` — `Sn-05` + captures dans `3-Evidence/` |
| **TP 2** | Rédaction du **livrable `Dn`** | `Session-n/2-Labs/` — `Sn-06` + le fichier `Dn-*.md` |
| **15 minutes de clôture** | La **sous-section *n*** de la note de stratégie | `Piece-1-Strategy-note/` |

> *« Les matins sont pour comprendre, les après-midi pour produire, et la notation porte sur ce qui a été
> produit. »*

**Quatre emplacements, une numérotation** — c'est une convention du dépôt, pas du module, et elle a dû être
imposée après coup : la séance 7 avait dérivé sur les deux points, corrigé le 14 septembre (**F14**).

Deux distinctions que le dépôt défend explicitement :

- **Un livrable ne se cache pas dans un compte rendu.** Il porte son nom `Dn-…`, il est autonome, il tient
  le format exigé ; le compte rendu de TP reste à côté comme trace de méthode. Cette règle a débloqué
  **13 points** à elle seule (**F10**) : les livrables existaient, mais enfouis dans des comptes rendus, donc
  invisibles pour un correcteur.
- **La note de stratégie est en français et ne mélange pas les langues.** Le dossier (pièce 2) peut être
  dans l'autre langue, la consigne l'autorise.

---

# 4. Les neuf séances — ce que chacune reçoit, décide, produit et transmet

C'est le cœur du document. Pour chaque séance : la question qu'elle pose, ce qu'elle hérite, la décision
qu'elle prend, et ce qu'elle passe à la suivante.

---

## Séance 1 · Gouvernance — *qui décide, et par quelle instance*

**Question du bureau du RSSI :** *De quoi un conseil d'administration a-t-il réellement besoin de la part de
son RSSI ?*

**Ce qu'elle reçoit :** rien. C'est le point de départ — un premier lundi de RSSI Groupe, aucune PSSI, trois
dossiers en souffrance sur le bureau : un conflit inter-filiales (flux Logistique↔Santé bloqué depuis
3 mois), une proposition de mutualisation de la supervision « parce que c'est le moins cher », et un
auditeur interne qui propose de **gérer** le registre qu'il devrait **contrôler**.

**Ce qu'elle décide :** une gouvernance à **trois niveaux** (stratégique / tactique / opérationnel), chaque
instance avec **sa fréquence** et la **nature de ses décisions** ; une **matrice RACI à un seul `A` par
ligne** ; **cinq directives codifiées** `PSSI-CADRE-*` ; **trois règles d'arbitrage** `ARB-01/02/03` ; et une
**charte** qui adopte le tout et le rend opposable.

**La logique sous-jacente**, et c'est ce qui distingue une bonne copie d'une liste d'organigrammes : chaque
élément de gouvernance est écrit **contre un dysfonctionnement nommé du cas**.

| L'élément | Ce qu'il empêche, concrètement |
|---|---|
| Comité sécurité groupe + `ARB-01` (veto suspensif, 72 h) | Que le flux Logistique↔Santé reste bloqué 3 mois faute d'arbitre |
| RACI, un seul `A` par ligne | Que l'auditeur reprenne la gestion du registre qu'il audite — *on n'audite pas son propre travail* |
| Fréquences inscrites | Qu'une instance existe sur le papier sans jamais se réunir |
| Chaque directive porte une **mesure de vérification** | Qu'une règle soit invérifiable — le *test du sceptique* : « comment saurait-on qu'elle n'est pas respectée ? » |
| `ARB-03` : toute dérogation validée sous 48 h | *Qu'une dérogation sans circuit devienne un droit acquis* |

**Ce qu'elle produit :** `D1` — note de cadrage et gouvernance cible (4 pts), deux pages.

**Ce qu'elle transmet :** l'autorité. Toutes les décisions ultérieures — le choix du référentiel, le seuil
d'acceptation du risque, la règle contractuelle sur les tiers — se réclament de cette gouvernance. La note
de stratégie le dit à chaque fois : *« c'est la gouvernance de la sous-section 1 qui parle ».*

> **Hors rendu, volontairement :** la feuille de route pluriannuelle chiffrée produite en séance 1 est
> conservée par le groupe mais **ne fait pas partie du rendu** — c'est le sujet du rattrapage (**F9**). La
> note de cadrage, elle, reste au dossier comme preuve de gouvernance.

---

## Séance 2 · Cartographie — *sur quoi cette gouvernance règne*

**Question du bureau du RSSI :** *Pourquoi tout inventaire d'actifs est-il faux, et qu'en fait-on ?*

**Ce qu'elle reçoit :** une gouvernance sans terrain. La sous-section 2 de la note l'écrit littéralement :
*« la gouvernance arrêtée en ouverture avait besoin de savoir sur quoi elle règne. »*

**Ce qu'elle décide :** la méthode **ANSSI / EBIOS RM** — et surtout la distinction qui structure tout le
reste du dossier :

- **Valeur métier** (*business asset*) : ce que la filiale perdrait. Test appliqué : *« la filiale
  pleurerait-elle sa disparition, ou seulement la DSI ? »* → **4 valeurs métier** (`LOG-PA-01` à `04`).
- **Bien support** (*supporting asset*) : ce qui la porte, et qui se protège, se remplace, se budgète →
  **13 biens supports** (`LOG-SA-01` à `13`), les trois natures couvertes (numérique, physique,
  **organisationnel**), **un propriétaire nommé pour chacun**.
- **Besoins DICT** (Disponibilité, Intégrité, Confidentialité, Traçabilité) sur une échelle à trois niveaux,
  **sans niveau intermédiaire inventé**.

Le WMS n'est **pas** une valeur métier : c'est un bien support. Cette discipline paraît scolaire ; elle est
ce qui permet, trois séances plus tard, de coter la gravité d'un événement en euros de métier plutôt qu'en
sévérité technique.

**Le Top 5 et sa règle d'or :** le critère de classement est **écrit avant le classement**, en quatre
conditions — (a) l'actif porte un besoin DICT *très important*, (b) son atteinte **déborde la filiale**,
(c) une faiblesse **connue et actuelle** rend l'atteinte plausible *aujourd'hui*, (d) **aucune substitution
rapide** n'existe. Écrire le critère après coup, c'est justifier un classement déjà fait ; l'écrire avant, on
peut être contredit sur le critère — et c'est précisément ce que la notation cherche.

Le classement porte sur les **biens supports**, pas les valeurs métier : celles-ci sont critiques par
construction, et un « top 5 » de quatre éléments ne classerait rien.

| Rang | Actif | Le fait qui le classe |
|---|---|---|
| 1 | `SA-01` **WMS** | 40 % du volume du groupe, reprise jamais démontrée, site unique |
| 2 | `SA-04` **Compte de service WMS ↔ automates** | Même mot de passe depuis 2019, en clair, connu de tous sur site |
| 3 | `SA-09` **Responsable Exploitation** | **Une personne** — seul bien support d'une valeur métier entière, savoir écrit nulle part |
| 4 | `SA-05` **Logiciel des sondes** | Le seul à porter **deux** valeurs métier : chaîne du froid **et** preuve d'audit |
| 5 | `SA-03` **Automates de tri** | IT/OT non cloisonnés, 4G hors supervision, aucun journal au SOC |

Les **deux enseignements** que la note porte au ComEx : un de **portée** (l'atteinte déborde la filiale) et
un de **nature** (l'un des cinq n'est ni un serveur ni un logiciel, mais une personne — *le seul actif
qu'aucun budget ne remplace après coup*).

**Six lacunes assumées**, et c'est délibéré : la première est *« aucun schéma réseau n'existe »*. Une
cartographie qui ne dit pas ce qu'elle ignore n'est pas honnête, et cette lacune précise **borne ce que la
filiale peut déclarer à un tiers** — on la retrouvera en séance 8 comme motif d'exclusion d'un entrepôt du
périmètre de certification.

**La règle de tenue**, qui est la gouvernance de S1 appliquée au terrain avec un délai vérifiable : *tout
élément découvert hors inventaire est rattaché à un propriétaire ou traité **sous trente jours**, et sa
découverte est **valorisée, jamais sanctionnée***.

**Ce qu'elle produit :** `D2` — cartographie (5 pts) · dans l'outil : **17 actifs** avec propriétaires, les
cinq du Top 5 marqués d'une étiquette `Top5` lisible sans ouvrir `D2` (**F3**).

**Ce qu'elle transmet :** la matière première de tout le reste. *« Ces cinq actifs sont ce que les risques
majeurs devront viser : une analyse de risque qui les ignorerait décrirait une autre entreprise que la
nôtre. »*

---

## Séance 3 · Référentiel — *dans quelle langue on va mesurer*

**Question du bureau du RSSI :** *Sommes-nous dans le champ de NIS 2, et à quel titre ?*

**Ce qu'elle reçoit :** une liste d'actifs critiques… et aucun moyen de dire s'ils sont protégés.

**Ce qu'elle décide :** **ISO/IEC 27001:2022** comme référentiel du groupe.

**La logique de la décision**, et c'est le passage le plus instructif du dossier. Trois options notées sur
300 :

| Option | Note | La vraie question |
|---|---|---|
| Guide d'hygiène ANSSI | 135 | Utilisable dès demain — mais aucune preuve au-delà d'une auto-déclaration |
| **ReCyF** | **205** | Le mieux placé sur l'obligation réglementaire — *c'est devant lui que NIS 2 se démontrera* |
| **ISO/IEC 27001:2022** | **230** | Le seul à couvrir les 4 filiales **et** à mener à une certification par tierce partie |

**Une règle de veto a été posée avant tout calcul** : est écarté, quelle que soit sa note, tout référentiel
ne couvrant pas simultanément les obligations de Santé, le périmètre industriel de Logistique et **une
filiale hors champ NIS 2**. Le ReCyF échoue à cette condition — *non par faiblesse, mais par destination.*

C'est le point à retenir : **ce n'est pas l'arithmétique qui décide.** La correction **F4** l'a démontré en
pratique — une erreur de fait sur le ReCyF a fait passer sa note de 195 à 205 et réduit l'écart de 35 à
25 points ; **la recommandation n'a pas bougé**, parce qu'elle tenait sur le veto, pas sur le score. Un
classement qui se renverse à 10 points près n'est pas une décision, c'est un calcul.

**La meilleure objection est écrite, pas esquivée** : *l'autorité nous contrôlera devant le ReCyF, pas devant
l'ISO.* Réponse assumée : le ReCyF est un texte de travail (v2.5, mars 2026) qu'on ne peut pas ériger en
colonne vertébrale d'un groupe de 7 550 salariés, il est muet sur une filiale sur quatre, et l'écart se
traite **par correspondance, pas par un second chantier**. Le ReCyF reste en **veille active**.

**La matrice de correspondance, et ce qu'elle refuse** : trois exigences instruites, **aucune ligne
« équivalence »**. *Il n'existe aucune présomption générale de conformité.* Une matrice ne transfère rien ;
elle impute chaque preuve à l'obligation qu'elle sert et **montre surtout ce qui reste à produire**.

**Ce qu'elle produit :** `D3` — note de business case (4 pts), **deux pages** — ramenée de 13 pages, le
rapport d'origine requalifié en pièce d'appui (**F1**), et complétée d'une **estimation de charge**
(≈ 60 jours-homme la première année, poste par poste — **F2**). Dans l'outil : **123 exigences** importées
(clauses 4 à 10 + les 93 contrôles de l'annexe A, en 37/8/14/34), évaluation créée et rattachée au
périmètre, **vierge** — son état normal à ce stade.

**Ce qu'elle transmet :** la langue commune. *« Les actifs critiques cessent d'être une liste et deviennent
un objet d'évaluation. »* Et ce que la décision **ne** change **pas**, dit explicitement : elle ne délivre
aucune conformité réglementaire ; les obligations sectorielles continuent de s'appliquer.

---

## Séance 4 · Audit — *où on en est vraiment*

**Question du bureau du RSSI :** *Que prouve réellement un certificat ISO 27001 à un client ?*

**Ce qu'elle reçoit :** un référentiel importé et une évaluation vide.

**Ce qu'elle décide :** mesurer. Douze exigences parmi les plus exposées sont auto-évaluées dans l'outil, et
les constats du cycle d'audit interne du groupe sont **gradués** (`C1` à `C8`).

**Le résultat, en une phrase** : *des fondations documentées, une application non prouvée, des angles morts
nommés.* Aucune des douze exigences n'est pleinement couverte ; deux le sont partiellement ; **une ne l'est
pas du tout faute d'avoir été posée à la filiale**.

**Le taux de conformité par thème — et pourquoi il compte plus que le taux global** (ajouté par **F20**) :

| Thème de l'annexe A | Taux | Ce que la ventilation révèle |
|---|---|---|
| Organisationnel | 8 % | — |
| Technologique | 10 % | — |
| **Physique (A.7)** | **zéro exigence évaluée sur quatorze** | **L'angle mort que seul ce découpage fait apparaître** — la filiale exploite six entrepôts, des chambres froides et un local serveur unique |
| Ensemble | 9 %, sur **13 % de l'annexe A seulement** | Le chiffre global aurait masqué les deux informations ci-dessus |

**La limite énoncée avant qu'on ne la trouve** : *c'est une auto-évaluation, pas un audit indépendant.* Le
rapport le dit explicitement, en section 1. C'est une constante du dossier, et l'une des raisons pour
lesquelles il tient : **chaque pièce nomme sa propre faiblesse avant qu'un lecteur ne la relève.**

**Deux non-conformités majeures touchent le même système** — le WMS : `C3` (réseaux IT/OT non cloisonnés) et
`C4` (compte de domaine partagé avec le prestataire, nombre de porteurs inconnu). La sous-section 2 avait
mesuré la portée de cinq actifs *sans savoir s'ils étaient protégés* ; la séance 4 répond : les lacunes
assumées décrivaient l'état réel, **sans excès de prudence**.

**Ce qu'elle produit :** `D4` — rapport d'audit initial (4 pts), six sections imposées : cadrage, synthèse
pour décision, constats gradués, recommandations tracées, plan d'action correctif (`M1`-`M4`), angles morts.
Dans l'outil : le suivi des constats (*Follow-ups*).

**Ce qu'elle transmet :** des écarts, pas encore des risques. *« La séance 5 pondérera ces écarts par
conséquence et vraisemblance. »* La distinction est capitale : un écart de conformité dit ce qui manque ; un
risque dit ce qu'il en coûterait et avec quelle probabilité.

---

## Séance 5 · Risques majeurs — *ce qui justifie l'effort* (EBIOS RM, ateliers 1-2)

**Question du bureau du RSSI :** *Qui fixe l'appétence au risque, et comment l'écrit-on ?*

**Ce qu'elle reçoit :** des écarts mesurés, et cinq actifs critiques.

**Ce qu'elle décide :** conduire les **ateliers 1 et 2 d'EBIOS Risk Manager**. Le premier critère
d'acceptation de `D5`, et le dossier l'a respecté à la lettre : **les objets de `D2` sont repris à
l'identique**, pas réinventés (vérifié par **F12**).

- **Atelier 1 — cadrage et socle de sécurité** : le périmètre, les valeurs métier, les biens supports, et
  ce qui est déjà en place (avec ses écarts connus — dont les sauvegardes jamais restaurées, assumé comme
  **écart connu non gradé**).
- **Atelier 2 — sources de risque et objectifs visés** : **cinq couples** SR/OV instruits, **trois
  retenus**, et — c'est ce qui est noté — **les raisons des deux écartés**.

| Acteur retenu | Ce qu'il ferait | Actif visé |
|---|---|---|
| Groupe cybercriminel | Chiffrer le WMS pour arrêter l'expédition du groupe et exiger une rançon | `SA-01` WMS |
| Agent interne mécontent | Fausser les données de préparation, emporter le savoir-faire des six entrepôts | Données · **la personne** |
| Concurrent | Capter les données d'exploitation et celles du client pharmaceutique | Données clients |

Un quatrième acteur — le **prestataire des automates**, dont le contrat n'offre aucune réversibilité — est
**tenu en veille et renvoyé à la séance 6** : *choix de méthode, pas oubli.* La note le dit, et la séance 6
tient la promesse. C'est exactement le type d'articulation que la note est notée sur.

**Sept événements redoutés cotés**, et le plus grave du dossier : *l'arrêt non planifié de l'expédition
au-delà de six heures* — 40 % du volume du groupe, 12 000 €/jour de pénalités. Et **crédible** : système
centralisé sans secours, sauvegardes jamais restaurées, **un arrêt de ce type a déjà eu lieu en avril** sans
que personne ne tienne de chronologie.

**L'articulation que la sous-section 5 porte, et qui est le vrai résultat de la séance :**

> *Les deux non-conformités majeures ne sont pas seulement des écarts de conformité — elles sont le chemin
> qui fait passer les scénarios du théorique au très probable, parce qu'elles retirent à un attaquant les
> deux obstacles qui le ralentiraient : la séparation des réseaux et la possibilité de savoir qui a agi.*

C'est la séance 4 transformée en séance 5. Un dossier qui se contenterait de juxtaposer « voici nos écarts »
et « voici nos risques » n'aurait pas écrit cette phrase.

**Les échelles et le seuil — la décision demandée à la Direction Générale** : gravité et vraisemblance
écrites **en termes du groupe** (pas en adjectifs génériques), matrice **4×4** importée dans l'outil, et un
seuil d'acceptation :

- `High` (**élevé**) — **inacceptable en l'état**, à traiter avant toute mise en production ;
- `Medium` (**moyen**) — toléré **daté, surveillé, confié à un propriétaire nommé** ;
- `Low` (**faible**) — accepté tel quel.

Et la gouvernance qui parle : *la Direction Générale fixe ce seuil, le Conseil d'Administration l'approuve.*

**Ce qu'elle produit :** `D5` — appréciation initiale des risques (3 pts) · dans l'outil : l'étude EBIOS RM
créée, 17 actifs reliés, 7 événements redoutés, 5 couples SR/OV.

**Ce qu'elle transmet :** la ligne. Tout ce que fait la séance 7 consiste à ramener des scénarios sous cette
ligne — ou à formaliser pourquoi on les laisse au-dessus.

> **Une tension assumée, et instructive.** Le module demande `D5` en *une demi-page*. Le livrable fait
> ≈ 2,9 pages, resserré à **724 mots de prose** (−49 %, **F20**) sans atteindre la cible : *le reste est la
> justification que le module exige par ailleurs, et la couper aurait échangé une consigne de taille contre
> une consigne de contenu.* Le choix est écrit plutôt que masqué.

---

## Séance 6 · Tiers et projets — *le risque qui entre par le contrat* (ateliers 3-4)

**Question du bureau du RSSI :** *Une attaque par la chaîne d'approvisionnement dont il faut tirer les
leçons, et la clause qui aurait aidé.*

**Ce qu'elle reçoit :** trois scénarios internes, et un quatrième acteur mis en attente à la séance 5.

**C'est la séance la plus lourde du module : `D6` vaut 7 points**, presque le double de ses voisines. Raison :
elle porte deux pièces distinctes et c'est la seule qui sorte du périmètre maîtrisé.

**Ce qu'elle décide :**

**① Coter l'écosystème (atelier 3).** Cinq parties prenantes notées sur deux axes —
*dépendance × pénétration* (exposition) et *maturité × confiance* (fiabilité) — avec un **seuil de
criticité écrit** (dangerosité ≥ 4,0) :

| Partie prenante | Criticité | Statut |
|---|---|---|
| **Intégrateur des automates** | **12,0** | ⚠️ critique |
| **APPLICA Services** (tierce maintenance du WMS) | **8,0** | ⚠️ critique |
| *(trois autres)* | 1,0 · 0,5 · 0,44 | — |

**② Deux scénarios stratégiques**, dont un **par le fournisseur** : un cybercriminel qui arrêterait
l'expédition du groupe **en passant par la tierce maintenance** plutôt que frontalement — coté `G4`,
critique. C'est la position exacte d'un transporteur européen en 2017 : *non piraté, mais ayant installé de
bonne foi la mise à jour d'un fournisseur compromis* — 250 à 300 M$ en un trimestre.

**③ La règle contractuelle que le groupe se donne** — et c'est la vraie décision de la séance :

> Aucun contrat donnant accès à un actif critique n'est signé ni renouvelé sans **trois exigences
> vérifiables** : journalisation par **utilisateur nommé**, **notification sous 24 h** d'une compromission
> chez le prestataire, **réversibilité** — opposables par la Direction Juridique **avant** signature.

Première application : le contrat APPLICA, **à renouvellement en novembre 2026 sans porter aucune des
trois**. La règle n'est pas théorique, elle a une date et un contrat.

**④ Six jalons de sécurité pour les projets**, chacun avec un **critère de passage démontré par un fait** et
un **propriétaire ultime unique**. Le principe : *une exigence de sécurité posée au cadrage coûte une
réunion ; la même rattrapée en production coûte un projet.*

Premier projet passé à cette grille : **la reprise du flux de réapprovisionnement d'urgence vers MERIDIAN
Santé** — celui-là même que `D1` citait comme la décision prise sans règle, bloqué depuis trois mois. Le
cadrer comme un projet, **avec la RSSI de Santé à la table dès le premier jalon**, *lève l'objection de Santé
au lieu de la contourner.* La boucle S1 → S6 se referme ici.

**Ce qu'elle produit :** `D6` (7 pts) — fiche projet (6 jalons, 3 régimes, points d'arbitrage) + exigences du
contrat APPLICA (5 familles, chacune **tracée à un scénario, un écart de `D4` ou un silence du contrat**) +
dispositif de surveillance du tiers · dans l'outil : 5 parties prenantes cotées, 2 scénarios stratégiques,
3 chemins d'attaque, 1 scénario opérationnel (kill chain en sept actions).

**Ce qu'elle transmet :** l'argument budgétaire, en négatif. *Aucune des deux décisions ne demande de budget
nouveau la première année — la règle des trois exigences est une condition de signature, pas un achat ; les
six jalons, une discipline de cadrage, pas une dépense.* La séance 7 chiffrera ce qui, lui, coûte.

---

## Séance 7 · Traitement — *ce qu'on décide, ce qu'on accepte, ce que ça coûte*

**Question du bureau du RSSI :** *Comment met-on un chiffre sur le coût de l'inaction ?*

**Ce qu'elle reçoit :** un seuil approuvé, un registre de scénarios, une carte d'écosystème.

**Ce qu'elle décide :** appliquer le seuil. *« Le seuil est désormais appliqué, pas seulement approuvé. »*
Sur les **huit scénarios du registre**, **aucun ne reste au-dessus de la ligne** après traitement : six
retombent à `Moyen`, deux à `Faible`.

**Et immédiatement, la phrase qui refuse le triomphalisme :**

> *La filiale ne ferme aucun risque — elle les fait tous passer d'inacceptable à **tolérable-formalisé**, ce
> qui n'est pas la même chose, et c'est dit ici sans le maquiller.*

**Treize mesures, organisées par décision et non par scénario.** Ce choix d'organisation est lui-même
l'argument : un comité exécutif ne signe pas des scénarios, il signe des décisions.

| Nature | Combien | Exemples |
|---|---|---|
| **Décisions de direction** (budget ou contrat) | 5 | 2 avenants contractuels · acceptation formalisée sur la chaîne du froid signée par la DG · pilotage du projet Santé |
| **Mesures d'exécution** | 8 | dont **2 transversales** : comptes nommés + authentification forte pour la TMA ; **segmentation IT/OT** (`PT-03`), la plus coûteuse et la plus large |

**L'arbitrage, tel qu'il est porté à la Direction Financière :**

> **≈ 82 000 € par an** pour le plan complet, contre une fourchette du coût de l'inaction : **au minimum
> 12 000 €** pour une seule journée d'arrêt du WMS, **plusieurs millions** en cas de rançongiciel abouti.
> *Un coût certain et borné contre une perte plausible et non bornée, qui excéderait le budget annuel du plan
> en une seule journée d'incident.*

Le TD 1 de la séance construit cette fourchette en rattachant chaque référence publique à une famille de
scénarios du registre — Mærsk 250-300 M$ (2017) et Norsk Hydro ~800 M NOK (2019) sur l'indisponibilité,
France Travail 5 M€ (CNIL, 2026) et Equifax ≥ 575 M$ sur la fuite, IBM en ordre de grandeur — **plus une
ligne « aucune référence ne colle » assumée** pour la malveillance interne. Une fourchette honnête dit aussi
où elle ne sait pas.

**Sept fiches d'acceptation**, six résiduels `Medium` et un `Low`. **Zéro dérogation — écrit et justifié** :
une acceptation formalisée n'est pas une dérogation, et le dire évite qu'un auditeur le demande.

**Trois points ouverts, chacun avec une date** — le passage que la soutenance reprend tel quel, parce que
c'est lui qui rend le reste crédible :

| Point ouvert | Échéance | Ce qui le lèvera |
|---|---|---|
| **RTO réel du WMS**, inconnu tant que la restauration n'est pas testée — c'est lui qui borne le haut de la fourchette | 14/11/2026 | Test de restauration |
| **Résiduel du scénario de l'intégrateur**, `Moyen` — un plancher que le traitement ne fait pas disparaître | ≤ 12 mois | Revue de la carte de dangerosité |
| **Reprise du flux Santé** : le résiduel visé n'est atteint qu'au 6ᵉ jalon — *`Élevé` dans les faits, `Moyen` dans la trajectoire décidée* | 14/09/2027 | Passage du jalon 6 |

**Ce qu'elle produit :** `D7` (5 pts) — plan par décision, sept fiches d'acceptation, chiffrage **sur trois
ans** (le total annuel seul n'aurait pas satisfait la consigne), table de rapprochement ISO/IEC 27001:2022 ·
dans l'outil : registre à 8 lignes, résiduels cotés, coûts saisis (82K €/an, 13/13 mesures), 2 objets
`Risk acceptances`.

**Ce qu'elle transmet :** la table de rapprochement mesure → contrôle, qui est l'entrée directe de la
séance 8.

---

## Séance 8 · Périmètre du SMSI — *ce que le système couvre, et ce qu'il exclut*

**Question du bureau du RSSI :** *Faut-il viser la certification ? Construisez le business case.*

**Ce qu'elle reçoit :** un plan de traitement chiffré et rattaché aux contrôles.

**Ce qu'elle décide :** **deux périmètres, pas un** — et c'est l'idée centrale de la séance.

| | Couvre | Pourquoi |
|---|---|---|
| **Périmètre du SMSI** | La filiale entière — 6 entrepôts, 4 valeurs métier, 13 biens supports, **6 exclusions nommées**, 4 interfaces déclarées | Le système de management gouverne tout ce qu'on maîtrise |
| **Périmètre de certification visé** | **Plus étroit, assumé** : les seuls services reçus par le client pharmaceutique — chaîne du froid et flux WMS des sites **E1 et E4** | On ne certifie que ce qu'on peut démontrer, et le client n'achète que cela |

**L'exclusion qui fait la valeur de la copie** : E4 est **à la fois** dédié au client pharmaceutique **et**
équipé d'automates de tri sur un réseau non cloisonné (`C3`). L'automatisation d'E4 est donc **exclue par
écrit jusqu'au 14/06/2027**, échéance de `PT-03` (segmentation IT/OT). C'est la lacune que `D2` avait
assumée en séance 2 — *« l'absence de schéma réseau borne ce que nous pouvons honnêtement déclarer »* — qui
produit trois séances plus tard une exclusion datée dans un document opposable. **Le fil rouge du module en
un exemple.**

**La déclaration d'applicabilité :** 15 contrôles investigués (les 12 de la séance 4 ∪ les 8 du CM =
quinze, intersection de cinq — le compte de l'énoncé retrouvé exactement), **16,1 % de couverture affichée
en tête**, une exclusion justifiée en trois lignes (`A.8.28`, codage sécurisé), et une **cohérence croisée
avec `D4` et `D7` vérifiée dans les deux sens** : aucun écart majeur orphelin, mais trois mesures et trois
contrôles encore sans contrepartie — **signalés plutôt que masqués**.

**Ce que l'évaluation initiale confirme**, et qui désigne la séance 9 : *la planification du risque tient —
c'est elle que la séance 7 chiffre — quand **l'information documentée et la mesure de la performance
restent les deux chantiers les plus nus du dossier**.* La séance 9 est précisément consacrée à ces deux-là.

**Ce qu'elle produit :** `D8` (2 pts) — périmètre, déclaration d'applicabilité, registre des exclusions,
synthèse en dix lignes · dans l'outil : 30 exigences de clauses 4 à 10 évaluées, 15 contrôles d'annexe A
investigués.

**Un arbitrage assumé, révélé par la relecture F22** : notre notation est **plus sévère que l'état présumé
du corrigé sur cinq des huit contrôles calibrés**. Les notes **n'ont pas été changées** — les adoucir aurait
contredit `D4` sans fait nouveau. Ce qui manquait n'était pas la sévérité mais **la règle de notation**,
désormais écrite dans `D8` §2.2 : *on note l'état constaté, jamais l'intention.*

---

## Séance 9 · Indicateurs et version finale — *comment on saura que ça tient*

**Question du bureau du RSSI :** *KPI ou KRI — qu'est-ce qui va sur le tableau de bord du conseil ?*

**Ce qu'elle reçoit :** huit sous-sections de note, huit livrables, et deux chantiers nommés par `D8`.

**Ce qu'elle décide :** fermer la boucle. Trois documents, un seul principe : **un indicateur qui ne
surveille aucun objectif de la note de stratégie est un chiffre orphelin, si bien construit soit-il.**

Le gabarit de `D9` est non négociable — *un item vide est un indicateur rejeté* : nom et nature, définition,
formule (numérateur, dénominateur, unité, inclusions/exclusions), source et propriétaire de la lecture,
seuil et ce que son franchissement déclenche, fréquence, destinataire et **la décision que cela éclaire pour
lui**, valeur du jour avec son comptage.

**Sept indicateurs retenus**, et chacun raccroché explicitement à une sous-section :

| Réf. | Indicateur | Nature | Objectif surveillé |
|---|---|---|---|
| `IND-01` | Couverture de la déclaration d'applicabilité | Conformité | §8 — périmètre du SMSI |
| `IND-02` | Écarts de conformité sans mesure de traitement | Conformité | §8 et §4 |
| `IND-03` | Restaurations du WMS testées sur 12 mois | Opérations | §7 — point ouvert « RTO réel » |
| `IND-04` | Avancement de la segmentation IT/OT | Risque | §7 et §8 — *l'exclusion d'E4 tombe à cette date* |
| `IND-05` | Risques résiduels au-dessus du seuil | Risque | §5 — seuil d'acceptation |
| `IND-06` | Accès TMA ouverts par compte nominatif | Risque | §6 — tiers et projets |
| `IND-07` | Respect du délai de notification `INC-01` | Opérations | §1 — gouvernance et directives |

Deux choses à remarquer, parce qu'elles sont la démonstration de toute la méthode :

1. **Les sept indicateurs couvrent les sept premières sous-sections de la note.** Ce n'est pas un hasard de
   présentation : chaque décision prise depuis la séance 1 reçoit son instrument de mesure. Le dossier
   boucle sur lui-même.
2. **`IND-07` est saisi en `Draft` parce qu'il n'est pas mesurable aujourd'hui.** Six des sept sont
   calculables le jour même — très au-delà du minimum d'un seul qu'exige l'énoncé — et le septième est
   déclaré non mesurable plutôt que rempli d'une valeur plausible. *C'est la même honnêteté que la ligne
   « aucune référence ne colle » de la séance 7.*

**Ce qu'elle produit :** `D9` (3 pts) — section de PSSI sur la gestion des vulnérabilités, une procédure,
une **fiche réflexe « suspicion de rançongiciel »**, les sept indicateurs et le tableau de bord · plus la
**sous-section 9** de la note, qui **clôt** le document : après elle, la note ne s'édite plus.

**État au 16 septembre :** le TD 1 est fait (note collective des cinq questions + **les deux pages
individuelles**, ce qui porte le bureau du RSSI à 18/18), le **mode opératoire du TP 1 est écrit** (**F23**),
les deux emplacements manquants de la séance ont été créés. Restent la saisie et le livrable.

---

## Séance 10 · Soutenance — *la séance qui ne crée rien*

**Le fil rouge est explicite : « la séance 10 ne crée rien : elle vérifie, consolide, remet et défend. »**

| Horaire | Ce qui se passe |
|---|---|
| 08:30 – 09:15 | Dépôt des documents, **export daté de l'instance** (pièce 3), dernières retouches aux slides |
| 09:15 – 12:30 | Soutenances des groupes 1 à 5, **30 minutes chacun** |
| 13:30 – 15:00 | Groupes 6 à 8 |
| 15:00 – 16:30 | Synthèse du module, table ronde, remise des exports |

**Le cadre : un comité exécutif, pas un jury technique.** L'auditoire est supposé **ne rien connaître à la
sécurité** et **avoir un budget à signer**. 18 minutes de présentation, 12 de questions, dont **une question
individuelle par étudiant** sur une partie du travail qu'il a déclarée comme sienne.

| Barème de la soutenance | Pts |
|---|---|
| Structure et clarté — *message principal identifiable dans la première minute*, temps tenu, slides lisibles | 6 |
| Pertinence pour la direction — *l'alternative, le coût de l'inaction, ce qu'on fait signer* | **8** |
| Maîtrise du fond — *chacun défend sa partie et situe celle des autres* | **10** |
| Dossier de preuve — complet, ordonné, **utilisable tel quel par un tiers** | 6 |

**Pourquoi les slides reprennent la note et non les livrables.** Les quinze slides construits
(`SOUTENANCE-S10-slides.md`) suivent l'ordre des sous-sections : les cinq actifs critiques (§2), ce que la
mesure a donné et l'angle mort (§4), les trois acteurs (§5), l'événement le plus grave (§6→§5), le risque
qui entre par le contrat (§6), le registre après traitement (§7), l'arbitrage 82 K€ contre plusieurs
millions (§7), les trois points ouverts (§7), les deux périmètres (§8), ce qu'on demande de signer, et la
limite. **La note de stratégie est déjà le scénario de la soutenance** — elle a été écrite pour un directeur
général, et c'est un directeur général qui est en face. Rien à réécrire, seulement à mettre en forme.

**La limite à énoncer avant que le comité ne l'énonce**, et le fil rouge dit que c'est ce qu'un jury attend
d'entendre :

> *Un dossier prouve la méthode, jamais la sécurité elle-même. Des serveurs mal configurés se moquent de la
> propreté du classeur.*

C'est la leçon constante du module depuis le rapport d'audit de la séance 4 — et c'est exactement pourquoi
`D4` écrit qu'il est une auto-évaluation, pourquoi `D7` écrit qu'aucun risque n'est fermé, et pourquoi `D8`
affiche 16,1 % de couverture en tête plutôt qu'en note de bas de page.

---

# 5. Les fils qu'on peut suivre de bout en bout

Voici la meilleure façon de vérifier que le dossier tient : prendre un fait de la séance 2 et le suivre
jusqu'à la séance 9. S'il se transforme sans jamais se contredire ni disparaître, la chaîne est bonne.

## Fil A — la segmentation IT/OT

| Séance | Ce qu'elle en fait |
|---|---|
| S2 | Fait brut : réseaux bureautique et industriel interconnectés, 4G hors supervision → `SA-03` classé **rang 5 du Top 5** |
| S2 | Devient une **lacune assumée** : *« aucun schéma réseau n'existe »* |
| S4 | Devient le constat **`C3`, non-conformité majeure** |
| S5 | Devient un **chemin d'attaque** : c'est lui qui fait passer le scénario cybercriminel au *très probable* |
| S7 | Devient la mesure **`PT-03`**, la plus coûteuse et la plus large du plan, échéance **14/06/2027** |
| S8 | Devient une **exclusion écrite et datée** du périmètre de certification (automatisation d'E4) |
| S9 | Devient l'indicateur **`IND-04`** — *« l'exclusion d'E4 tombe à cette date »* |

## Fil B — le tiers APPLICA

| Séance | Ce qu'elle en fait |
|---|---|
| S2 | `SA-10`, bien support **organisationnel** ; compte de domaine partagé, porteurs inconnus |
| S4 | Constat **`C4`**, non-conformité majeure ; la liste nominative n'a jamais été obtenue |
| S5 | **Mis en veille explicitement** — *« traité en séance 6 »* |
| S6 | **Coté 8,0**, partie prenante critique ; scénario stratégique **par le fournisseur** ; les **trois exigences contractuelles** ; renouvellement novembre 2026 |
| S7 | Deux **avenants contractuels**, décisions de direction ; comptes nommés + authentification forte (mesure transversale) |
| S8 | Le **test du tiers** : dedans ou dehors du périmètre du SMSI, et sur quel critère |
| S9 | Indicateur **`IND-06`** — accès TMA ouverts par compte nominatif |

## Fil C — le flux Logistique → Santé

| Séance | Ce qu'elle en fait |
|---|---|
| S1 | **Dossier n°1 sur le bureau** : bloqué depuis 3 mois, personne ne tranche → justifie `ARB-01` et le comité sécurité groupe |
| S2 | **Dépendance inter-filiales** : la valeur métier appartient à Santé, ses biens supports vivent chez nous — *limite structurelle de l'outil, assumée* |
| S5 | Événement redouté `ER5` |
| S6 | **Premier projet passé aux six jalons**, avec la RSSI de Santé à la table dès le jalon 1 |
| S7 | **Point ouvert daté** : résiduel visé atteint au 6ᵉ jalon, 14/09/2027 |
| S8 | **Exclusion nommée** du périmètre du SMSI — la valeur métier appartient à Santé |

## Fil D — le seuil d'acceptation

`D1` pose *qui* fixe l'appétence (la DG propose, le CA approuve) → `D5` l'écrit en trois niveaux sur la
matrice 4×4 → le TD 2 de S7 le **défend sans le confisquer** contre la proposition du Directeur Logistique,
veto `ARB-01` à l'appui → `D7` l'applique et formalise sept acceptations → `IND-05` le surveille.

---

# 6. La méthode de travail — pourquoi il existe un journal de corrections

`fixes.md` compte **26 000 mots et 23 corrections** (F1 à F23). Ce n'est pas un signe de désordre : c'est le
dispositif qui permet à un dossier cumulatif de rester vrai.

**Le principe** : *rien ne se supprime.* Une correction close **garde sa fiche** ; elle change d'état dans le
relevé. On peut donc reconstituer non seulement l'état du dossier, mais **son histoire de décisions** — ce
qui est exactement ce qu'un successeur doit pouvoir faire.

**Les classes d'erreurs trouvées, et ce que chacune enseigne :**

| Classe | Exemples | La leçon |
|---|---|---|
| **Le livrable existe mais n'est pas présenté comme tel** | F10 — enfoui dans un compte rendu de TP | **13 points** rendus invisibles à un correcteur |
| **Une affirmation sans pièce derrière** | F20 — la charte de `D1`, le taux par thème de `D4` | Le module disqualifie ce cas en toutes lettres |
| **Une erreur de fait contredite par nos propres preuves** | F4 — le ReCyF déclaré absent de la bibliothèque, la capture le montre présent | Corrigé dans les 4 fichiers ; **la recommandation n'a pas bougé** |
| **Un chiffre qui dérive d'une séance à l'autre** | F17 — contrôle de continuité sur les 8 séances, 60 liens relatifs revérifiés | La colonne vertébrale tient ; 4 corrections mécaniques |
| **Un dépassement de format masqué par une auto-estimation fausse** | F18 — la note annonçait 3,5 pages et en faisait 4,8 à 5,8 | Ramenée de 2 902 à 2 018 mots, **sans supprimer une seule décision** |
| **La saisie jamais confrontée au corrigé** | F22 — les deux TP de S8 relus contre leurs *answer keys* | Conforme au chiffre près ; 4 corrections, dont 2 dans l'outil |
| **Une citation fausse** | F23 — `A.6.3` mal cité dans le TD de S9 | Trouvée en relisant l'énoncé pièce en main |

**Et une pratique qui mérite d'être nommée : les points volontairement laissés ouverts.** `fixes.md` §3
décrit quatre écarts **sans les corriger**, avec la raison :

| Écart | Pourquoi il n'est pas corrigé d'office |
|---|---|
| Trois mesures datées deux fois (`M1`/`PT-03`, `M2`/`PT-06`, `M4`/`PT-02`) | Décréter l'une « supersédée » effacerait peut-être une distinction réelle |
| Le dirigeant de la filiale a deux titres et deux genres selon les séances | Le titre comme le genre appartiennent aux auteurs |
| Les porteurs des mesures de `D4` sont des étudiants, pas des rôles | Réattribuer est une décision de fond |
| Les six jalons de `D6` ne portent aucune date | Rien de faux n'est écrit — mais le livrable dont le sujet *est* un projet à six jalons n'en date aucun |

**Décrire un écart sans le corriger est un acte délibéré**, pas un oubli : le journal ne prend pas à la place
des auteurs une décision qui leur revient. C'est la même posture que `D4` (« c'est une auto-évaluation »),
que `D7` (« aucun risque n'est fermé ») et que `D8` (« trois mesures restent sans contrepartie »).

---

# 7. Où est quoi

```
ISMS/
├── COMPRENDRE-LE-DOSSIER.md          ← ce document : la logique de bout en bout
├── README.md                         ← état d'avancement et prochains objectifs
├── ISMS module common thread.pdf     ← LA source de vérité : consignes et barème
├── SOUTENANCE-S10.md                 ← le cadre de la séance 10, minute par minute
├── SOUTENANCE-S10-slides.md          ← les 15 slides, slide par slide
├── SOUTENANCE-S10-script.md          ← le texte des passages à dire mot à mot
├── meridian.pptx                     ← le support en cours de fabrication
│
├── G4- Translog Maxime - Miguel - TP/ ← 🎯 LE RENDU
│   ├── fixes.md                       ← journal des corrections F1 → F23
│   ├── 0-Reference/                   ← dossier de filiale reçu + supports de cadrage
│   ├── Piece-1-Strategy-note/         ← PIÈCE 1 · la note, 9 sous-sections
│   ├── Piece-2-File/Session-1…9/      ← PIÈCE 2 · le dossier
│   │   ├── 1-CISO-desk/               ← bureau du RSSI : note collective Sn-01 + 1 page/étudiant
│   │   ├── 2-Labs/                    ← TP (Sn-05, Sn-06) et le livrable Dn
│   │   ├── 3-Evidence/                ← captures de l'instance CISO Assistant
│   │   └── 4-Working-notes/           ← TD 2 (Sn-03), non noté
│   └── Piece-3-Proof-of-state/        ← PIÈCE 3 · export de l'instance (séance 10)
│
├── DELIVERABLE/                       ← copie de travail + questions.md (résumé des énoncés)
├── Seance-1…3/, S2 - Sources/ … S9 - Sources/  ← supports de cours reçus (CM/TD/TP)
├── 00-Reference/                      ← dossier de référence MERIDIAN + accès à l'instance
└── .FIRST_TP-backup-…/                ← archive d'avant la réorganisation du 8 sept.
```

**Par où commencer, selon ce qu'on cherche :**

| Je veux… | J'ouvre |
|---|---|
| Comprendre la logique d'ensemble | **ce document** |
| Savoir ce qu'il reste à faire | `README.md` §3, ou `fixes.md` « Ce qui reste » |
| Le document qu'un directeur général lit | `Piece-1-Strategy-note/MERIDIAN-strategy-note.md` |
| Le livrable noté d'une séance | `Piece-2-File/Session-n/2-Labs/Dn-*.md` |
| Ce que l'énoncé demandait exactement | `DELIVERABLE/questions.md`, ou le PDF dans `Sn - Sources/` |
| La consigne officielle et le barème | `ISMS module common thread.pdf` |
| Préparer la soutenance | `SOUTENANCE-S10.md` puis `-slides.md` puis `-script.md` |

---

# 8. Où en est le dossier, et ce qui reste

**Acquis au 16 septembre 2026 :**

- **Séances 1 à 8 closes** — dossier, outil et bureau du RSSI. `D1` à `D8` assemblés, **34 points sur 40**.
- **Bureau du RSSI : 18 pages sur 18** (S1 à S9, deux étudiants), chacune close par une recommandation à la
  direction, chacune d'un angle distinct de celui du binôme.
- **Note de stratégie : 8 sous-sections sur 9**, 1 939 mots de corps — dans le plafond.
- **Séance 9 ouverte** : TD 1 fait, deux pages individuelles rendues, mode opératoire du TP 1 écrit.
- **Instance `translog-b`** : 17 actifs, étude EBIOS RM complète (ateliers 1 à 4), registre à 8 lignes,
  30 exigences de clauses évaluées, 15 contrôles d'annexe A, tous les objets **avec un auteur nommé**.

**Ce qui reste, par enjeu décroissant :**

| # | Quoi | Enjeu |
|---|---|---|
| 1 | **La séance 9** — TP 1 et TP 2, livrable `D9`, **sous-section 9 qui clôt la note** | 3 pts + clôture de la pièce 1 |
| 2 | **Les supports de soutenance** — le `.pptx` en cours, à partir des trois documents `SOUTENANCE-S10-*` | **30 pts, coef. 3** |
| 3 | **La note de stratégie en PDF** — la pièce 1 est définie comme « un fichier PDF » | forme du rendu |
| 4 | **F17** — trancher les quatre écarts de fond laissés ouverts | pas de points directs, mais lu en soutenance |
| 5 | **F19** — resserrer les pages du bureau du RSSI à une page franche (574 à 864 mots aujourd'hui) | **3 des 10 pts individuels** |
| 6 | **Séance 10, 08:30-09:15** — export daté de l'instance = **pièce 3** | dossier de preuve, 6 pts |

---

# 9. Les cinq idées à retenir

Si l'on ne devait garder que cinq choses de tout le dossier :

1. **Affirmer, prouver, montrer.** La note affirme, le dossier prouve, l'export montre. Une affirmation sans
   pièce ne compte pas ; une pièce dont la note ne dit rien est du travail perdu.

2. **Rien ne se réinvente d'une séance à l'autre.** Les objets de `D2` se retrouvent dans `D5` à l'identique,
   les constats de `D4` deviennent les chemins d'attaque de `D5`, les mesures de `D7` deviennent les
   contrôles de `D8`, et les décisions de la note deviennent les indicateurs de `D9`. Chaque objet du dossier
   peut répondre à la question *« d'où viens-tu ? »*.

3. **La règle s'écrit avant le résultat.** Le critère du Top 5 avant le classement. Le veto avant le calcul
   des notes de référentiels. Le seuil de criticité avant la cotation de l'écosystème. La règle de notation
   avant la déclaration d'applicabilité. C'est ce qui rend une décision contestable — donc argumentée.

4. **Chaque pièce nomme sa propre faiblesse.** `D4` dit qu'il n'est pas indépendant. `D7` dit qu'aucun risque
   n'est fermé. `D8` affiche 16,1 % en tête et signale ses trois orphelins. `D9` laisse `IND-07` en `Draft`.
   La soutenance énonce la limite avant le comité. **Ce n'est pas de la modestie : c'est ce qui rend le reste
   croyable.**

5. **On parle au décideur, pas au technicien.** 40 % du volume expédié du groupe. 12 000 € par jour.
   82 000 € par an contre plusieurs millions. Six jalons, trois exigences contractuelles, une signature à
   apposer. *Un dossier qui raconte ce qui a été fait est descriptif ; un dossier qui dit ce qui est décidé,
   ce qui reste ouvert et ce que cela coûte est une stratégie.*
