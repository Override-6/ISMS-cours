# NOTE DE STRATÉGIE DE SÉCURITÉ — MERIDIAN LOGISTIQUE

**Groupe 4 (Translog)** · Miguel Monereo, Maxime Batista · filiale **MERIDIAN Logistique** · instance `translog-b`, périmètre `MERIDIAN-LOGISTIQUE`
**Version du 15 septembre 2026** · huit sous-sections, une par séance de travail

> **Objet.** Ce document répond à quatre questions, et à celles-là seules : **où en est la filiale, où
> elle doit aller, comment elle y va, ce que cela coûte.** Il n'est pas un résumé des livrables. Chaque
> sous-section s'articule aux précédentes ; rien n'y est supprimé — une sous-section qui en contredit une
> autre l'amende par une phrase datée au journal, elle ne l'efface pas.

| # | Séance | Sous-section | Question servie |
|---|---|---|---|
| 1 | S1 | Contexte et gouvernance cible | Où en est la filiale |
| 2 | S2 | Actifs critiques | Où en est la filiale |
| 3 | S3 | Choix du référentiel | Où elle doit aller |
| 4 | S4 | État des lieux | Où en est la filiale |
| 5 | S5 | Risques majeurs | Où elle doit aller |
| 6 | S6 | Tiers et projets | Comment elle y va |
| 7 | S7 | Traitement du risque | Comment, et ce que cela coûte |
| 8 | S8 | Périmètre du SMSI | Comment elle y va |

---

## Sous-section 1 — Contexte et gouvernance cible *(séance 1)*

> Le groupe MERIDIAN, quatre filiales aux métiers et obligations disjoints, s'est doté d'une gouvernance de sécurité commune : des instances dont les rôles sur l'appétence au risque sont désormais codifiés, une matrice de responsabilité à propriétaire unique par ligne, des directives de groupe et des règles d'arbitrage écrites, réunies dans la charte de gouvernance à laquelle cette note renvoie. Cette gouvernance répond aux constats de l'analyse d'écart annexée au dossier : des décisions de sécurité jusqu'ici prises sans niveau ni règle identifiés — notamment le blocage de trois mois du flux Logistique–Santé et l'absence de propriétaire du registre des comptes administrateur de Santé. Chaque filiale adapte la PSSI-cadre sous six mois ; cette adaptation constitue le premier jalon de la feuille de route triennale approuvée en principe par le Comité Exécutif.

---

## Sous-section 2 — Actifs critiques *(séance 2)*

> La gouvernance arrêtée en ouverture avait besoin de savoir **sur quoi elle règne** : la filiale a été cartographiée — quatre valeurs métier, treize biens supports, un propriétaire nommé pour chacun. La règle de tenue qui en découle — tout élément découvert hors inventaire rattaché ou traité **sous trente jours**, sa découverte valorisée plutôt que sanctionnée — est la gouvernance de la sous-section 1 appliquée au terrain, avec un délai qui la rend vérifiable.
>
> **Ce qui compte le plus.** Cinq actifs critiques sont arrêtés et justifiés au dossier, sur un critère écrit **avant** le classement : besoin de sécurité porté, portée de l'atteinte, faiblesse **connue et actuelle**, absence de substitution rapide. Deux enseignements en sortent. Le premier est de **portée** : l'atteinte de ces actifs déborde la filiale — l'arrêt du système de gestion d'entrepôt bloque 40 % du volume expédié du groupe, la rupture de la chaîne du froid se paie au contrat. Le second est de **nature** : l'un des cinq n'est ni un serveur ni un logiciel mais **une personne**, seul détenteur d'un savoir-faire écrit nulle part — le seul actif qu'aucun budget ne remplace après coup.
>
> **Ce que cela engage.** Ces cinq actifs sont ce que les risques majeurs devront viser : une analyse de risque qui les ignorerait décrirait une autre entreprise que la nôtre. La filiale assume par ailleurs six lacunes au dossier, dont l'**absence de tout schéma réseau** — c'est elle qui borne aujourd'hui ce que nous pouvons honnêtement déclarer à un tiers.

---

## Sous-section 3 — Choix du référentiel *(séance 3)*

