# Séance 8 — TD (S8-01) : The CISO's Desk — Le business case de la certification
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN — appliquées à **MERIDIAN Logistique** (instance `translog-b`)

> Enchaînement de la journée : ce TD du matin **construit le dossier de décision** — le certificat que le
> tiers demande n'existe pas encore, mais une démarche réelle, oui — que le RSSI Groupe présente au Comité
> Exécutif jeudi. Le CM qui suit (*architecture de l'ISO/IEC 27001:2022 et rôle de la direction*) ouvre
> enfin la norme elle-même ; le TP 1 évalue la conformité et la déclaration d'applicabilité dans
> `translog-b` ; le TP 2 en sort le livrable **D8** — périmètre du SMSI, contrôles retenus, exclusions
> justifiées par écrit, taux de couverture, écarts restants — et la sous-section 8 de la note de stratégie.
> Rien de ce qui est écrit ici n'est jetable : le périmètre défendu à la question 4 est celui que D8 devra
> déclarer, et les limites de la question 3 nourrissent directement les exclusions que D8 doit justifier.

**Vocabulaire** : business case de certification, valeur métier du SMSI — au sens du TD de la séance 8.
Filiale sous revue : **MERIDIAN Logistique** (instance `translog-b`). Besoins de sécurité notés **DICT**
(Disponibilité, Intégrité, Confidentialité, Traçabilité). Sigles développés au premier emploi : **WMS**
(*warehouse management system*, logiciel de gestion d'entrepôt), **TMA** (tierce maintenance applicative),
**SMSI** (système de management de la sécurité de l'information, *ISMS*), **SoA** (déclaration
d'applicabilité, *Statement of Applicability*), **IT/OT** (bureautique / industriel).
**Sources utilisées** : le briefing *« The CISO's Desk: The Certification Business Case »* (séance 8,
TD 1), le pack de filiale MERIDIAN Logistique (version 1, 3 septembre 2026) §2, §3, §4, §6, la gouvernance de
D1, la cartographie D2, le référentiel adopté D3, l'audit initial D4, le plan de traitement D7.

---

## Rappel du cas

**Lundi matin.** La Directrice Générale de MERIDIAN Logistique fait suivre au RSSI Groupe une exigence
reçue d'un tiers. Chez nous, le déclencheur est connu depuis la séance 3 : le client pharmaceutique — deux
entrepôts qui lui sont dédiés, pénalités de 12 000 €/jour d'arrêt, audit chaîne du froid annuel (pack §2) —
**a annoncé un questionnaire de sécurité pour son prochain audit** (pack §3). La Directrice Générale de la
filiale transmet l'exigence sous la forme d'une clause type : *« La filiale devra démontrer une
certification ISO/IEC 27001 valide couvrant les services fournis à ce tiers, ou une démarche documentée
équivalente. »* Le message qui l'accompagne tient en une phrase : *« Dites-moi qu'on l'a. »*

**On ne l'a pas.** Mais le dossier n'est pas vide : le groupe a choisi ISO/IEC 27001:2022 comme référentiel
en séance 3 (D3), l'a importé dans l'outil, a mené un audit interne en séance 4 (D4) qui laisse une liste
d'écarts par exigence, et vient d'arrêter en séance 7 (D7) un plan de traitement daté et chiffré
(≈ 82 000 €/an, 13 mesures, zéro résiduel au-dessus de `Medium`). **Une démarche existe, réelle et
documentée. Un certificat, non.**

La Directrice Générale du groupe, informée, cadre la semaine du RSSI Groupe : *« Jeudi, au Comité Exécutif,
je veux votre recommandation : lançons-nous un effort de certification, sur quel périmètre, et que
répondons-nous à ce tiers en attendant. Pas de lyrisme, des faits. »* Le travail du matin prépare ce
dossier.

**Ce que la séance 4 avait déjà entrouvert.** La tension n'est pas neuve : les **deux** pages du bureau du
RSSI de la séance 4 l'avaient posée, chacune de son côté. Miguel y opposait les deux commandes du matin —
le client pharmaceutique demande *« un certificat couvrant **le service qu'il achète** »*, la Directrice
Générale du groupe en veut un couvrant *« le groupe »*, et ce ne sont pas deux tailles du même document
mais deux projets, deux budgets, deux calendriers
(`../../Session-4/1-CISO-desk/S4-bureau-du-RSSI-Miguel-Monereo.md`). Maxime en tirait la conséquence de
calendrier : le *« toutes filiales, et vite »* de la Directrice Générale l'inquiétait moins pour ce qu'il
coûte que pour ce qu'il romprait, parce qu'un périmètre ingagnable ne produit pas une échéance
disciplinante, il en produit une qu'on repousse puis qu'on tait
(`../../Session-4/1-CISO-desk/S4-bureau-du-RSSI-Maxime.md`). Ce matin ne réinvente pas cette position : il
l'**instruit** avec ce que D2, D4 et D7 ont produit depuis.

---

## Les deux notions posées avant l'exercice

| Notion | Ce que c'est | Ce qu'elle n'est pas |
|---|---|---|
| **Business case de certification** | Le document court qui organise une décision que la direction ne peut pas prendre seule : ce que le certificat prouverait, et à qui ; ce qu'il ne prouverait pas ; l'effort et la trajectoire pour l'obtenir ; la décision demandée | Il ne **décide** pas — il **rend la décision possible**. Si la direction dit non, un bon dossier aura quand même clarifié ce que le groupe attend de sa sécurité |
| **Valeur métier du SMSI** | Ce que le groupe gagne à faire *vivre* un système de management, au-delà du confort du RSSI : confiance démontrable, constance (les contrôles survivent aux départs), arbitrages informés, réutilisation (un système répond à plusieurs obligations) | Elle ne se matérialise **que si le système vit** — un SMSI papier a un coût certain et une valeur nulle, ce que D7 illustre déjà : 31 400 €/an de fonctionnement (*run*), pas seulement 51 000 €/an d'investissement amorti (*build*) |

**Un repère de marché, cité par l'énoncé** : selon l'AFNOR, qui reprend l'*ISO Survey* internationale, la
France comptait un peu plus de mille organisations certifiées ISO/IEC 27001 fin 2023 — trois fois plus
qu'en 2019, avec une progression déjà de 11 % en France et 22 % dans le monde en 2020. Traduction pour le
Comité : être certifié différencie encore, et la croissance du club dit que les donneurs d'ordre le
demandent de plus en plus.

**Le réflexe de méthode** : un dossier de certification se juge à ses phrases négatives. S'il ne contient
aucun *« ceci ne prouvera pas »*, aucun *« ceci ne couvrira pas »*, c'est une plaquette commerciale, et une
direction expérimentée le balaiera d'une question. C'est au RSSI Groupe de poser les limites, avant qu'un
autre ne les découvre à sa place.

---

## Question 1 — Analyser la clause transmise

*Ce qu'elle exige exactement, la portée des mots « couvrant les services fournis à ce tiers » et « ou une
démarche documentée équivalente », au moins deux lectures et leurs conséquences pour la réponse du groupe.*

La clause porte **trois exigences emboîtées**.

1. **« Certification ISO/IEC 27001 valide »** : un certificat délivré par un **organisme tiers**, toujours
   valide — donc ni une auto-déclaration, ni notre propre audit interne (D4), qui n'a d'ailleurs pas
   l'indépendance requise (D4 §1 : *« auto-évaluation outillée [...] n'a donc pas l'indépendance qu'exige
   la définition normative de l'audit »*).
2. **« Couvrant les services fournis à ce tiers »** : c'est exactement la leçon de périmètre de la
   séance 3. Un certificat de groupe qui exclurait les services que le client pharmaceutique reçoit de
   Logistique ne satisferait pas la clause ; inversement, un certificat étroit couvrant précisément ces
   services suffirait. **Le périmètre compte plus que l'échelle.**
3. **« Ou une démarche documentée équivalente »** : c'est l'échappatoire, et l'objet du vrai débat.
   - **Lecture stricte** : une démarche formalisée et orientée vers la certification, avec des preuves
     datées — un référentiel adopté, une évaluation menée, un plan de traitement arrêté. Le groupe peut la
     documenter **dès aujourd'hui** : D3 (référentiel), D4 (évaluation), D7 (plan de traitement daté et
     chiffré).
   - **Lecture large** : n'importe quel dossier de sécurité raisonnablement étoffé. Possible, mais le
     groupe ne peut pas parier sa réponse sur la lecture la plus indulgente d'un client qui vient
     précisément d'**annoncer un questionnaire de sécurité** — un client qui pose la question la pose pour
     vérifier, pas pour se satisfaire d'un dossier vague.

**Conséquence pour notre réponse** : nous construisons la réponse au client sur la **lecture stricte**, avec
les livrables des séances 2 à 7 comme pièces à l'appui — c'est déjà une réponse défendable, et c'est celle
qui tient si le client durcit sa lecture après coup.

---

## Question 2 — Ce que le certificat prouverait

*Trois audiences au minimum, tirées du pack de filiale (§3 et §6), un bénéfice par audience, en lien avec ce
que la séance 3 a établi sur ce qu'atteste une certification.*

| Audience | Ce que le certificat lui prouverait | Source |
|---|---|---|
| **Le client pharmaceutique** — le tiers qui demande | Qu'un organisme accrédité a vérifié que la chaîne du froid et le WMS qui l'alimentent sont gouvernés selon une norme internationale : transforme la promesse commerciale (*« dites-moi qu'on l'a »*) en preuve opposable, réponse exacte au questionnaire de sécurité annoncé (pack §3) et à l'audit chaîne du froid annuel (pack §2) | Pack §2, §3 |
| **MERIDIAN Santé** — filiale sœur et **client interne**, la seule audience que **seul** le §6 donne | Que les scannettes d'entrepôt et le WMS qui les alimente sont gouvernés selon la même norme que le reste du groupe : c'est exactement l'argument qui manque aujourd'hui pour rouvrir le flux de réapprovisionnement d'urgence, bloqué depuis trois mois à la demande du RSSI de Santé (*« their equipment cannot be trusted »*, pack §6) alors que la Pharmacienne-chef le réclame (*« it will not last the winter »*). Entre deux filiales du même groupe, une vérification faite de l'extérieur pèse plus qu'une promesse — précisément là où la confiance a été retirée | Pack §6 ; D6 (jalons M1-M6), D7 (`ER5`, `PT-11`) |
| **La Direction Générale et les actionnaires du holding** | Que l'effort engagé depuis six séances (référentiel adopté, audit mené, 82 000 €/an de plan de traitement) produit un **actif durable et visible**, pas seulement une dépense — le club reste assez fermé pour que l'appartenance se remarque (un peu plus de mille organisations certifiées en France fin 2023, AFNOR) | Énoncé du TD, D7 |
| **L'Audit Interne du holding** — cité deux fois par le pack, au §3 et au §6 | Qu'un tiers accrédité vérifiera chaque année ce qu'il réclame en vain : la **liste nominative** des porteurs du compte de la TMA, dont il n'a reçu qu'un nom de compte et aucun nom de personne. Le certificat ne lui livre pas la liste — il rend son absence intenable sur le périmètre couvert, puisque l'imputabilité y devient auditable de l'extérieur (constat C4 de D4, registre nominatif et journalisation `PT-02` de D7) | Pack §3, §6 ; D4 (C4), D7 (`PT-02`) |
| **Les filiales et les équipes de Logistique elles-mêmes** | Que les règles du groupe (PSSI-cadre, directives `ACC-01`, `ACC-02`, `INC-01`, `JRN-01`, `COR-01` de D1) ne sont pas un caprice du RSSI mais un système vérifié de l'extérieur — déplace le débat interne de « faut-il le faire » à « comment le faire », notamment sur les deux non-conformités majeures encore ouvertes (C3, C4 de D4) | D1, D4 |
| **Le régulateur** — audience acceptée, avec une nuance | Une gouvernance démontrée **sur le périmètre certifié uniquement** — jamais une présomption de conformité réglementaire, cf. la limite posée en question 3 | D3 §4 |

**Ce que le pack ne nous donne pas, et qu'on n'invente pas** : contrairement à Territoires (une trentaine de
collectivités clientes) ou Éducation, le pack de filiale ne documente **aucun autre client externe** que le
client pharmaceutique pour Logistique — la carte du pouvoir (§3) n'en cite pas d'autre. Nous ne rajoutons
donc pas une audience « autres clients » qui ne figure nulle part au dossier. Le seul autre client que le
dossier documente est **interne** — MERIDIAN Santé, ligne ci-dessus — et c'est le §6 qui le donne, pas le
§3 : c'est bien la frontière de la filiale, pas sa carte du pouvoir, qui porte cette audience-là.

---

## Question 3 — Ce que le certificat ne prouverait pas

*Trois limites au minimum, chacune en une phrase, dont une sur la conformité réglementaire et une sur la
sécurité réelle des systèmes.*

1. **Limite réglementaire.** La certification ne vaut pas conformité réglementaire : le RGPD, la
   qualification NIS 2 encore en arbitrage (D3 §1) et les obligations contractuelles continuent de
   s'appliquer indépendamment du certificat — D3 l'écrit déjà noir sur blanc : *« Ce choix ne délivre aucune
   conformité réglementaire. »*
2. **Limite de sécurité réelle.** Le certificat atteste un **système de management**, pas l'absence de
   vulnérabilité : le secret du compte de service WMS↔automates, identique sur les six entrepôts depuis
   2019 et en clair dans un fichier de configuration (constat de D4, rotation `PT-09` du plan de traitement
   de D7 échéance 14/01/2027, donc **encore ouvert à ce jour**), pourrait très bien coexister avec un
   certificat valide. Le rappel le plus connu de cet écart entre conformité affichée et sécurité réelle reste **Equifax, 2017** (cité
   par l'énoncé).
3. **Limite de périmètre.** Le certificat ne prouve rien au-delà de son périmètre déclaré : un certificat
   limité à Logistique ne dira **rien** des trois autres filiales du groupe (Santé, Éducation, Territoires),
   chacune porteuse de ses propres écarts — position déjà posée en D3 : *« Un certificat obtenu sur la
   filiale la mieux tenue n'aurait rien prouvé sur les trois autres. »*
4. **Limite de fraîcheur et de vivacité, honnête et supplémentaire.** La photographie date de l'audit, pas
   d'aujourd'hui — notre propre D4 est une **auto-évaluation sans indépendance** (D4 §1), pas un audit au
   sens normatif — et l'entretien du système a un coût récurrent : le plan de traitement de D7 porte déjà
   31 400 €/an de fonctionnement (*run*), sans lequel les mesures qui abaissent les résiduels à `Medium`
   cesseraient de produire cet effet.

---

## Question 4 — Proposer un périmètre de certification

*Le groupe entier, la filiale sous revue seule, ou seulement les services visés par le tiers ? En s'appuyant
sur la cartographie de la séance 2 et les écarts de la séance 4, défendu en cinq lignes.*

**Proposition : MERIDIAN Logistique d'abord, et plus précisément les services que vise le client
pharmaceutique — chaîne du froid et flux WMS des entrepôts E1 et E4 (`LOG-PA-02`, `LOG-PA-04` de D2) —
avec une extension au reste du groupe à étudier ensuite.**

- **Demande** : c'est là qu'est la pression. Le questionnaire de sécurité annoncé (pack §3) vise
  précisément ces services, et un certificat qui ne les couvrirait pas ne répondrait pas à la clause
  (question 1).
- **Matière** : la cartographie de la séance 2 décrit ces valeurs métier et leurs biens supports — WMS
  (`LOG-SA-01`), logiciel des sondes de température (`LOG-SA-05`), chambres froides et remorques
  réfrigérées (`LOG-SA-08`), Responsable Qualité (`LOG-SA-11`) — sans qu'il faille rien inventer ; elle ne
  décrit pas les trois autres filiales du groupe.
- **Réalisme** : l'audit de la séance 4 ne referme aucune des douze exigences évaluées (0/12 pleinement
  couvertes, deux non-conformités majeures C3 et C4), et le plan de traitement de la séance 7 — déjà
  engagé, chiffré à 82 000 €/an, 13 mesures — est un chantier **borné et daté** sur lequel appuyer un
  dossier de certification, pas une promesse à construire depuis rien.
- **Réserve honnête, à écrire au Comité et non à lui laisser découvrir** : E4 est **à la fois** dédié au
  client pharmaceutique **et** équipé d'automates de tri — ce n'est pas un rapprochement de notre fait,
  c'est écrit littéralement dans le même paragraphe du pack de filiale (§4, notes d'entretien du
  Responsable Exploitation) : *« E2 and E3 have sorting machines, E4 too since last year [...] E1 and E4
  are reserved for the pharma customer »* — repris à l'identique en D2 §1 — sur un réseau
  bureautique/industriel **interconnecté sans cloisonnement** (constat C3, majeur). Un périmètre déclaré
  aujourd'hui devra donc soit **exclure explicitement l'automatisation d'E4** de la certification tant
  que la segmentation IT/OT
  (`PT-03` de D7, échéance 14/06/2027) n'est pas faite, soit accepter de retarder l'audit de certification
  jusqu'à ce chantier — aucun périmètre ISO incluant l'industriel ne serait honnêtement déclarable avant, ce
  que D3 avait déjà posé comme angle mort assumé.
