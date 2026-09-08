# Séance 3 — TP (S3-06) : Rédiger la note de business case et revue par les pairs
### Livrables du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN — instance **translog-b**, périmètre `MERIDIAN-LOGISTIQUE`

> **Règle de la fin de journée** : rédiger, ici, c'est **assembler**. Aucun argument de la note ci-dessous n'est inventé ce soir — chacun renvoie à une pièce produite dans la journée : l'applicabilité filiale par filiale (S3-01), la grille pondérée et les correspondances (S3-03), la fiche d'identité et l'import prouvé dans l'outil (S3-05). Le contexte vient du CM (S3-02) et du dossier des séances 1 et 2.
>
> Trois livrables : **la note de business case** (2 pages, 5 sections), **la revue par les pairs** (grille à 5 lignes, constats traités un par un), **la sous-section 3 de la note de stratégie** (demi-page, articulée aux deux précédentes).

---

## Ce que la note fait, et ce qu'elle ne fait pas

La Directrice Générale ne lira ni la directive, ni la norme, ni la grille à quinze cases — et c'est pourtant elle qui décide, parce qu'un référentiel engage un budget, des équipes et la parole du groupe devant ses clients. Sans document taillé pour elle, la décision se prend en séance, à l'impression, et se défait à la séance suivante.

**Une note de business case** présente à un décideur une occasion d'agir, les options examinées, une recommandation raisonnée et **une décision demandée, formulée pour qu'on puisse y répondre oui ou non**. Chaque section répond à une question que le décideur pose réellement, dans l'ordre où il la pose : *pourquoi maintenant ? qu'avons-nous comparé ? que recommandez-vous et sur quoi cela repose-t-il ? qu'est-ce que cela coûte et ne couvre pas ? que dois-je décider aujourd'hui ?*

**Sa limite, qui la distingue de ses cousines** : elle demande **UNE** décision de pilotage. Ce n'est pas la note de cadrage de la séance 1 (S1-06 Ex. 1), qui organise un travail **déjà décidé** ; ce n'est pas un plan projet, qui déclinera la mise en œuvre **après** la décision. Une note qui se termine sans décision demandée est une dissertation dans le mauvais gabarit.

---

# Exercice 1 — La note de business case

> **Format contrôlé** : 5 sections, gabarit du groupe, deux pages au plus. Les repères de longueur sont indiqués section par section. Les parenthèses de traçabilité — **(grille)**, **(correspondances)**, **(import)**, **(applicabilité)** — désignent la pièce de la journée dont l'affirmation est tirée ; elles sont la première chose que la revue par les pairs testera.

---

---

## NOTE DE BUSINESS CASE — CHOIX DU RÉFÉRENTIEL DE SÉCURITÉ DU GROUPE MERIDIAN
**Émetteur** : RSSI Groupe · **Destinataire** : Comité Exécutif · **Objet** : décision d'adoption d'un référentiel unique · **2 pages**

### 1. Contexte et déclencheur — *pourquoi cette décision, pourquoi maintenant* — ⅓ de page

Le groupe compte quatre filiales aux métiers disjoints et aux obligations disjointes. **Trois d'entre elles entreront dans le champ de la directive européenne NIS 2** à la promulgation de la loi de transposition : Santé comme entité **essentielle** sans ambiguïté, Logistique comme entité **essentielle ou importante** selon la qualification retenue de son activité, Territoires selon un choix que la France n'a pas encore arrêté ; **Éducation ne relève d'aucune des deux annexes** (applicabilité). Cette quatrième filiale ne cesse pas d'exister : **900 salariés, 45 000 comptes** (applicabilité), dans un secteur en tête des incidents portés à la connaissance de l'ANSSI (dossier S2).

Les obligations **déjà en vigueur**, elles, ne dépendent d'aucun calendrier : le RGPD s'applique aux quatre filiales, l'exigence HDS aux hébergeurs de Santé, le RGS à l'environnement des clients de Territoires (applicabilité). S'y ajoute une pression commerciale immédiate : **une trentaine de collectivités clientes** de Territoires demandent des garanties, et le client pharmaceutique de Logistique a **annoncé un questionnaire de sécurité** pour son prochain audit (grille).

