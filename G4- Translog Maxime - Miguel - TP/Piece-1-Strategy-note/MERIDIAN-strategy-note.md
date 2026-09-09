# NOTE DE STRATÉGIE DE SÉCURITÉ — MERIDIAN LOGISTIQUE

**Groupe 4 (Translog)** · Miguel Monereo, Maxime · filiale d'instruction **MERIDIAN Logistique** · instance `translog-b`, périmètre `MERIDIAN-LOGISTIQUE`

> **Pièce 1 du rendu.** Ce document est le fil rouge : celui qu'un directeur général lit, et qui ouvre le dossier de soutenance. Il répond à quatre questions et à celles-là seules — **où en est la filiale, où elle doit aller, comment elle y va, ce que cela coûte**. Ce n'est pas un résumé des livrables.
>
> **Les trois règles du document.** Trois à cinq pages de texte au total (trois est la cible, cinq le plafond ; tableaux, schémas et annexes ne comptent pas). **Rien ne se supprime** : une sous-section qui en contredit une précédente l'amende d'une phrase de justification, elle ne l'efface pas. **Chaque sous-section s'articule aux précédentes** — c'est le critère de notation, pas le contenu.
>
> **Langue** : ce document est tenu en français. Le dossier (pièce 2) peut être dans l'autre langue, la consigne l'autorise ; la note, elle, ne mélange pas.

**État d'avancement : 5 sous-sections sur 9, toutes rédigées.** Les séances 6 à 9 n'ont pas encore eu lieu. Version close en séance 9, déposée en séance 10.

| # | Séance | Sous-section | Question servie | État |
|---|---|---|---|---|
| 1 | S1 | Contexte et gouvernance cible | Où en est la filiale | ✅ rédigée |
| 2 | S2 | Actifs critiques | Où en est la filiale | ✅ rédigée |
| 3 | S3 | Choix du référentiel | Où elle doit aller | ✅ rédigée |
| 4 | S4 | État des lieux | Où en est la filiale | ✅ rédigée |
| 5 | S5 | Risques majeurs | Où elle doit aller | ✅ rédigée |
| 6 | S6 | Tiers et projets | Comment elle y va | ⏳ séance non tenue |
| 7 | S7 | Traitement du risque | Comment, et ce que cela coûte | ⏳ séance non tenue |
| 8 | S8 | Périmètre du SMSI | Comment elle y va | ⏳ séance non tenue |
| 9 | S9 | Indicateurs et version finale | Comment nous le saurons | ⏳ séance non tenue |

**Budget de pages** : cinq sous-sections rédigées ≈ **2,5 pages** (la sous-section 5 est plus longue, une demi-page). La marge se resserre ; la contrainte mordra vers la séance 6 ou 7 et se traitera en resserrant la **nouvelle** sous-section, jamais en supprimant une précédente.

---

## Sous-section 1 — Contexte et gouvernance cible *(séance 1)*

> Le groupe MERIDIAN, quatre filiales aux métiers et obligations disjoints, s'est doté d'une gouvernance de sécurité commune : des instances dont les rôles sur l'appétence au risque sont désormais codifiés, une matrice de responsabilité à propriétaire unique par ligne, des directives de groupe et des règles d'arbitrage écrites, réunies dans la charte de gouvernance à laquelle cette note renvoie. Cette gouvernance répond aux constats de l'analyse d'écart annexée au dossier : des décisions de sécurité jusqu'ici prises sans niveau ni règle identifiés — notamment le blocage de trois mois du flux Logistique–Santé et l'absence de propriétaire du registre des comptes administrateur de Santé. Chaque filiale adapte la PSSI-cadre sous six mois ; cette adaptation constitue le premier jalon de la feuille de route triennale approuvée en principe par le Comité Exécutif.

*Preuve au dossier : `Piece-2-File/Session-1/2-Labs/` — gouvernance cible (S1-05) et note de cadrage (S1-06).*

---

## Sous-section 2 — Actifs critiques *(séance 2)*

> La gouvernance arrêtée en ouverture de ce document avait besoin de savoir **sur quoi elle règne** : la filiale a donc été cartographiée — quatre valeurs métier, treize biens supports, un propriétaire nommé pour chacun. La règle de tenue qui en découle — tout élément découvert hors inventaire rattaché ou traité **sous trente jours**, et sa découverte valorisée plutôt que sanctionnée — n'est pas une consigne technique : c'est la gouvernance de la sous-section précédente appliquée au terrain, avec un délai qui la rend vérifiable.
>
> **Ce qui compte le plus.** Cinq actifs critiques ont été arrêtés et justifiés au dossier, classés selon un critère écrit **avant** le classement : le niveau de besoin de sécurité de la valeur qu'ils portent, la portée de leur atteinte, l'existence d'une faiblesse **connue et actuelle**, et l'absence de substitution rapide. Deux enseignements en sortent, et ils orientent toute la trajectoire. Le premier est de **portée** : l'atteinte de ces actifs déborde la filiale — l'arrêt du système de gestion d'entrepôt bloque 40 % du volume expédié du groupe, et la rupture de la chaîne du froid se paie au contrat. Le second est de **nature** : l'un des cinq n'est ni un serveur ni un logiciel mais **une personne**, seul détenteur d'un savoir-faire qui n'est écrit nulle part — le seul actif de la liste qu'aucun budget ne remplace après coup.
>
> **Ce que cela engage pour la suite.** Ces cinq actifs sont ce que les risques majeurs devront viser : une analyse de risque qui les ignorerait décrirait une autre entreprise que la nôtre. La filiale assume par ailleurs six lacunes au dossier, dont l'**absence de tout schéma réseau** — c'est elle qui borne aujourd'hui ce que nous pouvons honnêtement déclarer à un tiers.

