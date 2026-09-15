# Séance 4 — TD (S4-01) : The CISO's briefing — La valeur de la certification ISO 27001
### Réponses du Groupe 4 (Translog) — appliquées à **MERIDIAN Logistique**

---

## Rappel du cas

Lundi matin. **Deux messages** attendent le RSSI Groupe, et ils ne portent pas sur le même objet.

- **Le premier vient du Directeur de MERIDIAN Logistique.** Le **client pharmaceutique** — le tiers que le §3 du pack de filiale désigne, celui qui impose des **audits annuels de chaîne du froid** et des **pénalités de 12 000 € par jour d'arrêt** — a précisé sa demande, sous la forme classique d'un questionnaire qui s'ouvre ainsi : *« Êtes-vous certifiés ISO/IEC 27001 ? Si oui, joignez le certificat et son périmètre. Si non, décrivez la preuve équivalente. »* Le Directeur demande quoi répondre pour ne pas perdre le client.
- **Le second vient de la Directrice Générale**, qui a lu la note de business case de la séance 3 : *« Le comité a approuvé votre norme. Alors allons au bout : je veux le groupe certifié, toutes filiales, et vite. Dites-moi ce qui nous en empêche. »*

**L'état réel du groupe ce matin**, et c'est lui qui borne toutes les réponses : le référentiel est **choisi et approuvé** (D3), **importé** dans l'instance `translog-b`, la **cartographie** de Logistique est saisie (D2), l'**évaluation de conformité est créée et vierge** (TP S3-05) — et il n'existe **aucun état des lieux mesuré**. L'audit initial du groupe commence précisément aujourd'hui.

---

## Les trois notions posées avant l'exercice

- **La mécanique de la certification ISO/IEC 27001**, dont la séance 3 avait donné la valeur mais pas la plomberie. Elle résout un problème de **confiance à l'échelle** : n'importe quelle organisation peut déclarer « notre sécurité est bien gérée », et cette déclaration ne vaut rien précisément parce qu'elle ne coûte rien. La certification y substitue une preuve en **trois maillons** : l'organisation **applique** ; un **organisme certificateur** tiers et indépendant **audite et délivre** le certificat, engageant sa propre réputation ; et l'**accréditation surveille les certificateurs** eux-mêmes — la norme **ISO/IEC 27006**, en complément d'**ISO/IEC 17021**, fixe les exigences applicables aux organismes qui auditent et certifient les SMSI et sert de base à leur accréditation. Ce troisième maillon, invisible du client, est ce qui fait tenir l'édifice. Sa limite, déjà connue : le certificat atteste **un système de management, sur un périmètre, à une date** ; il ne garantit aucun serveur et ne remplace aucune obligation légale.
- **Le périmètre de certification**, à regarder désormais en stratège et non plus en lecteur. Le certificat couvre **ce que l'organisation a choisi d'y mettre** : une activité, un site, une filiale, un groupe entier. Ce choix est le premier arbitrage économique et politique de tout projet de certification, parce que **l'effort croît avec le périmètre, et la valeur aussi, mais pas au même rythme**. Un périmètre étroit se certifie vite et rassure moins ; un périmètre large impressionne et peut engloutir deux ans d'énergie. La conséquence pratique, en une phrase héritée de la séance 3 : *face à un certificat, lire le périmètre avant la date ; face à un projet de certification, dessiner le périmètre avant le calendrier.*
- **La valeur stratégique**, c'est-à-dire ce que le certificat change au rapport de force du groupe, en trois effets. **Effet commercial** : le certificat est une preuve opposable en appel d'offres, qui évite de répondre à cinquante questionnaires de sécurité par an, ou du moins les raccourcit. **Effet de rareté** : selon l'**AFNOR**, s'appuyant sur l'**ISO Survey**, la France comptait un peu plus de **mille organisations certifiées ISO 27001 fin 2023**, soit **trois fois plus qu'en 2019** ; être certifié reste distinctif, et la dynamique — déjà **+11 % en France et +22 % dans le monde dès 2020** — dit que les concurrents s'y mettent. **Effet interne**, le moins visible et le plus durable : l'échéance d'un audit externe discipline une organisation comme aucune note de service ne le fait. Et la limite, apprise en séance 3 et jamais assez répétée en comité : **la certification ne vaut pas conformité réglementaire** — la FAQ NIS 2 de l'ANSSI l'écrit sans détour, *« l'obtention d'une certification ISO 27001 ne permet pas, en elle-même, une conformité à NIS 2 »*. Ce que le cadre français lui accorde est plus étroit et plus utile : la possibilité de s'en prévaloir pour **un seul objectif, la gouvernance**, et **sur les seuls systèmes couverts** par la certification.