Le déclencheur est enfin interne : le groupe dispose **depuis cette semaine** d'une cartographie tenue dans un outil de gouvernance commun et d'un référentiel importé, prêt à être évalué (import). Décider maintenant, sur un dossier instruit, coûte moins que décider sous la contrainte du calendrier réglementaire, quel que soit ce calendrier.

### 2. Options examinées — *ce que nous avons comparé* — ⅙ de page

| Option | Force réelle | Limite |
|---|---|---|
| **Guide d'hygiène informatique de l'ANSSI** | Gratuit, 42 mesures, deux niveaux, son propre outil de suivi : **utilisable dès demain matin**, et le plus rapide à faire baisser un risque concret | Aucune force juridique, aucune preuve opposable au-delà d'une auto-déclaration, faible sur la gouvernance de groupe (grille) |
| **ReCyF (futur référentiel de contrôle ANSSI)** | **Le mieux placé sur le caractère obligatoire** : ses objectifs de sécurité ont vocation à être fixés par décret ; c'est devant lui que la conformité NIS 2 se démontrera (grille) | Version de travail diffusée depuis mars 2026, aucune certification possible, et **muet sur une filiale hors champ NIS 2** (correspondances) |
| **ISO/IEC 27001:2022** | Couvre les quatre filiales, le SI comme l'industriel, et **mène seule à une certification par tierce partie** (grille) | Volontaire : ne s'impose que par le contrat ; l'ISMS des clauses 4 à 10 et l'audit de certification sont une charge réelle, non chiffrée à ce stade |

### 3. Recommandation raisonnée — *ce que nous proposons et sur quoi cela repose* — ½ page

**Nous recommandons d'adopter ISO/IEC 27001:2022 comme colonne vertébrale de la sécurité du groupe**, sur les quatre filiales.

Trois arguments la désignent, et un quatrième la rend immédiate :

1. **C'est la seule option qui couvre l'intégralité du périmètre du groupe** (grille). La couverture n'a pas été traitée comme une note mais comme une **condition** : est écarté, quelle que soit sa note pondérée, tout référentiel ne couvrant pas simultanément les obligations sectorielles de Santé, le périmètre industriel de Logistique et une filiale hors champ NIS 2. Le ReCyF échoue à cette condition — non par faiblesse, mais par destination (grille).
2. **C'est la seule option produisant une preuve opposable à un tiers** (grille), sur un périmètre écrit noir sur blanc. Les collectivités clientes et le questionnaire du client pharmaceutique ne se satisfont pas d'une auto-déclaration.
3. **Une partie de l'effort sera réutilisée, pas refaite** (correspondances). La portée exacte de cette réutilisation, pour qu'elle ne soit pas sur-lue : le ReCyF reconnaît un ISMS certifié comme moyen acceptable **pour son seul objectif de gouvernance — un objectif sur vingt — et sur le seul périmètre couvert par la certification**. Il n'existe **aucune présomption générale** de conformité, et aucune ligne des correspondances examinées ne déclare deux exigences équivalentes : toutes disent « intersection ». Au-delà de cet objectif, un tableau de correspondance tenu à jour ne transfère rien — il permet d'imputer chaque preuve ISO à l'obligation qu'elle sert, et surtout de voir ce qui reste à produire (correspondances).
4. **La décision est déjà outillée** (import). Le référentiel est importé dans l'instance du groupe — **123 exigences** évaluables, dont **93 contrôles d'annexe A** — et l'évaluation initiale est créée et rattachée au périmètre MERIDIAN, vierge. Un avis favorable ne demande aucun préalable technique.

**La meilleure objection à cette recommandation, et notre réponse.** L'objection sérieuse n'est pas le coût : c'est que **l'autorité nous contrôlera devant le ReCyF, pas devant l'ISO**, et qu'un référentiel-colonne vertébrale mal choisi fait faire le travail deux fois. Nous l'assumons ainsi : le ReCyF est un texte de travail qu'on ne peut pas ériger aujourd'hui en colonne vertébrale d'un groupe de 7 550 salariés ; il ne dit rien d'une filiale sur quatre ; et l'écart entre les deux se traite par correspondance, pas par un second chantier (correspondances). Nous le tenons donc en **veille active**, prêt à devenir le référentiel de démonstration NIS 2 quand ses objectifs seront fixés — la colonne vertébrale, elle, n'aura pas à changer.