*Preuve au dossier : `Piece-2-File/Session-2/2-Labs/D2-cartographie-MERIDIAN-LOGISTIQUE.md` — valeurs métier, biens supports, besoins DICT, dépendances inter-filiales, Top 5 justifié, lacunes assumées, processus de mise à jour. Preuve d'état : `Piece-2-File/Session-2/3-Evidence/`.*

---

## Sous-section 3 — Choix du référentiel *(séance 3)*

> Conformément à la gouvernance arrêtée en ouverture de ce document — instances, matrice de responsabilité à propriétaire unique et règles d'arbitrage —, le Comité Exécutif a retenu **ISO/IEC 27001:2022** comme référentiel de sécurité du groupe, sur proposition raisonnée du RSSI Groupe. La décision est un **produit de cette gouvernance**, non une préférence technique : elle a suivi le circuit que la première sous-section décrit, proposition du RSSI Groupe et arbitrage du Comité.
>
> **Pourquoi celui-ci** : parce qu'il est le seul des candidats examinés à couvrir simultanément les quatre filiales — y compris celle qui reste hors du champ de la réglementation européenne — et à mener à une preuve opposable aux clients qui l'exigent déjà. Le détail de la comparaison, des pondérations et des correspondances est tenu au dossier, auquel cette note renvoie.
>
> **Ce que ce choix change pour le reste de la trajectoire** : les actifs critiques arrêtés à la sous-section précédente **cessent d'être une liste et deviennent un objet d'évaluation** — le référentiel retenu est désormais la **langue commune dans laquelle ils seront évalués**, filiale par filiale, exigence par exigence. Le référentiel est importé dans l'outil de gouvernance du groupe et l'évaluation de conformité initiale y est ouverte ; elle est aujourd'hui vierge, et c'est son état normal. Sa mesure est le prochain jalon de la trajectoire, et l'audit de conformité qui vient en sera le premier verdict.
>
> **Ce que ce choix ne change pas** : il ne délivre par lui-même aucune conformité réglementaire, et les obligations sectorielles des filiales continuent de s'appliquer indépendamment.

*Preuve au dossier : `Piece-2-File/Session-3/2-Labs/` — qualification et import (S3-05), note de business case et revue par les pairs (S3-06). Preuve d'état : `Piece-2-File/Session-3/3-Evidence/`.*

---

## Sous-section 4 — État des lieux *(séance 4)*

> Le référentiel retenu à la sous-section précédente vient de connaître sa première utilisation à pleine échelle : une auto-évaluation outillée des douze exigences les plus exposées de Logistique, conduite dans l'instance de gouvernance, complétée par les constats gradés du premier cycle d'audit interne du groupe. La feuille de route arrêtée en sous-section 1 gagne ici son premier jalon mesuré. En une phrase, l'état est celui-ci : **des fondations documentées, une application non prouvée, des angles morts nommés** — aucune des douze exigences évaluées n'est pleinement couverte, deux le sont partiellement, et un point ne l'est pas du tout faute d'avoir été posé à la filiale.
>
> **Ce que cela donne à ceux qui décident.** La gouvernance à trois niveaux arrêtée en sous-section 1 avait pour objet de faire décider sur des faits plutôt que sur des impressions ; l'état des lieux est le premier jeu de faits de cette nature que la filiale se donne sur elle-même — deux non-conformités majeures touchent le même système, le WMS, dont l'arrêt bloque 40 % du volume expédié du groupe.
>
> **Ce que cela dit des actifs critiques.** La sous-section 2 avait mesuré la portée de cinq actifs sans savoir s'ils étaient protégés ; l'auto-évaluation vient de mesurer une partie de cette protection réelle, et le résultat — un cloisonnement réseau absent, un compte d'administration partagé avec un prestataire — confirme que les lacunes assumées en séance 2 n'étaient pas prudentes par excès, elles décrivaient l'état réel.
>
> **La limite à ne pas maquiller.** Cette mesure est une auto-évaluation, pas un audit indépendant au sens de la définition retenue en sous-section 3 — il lui manque l'indépendance, et le rapport qui l'accompagne le dit explicitement. Ce que cet état des lieux engage pour la suite : la séance 5 pondérera ces écarts par conséquence et vraisemblance dans l'analyse de risque, et l'approche d'homologation du WMS, cadrée mais incomplète, y trouvera son premier exhibit manquant à combler.

