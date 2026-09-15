# D3 — NOTE DE BUSINESS CASE : CHOIX DU RÉFÉRENTIEL DE SÉCURITÉ DU GROUPE

**Émetteur** RSSI Groupe · **Destinataire** Comité Exécutif · **Objet** décision d'adoption d'un référentiel unique
**Groupe 4 (Translog)** · instance `translog-b` · **Séance 3** · deux pages

---

## 1. Contexte et déclencheur

**Qualification réglementaire, filiale par filiale.** NIS 2 s'applique par deux filtres cumulatifs — le secteur, puis la taille. Chez MERIDIAN le filtre taille ne discrimine rien : les quatre filiales dépassent tous les seuils. Tout se joue donc sur la description de l'activité réellement exercée.

| Filiale | Annexe | Caractérisation | Ce qui reste ouvert |
|---|---|---|---|
| Santé | I — santé | **Entité essentielle** | Rien : aucune lecture alternative sérieuse |
| Logistique | I **ou** II | **Essentielle ou importante** | La rubrique « transport routier » vise les autorités routières et les exploitants de systèmes de transport intelligents, pas tout transporteur privé ; la rubrique « services postaux et d'expédition » colle à l'activité d'expédition. **C'est l'annexe, pas la taille, qui fixe la catégorie** |
| Territoires | I, deux hypothèses | **Dépend d'un choix français non arrêté** | Inclusion des administrations locales, ou qualification en service TIC géré |
| Éducation | Aucune | **Hors champ** | L'annexe II vise la recherche, pas l'enseignement |

**La catégorie a un prix** : essentielle = supervision *ex ante* **et** *ex post*, amende plafonnée à 2 % du chiffre d'affaires mondial ; importante = *ex post* seulement, plafond 1,4 %. Nous préparons Logistique sur l'**hypothèse haute** tout en portant la qualification à l'arbitrage.

**Les obligations déjà en vigueur ne dépendent d'aucun calendrier** : le RGPD s'applique aux quatre filiales, l'exigence HDS aux hébergeurs de Santé, le RGS à l'environnement des clients de Territoires. S'y ajoute une pression commerciale immédiate — une trentaine de collectivités clientes demandent des garanties, et le client pharmaceutique de Logistique a **annoncé un questionnaire de sécurité** pour son prochain audit.

**Le déclencheur est interne** : le groupe dispose depuis cette semaine d'une cartographie tenue dans un outil commun et d'un référentiel importé, prêt à être évalué. Décider maintenant, sur un dossier instruit, coûte moins que décider sous la contrainte du calendrier réglementaire.

## 2. Options examinées

| Option | Force réelle | Limite | Note /300 |
|---|---|---|---|
| **Guide d'hygiène ANSSI** | Gratuit, 42 mesures, deux niveaux, son propre outil de suivi : **utilisable dès demain matin** | Aucune force juridique, aucune preuve au-delà d'une auto-déclaration, faible sur la gouvernance de groupe | 135 |
| **ReCyF** | **Le mieux placé sur le caractère obligatoire** : ses objectifs ont vocation à être fixés par décret ; c'est devant lui que la conformité NIS 2 se démontrera | Version de travail (v2.5 du 17/03/2026), aucune certification possible, et **muet sur une filiale hors champ NIS 2** | 205 |
| **ISO/IEC 27001:2022** | Couvre les quatre filiales, le SI comme l'industriel, et **mène seule à une certification par tierce partie** | Volontaire : ne s'impose que par le contrat ; l'ISMS des clauses 4 à 10 et l'audit sont une charge réelle | **230** |

## 3. Recommandation raisonnée

**Nous recommandons ISO/IEC 27001:2022 comme colonne vertébrale de la sécurité du groupe, sur les quatre filiales.**

**Une règle de veto a été posée avant tout calcul** : est écarté, quelle que soit sa note, tout référentiel ne couvrant pas simultanément les obligations sectorielles de Santé, le périmètre industriel de Logistique et une filiale hors champ NIS 2. **Le ReCyF échoue à cette condition** — non par faiblesse, mais par destination. Ce n'est pas sa note de 205 qui l'écarte, c'est une condition qu'il ne remplit pas. Nous ne l'écartons pas comme *mauvais* : nous l'écartons comme *colonne vertébrale*, et le gardons en **veille active**.

Trois arguments, et un quatrième qui rend la décision immédiate :

1. **Seule option couvrant l'intégralité du périmètre du groupe** — filiales dans le champ NIS 2 comme filiale hors champ, systèmes de gestion comme environnements industriels.
2. **Seule option produisant une preuve opposable à un tiers**, sur un périmètre écrit. Les collectivités clientes et le questionnaire du client pharmaceutique ne se satisfont pas d'une auto-déclaration.
3. **Une partie de l'effort sera réutilisée, pas refaite** — dans les bornes exactes que la matrice ci-dessous établit.
4. **La décision est déjà outillée** : **123 exigences** évaluables importées dans l'instance (clauses 4 à 10 + les 93 contrôles de l'annexe A), évaluation initiale créée et rattachée au périmètre `MERIDIAN-LOGISTIQUE`, vierge. Un avis favorable ne demande aucun préalable technique.