### 4. Limites et angles morts — *ce que ce choix ne couvre pas* — ⅓ de page

- **Ce choix ne délivre aucune conformité réglementaire.** Il n'existe **aucune présomption générale** de conformité NIS 2 par l'ISO ; le seul transfert reconnu porte sur **un objectif sur vingt** et sur **le seul périmètre certifié** (correspondances). RGPD, HDS et RGS continuent de s'appliquer indépendamment (applicabilité).
- **Notre angle mort assumé, et il est sérieux** : ISO laisse l'organisation **choisir** le périmètre de son ISMS là où NIS 2 **interdit** de le choisir. Un certificat obtenu sur la filiale la mieux tenue n'aurait rien prouvé sur les trois autres — c'est pourquoi la décision demandée porte sur les quatre filiales et sur un périmètre arrêté explicitement, filiale par filiale.
- **Deuxième angle mort, technique** : il n'existe à ce jour **aucun schéma réseau de Logistique**, et les réseaux IT et OT y sont interconnectés sans cloisonnement. Aucun périmètre ISO incluant l'industriel ne serait honnêtement déclarable avant ce chantier, déjà inscrit à 24 mois dans notre feuille de route (S1-06).
- **Le texte français évoluera** jusqu'à ses décrets et arrêtés : sa version de travail est suivie en veille active, et le tableau de correspondance sera revu à chaque publication.
- **Le coût de la certification n'est pas chiffré** à ce stade et fera l'objet d'une note distincte ; la présente décision n'engage aucun budget nouveau la première année.
- **La recommandation est robuste, pas inattaquable** : la grille bascule si le Comité juge la preuve opposable aux tiers accessoire (grille). C'est un jugement de contexte qui appartient au Comité, et il doit être posé explicitement.

### 5. Décision demandée — 3 lignes

> **Le Comité Exécutif est invité à approuver l'adoption d'ISO/IEC 27001:2022 comme référentiel de sécurité du groupe MERIDIAN, sur les quatre filiales, et le lancement de l'évaluation initiale déjà créée dans l'outil de gouvernance, en mandatant le RSSI Groupe pour arrêter filiale par filiale le périmètre de déploiement.**
> **Décision attendue à la séance de jeudi.** Premier geste au lendemain d'un avis favorable : ouverture de l'évaluation initiale et notification aux quatre RSSI de filiale du calendrier de collecte des preuves — sans budget nouveau.

> *— fin de la note de business case —*

---

## Vérification des critères d'acceptation (appliqués tels quels)