*Preuve au dossier : `Piece-2-File/Session-4/2-Labs/D4-rapport-d-audit-initial.md` (rapport d'audit initial), `Seance-4-TP-S4-05-feuille-de-travail-auto-evaluation.md` (auto-évaluation), `Seance-4-TP-S4-06-exercice1-cadrage-homologation-WMS-et-exercice3-recommandations.md` (cadrage d'homologation). Preuve d'état : `Piece-2-File/Session-4/3-Evidence/`, et suivi outillé des constats dans `translog-b` (Follow-ups).*

---

## Sous-section 5 — Risques majeurs *(séance 5)*

> L'analyse de risque annoncée en clôture de la sous-section précédente a été conduite selon les deux premiers ateliers de la méthode EBIOS Risk Manager. Elle confronte les cinq actifs critiques de la sous-section 2 à ceux qui pourraient vouloir leur nuire, et retient **trois scénarios majeurs**, chacun dirigé contre l'un de ces actifs : un **groupe cybercriminel** qui chiffrerait le système de gestion d'entrepôt pour arrêter l'expédition du groupe et exiger une rançon ; un **agent interne mécontent ou sur le départ** qui fausserait les données de préparation et emporterait le savoir-faire des six entrepôts, aujourd'hui écrit nulle part ; un **concurrent** qui capterait les données d'exploitation et celles du client pharmaceutique pour disputer le marché. Un quatrième acteur — le prestataire des automates, dont le contrat n'offre aucune réversibilité — est tenu en veille et sera traité en séance 6 avec le reste de l'écosystème ; c'est le seul des cinq actifs critiques qu'aucun des trois scénarios ne vise directement, et ce n'est pas un oubli mais un choix de méthode.
>
> **L'événement le plus grave du dossier** est l'arrêt non planifié de l'expédition au-delà de six heures : il bloque 40 % du volume expédié du groupe, déclenche des pénalités de 12 000 € par jour, et il est **crédible** — le système est centralisé sur un seul site sans secours, ses sauvegardes n'ont jamais été restaurées, et un arrêt de ce type a déjà eu lieu en avril sans que personne ne tienne de chronologie.
>
> **Ce que l'état des lieux de la sous-section 4 change à ces risques**, en une phrase : les deux non-conformités majeures — réseaux industriel et bureautique non cloisonnés, compte d'administration partagé avec un prestataire sans porteur identifié — ne sont pas seulement des écarts de conformité, ce sont le chemin qui fait passer les scénarios cybercriminel et interne du théorique au **très probable**, parce qu'elles retirent à un attaquant les deux obstacles qui le ralentiraient : la séparation des réseaux et la possibilité de savoir qui a agi.
>
> **Décision demandée à la Direction Générale** : confirmer le seuil d'acceptation dérivé de l'appétence proposée au comité — un risque **élevé** est inacceptable en l'état et doit être traité avant toute mise en production ; un risque **moyen** n'est toléré que daté, surveillé et confié à un propriétaire nommé ; un risque **faible** est accepté tel quel. C'est la gouvernance de la sous-section 1 qui parle : la Direction Générale fixe ce seuil, le Conseil d'Administration l'approuve.

*Preuve au dossier : `Piece-2-File/Session-5/2-Labs/D5-appreciation-initiale-des-risques.md` (appréciation initiale des risques — cadrage, socle, sources de risque, événements redoutés, échelles justifiées), `Piece-2-File/Session-5/1-CISO-desk/Seance-5-TD-S5-01-appetence-au-risque.md` (bureau du RSSI : appétence), `Piece-2-File/Session-5/4-Working-notes/Seance-5-TD-S5-03-ateliers-1-et-2-EBIOS-RM.md` (ateliers 1 et 2), `Piece-2-File/Session-5/2-Labs/Seance-5-TP-S5-06-echelles-et-assemblage-D5.md` (échelles et assemblage). Preuve d'état : `Piece-2-File/Session-5/3-Evidence/`, et l'étude EBIOS RM dans `translog-b` (17 actifs, 7 événements redoutés, 5 couples source de risque / objectif visé).*

---

## Journal des amendements

*Règle : rien n'est supprimé ; toute contradiction entre deux sous-sections s'amende d'une phrase de justification, datée.*

| Date | Sous-section amendée | Amendement | Justification |
|---|---|---|---|
| — | — | Aucun amendement à ce jour | Les sous-sections 1 à 5 ne se contredisent pas : la sous-section 5 **tient** la promesse de la sous-section 2 (les risques majeurs visent les cinq actifs critiques), elle ne la corrige pas. |

**Amendement déjà identifié pour plus tard** : quand le périmètre de déploiement ISO sera arrêté filiale par filiale, la sous-section 1 gagnera une phrase mentionnant cet arbitrage — la gouvernance décrite en S1 aura alors produit une décision de plus.