> **Réflexe de méthode.** Quand on demande au RSSI Groupe *« combien coûte une certification »* ou *« combien de temps »*, la seule réponse professionnelle avant un état des lieux mesuré est : *« cela dépend du périmètre et de l'écart entre ce que nous affirmons et ce que nous faisons, et cet écart, je saurai le mesurer cette semaine. »* **Un chiffre lancé avant l'audit initial est une dette.**

---

## Question 1 — Analyser la question du tiers

*Que cherche-t-il à obtenir en demandant le certificat ET son périmètre, et pourquoi la formule « preuve équivalente » est-elle une sortie honorable ? Trois preuves existantes qui peuvent en tenir lieu aujourd'hui.*

### Ce que le tiers cherche à obtenir

Le client pharmaceutique **transfère son risque et achète la preuve la moins chère à vérifier** : un audit que quelqu'un d'autre a payé, conduit par un tiers dont l'accréditation répond de la compétence. Il n'a ni les moyens ni la légitimité d'auditer lui-même chacun de ses prestataires logistiques ; le certificat lui permet de sous-traiter ce contrôle à l'organisme certificateur.

**Et il demande le périmètre parce qu'il connaît le certificat cosmétique.** C'est la leçon de lecture de la séance 3, appliquée dans l'autre sens : un « SMSI du siège social » est un certificat authentique qui ne couvre **pas** l'entrepôt sous température dirigée où transitent ses produits. La demande conjointe *certificat **et** périmètre* n'est donc pas une précaution de forme, c'est **la vraie question** — la première moitié ne veut rien dire sans la seconde.

### Pourquoi « preuve équivalente » est une sortie honorable

Parce que cette mention révèle ce que le tiers évalue réellement : **une réalité, pas un papier**. S'il exigeait strictement un certificat, il éliminerait mécaniquement tout prestataire en cours de démarche — y compris ceux qui sont mieux tenus que certains certifiés. En ouvrant la porte à la preuve équivalente, il accepte d'examiner **la démarche elle-même**, à condition qu'elle soit documentée et datée.

C'est une sortie **honorable**, et non une échappatoire, à une condition : que MERIDIAN produise de véritables pièces et non un discours. Une démarche existe chez nous, réelle et documentée ; un certificat, non. La réponse se construit sur cette distinction, jamais en la brouillant.

### Les trois preuves existantes, mobilisables dès aujourd'hui

| Preuve | Ce qu'elle démontre au client | Séance |
|---|---|---|
| La **cartographie de MERIDIAN Logistique** dans l'outil de gouvernance — valeurs métier, biens supports des trois natures, besoins DICT, **un propriétaire nommé par actif** | Que le prestataire **sait ce qu'il exploite** et qui en répond : la précondition de toute mesure, et ce qu'un questionnaire de sécurité cherche d'abord à établir | **S2** (D2) |
| La **note de cadrage et la gouvernance cible** — périmètre, instances et fréquences, matrice RACI à propriétaire unique, cinq directives codifiées, trois règles d'arbitrage, charte signée au niveau qui engage le groupe | Que les décisions de sécurité ont **un niveau, un propriétaire et un délai** — c'est-à-dire l'objet même des clauses 5 et 6 de la norme | **S1** (D1) |
| Le **référentiel ISO/IEC 27001:2022 adopté par le comité, importé dans l'instance, et son évaluation de conformité ouverte** sur le périmètre `MERIDIAN-LOGISTIQUE` | Que la démarche est **engagée et outillée**, pas annoncée : le référentiel est installé, l'évaluation existe et porte le nom du périmètre concerné | **S3** (D3, TP S3-05) |

*Une quatrième pièce existera ce soir — le rapport d'audit initial — et c'est la première qui portera des **chiffres**. Elle n'est pas promise au client dans la réponse d'aujourd'hui : on ne promet pas une pièce qu'on n'a pas encore lue.*

---

## Question 2 — Évaluer la demande de la Directrice Générale

*Quelles sont les deux hypothèses discutables de « le groupe certifié, toutes filiales, et vite » ?*

La phrase est flatteuse, et c'est ce qui la rend piégeuse : elle donne au RSSI Groupe exactement ce qu'il est censé vouloir. Elle contient **deux hypothèses**, chacune fausse pour une raison différente.