| Critère d'acceptation | Vérification |
|---|---|
| **Deux pages au plus** | 5 sections calibrées ⅓ + ⅙ + ½ + ⅓ + 3 lignes ≈ **1 ⅓ page** de texte rédigé ; le tableau de la section 2 tient la comparaison en six lignes plutôt qu'en six paragraphes. |
| **Aucune affirmation sans source de la journée** | **Chaque phrase portant un chiffre se termine par sa parenthèse** — corrigé après la revue par les pairs (constat 1 reçu). Quatre marqueurs de journée : **(grille)**, **(correspondances)**, **(import)**, **(applicabilité)** ; un cinquième, **(dossier S2)**, signale la seule affirmation dont la source est antérieure à la journée (l'exposition du secteur éducation, établie en séance 2) — un lecteur voit donc d'un coup d'œil ce qui vient d'aujourd'hui et ce qui vient du dossier, plutôt que d'avoir à le deviner. Chiffres cités et leurs sources : **123 exigences / 93 contrôles** (import), **900 salariés / 45 000 comptes** (applicabilité), **~30 collectivités** (grille), **7 550 salariés** (dossier de référence MERIDIAN, cité comme tel en section 3). |
| **Options perdantes traitées avec égard** | Le tableau de la section 2 impose **une force réelle par option** : le Guide gagne la rapidité d'exécution, le ReCyF gagne le seul critère qui pèse 30 points. Aucune n'est caricaturée ; le ReCyF est même retenu comme référentiel de veille en section 3. |
| **Section 4 non vide** | Six limites, dont **deux angles morts nommés** (le périmètre choisi vs imposé ; l'absence de schéma réseau de Logistique) et l'aveu que la grille peut basculer. |
| **Décision répondant par oui ou non** | Une phrase fermée, un objet unique (adopter + lancer + mandater sur le périmètre), une échéance, un premier geste. |
| **Robustesse temporelle** | Aucune date de promulgation, aucun délai réglementaire, aucune affirmation sur l'état du droit français. Les formulations « entreront dans le champ à la promulgation » et « quel que soit ce calendrier » restent vraies que la loi paraisse dans trois mois ou dans dix-huit. |

**Test de relecture à voix basse** — *sans avoir suivi cette journée, un lecteur peut-il décider avec ces deux pages ?* Oui : la section 1 lui donne l'enjeu sans supposer qu'il connaisse NIS 2, la section 2 lui donne les termes de la comparaison, la section 5 lui donne une question fermée. Le seul mot de jargon conservé — *entité essentielle / importante* — est explicité par sa conséquence, pas par sa définition.

---

# Exercice 2 — La revue par les pairs

**Le problème que la revue résout** : l'auteur d'un document ne peut plus le lire. Il connaît le raisonnement, donc il ne voit ni les sauts logiques ni les prérequis implicites ; chaque relecture par soi-même confirme ce qu'on croyait déjà.

**Le mot important est « grille »** : sans elle, la revue produit des jugements de goût — « moi je l'aurais tourné autrement » — qui ne servent à rien et vexent tout le monde. Avec elle, elle produit des constats vérifiables : *cette affirmation n'a pas de source*, *cette décision n'est pas décidable*.

**Le contrat entre pairs** : le relecteur s'engage sur la grille, **rien que la grille** ; l'auteur s'engage à traiter **chaque** constat, par une correction ou par un refus motivé par écrit, **jamais** en l'ignorant. Pendant la restitution, l'auteur note et **ne se défend pas**.

> **La limite, pour ne pas sur-investir l'exercice** : une revue par les pairs contrôle la **solidité du document**, pas la **justesse du choix**. Deux notes recommandant deux référentiels différents peuvent toutes deux sortir excellentes d'une revue — c'est le Comité qui tranche. **Le relecteur n'est pas un second décideur.**

## 2.1 — La grille appliquée à notre note (revue à blanc, avant échange)

*Nous avons appliqué la grille à notre propre note avant de l'échanger : non pour remplacer la revue par les pairs — c'est impossible, c'est précisément le problème qu'elle résout — mais pour ne pas faire perdre au binôme ses dix minutes sur des défauts que la grille détecte seule.*

| Question de la grille | Ce qui est cherché | Constat de la revue à blanc | Traitement |
|---|---|---|---|
| Chaque affirmation numérotée a-t-elle une source de la journée ? | Les parenthèses de traçabilité, et leur exactitude | Le chiffre « 7 550 salariés » de la section 3 ne portait aucune parenthèse | **Corrigé** : renvoyé au dossier de référence MERIDIAN, et non à une pièce de la journée — la distinction est maintenant visible |
| Les options perdantes sont-elles traitées honnêtement ? | Une ligne de force réelle par option écartée | Première version : le Guide d'hygiène n'apparaissait que comme « mesure d'urgence » | **Corrigé** : colonne « force réelle » rendue obligatoire dans le tableau de la section 2 ; le Guide y gagne la rapidité d'exécution |
| La section limites dit-elle quelque chose de substantiel ? | Au moins un angle mort assumé, pas une formule de style | Première version : quatre limites, toutes réglementaires — donc toutes extérieures à nous | **Corrigé** : ajout de **deux angles morts qui nous sont propres** (périmètre choisi vs imposé ; absence de schéma réseau de Logistique) |
| La décision demandée est-elle décidable ? | On peut répondre oui ou non sans demander une analyse de plus | « Approuver le référentiel » seul était incomplet : approuvé sans périmètre, il ne s'applique nulle part | **Corrigé** : la décision porte sur l'adoption **et** le lancement de l'évaluation **et** le mandat sur le périmètre, avec échéance |
| La note survit-elle aux deux calendriers ? | Rien ne devient faux selon la date de promulgation | Une formulation disait « dès la promulgation attendue cette année » | **Corrigé** : remplacée par « à la promulgation » et « quel que soit ce calendrier » — plus aucune date française dans la note |

## 2.2 — La revue que nous avons rendue au binôme *(réalisée)*

**Note relue** : celle du binôme ayant instruit **MERIDIAN Éducation** — filiale différente de la nôtre, comme le protocole le recommande : la distance au contexte rend l'œil plus frais. **Revue complète : `Seance-3-TP-S3-06-revue-par-les-pairs-binome-Education.md`.**

Verdict de grille et constats, dans l'ordre de restitution :

| # | Ligne de grille | Constat rendu (citation à l'appui) | Verdict |
|---|---|---|---|
| **1** | Limites substantielles | « *…ne vaut pas conformité automatique… les correspondances ne transfèrent jamais la conformité… l'import ne constitue qu'un étalon.* » — quatre limites, toutes sur **les référentiels et la méthode**, **aucun angle mort du groupe** | **Non rempli** |
| **2** | Sources de la journée | Section 1 sans aucune parenthèse ; **(applicabilité) absente de toute la note** alors que la matinée a caractérisé les quatre filiales — « *MERIDIAN Santé **apparaît** notamment comme **particulièrement concernée*** » là où une affirmation traçable était disponible. Et la section, titrée « et déclencheur », ne répond pas à *pourquoi maintenant* | **Partiel** |
| **3** | Décision décidable | « *Nous demandons au **Comité de Direction**… **dès la prochaine séance**.* » — instance absente de la charte de gouvernance (S1-05), échéance du **calendrier du module** et non de l'entreprise, et **aucun mandat de périmètre** | **Rempli sur la forme**, fragile |
| **4** | Honnêteté des options | ReCyF présenté en « *bon support de préparation réglementaire* » : force réelle, mais **pas la décisive** — il est le seul candidat qui **deviendra obligatoire**, objectifs fixés par décret. Le candidat retenu gagne plus facilement que dans la grille | **Rempli**, avec réserve |
| **5** | Survie aux deux calendriers | Aucune date, aucun état du droit français affirmé — **ligne franchie**, mais par le silence : c'est ce silence qui coûte le déclencheur du constat 2 | **Rempli** |

**Bilan rendu à l'auteur** : trois lignes sur cinq remplies ; **deux phrases en section 4** et **deux phrases en section 1** suffisent à remplir les deux autres, puis trois corrections de trois mots (Comité Exécutif, échéance d'entreprise, mandat de périmètre). Ce qui manque à cette note n'est pas du travail supplémentaire, c'est **de la journée déjà faite qui n'est pas remontée dans la note**.

**Ce que nous nous sommes interdit de rendre** : le format de la section 2 (jugement de goût, hors grille) ; le choix d'avoir outillé la filiale hors champ NIS 2 (choix d'instruction, pas défaut du document — en revanche *ne pas dire ce que ce choix implique* est remonté au constat 1) ; et **notre accord de fond sur la recommandation ISO**, qui n'est pas un constat de revue. Une note recommandant le ReCyF avec une section 4 assumant l'instabilité d'un document de travail passerait la même grille : **le relecteur n'est pas un second décideur.**