> Sur proposition raisonnée du RSSI Groupe, le Comité Exécutif a retenu **ISO/IEC 27001:2022** comme référentiel de sécurité du groupe. La décision est un **produit de la gouvernance** de la sous-section 1, non une préférence technique : elle a suivi le circuit que celle-ci décrit, proposition du RSSI Groupe et arbitrage du Comité.
>
> **Pourquoi celui-ci** : il est le seul des candidats examinés à couvrir simultanément les quatre filiales — y compris celle qui reste hors du champ de la réglementation européenne — et à mener à une preuve opposable aux clients qui l'exigent déjà. Comparaison, pondérations et correspondances sont tenues au dossier.
>
> **Ce que ce choix change** : les actifs critiques de la sous-section 2 **cessent d'être une liste et deviennent un objet d'évaluation**, le référentiel devenant la langue commune dans laquelle ils seront évalués, filiale par filiale, exigence par exigence. Il est importé dans l'outil de gouvernance et l'évaluation de conformité initiale y est ouverte, aujourd'hui vierge — son état normal à ce stade. Sa mesure est le prochain jalon.
>
> **Ce que ce choix ne change pas** : il ne délivre par lui-même aucune conformité réglementaire, et les obligations sectorielles des filiales continuent de s'appliquer indépendamment.

---

## Sous-section 4 — État des lieux *(séance 4)*

> Le référentiel retenu connaît sa première utilisation à pleine échelle : une auto-évaluation outillée des douze exigences les plus exposées de Logistique, complétée par les constats gradés du premier cycle d'audit interne du groupe. La feuille de route de la sous-section 1 gagne ici son premier jalon mesuré. L'état tient en une phrase — **des fondations documentées, une application non prouvée, des angles morts nommés** : aucune des douze exigences n'est pleinement couverte, deux le sont partiellement, une ne l'est pas du tout faute d'avoir été posée à la filiale.
>
> **Ce que cela donne à ceux qui décident.** La gouvernance à trois niveaux avait pour objet de faire décider sur des faits plutôt que sur des impressions ; c'est le premier jeu de faits que la filiale se donne sur elle-même, et deux non-conformités majeures touchent le même système, le WMS, dont l'arrêt bloque 40 % du volume expédié du groupe. La sous-section 2 avait mesuré la portée de cinq actifs sans savoir s'ils étaient protégés : un cloisonnement réseau absent et un compte d'administration partagé avec un prestataire confirment que les lacunes alors assumées décrivaient l'état réel, sans excès de prudence.
>
> **La limite à ne pas maquiller.** Cette mesure est une auto-évaluation, pas un audit indépendant au sens retenu en sous-section 3 — il lui manque l'indépendance, et le rapport le dit explicitement. La séance 5 pondérera ces écarts par conséquence et vraisemblance ; l'approche d'homologation du WMS, cadrée mais incomplète, y trouvera son premier exhibit à combler.

---

## Sous-section 5 — Risques majeurs *(séance 5)*

> L'analyse annoncée en clôture de la sous-section 4 a été conduite selon les deux premiers ateliers d'EBIOS Risk Manager. Elle confronte les cinq actifs critiques de la sous-section 2 à ceux qui pourraient vouloir leur nuire, et retient **trois scénarios majeurs**, chacun dirigé contre l'un de ces actifs.

| Acteur | Ce qu'il ferait | Actif visé |
|---|---|---|
| Groupe cybercriminel | Chiffrer le système de gestion d'entrepôt pour arrêter l'expédition du groupe et exiger une rançon | WMS |
| Agent interne mécontent ou sur le départ | Fausser les données de préparation et emporter le savoir-faire des six entrepôts, écrit nulle part | Données de préparation · la personne |
| Concurrent | Capter les données d'exploitation et celles du client pharmaceutique pour disputer le marché | Données clients |