### Hypothèse 1 — « toutes filiales » : que le périmètre soit une ambition, alors qu'il est un arbitrage

Le périmètre n'est pas une fierté, c'est le **rapport entre un effort et une valeur**, et les deux ne croissent pas au même rythme. Le vérifier filiale par filiale suffit à démonter l'hypothèse :

- **Notre client pharmaceutique se moque totalement de la certification d'Éducation.** La valeur commerciale d'un certificat est locale : elle ne vaut que devant le tiers qui la demande, sur les services qu'il achète.
- **Santé répond d'abord de son agrément HDS** — hébergeur de données de santé — qui est une obligation, là où ISO 27001 est un choix. Lui imposer les deux chantiers de front, c'est retarder celui qui est obligatoire.
- **Territoires est gouvernée par le RGS et par les clauses de ses contrats de délégation**, dont les ~30 collectivités clientes sont les vrais prescripteurs.
- **Éducation** n'a, à ce jour, aucun tiers qui lui demande quoi que ce soit — et des moyens limités.

Quatre filiales, quatre prescripteurs différents, quatre calendriers. « Toutes filiales » n'additionne pas quatre efforts : il ajoute la **description d'un périmètre de groupe**, avec ses interfaces inter-filiales, c'est-à-dire l'objet le plus difficile du dossier — celui-là même qui est bloqué depuis trois mois entre Logistique et Santé.

### Hypothèse 2 — « et vite » : qu'on puisse dater un chantier dont on n'a pas mesuré l'écart

Notre **évaluation de conformité est vierge**. L'état des lieux commence ce matin. Nous ignorons donc, à l'heure où la question est posée, **l'écart entre ce que le groupe affirme et ce qu'il fait** — et c'est précisément cet écart, et non le périmètre seul, qui détermine la durée.

D'où la règle que nous tiendrons : **aucun calendrier ne se promet avant cette mesure.** Un chiffre lancé ce matin serait une dette contractée au nom du groupe, et elle serait réclamée — par la Directrice Générale en interne, et par le client pharmaceutique en externe, qui retient les dates bien mieux que les nuances qui les accompagnent.

---

## Question 3 — Proposer un séquencement de périmètre défendable en comité

*Quelle filiale ou quelle activité est la première candidate, et pourquoi ? Justifier par la cartographie de la séance 2 et le contexte réglementaire de chaque filiale, pas par une préférence.*

**Premier périmètre : MERIDIAN Logistique — transport et entreposage sous température dirigée, le WMS et les six entrepôts.** Trois données du dossier le désignent, et aucune n'est une préférence.

**1. La pression externe est ici, et nulle part ailleurs.** C'est la seule filiale dont un client **exige** une preuve par écrit, avec un audit annuel de chaîne du froid et des pénalités de 12 000 €/jour à l'appui. La valeur du certificat étant locale, c'est le seul endroit où elle est immédiatement encaissable.

**2. La sensibilité est établie, et par nos propres pièces.** La cartographie de la séance 2 l'écrit : l'arrêt du **WMS** au-delà de six heures bloque **40 % du volume expédié du groupe**. Certifier ce périmètre, ce n'est pas certifier la filiale la plus facile, c'est certifier celle dont l'indisponibilité coûte le plus au groupe.

**3. Le périmètre est descriptible, donc gagnable.** Il tient en une ligne — *transport et entreposage sous température dirigée, WMS et six entrepôts* — parce que la cartographie de la séance 2 en décrit les valeurs métier, les biens supports et les interfaces. **Un périmètre de certification qu'on ne sait pas décrire est un projet qui déraille** ; nous savons décrire celui-là, et nous ne savons pas encore décrire les trois autres.

### La réserve à écrire nous-mêmes plutôt que de la laisser découvrir

Deux constats de notre propre diagnostic bornent ce périmètre, et il vaut mieux les porter au comité que les laisser sortir à l'audit : **il n'existe aucun schéma réseau de Logistique**, et les réseaux bureautique et industriel ne sont **pas cloisonnés**. Aucun périmètre incluant les automates de tri n'est donc déclarable honnêtement avant ce chantier. Le contre-argument à consigner, parce qu'un comité le trouvera de toute façon : un périmètre étroit a **moins de valeur d'affichage** pour le reste du groupe — mieux vaut le dire que le laisser découvrir.