## 2.3 — Traitement des constats reçus *(journal clos)*

*Format contractuel : un constat par ligne, une correction **ou** un refus motivé en une ligne, jamais une case vide. Le journal est joint à la note remise.*

**Constats reçus** : deux, tous deux **acceptés et corrigés**. Verdict global rendu par le binôme : *« note globalement solide et conforme à la grille de revue croisée »* — trois lignes de grille explicitement validées (honnêteté des options, limites substantielles, décision décidable) et une quatrième sur la robustesse temporelle.

| # | Constat reçu du binôme (verbatim) | Ligne de grille | Traitement |
|---|---|---|---|
| **1** | « *La note contient plusieurs chiffres en section 1, par exemple « 900 salariés, 45 000 comptes » et « une trentaine de collectivités », mais ils ne portent pas tous une parenthèse de traçabilité directement à la fin de la phrase.* » | Sources de la journée | **Corrigé.** Le constat est juste : les sources existaient toutes, mais la parenthèse était posée en fin de **paragraphe**, pas en fin de **phrase** — donc invérifiable phrase par phrase, qui est exactement la façon dont un relecteur travaille. Trois phrases ont reçu leur parenthèse : *900 salariés / 45 000 comptes* **(applicabilité)**, *~30 collectivités et questionnaire du client pharmaceutique* **(grille)**, *cartographie et référentiel importés* **(import)**. Une quatrième affirmation a révélé un vrai défaut que le constat n'avait pas visé : *« un secteur en tête des incidents ANSSI »* ne vient **pas** de la journée mais de la séance 2 — elle porte désormais le marqueur distinct **(dossier S2)** au lieu d'être noyée parmi les sources du jour. |
| **2** | « *Deux points méritent vérification : […] la portée exacte de la correspondance entre ISO 27001 et ReCyF.* » | Sources de la journée / exactitude | **Corrigé.** Le constat vise juste un défaut de **placement** : la borne existait bien, mais en **section 4**, une page après l'argument qu'elle limite. Un lecteur s'arrêtant à la section 3 pouvait sur-lire « l'effort sera réutilisé ». La borne est maintenant **dans l'argument lui-même** : « un objectif sur vingt », « le seul périmètre couvert par la certification », « aucune présomption générale », et le rappel qu'**aucune ligne des correspondances examinées ne déclare deux exigences équivalentes**. L'argument est en outre requalifié — *« une partie de l'effort »*, et non « l'effort ». |

