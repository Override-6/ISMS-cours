# Séance 3 — TD (S3-01) : The CISO's briefing — Applicabilité de NIS 2
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN

---

## Rappel du cas

Lundi matin, 8h40. La Directrice Générale du groupe MERIDIAN interpelle le RSSI Groupe au passage : *« J'ai lu ce week-end un article sur la loi Résilience et les quinze mille entreprises concernées. En sommes-nous ? Il paraît que les dirigeants sont personnellement responsables. Je veux une réponse au Comité Exécutif de jeudi. »* Elle est déjà partie.

**Matériel disponible** : la cartographie construite en séance 2 (valeurs métier, biens supports, besoins DICT de MERIDIAN Logistique — notre filiale d'instruction), et les chiffres du groupe :

| Filiale | Effectif | Activité |
|---|---|---|
| MERIDIAN Santé | 3 200 | 4 établissements de soin |
| MERIDIAN Logistique | 2 800 | 6 entrepôts ; transport, entreposage sous température dirigée, expédition |
| MERIDIAN Éducation | 900 | portail pédagogique, 45 000 comptes utilisateurs |
| MERIDIAN Territoires | 650 | plateforme de services citoyens pour ~30 collectivités clientes |

**Attendu** : pas une dissertation juridique — une **caractérisation raisonnée, filiale par filiale**, avec ce qu'elle implique.

**Périmètre de traitement (consigne)** : les **questions 1 à 4 portent sur les quatre filiales** du groupe — c'est le RSSI Groupe qui répond, et la Directrice Générale demande « en sommes-nous ? » pour MERIDIAN, pas pour un entrepôt. La **question 5 ne porte que sur MERIDIAN Logistique**, notre filiale d'instruction, puisqu'elle se rattache à la cartographie que notre groupe a effectivement construite en séance 2.

### Les trois notions posées avant l'exercice

- **NIS 2** = directive (UE) 2022/2555 du 14 décembre 2022, succédant à NIS 1 (2016, transposée en France en 2018, quelques centaines d'entités de 10 secteurs). Elle étend massivement le champ : selon l'ANSSI, plusieurs milliers d'entités sur **18 secteurs** et environ **600 types d'entités**.
- **Directive ≠ règlement** : une directive fixe un **résultat à atteindre** et laisse chaque État la transposer ; seule la loi nationale crée l'obligation. *(Ce détail juridique est le cœur de la réponse de jeudi — cf. Q4.)*
- **Deux filtres cumulatifs** : le **secteur** (annexe I « secteurs hautement critiques » / annexe II « autres secteurs critiques ») puis la **taille**.

### Les seuils utilisés dans tout ce document (publiés par l'ANSSI sur MonEspaceNIS2)

| Catégorie | Condition | Conséquences |
|---|---|---|
| **Entité essentielle** | secteur de l'**annexe I** **et** ≥ 250 salariés, ou CA > 50 M€ et bilan > 43 M€ | Supervision **ex ante *et* ex post** ; amende plafonnée à **2 % du CA mondial** (plancher ~10 M€) |
| **Entité importante** | à défaut d'être essentielle : ≥ 50 salariés, ou CA et bilan > 10 M€ | Supervision **ex post uniquement** (sur signalement ou incident) ; amende plafonnée à **1,4 % du CA mondial** (plancher ~7 M€) |

> ⚠️ **Réflexe de méthode appliqué à tout le document** : l'applicabilité **déclenche des obligations, elle ne mesure rien**. Une entité peut être dans le champ et bien protégée, hors champ et vulnérable. Et l'on sépare systématiquement **ce que dit le texte européen** (stable, publié) de **ce que dit le droit national** (ici : encore en construction).

---

## Question 1 — Premier filtre : le secteur

*Pour chaque filiale : annexe candidate (I, II, ou hors annexes) et rubrique sectorielle la plus proche.*
*Ordre de traitement imposé par la méthode : Santé → Logistique → Territoires → Éducation (difficulté croissante du raisonnement, pas l'organigramme).*

### MERIDIAN Santé — annexe I, sans difficulté

- **Fait** : la filiale exploite 4 établissements de soin, elle est prestataire de soins de santé.
- **Règle** : l'annexe I liste la **santé** parmi les secteurs hautement critiques, rubrique « prestataires de soins de santé ».
- **Conclusion** : **annexe I**, rubrique santé. Aucune lecture alternative sérieuse.

### MERIDIAN Logistique — **deux lectures**, toutes deux conservées à ce stade

L'énoncé demande explicitement deux lectures possibles. Elles ne s'opposent pas sur les faits, elles s'opposent sur **la qualification de l'activité réellement exercée** — et c'est bien ce que fait la filiale qui tranchera, pas son nom.

- **Fait** : 2 800 salariés, 6 entrepôts, trois activités mêlées — **transport** (flotte de véhicules avec télématique, entre entrepôts et vers les clients), **entreposage sous température dirigée**, et **expédition** pour compte de tiers (portail d'expéditions du client pharmaceutique, un compte par entrepôt).

**Lecture A — annexe I, secteur « Transports », rubrique transport routier.**
La filiale exploite une flotte et achemine physiquement du fret : lue comme un transporteur, elle relève du secteur hautement critique des transports.
*Point de vigilance honnête, à porter à l'arbitrage* : la rubrique « transport routier » de l'annexe I vise nommément les **autorités routières** et les **exploitants de systèmes de transport intelligents**, pas tout transporteur privé de marchandises. La lecture A est donc plaidable mais **moins évidente que son intitulé ne le suggère** — c'est précisément pour cela qu'elle ne peut pas être tranchée seule dans un couloir.

**Lecture B — annexe II, secteur « Services postaux et d'expédition ».**
L'activité d'**expédition** pour compte du client pharmaceutique, avec entreposage et remise, correspond à la rubrique des services postaux et de courrier/expédition des « autres secteurs critiques ».

- **Conclusion (Q1)** : **annexe I *ou* annexe II selon la qualification de l'activité** — les deux lectures sont conservées, et **le choix n'est pas cosmétique** : il change la catégorie (cf. Q3), donc le régime de supervision et le plafond de sanction.

### MERIDIAN Territoires — annexe candidate suspendue à un choix français

- **Fait** : 650 salariés, exploite une **plateforme de services citoyens** pour ~30 collectivités clientes. La filiale est un **prestataire privé** ; ce sont ses **clients** qui sont des administrations.
- **Règle** : l'annexe I comporte une rubrique **« administration publique »**, mais la directive laisse aux États le soin de décider s'ils y incluent les **administrations locales et régionales**. La France n'a pas arrêté ce choix.
- **Lecture alternative à instruire** : l'annexe I comporte également une rubrique **gestion des services TIC (B2B)**, visant notamment les **fournisseurs de services gérés**. Exploiter la plateforme de trente collectivités ressemble beaucoup à cette activité — cette lecture, si elle prospérait, rendrait Territoires **essentielle indépendamment** du choix français sur les administrations locales.
- **Conclusion** : **annexe I sous deux hypothèses distinctes, aucune fermée aujourd'hui**. C'est la filiale sur laquelle il est légitime — et professionnel — de répondre « cela dépend d'un choix que la France n'a pas encore fait ».

### MERIDIAN Éducation — hors annexes

- **Fait** : 900 salariés, portail pédagogique, 45 000 comptes.
- **Règle** : l'annexe II mentionne la **recherche**, pas l'enseignement en tant que tel ; aucune rubrique des deux annexes ne couvre l'activité d'Éducation.
- **Conclusion** : **hors des annexes**. Le filtre secteur échoue dès la première étape ; le filtre taille n'a donc pas à être appliqué (cf. Q2).

---

## Question 2 — Second filtre : la taille

*Pour chaque filiale retenue en Q1 : seuil franchi et critère utilisé.*

| Filiale | Effectif | Seuil « entité essentielle » (≥ 250 sal.) | Seuil « entité importante » (≥ 50 sal.) | Critère utilisé |
|---|---|---|---|---|
| Santé | 3 200 | **franchi** | *(sans objet, essentielle prime)* | Effectif salarié |
| Logistique | 2 800 | **franchi** | franchi | Effectif salarié |
| Territoires | 650 | **franchi** | franchi | Effectif salarié |
| Éducation | 900 | *non applicable* | *non applicable* | **Filtre secteur non franchi : la taille ne se pose pas** |

**Ce que ce tableau démontre, et qui mérite d'être dit au ComEx** : chez MERIDIAN, **le filtre taille ne discrimine rien**. Les quatre filiales dépassent largement tous les seuils. Toute la caractérisation se joue donc **sur le secteur**, c'est-à-dire sur la **description exacte de l'activité réellement exercée** — un travail de cartographie, pas de droit.

*Deux précisions de méthode* : (1) l'appréciation se fait **entité par entité**, pas au niveau consolidé du groupe — c'est bien 2 800 salariés pour Logistique qui compte, pas les 7 550 du groupe ; (2) les données financières (CA, bilan) des filiales n'ont pas été communiquées au RSSI Groupe : le critère d'effectif suffit ici à conclure, mais **le dossier remis à l'autorité devra les contenir** et devra être demandé au Directeur Financier du holding.

---

## Question 3 — Caractérisation provisoire, une phrase de justification chacune

| Filiale | Caractérisation provisoire | Justification (une phrase) |
|---|---|---|
| **Santé** | **Entité essentielle** | Prestataire de soins de santé (annexe I, secteur hautement critique) avec 3 200 salariés, soit très au-delà du seuil de 250 : les deux filtres sont franchis sans ambiguïté. |
| **Logistique** | **Essentielle *ou* importante — selon un arbitrage de qualification encore ouvert** | Avec 2 800 salariés, la filiale franchit tous les seuils : elle sera **essentielle** si son activité est qualifiée au titre du transport (annexe I) et **importante** si elle l'est au titre des services d'expédition (annexe II) — c'est l'annexe, et non la taille, qui décide de la catégorie. |
| **Territoires** | **Dépend d'un choix encore ouvert** | Ses 650 salariés franchissent tous les seuils, mais son rattachement à l'annexe I dépend soit du choix français d'y inclure les administrations locales — non arrêté à ce jour — soit de la qualification de la plateforme en service TIC géré, à instruire. |
| **Éducation** | **Hors champ en l'état** | Aucune rubrique des annexes I et II ne couvre son activité d'enseignement : le premier filtre échoue, et le second n'a pas à être appliqué. |

**Trois conséquences concrètes à afficher au ComEx** :

1. **La catégorie n'est pas une étiquette.** Essentielle = contrôle **ex ante *et* ex post** par l'autorité + plafond à **2 % du CA mondial** ; importante = contrôle **ex post seulement** + plafond à **1,4 %**. L'arbitrage de qualification de Logistique a donc un **prix**.
2. **Hors champ ≠ hors risque.** Éducation reste soumise au RGPD, porte 45 000 comptes utilisateurs, et la séance 2 y a déjà identifié onze services non gouvernés dont un outil d'IA générative recevant des copies d'élèves. Le fait qu'aucune obligation NIS 2 ne la vise ne retire **rien** à cette exposition.
3. **Position de prudence assumée pour Logistique** : nous préparons la filiale sur **l'hypothèse haute** (entité essentielle) tout en portant la question de qualification à l'arbitrage. Se préparer au régime le plus exigeant puis se voir classer « importante » coûte quelques mois d'avance ; l'inverse coûte un plan de mise en conformité à refaire sous contrainte de calendrier.

---

## Question 4 — Les trois phrases à dire à la Directrice Générale jeudi

**Contrainte de l'exercice** : aucune des trois phrases ne doit pouvoir être démentie si la loi est promulguée dans les six mois. Le piège est connu : le RSSI qui répond *« on verra quand la loi sortira »* et celui qui répond *« nous sommes déjà conformes »* ont **tous les deux tort**. Voici la troisième réponse.

> **1.** « Trois de nos quatre filiales entrent dans le champ de la directive européenne NIS 2 : Santé comme entité essentielle, Logistique comme entité essentielle ou importante selon la qualification retenue de son activité de transport ou d'expédition, et Territoires selon un choix que la France n'a pas encore arrêté ; Éducation ne relève d'aucune des deux annexes. »
>
> **2.** « À ce jour, aucune obligation NIS 2 ne nous est opposable en France : la directive devait être transposée avant le 17 octobre 2024, et la loi dite Résilience — adoptée par le Sénat le 12 mars 2025, votée en commission spéciale à l'Assemblée nationale le 10 septembre 2025 — n'est toujours pas promulguée, non plus que ses décrets et arrêtés. »
>
> **3.** « Les obligations que cette loi portera sont, elles, déjà connues et ne dépendent plus du calendrier — mesures de gestion des risques, **approbation des mesures par l'organe de direction et formation des dirigeants**, notification des incidents significatifs en 24 h / 72 h / un mois, et enregistrement auprès de l'autorité nationale — c'est pourquoi nous engageons dès maintenant la pré-inscription sur MonEspaceNIS2 et la complétion de notre cartographie, qui seront exigées quel que soit le texte final. »

### Couverture des quatre filiales par les trois phrases

*Contrôle avant le ComEx : la réponse doit caractériser les quatre filiales, pas seulement celles qui posent problème.*

| Filiale | Où elle est traitée | Ce qui en est dit |
|---|---|---|
| Santé | Phrase 1 | Entité essentielle — la seule affirmée sans réserve |
| Logistique | Phrase 1 | Essentielle **ou** importante, l'incertitude nommée comme telle et rattachée à sa cause (qualification transport / expédition) |
| Territoires | Phrase 1 | Dans le champ **sous réserve d'un choix français non arrêté** |
| Éducation | Phrase 1 | Hors des deux annexes — dit explicitement, pour éviter que le silence passe pour un oubli |
| Les quatre | Phrases 2 et 3 | L'état de la transposition et les obligations à venir valent pour l'ensemble du groupe, et le plan d'action engagé n'attend aucune des trois réserves ci-dessus |

### Vérification de la contrainte, phrase par phrase

| Phrase | Ce qu'elle affirme | Pourquoi la promulgation ne peut pas la démentir |
|---|---|---|
| 1 | Le champ de la **directive** (texte européen stable, publié, non modifiable par la loi française) | Elle ne parle jamais du droit français, et la seule zone d'incertitude — Territoires — est **explicitement nommée comme incertaine**, donc la lever ne la contredira pas. |
| 2 | Un état de fait **daté** (« à ce jour ») avec ses références vérifiables | Une promulgation ultérieure ne rend pas fausse une affirmation horodatée ; elle la périme, ce qui n'est pas la même chose. |
| 3 | Le **contenu** des obligations (articles 20 et 21 de la directive, notification en trois temps, enregistrement) et **nos propres actions** | La transposition peut préciser des seuils et des délais d'application, elle ne peut pas supprimer des obligations posées par la directive qu'elle transpose ; et une action que nous engageons ne peut pas être démentie par un texte. |

*Sur la responsabilité personnelle qui inquiète la Directrice Générale : la phrase 3 y répond sans la dramatiser ni la nier — l'article 20 de la directive fait approuver les mesures par les organes de direction, qui peuvent être tenus responsables et doivent suivre une formation. C'est exact, c'est écrit, et c'est déjà dans le texte européen.*

---

## Question 5 — Rattachement à la cartographie de la séance 2 — **MERIDIAN Logistique uniquement**

*Question traitée pour notre seule filiale d'instruction, conformément à l'énoncé : c'est la cartographie de Logistique que le Groupe 4 a construite en séance 2 (S2-01, S2-03, S2-05), et elle seule peut être confrontée aux exigences de l'article 3.*

*Ce que l'article 3 de la directive imposera de communiquer à l'autorité nationale si la filiale est dans le champ, et ce que l'inventaire de la séance 2 sait déjà fournir.*

L'article 3 de la directive est celui qui définit les entités essentielles et importantes ; il impose aux États d'établir la **liste** de ces entités, et aux entités de **fournir à l'autorité** au minimum : **nom, adresse et coordonnées à jour** (adresse électronique, **plages d'adresses IP**, numéros de téléphone), **secteur et sous-secteur** de rattachement au titre des annexes I et II, et **liste des États membres** où l'entité fournit des services relevant du champ. C'est un dossier d'**identification**, pas un dossier de sécurité — mais il se remplit avec la cartographie, pas avec l'organigramme.

| Élément exigé par l'article 3 | Ce que la cartographie S2 fournit déjà | Ce qui manque, et pourquoi |
|---|---|---|
| **Nom, adresse, sites** | Les six entrepôts E1 à E6 sont identifiés, y compris leur rôle (E1 le plus ancien, salle serveurs WMS ; E1 et E4 dédiés au client pharmaceutique ; E2/E3/E4 automatisés ; E5/E6 manuels) | Rien de bloquant — l'entretien avec le Responsable Exploitation a produit cette liste, il reste à **l'écrire** hors de sa mémoire. |
| **Secteur et sous-secteur (annexes I / II)** | La cartographie décrit **l'activité réellement exercée** — exécution des flux logistiques, transport inter-entrepôts et vers clients, entreposage sous température dirigée, expédition via le portail du client pharma | C'est exactement la matière de l'arbitrage de la Q1 : **la cartographie ne tranche pas la qualification, elle en fournit la preuve**. Sans elle, l'arbitrage se ferait sur l'intitulé social de la filiale. |
| **Coordonnées à jour, dont un point de contact** | Le « map of power » de la filiale identifie qui décide de quoi (Directeur de filiale, Responsable Exploitation, Responsable SI, 6 chefs d'entrepôt, Responsable Qualité) | **Aucun point de contact unique n'existe.** L'arrêt WMS d'avril l'a prouvé : trois chefs d'entrepôt ont appelé la TMA, deux l'intégrateur, un le Responsable SI en congé, et personne n'a tenu de chronologie. **Un point de contact nommé est un livrable à produire.** |
| **Plages d'adresses IP** | Partiellement : le réseau bureautique est connu du Responsable SI et ses journaux remontent au SOC du groupe | **Le trou est structurel** : réseaux IT et OT interconnectés sans segmentation, **box 4G de l'intégrateur hors du réseau supervisé**, ~300 scannettes en Wi-Fi, logiciel des sondes hébergé chez le fournisseur, télématique chez un autre. Déclarer des plages IP suppose de savoir ce qui est raccordé — c'est le **cloisonnement IT/OT** déjà fixé à 24 mois en séance 1. |
| **États membres où des services sont fournis** | Non documenté à ce jour | À demander au Directeur de la filiale avec les contrats (client pharmaceutique, transport). |

### Ce que la cartographie apporte au-delà de l'article 3

L'enregistrement n'est que la porte d'entrée ; les obligations réelles arriveront avec l'article 21, et la séance 2 y a déjà travaillé sans le savoir :

- **Sécurité de la chaîne d'approvisionnement** (art. 21) : la cartographie liste déjà les six dépendances externes de la filiale — TMA du WMS, intégrateur des automates, fournisseur des sondes et son logiciel hébergé, fournisseur de télématique, opérateur des liaisons inter-entrepôts, portail du client pharmaceutique. Deux d'entre elles sont **contractuellement nues** : compte de domaine partagé par la TMA dont personne ne connaît le nombre de porteurs, et intégrateur sous contrat **sans clause de réversibilité ni exigence de sécurité**.
- **Notification en 24 h** : elle suppose de savoir **qui appelle qui, et qui décide de notifier** — la question posée par la Direction Générale après l'arrêt d'avril, toujours sans réponse écrite. Il n'existe **aucune procédure d'incident** dans la filiale.
- **Le Top 5 des actifs critiques** consolidé en séance 2 est l'ancrage de la quatrième mesure préventive prioritaire de l'ANSSI (« établir une liste priorisée des services numériques critiques ») : ce travail est **déjà fait** et servira tel quel.
- **Le questionnaire de sécurité annoncé par le client pharmaceutique** pour le prochain audit se remplira avec la même cartographie. La conformité NIS 2 et la conformité contractuelle demandent **le même livrable** — c'est l'argument à opposer à qui verra dans NIS 2 un coût sans contrepartie.

> **À dire au ComEx en une ligne** : l'enregistrement au titre de l'article 3 est **administratif et rapide** ; ce qui prend du temps, c'est de pouvoir répondre honnêtement à la case « plages d'adresses IP », et c'est le même chantier que le cloisonnement IT/OT déjà inscrit à notre trajectoire 24 mois.

---

## Ce que nous n'affirmons pas (et pourquoi c'est volontaire)

Trois conclusions que le dossier ne permet **pas** de tirer, et qu'il aurait été facile d'écrire :

1. **« Logistique est une entité essentielle. »** Le dossier ne le permet pas : la rubrique « transport routier » de l'annexe I ne vise pas explicitement les transporteurs privés de marchandises. Nous nous **préparons** sur cette hypothèse, nous ne la **déclarons** pas.
2. **« Territoires est concernée. »** Le choix français sur les administrations locales n'est pas arrêté. Savoir dire « cela dépend d'un choix que la France n'a pas encore fait » est une compétence, pas un aveu de faiblesse.
3. **« Nous serons conformes à la promulgation. »** Aucun élément du dossier ne le soutient : ni procédure d'incident, ni cloisonnement IT/OT, ni comptes nominatifs côté prestataires. L'applicabilité **déclenche des obligations, elle ne mesure aucun niveau de sécurité** — et nous en sommes, sur Logistique, très loin.

---

## Auto-évaluation (grille du TD)

| Critère | Notre niveau atteint |
|---|---|
| **Filtre secteur (Q1)** | Annexe candidate + rubrique pour les 4 filiales ; **deux lectures conservées pour Logistique** (annexe I transport / annexe II expédition) avec l'argument qui les départage, et une lecture alternative instruite pour Territoires (service TIC géré) |
| **Filtre taille (Q2)** | Critère cité pour chaque filiale, **et** démonstration que le filtre taille ne discrimine rien chez MERIDIAN — toute la caractérisation se joue sur le secteur ; appréciation faite entité par entité, pas au niveau consolidé |
| **Caractérisation (Q3)** | Une phrase de justification par filiale, les quatre issues du barème représentées (essentielle / essentielle ou importante / dépend d'un choix ouvert / hors champ), **et** conséquences concrètes tirées (supervision, plafond de sanction, posture de prudence sur Logistique) |
| **Les trois phrases (Q4)** | Séparation stricte texte européen / droit national, état de la transposition daté et référencé, réponse à la question de la responsabilité des dirigeants, **et** vérification explicite de la contrainte de falsifiabilité à six mois pour chacune des trois phrases |
| **Lien à la cartographie (Q5)** | Contenu de l'article 3 déroulé item par item face à ce que la S2 fournit déjà, **et** identification du seul item réellement bloquant (plages IP) rattaché au chantier de cloisonnement IT/OT déjà planifié en séance 1 |
| **Méthode (fait → règle → conclusion)** | Appliquée filiale par filiale dans l'ordre imposé Santé → Logistique → Territoires → Éducation, avec refus explicite de conclure là où le texte ne le permet pas |

*Chaque case vise la colonne « Excellent » de la grille officielle — à confronter en séance avec le corrigé de référence du module.*