- **Contre-argument à assumer** : un périmètre étroit a moins de valeur de vitrine pour le reste du groupe
  — il faudra le dire au Comité, pas le laisser découvrir.

---

## Question 5 — La décision demandée au Comité Exécutif

*Trois phrases au plus : la recommandation, ce qu'elle engage, la réponse proposée au tiers dans
l'intervalle. Contrainte : aucune date de certification promise, aucun coût improvisé.*

> Je recommande de lancer l'effort de certification ISO/IEC 27001:2022 sur le périmètre retenu pour
> MERIDIAN Logistique — la chaîne du froid et le flux WMS des entrepôts E1 et E4, hors automatisation d'E4
> tant que la segmentation IT/OT n'est pas faite —, avec une extension au reste du groupe à étudier ensuite ;
> cela engage la poursuite du plan de traitement arrêté en séance 7 (≈ 82 000 €/an, déjà budgété) et un
> budget de soutien à la démarche de certification proprement dite, qui fera l'objet d'une note séparée. Au
> client, nous répondons dès aujourd'hui au titre de la démarche documentée équivalente, avec pour pièces à
> l'appui notre référentiel adopté (D3), notre évaluation outillée (D4) et notre plan de traitement daté et
> chiffré (D7). Je demande au Comité de valider ces deux orientations jeudi.