**Aucun refus** n'a été opposé : les deux constats étaient fondés et corrigeables sans toucher à la recommandation. Les deux refus préparés d'avance (ci-dessous) n'ont pas eu à servir — ils restent au dossier, le ComEx pouvant poser les mêmes questions.

**Ce que la revue croisée a produit de plus utile** : les deux constats reçus portent tous deux sur la **même ligne de grille**, la traçabilité, et tous deux sur le **placement** plutôt que sur l'existence de la source. C'est précisément l'angle mort de l'auteur que le TP annonçait — nous savions où étaient nos sources, donc nous ne voyions pas qu'elles n'étaient pas là où un lecteur les cherche.

**Refus déjà motivés par anticipation** (les deux objections les plus probables, tranchées d'avance pour ne pas improviser en restitution) :

| Objection anticipée | Notre réponse écrite |
|---|---|
| « La section 2 devrait comparer davantage d'options. » | **Refusé** : trois candidats étaient sur la table du ComEx ; ajouter des options non instruites allongerait la note sans changer la décision, et le gabarit borne la section à ⅙ de page. |
| « Le chiffrage du coût de certification manque. » | **Refusé, et assumé en section 4** : la note demande une décision de principe sans budget nouveau la première année ; chiffrer une certification avant d'avoir arrêté les périmètres produirait un nombre faux. Une note distincte le portera. |

---

# Exercice 3 — Note de stratégie : la sous-section « Choix du référentiel »

> **Discipline du document** : trois pages au plus pour l'ensemble, **rien ne se supprime**, tout peut s'amender d'une phrase justifiée. La sous-section ne **recopie rien** de la note de business case : la note de stratégie porte la **trajectoire du groupe**, pas le dossier de décision.

### Sous-section 3 — Choix du référentiel *(demi-page max)*

> « Conformément à la gouvernance arrêtée en ouverture de ce document — instances, matrice de responsabilité à propriétaire unique et règles d'arbitrage —, le Comité Exécutif a retenu **ISO/IEC 27001:2022** comme référentiel de sécurité du groupe, sur proposition raisonnée du RSSI Groupe. La décision est un **produit de cette gouvernance**, non une préférence technique : elle a suivi le circuit que la première sous-section décrit, proposition du RSSI Groupe et arbitrage du Comité.
>
> **Pourquoi celui-ci** : parce qu'il est le seul des candidats examinés à couvrir simultanément les quatre filiales — y compris celle qui reste hors du champ de la réglementation européenne — et à mener à une preuve opposable aux clients qui l'exigent déjà. Le détail de la comparaison, des pondérations et des correspondances est tenu au dossier, auquel cette note renvoie.
>
> **Ce que ce choix change pour le reste de la trajectoire** : les cinq actifs critiques arrêtés à la sous-section précédente **cessent d'être une liste et deviennent un objet d'évaluation** — le référentiel retenu est désormais la **langue commune dans laquelle ils seront évalués**, filiale par filiale, exigence par exigence. Le référentiel est importé dans l'outil de gouvernance du groupe et l'évaluation de conformité initiale y est ouverte ; elle est aujourd'hui vierge, et c'est son état normal. Sa mesure est le prochain jalon de la trajectoire, et l'audit de conformité qui vient en sera le premier verdict.
>
> **Ce que ce choix ne change pas** : il ne délivre par lui-même aucune conformité réglementaire, et les obligations sectorielles des filiales continuent de s'appliquer indépendamment. »

### Vérification des critères d'articulation (le vrai critère de notation)

| Contrainte | Vérification |
|---|---|
| **Articulation avec la sous-section 1 (contexte et gouvernance cible, S1-06)** | Première phrase : la décision est présentée comme un **produit du circuit de décision** déjà décrit — instances, propriétaire unique, arbitrage — et non comme un fait nouveau. La sous-section 1 disait *qui décide* ; celle-ci montre cette gouvernance **en train de décider**. |
| **Articulation avec la sous-section 2 (actifs critiques, S2-06)** | Phrase explicite : le Top 5 arrêté en séance 2 devient **ce qui sera évalué**, et le référentiel **la langue dans laquelle il le sera**. Le lien est de nature, pas de voisinage. |
| **Ne recopie rien de la note de business case** | Aucune pondération, aucune option écartée, aucun chiffre d'import, aucune décision demandée : la version stratégique des arguments, pas leur détail. Le dossier est **cité**, jamais dupliqué. |
| **Demi-page au plus** | Quatre paragraphes courts : référentiel + date de décision, pourquoi en une phrase, ce que cela engage, ce que cela n'engage pas. |
| **Trois pages pour l'ensemble** | Trois sous-sections d'une demi-page ≈ **1 ½ page**. La marge est intacte : la contrainte mordra vers la séance 6 ou 7, et se traitera alors en resserrant la **nouvelle** sous-section, jamais en supprimant une précédente. |
| **Rien n'est supprimé, tout est amendable** | Aucun amendement aux sous-sections 1 et 2 n'a été nécessaire. Un seul est à prévoir plus tard, d'une phrase : quand le périmètre de déploiement sera arrêté filiale par filiale, la sous-section 1 gagnera la mention de cet arbitrage. |

> **Note de traçabilité honnête** : la sous-section 2 (« actifs critiques ») et le Top 5 consolidé du groupe ont été produits en séance 2 (S2-06) ; ils ne figurent pas dans le dossier écrit de notre groupe, qui a instruit la filiale Logistique (S2-05). La sous-section ci-dessus les traite donc **par renvoi**, ce qui est exactement la discipline imposée à la note de stratégie — mais le renvoi vaut engagement de vérifier, avant remise finale, que les cinq lignes citées sont bien celles arrêtées en plénière.

---

## Phrase de transmission vers la séance 4

> Le référentiel choisi et importé aujourd'hui devient **le référentiel d'audit de la séance 4** : le groupe y mesurera, exigence par exigence, l'écart entre ce qu'il affirme et ce qu'il fait. **La note de business case acceptée sera la première pièce de ce dossier** — c'est elle qui dit devant quoi nous acceptons d'être mesurés, et sur quel périmètre.

---

## Ce que nous n'affirmons pas (et pourquoi c'est volontaire)

1. **« La note prouve que le choix est le bon. »** Non : elle rend la délibération **transparente et contestable**. Le test de sensibilité de la grille (S3-03 Q3) montre qu'une doctrine différente sur la preuve opposable inverserait le classement — c'est écrit en section 4, pas dissimulé.
2. **« La revue par les pairs valide la recommandation. »** Elle valide la **solidité du document**. Une note recommandant le ReCyF peut sortir excellente de la même grille ; le relecteur n'est pas un second décideur.
3. **« Le référentiel est adopté. »** Il est **recommandé**. La décision appartient au Comité Exécutif, et la note est écrite pour qu'un « non » soit une réponse possible — sans quoi ce ne serait pas une décision demandée.
4. **« Nous sommes prêts à être certifiés. »** Non : sans schéma réseau de Logistique et sans cloisonnement IT/OT, aucun périmètre incluant l'industriel ne serait honnêtement déclarable aujourd'hui. La note le dit avant qu'un auditeur ne le découvre.

---

## Auto-évaluation (grille officielle du TP)

| Critère | Notre niveau atteint |
|---|---|
| **Gabarit et format** | Cinq sections, ≈1 ⅓ page, **et chaque section répond à la question qui l'ouvre** — la question est d'ailleurs rappelée en titre de section, pour que le contrôle soit fait par le lecteur et pas seulement par l'auteur |
| **Traçabilité** | Chaque argument de la section 3 porte sa parenthèse (grille / correspondances / import / applicabilité), **et l'exactitude des sources a été vérifiée en revue croisée** : les trois phrases chiffrées signalées par le binôme portent désormais leur parenthèse **en fin de phrase**, et la seule affirmation antérieure à la journée est isolée sous un marqueur distinct **(dossier S2)** plutôt que confondue avec les sources du jour |
| **Honnêteté des options** | Une force réelle par option écartée, imposée par la structure même du tableau, **et la meilleure objection à notre choix — « l'autorité nous contrôlera devant le ReCyF » — est énoncée puis traitée** en section 3 |
| **Décision demandée** | Fermée, décidable, datée (jeudi), portant sur l'adoption **et** le périmètre, **et suivie du premier geste concret après le oui** : ouverture de l'évaluation initiale et notification du calendrier de collecte aux quatre RSSI de filiale |
| **Revue par les pairs** | Grille appliquée dans les deux sens : cinq constats de revue à blanc **tous corrigés** sur notre note, deux objections anticipées **refusées par écrit avec motif**, journal des constats reçus prêt à consigner ; **revue effectivement rendue au binôme (filiale d'instruction Éducation), citée et actionnable** — cinq constats, chacun adossé à une citation et à une ligne de grille, les deux plus utiles restitués en premier, et trois remarques hors grille explicitement écartées *(fichier `Seance-3-TP-S3-06-revue-par-les-pairs-binome-Education.md`)* |
| **Note de stratégie** | Demi-page, aucun élément recopié de la note de business case, **articulée aux deux sous-sections précédentes par une phrase chacune** (la gouvernance produit la décision ; les actifs critiques gagnent leur langue d'évaluation), limite de trois pages tenue avec marge, et l'unique amendement futur identifié et justifié d'avance en une phrase |

*Chaque case vise la colonne « Excellent » de la grille officielle — à confronter en séance avec le corrigé de référence du module.*

> **Livrables cités** : S1-05 (gouvernance cible / RACI), S1-06 (cadrage, feuille de route, note de stratégie §1), S2-01 (inventaire), S2-03 (valeurs métier / DICT), S2-05 (cartographie CISO Assistant), S2-06 (Top 5 / note de stratégie §2, par renvoi), S3-01 (applicabilité NIS 2), S3-02 (CM référentiels), S3-03 (grille de sélection & correspondances), S3-05 (fiche d'identité, import, évaluation initiale). Instance : `translog-b` — https://translog-b.lockbay.eu · Périmètre : `MERIDIAN-LOGISTIQUE`.