**Séquencement proposé** : Logistique d'abord, sur les services que le client achète ; extension au groupe **étudiée ensuite**, une fois l'écart mesuré et le premier certificat obtenu — c'est-à-dire une fois qu'on saura ce que coûte réellement un périmètre chez MERIDIAN.

---

## Question 4 — Corriger l'enthousiasme du Directeur Financier

*« Si nous sommes certifiés, NIS 2 est réglé, autant le budgéter comme un projet de conformité. » — La mise au point, en trois phrases, juridiquement exactes et utilisables en comité.*

> **1.** La certification ISO/IEC 27001 ne vaut pas conformité à **NIS 2**, la directive européenne sur la sécurité des réseaux et des systèmes d'information : l'ANSSI écrit qu'elle ne le permet pas en elle-même, et aucune présomption générale de conformité ne lui est accordée.
>
> **2.** Ce que le cadre français lui reconnaît est plus étroit : elle sert de **moyen acceptable pour un seul objectif, la gouvernance**, et **sur les seuls systèmes d'information couverts par le certificat** — ce qui, avec le périmètre que je propose, exclurait d'emblée les trois autres filiales.
>
> **3.** Nous budgétons donc **deux chantiers distincts** : la certification, comme un projet de **preuve vis-à-vis du marché**, et la conformité NIS 2 comme un chantier réglementaire qui ne disparaîtra pas parce que le premier aboutit.

*La correction porte sur la ligne budgétaire autant que sur le droit : classer la certification en « projet de conformité » ferait disparaître le second chantier du budget, sans que personne n'ait décidé de l'abandonner.*

---

## Question 5 — Formuler la réponse au tiers

*Sans certificat aujourd'hui, sans promettre de date, mais sans laisser la case vide.*

> **« MERIDIAN Logistique n'est pas certifiée ISO/IEC 27001 à ce jour.** Notre comité de direction a adopté cette norme comme référentiel du groupe et le déploiement a commencé : le référentiel est importé dans notre outil de gouvernance et l'évaluation de conformité de notre périmètre — transport et entreposage sous température dirigée, système de gestion d'entrepôt et six entrepôts — y est ouverte. Au titre de la **démarche documentée équivalente**, nous pouvons vous communiquer, sous accord de confidentialité, la cartographie de nos actifs et de leurs propriétaires, notre gouvernance documentée avec sa matrice de responsabilité et ses directives, ainsi que l'état de cette évaluation. **Un état des lieux mesuré est en cours** et ses conclusions vous seront transmises ; nous ne vous annoncerons **aucune date de certification** avant d'en disposer. »

**Ce que ce paragraphe fait, et pourquoi il tient** : il ne laisse pas la case vide — trois pièces datées y sont nommées ; il ne bluffe pas — la première phrase dit non ; il ne promet rien d'invérifiable — pas de date, pas de coût ; et il **distingue explicitement la démarche du certificat**, ce que le tiers saura de toute façon distinguer. Une réponse qui aurait présenté notre démarche comme un quasi-certificat aurait coûté plus cher qu'un « non » franc, parce qu'elle aurait été découverte au premier audit annuel de chaîne du froid.

---

## Ce qui entre dans la suite de la journée

| Ce que ce TD produit | Où cela sert |
|---|---|
| La distinction **démarche / certificat**, et les trois preuves équivalentes nommées | Réponse écrite au client cette semaine ; section « cadrage » de **D4**, qui doit assumer d'être une auto-évaluation sans indépendance |
| Le constat qu'**aucun écart n'est mesuré** | C'est l'objet même du TP 1 (auto-évaluation de douze exigences) et du rapport d'audit initial **D4** |
| Le **périmètre candidat** et sa réserve (pas de schéma réseau, IT/OT non cloisonnés) | Le cadrage de l'homologation du système exposé (TP 2, exercice 1), puis le **périmètre du SMSI** de `D8` en séance 8 |
| La règle **« aucune date avant la mesure »** | Tenue jusqu'au bout : la décision de certification n'est instruite qu'en séance 8, et `D8` ne porte toujours aucune date de certificat |

---

*Note collective du TD 1 de la séance 4, consolidée le 15 septembre 2026 à partir du travail de la séance du 8 septembre 2026. Les deux pages individuelles du bureau du RSSI de cette séance en traitent chacune un angle propre — Miguel sur le découplage des deux demandes (client / Direction Générale), Maxime sur l'effet disciplinant de l'échéance externe — et ne se substituent pas à cette note.*