> Un quatrième acteur — le prestataire des automates, dont le contrat n'offre aucune réversibilité — est tenu en veille et traité en sous-section 6 : choix de méthode, pas oubli.
>
> **L'événement le plus grave du dossier** est l'arrêt non planifié de l'expédition au-delà de six heures : il bloque 40 % du volume expédié du groupe, déclenche des pénalités de 12 000 € par jour, et il est **crédible** — système centralisé sur un seul site sans secours, sauvegardes jamais restaurées, et un arrêt de ce type a déjà eu lieu en avril sans que personne ne tienne de chronologie.
>
> **Ce que l'état des lieux change à ces risques** : les deux non-conformités majeures ne sont pas seulement des écarts de conformité, elles sont le chemin qui fait passer les scénarios cybercriminel et interne du théorique au **très probable**, parce qu'elles retirent à un attaquant les deux obstacles qui le ralentiraient — la séparation des réseaux et la possibilité de savoir qui a agi.
>
> **Décision demandée à la Direction Générale** : confirmer le seuil d'acceptation dérivé de l'appétence proposée au comité — un risque **élevé** (`High` dans l'outil) est inacceptable en l'état et doit être traité avant toute mise en production ; un risque **moyen** (`Medium`) n'est toléré que daté, surveillé et confié à un propriétaire nommé ; un risque **faible** (`Low`) est accepté tel quel. C'est la gouvernance de la sous-section 1 qui parle : la Direction Générale fixe ce seuil, le Conseil d'Administration l'approuve.

---

## Sous-section 6 — Tiers et projets *(séance 6)*

> Les risques majeurs ne viennent pas tous de l'intérieur. L'écosystème du WMS a été **coté** selon l'atelier 3 : cinq parties prenantes, **deux critiques** — la tierce maintenance applicative du WMS et l'intégrateur des automates. Un scénario stratégique en ressort, coté **critique** : un groupe cybercriminel qui arrêterait l'expédition du groupe **en passant par le prestataire de maintenance** plutôt que frontalement — la position exacte d'un transporteur européen en 2017, non piraté mais ayant installé de bonne foi la mise à jour d'un fournisseur compromis : 250 à 300 millions de dollars en un trimestre.
>
> **La règle que le groupe se donne** : aucun contrat donnant accès à un actif critique de la sous-section 2 n'est signé ni renouvelé sans trois exigences vérifiables — **journalisation par utilisateur nommé, notification sous vingt-quatre heures d'une compromission chez le prestataire, réversibilité** —, opposables par la Direction Juridique **avant** signature. C'est la gouvernance de la sous-section 1 appliquée aux tiers. Première application : le contrat de maintenance du WMS, à renouvellement en novembre 2026 sans porter aucune des trois.
>
> **Les projets, ensuite.** Une exigence de sécurité posée au cadrage coûte une réunion ; la même rattrapée en production coûte un projet. Le groupe adopte **six jalons de sécurité** à critère de passage vérifiable. Premier projet passé à cette grille : la **reprise du flux de réapprovisionnement d'urgence vers MERIDIAN Santé**, bloqué depuis trois mois — ce flux que la sous-section 1 citait déjà comme une décision prise sans règle. Le cadrer comme un projet, avec la RSSI de Santé à la table dès le premier jalon, lève l'objection de Santé au lieu de la contourner.
>
> **Ce que cela engage** : la sous-section 7 chiffre le traitement de ces risques d'écosystème. Aucune des deux décisions ci-dessus ne demande de budget nouveau la première année — la règle des trois exigences est une condition de signature, pas un achat ; les six jalons, une discipline de cadrage, pas une dépense.

---

## Sous-section 7 — Traitement du risque *(séance 7)*

> **Le seuil est désormais appliqué, pas seulement approuvé.** Sur les huit scénarios du registre issu de l'atelier 4, **aucun ne reste au-dessus de la ligne** après traitement : six retombent à `Moyen`, deux à `Faible`. La filiale ne ferme aucun risque — elle les fait tous passer d'inacceptable ou tolérable-sous-condition à **tolérable-formalisé**, ce qui n'est pas la même chose, et c'est dit ici sans le maquiller.
>
> **Les décisions structurantes.** Treize mesures, organisées **par décision et non par scénario** : cinq engagent la Direction — deux avenants contractuels (intégrateur des automates, clause de sous-traitance du mainteneur du WMS), une acceptation formalisée sur la chaîne du froid signée par la Direction Générale, une acceptation simple sur la fuite vers le client pharmaceutique, et le pilotage du projet de reprise du flux Santé déjà cadré en sous-section 6 ; huit relèvent de l'exécution, dont **deux mesures transversales** qui traitent plusieurs scénarios à la fois — comptes nommés et authentification forte pour la tierce maintenance, et segmentation des réseaux bureautique et industriel, cette dernière la plus coûteuse et la plus large du plan.
>
> **Ce que cela coûte, et contre quoi.** Le plan complet vaut de l'ordre de **82 000 € par an**, à mettre en face de la fourchette du coût de l'inaction chiffrée le même jour : au minimum **12 000 €** pour une seule journée d'arrêt du WMS, un ordre de grandeur de **plusieurs millions** en cas de rançongiciel abouti. Un coût certain et borné contre une perte plausible et non bornée, qui excéderait le budget annuel du plan en une seule journée d'incident — c'est l'arbitrage que ce document porte à la Direction Financière.
>
> **Ce qui reste ouvert.** Trois points n'ont pas de réponse aujourd'hui, et chacun porte une date.

| Point ouvert | Échéance | Ce qui le lèvera |
|---|---|---|
| **RTO réel du WMS**, inconnu tant que la restauration n'a pas été testée en conditions réelles — c'est lui qui bornera la partie haute de la fourchette du coût de l'inaction | **14/11/2026** | Test de restauration, mesure engagée |
| **Résiduel du scénario porté par l'intégrateur des automates**, `Moyen` : un plancher que le traitement engagé ne fait pas disparaître, par nature de ce type de tiers | Prochaine revue, **au plus tard 12 mois** | Revue de la carte de dangerosité de l'écosystème |
| **Reprise du flux vers MERIDIAN Santé** : le résiduel visé n'est atteint qu'au sixième jalon — jusque-là le risque reste `Élevé` dans les faits, `Moyen` dans la trajectoire décidée | **14/09/2027** | Passage du jalon 6 (fin de projet) |

---

## Sous-section 8 — Périmètre du SMSI *(séance 8)*

> **Le système sait désormais sur quoi il porte.** Le périmètre du système de management est arrêté et daté : la filiale entière — six entrepôts, les quatre valeurs métier et les treize biens supports de la sous-section 2 —, six exclusions nommées et quatre interfaces déclarées, dont celle, suspendue, vers MERIDIAN Santé. **Le périmètre visé pour la certification est plus étroit, et c'est un choix assumé** : les services que reçoit le client pharmaceutique — chaîne du froid et flux du système de gestion d'entrepôt des sites E1 et E4 —, hors automatisation d'E4 jusqu'au 14 juin 2027, échéance de la segmentation des réseaux bureautique et industriel. La sous-section 2 posait que l'absence de tout schéma réseau bornait ce que la filiale peut honnêtement déclarer : c'est cette borne qui fixe l'exclusion, pas une prudence de façade.
>
> **La décision demandée** : lancer l'effort de certification sur ce périmètre, l'extension au reste du groupe restant à étudier ensuite, et répondre dès aujourd'hui au client au titre de la démarche documentée équivalente qu'autorise sa propre clause — référentiel adopté, évaluation outillée, plan de traitement daté et chiffré —, sans promettre de date de certificat.
>
> **Ce que la déclaration d'applicabilité doit à la sous-section 7** : chaque contrôle retenu y est tracé à un risque du registre ou à une exigence nommée ; une seule exclusion est prononcée, le codage sécurisé, sur une absence d'objet vérifiée — la filiale ne développe aucun logiciel.
>
> **L'état, en une phrase honnête** : quinze contrôles sur quatre-vingt-treize investigués, aucun pleinement en place ; les clauses de planification tiennent, celles du support et de la mesure sont nues. Deux chantiers en sortent désignés — le corpus documentaire et les indicateurs — ceux que la sous-section suivante doit ouvrir.

---

## Journal des amendements

*Règle : rien n'est supprimé ; toute contradiction entre deux sous-sections s'amende d'une phrase de justification, datée.*

| Date | Sous-section amendée | Amendement | Justification |
|---|---|---|---|
| — | — | Aucun amendement à ce jour | Les sous-sections 1 à 6 ne se contredisent pas. La sous-section 5 **tient** la promesse de la sous-section 2 (les risques majeurs visent les cinq actifs critiques). La sous-section 6 **tient** celle de la sous-section 5 : le prestataire des automates, « tenu en veille et traité en séance 6 avec le reste de l'écosystème », est désormais coté comme partie prenante critique — la sous-section 6 complète la 5, elle ne la corrige pas. |
| 14 sept. 2026 | Sous-section 6 | Précision, pas correction : *« aucune de ces décisions ne demande de budget nouveau la première année »* (sous-section 6) portait sur les **deux** décisions qu'elle traitait — la règle des trois exigences contractuelles et la discipline des six jalons de cadrage — pas sur l'ensemble de la trajectoire de traitement du risque. La sous-section 7 engage un budget nouveau (**≈ 82 000 €/an**) sur les mesures techniques du registre ; les deux affirmations coexistent, chacune sur son périmètre exact. |
| 15 sept. 2026 | Sous-section 8 | **Aucun amendement appelé.** Le périmètre déclaré en sous-section 8 est celui de la cartographie de la sous-section 2, sans objet ajouté ni retiré, et l'exclusion d'E4 applique la borne que cette même sous-section avait posée (l'absence de schéma réseau) ; la déclaration d'applicabilité repose sur le registre et le plan de la sous-section 7, dont elle ne modifie ni les cotations ni les montants. | Les huit sous-sections restent compatibles entre elles. |

---

## Annexe — où se prouve chaque sous-section

*Annexe : ne compte pas au budget de pages. Elle rend vérifiable la règle du module — la sous-section n affirme, la séance n du dossier prouve, l'export montre que l'objet existe dans l'outil.*

| Sous-section | Preuve au dossier (pièce 2) | Preuve d'état |
|---|---|---|
| **1** — Contexte et gouvernance cible | `Session-1/2-Labs/` — gouvernance cible (S1-05), note de cadrage (S1-06), livrable `D1` | — *(instance ouverte en séance 2)* |
| **2** — Actifs critiques | `Session-2/2-Labs/D2-cartographie-MERIDIAN-LOGISTIQUE.md` — valeurs métier, biens supports, besoins DICT, dépendances inter-filiales, Top 5 justifié, lacunes assumées, processus de mise à jour | `Session-2/3-Evidence/` |
| **3** — Choix du référentiel | `Session-3/2-Labs/` — qualification et import (S3-05), note de business case `D3` et revue par les pairs (S3-06) | `Session-3/3-Evidence/` |
| **4** — État des lieux | `Session-4/2-Labs/D4-rapport-d-audit-initial.md`, feuille de travail d'auto-évaluation (S4-05), cadrage d'homologation du WMS (S4-06) | `Session-4/3-Evidence/` · suivi des constats dans `translog-b` (*Follow-ups*) |
| **5** — Risques majeurs | `Session-5/2-Labs/D5-appreciation-initiale-des-risques.md` (cadrage, socle, sources de risque, événements redoutés, échelles justifiées), `Session-5/1-CISO-desk/` (appétence), `Session-5/4-Working-notes/` (ateliers 1 et 2) | `Session-5/3-Evidence/` · étude EBIOS RM dans `translog-b` : 17 actifs, 7 événements redoutés, 5 couples source de risque / objectif visé |
| **6** — Tiers et projets | `Session-6/2-Labs/D6-tiers-et-projets.md` (fiche projet à six jalons, exigences du contrat d'infogérance, surveillance du tiers), `Session-6/1-CISO-desk/` (seize dépendances tierces), `Session-6/4-Working-notes/` (carte de dangerosité) | `Session-6/3-Evidence/` · étude EBIOS RM : 5 parties prenantes cotées, 2 scénarios stratégiques, 1 scénario opérationnel |
| **7** — Traitement du risque | `Session-7/2-Labs/D7-plan-de-traitement-et-risque-residuel.md` (plan par décision, sept fiches d'acceptation, aucune dérogation et pourquoi, total budgétaire contre coût de l'inaction), feuille de travail du registre (S7-05), `Session-7/1-CISO-desk/` (coût de l'inaction), `Session-7/4-Working-notes/` (matrice de cotation, ligne d'acceptation) | `Session-7/3-Evidence/` · registre dans `translog-b` : 8 scénarios, contrôle qualité au vert |
| **8** — Périmètre du SMSI | `Session-8/2-Labs/D8-declaration-d-applicabilite.md` (périmètre et exclusions datées, déclaration d'applicabilité à 15 contrôles, registre des exclusions, synthèse pour la direction, écarts restants), feuille de travail de l'évaluation (S8-05), `Session-8/1-CISO-desk/` (business case de la certification) | `Session-8/3-Evidence/` · évaluation dans `translog-b` : 30 clauses et 15 contrôles d'annexe A renseignés, exclusion `A.8.28` justifiée |