Trois phrases, aucune date de certificat, aucun chiffre inventé — le seul montant cité (82 000 €/an) est
déjà arrêté et confirmé dans `translog-b` depuis D7, pas un coût de certification improvisé pour
l'occasion.

---

## Auto-évaluation (grille officielle de l'énoncé)

| Critère | Niveau visé | Justification |
|---|---|---|
| **Lecture de la clause** | Excellent | Les trois exigences emboîtées décomposées, deux lectures de l'équivalence, et la conséquence de chaque lecture tirée pour la réponse du groupe (Q1) |
| **Équilibre du dossier** | Excellent | **Six** audiences avec un bénéfice chacune (Q2) — les deux sections que l'énoncé désigne sont effectivement mobilisées, le §3 (client pharmaceutique, Audit Interne) **et** le §6 (MERIDIAN Santé, Audit Interne) — et quatre limites dont une réglementaire et une opérationnelle (Q3), chaque énoncé rattaché à un fait établi en séances 1 à 7 |
| **Périmètre** | Excellent | Un périmètre proposé, défendu par la cartographie et les écarts de l'audit (Q4), **et** la réserve de périmètre étroit assumée par écrit (la tension E4 automatisé/dédié pharma) |
| **Décision demandée** | Excellent | Close, décidable jeudi, aucun engagement invérifiable, réponse au tiers dans l'intervalle incluse (Q5) |
| **Honnêteté** | Excellent | La distinction démarche/certificat tenue partout, et le dossier énonce ce qu'il ne peut pas encore chiffrer (le coût de la certification elle-même, distinct du plan de traitement) |

*La grille ci-dessus **est** celle de l'énoncé : le corrigé et la matrice d'évaluation sont dépliés dans
l'export PDF de la séance (`../../../../S8 - Sources/TD 1/`), et les cinq critères sont repris mot pour
mot. Ce qui reste à confronter en séance n'est donc pas la grille, mais le **niveau** que nous nous
attribuons sur chacun de ses critères.*

---

> **Suite immédiate.** Le périmètre défendu en question 4 est celui que **D8** devra déclarer comme
> périmètre du SMSI ; la réserve sur E4 devient une **exclusion à justifier par écrit** dans la déclaration
> d'applicabilité ; les quatre limites de la question 3 nourrissent directement la section « écarts
> restants » de D8. Le CM qui suit (*architecture de l'ISO/IEC 27001:2022 et rôle de la direction*) ouvre la
> norme elle-même ; le TP 1 évalue la conformité et la SoA dans `translog-b` ; le TP 2 assemble **D8** et la
> sous-section 8 de la note de stratégie.