**Matrice de correspondance** — trois exigences instruites, **aucune ligne « équivalence »**, comme dans les 180 lignes du jeu livré avec l'outil :

| Exigence source | Cible ISO/IEC 27001:2022 | Relation | Justification |
|---|---|---|---|
| NIS 2 `1.1-EI/EE` — activités, services, propriétaires, SI supports | Clause 4 + `A.5.9` | intersect | *semantic* — la source impose de lister **hors** périmètre d'applicabilité : **ISO laisse choisir son périmètre, NIS 2 interdit de le choisir** |
| ReCyF objectif 2 — cadre de gouvernance | Clauses 5, 6, 9 + `A.5.1`, `A.5.2` | intersect (forte) | *semantic* — reconnu comme moyen acceptable, borné à **un objectif sur vingt** et au **seul périmètre certifié** |
| Guide d'hygiène mesure 4 — actifs sensibles et schéma réseau | `A.5.9`, `A.5.12` | intersect | *semantic* — le schéma « simplifié » est moins exigeant que l'inventaire NIS 2 |

**Il n'existe donc aucune présomption générale de conformité.** Une matrice tenue à jour ne transfère rien ; elle impute chaque preuve ISO à l'obligation qu'elle sert, et montre surtout ce qui reste à produire.

**La meilleure objection, et notre réponse.** L'objection sérieuse n'est pas le coût : c'est que **l'autorité nous contrôlera devant le ReCyF, pas devant l'ISO**. Nous l'assumons ainsi — le ReCyF est un texte de travail qu'on ne peut pas ériger aujourd'hui en colonne vertébrale d'un groupe de 7 550 salariés, il ne dit rien d'une filiale sur quatre, et l'écart se traite par correspondance, pas par un second chantier.

## 4. Charge, limites et angles morts

**Estimation de la charge — première année, à moyens constants.** *Base : 123 exigences importées, quatre filiales, journée de 7,5 h. Les trois hypothèses de productivité sont écrites pour être contestées : aucune donnée de ce type n'existe au dossier.*

| Poste | Hypothèse | Charge |
|---|---|---|
| Évaluation initiale des 123 exigences, premier passage | 20 min par exigence | 5,5 j-h / filiale |
| Collecte des preuves | 40 % des exigences, 30 min chacune | 3,5 j-h / filiale |
| Entretiens (DSI, exploitation, qualité) | 4 demi-journées | 2 j-h / filiale |
| Consolidation et restitution | — | 1 j-h / filiale |
| **Sous-total par filiale** | | **12 j-h** → **48 j-h** pour quatre |
| Arrêt du périmètre filiale par filiale | 4 × 1 j-h + 2 j-h de consolidation | 6 j-h |
| Pilotage RSSI Groupe sur la période | | 5 j-h |
| **Total première année** | | **≈ 60 jours-homme** |

*Le poste dominant est le **nombre de filiales retenues au périmètre** : 12 j-h chacune. Ne sont **pas** compris : la remédiation, déjà financée sur l'axe résilience OT/IT de la trajectoire ; l'audit de certification, non chiffré ; le maintien du SMSI après la première année.*

**Limites et angles morts**

- **Ce choix ne délivre aucune conformité réglementaire.** RGPD, HDS et RGS continuent de s'appliquer indépendamment.
- **Angle mort assumé** : ISO laisse **choisir** le périmètre de son ISMS là où NIS 2 **interdit** de le choisir. Un certificat obtenu sur la filiale la mieux tenue n'aurait rien prouvé sur les trois autres — d'où une décision portant sur les quatre filiales.
- **Angle mort technique** : il n'existe **aucun schéma réseau de Logistique**, et les réseaux IT et OT y sont interconnectés sans cloisonnement. Aucun périmètre ISO incluant l'industriel ne serait honnêtement déclarable avant ce chantier, inscrit à 24 mois.
- **Le coût de la certification n'est pas chiffré** : il se calcule une fois les périmètres arrêtés, ce que la décision ci-dessous mandate. Aucun budget nouveau la première année.
- **La recommandation est robuste, pas inattaquable** : l'écart avec le ReCyF n'est que de 25 points sur 300, et les deux tests de bascule de la grille basculent. **Ce n'est pas l'arithmétique qui porte la recommandation, c'est la règle de veto** — une condition, pas une note.

## 5. Décision demandée

> **Le Comité Exécutif est invité à approuver l'adoption d'ISO/IEC 27001:2022 comme référentiel de sécurité du groupe MERIDIAN, sur les quatre filiales, et le lancement de l'évaluation initiale déjà créée dans l'outil, en mandatant le RSSI Groupe pour arrêter filiale par filiale le périmètre de déploiement.**
>
> **Décision attendue à la séance de jeudi.** Premier geste au lendemain d'un avis favorable : ouverture de l'évaluation initiale et notification aux quatre RSSI de filiale du calendrier de collecte des preuves — sans budget nouveau, pour une charge estimée à 60 jours-homme la première année.

---

> **Pièces à l'appui** : preuve d'état dans `../3-Evidence/` (référentiel importé, évaluation rattachée au périmètre, recherches en bibliothèque) · grille pondérée et correspondances en `../4-Working-notes/` · dossier argumenté complet dans `MERIDIAN-business-case-framework-selection.pdf`.
