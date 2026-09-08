# NOTE DE STRATÉGIE DE SÉCURITÉ — MERIDIAN LOGISTIQUE

**Groupe 4 (Translog)** · Miguel Monereo, Maxime · filiale d'instruction **MERIDIAN Logistique** · instance `translog-b`, périmètre `MERIDIAN-LOGISTIQUE`

> **Pièce 1 du rendu.** Ce document est le fil rouge : celui qu'un directeur général lit, et qui ouvre le dossier de soutenance. Il répond à quatre questions et à celles-là seules — **où en est la filiale, où elle doit aller, comment elle y va, ce que cela coûte**. Ce n'est pas un résumé des livrables.
>
> **Les trois règles du document.** Trois à cinq pages de texte au total (trois est la cible, cinq le plafond ; tableaux, schémas et annexes ne comptent pas). **Rien ne se supprime** : une sous-section qui en contredit une précédente l'amende d'une phrase de justification, elle ne l'efface pas. **Chaque sous-section s'articule aux précédentes** — c'est le critère de notation, pas le contenu.
>
> **Langue** : ce document est tenu en français. Le dossier (pièce 2) peut être dans l'autre langue, la consigne l'autorise ; la note, elle, ne mélange pas.

**État d'avancement : 3 sous-sections sur 9, toutes rédigées.** Les séances 4 à 9 n'ont pas encore eu lieu. Version close en séance 9, déposée en séance 10.

| # | Séance | Sous-section | Question servie | État |
|---|---|---|---|---|
| 1 | S1 | Contexte et gouvernance cible | Où en est la filiale | ✅ rédigée |
| 2 | S2 | Actifs critiques | Où en est la filiale | ✅ rédigée |
| 3 | S3 | Choix du référentiel | Où elle doit aller | ✅ rédigée |
| 4 | S4 | État des lieux | Où en est la filiale | ⏳ séance non tenue |
| 5 | S5 | Risques majeurs | Où elle doit aller | ⏳ séance non tenue |
| 6 | S6 | Tiers et projets | Comment elle y va | ⏳ séance non tenue |
| 7 | S7 | Traitement du risque | Comment, et ce que cela coûte | ⏳ séance non tenue |
| 8 | S8 | Périmètre du SMSI | Comment elle y va | ⏳ séance non tenue |
| 9 | S9 | Indicateurs et version finale | Comment nous le saurons | ⏳ séance non tenue |

**Budget de pages** : trois sous-sections rédigées d'une demi-page ≈ **1 ½ page**. La marge est intacte ; la contrainte mordra vers la séance 6 ou 7 et se traitera en resserrant la **nouvelle** sous-section, jamais en supprimant une précédente.

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

## Journal des amendements

*Règle : rien n'est supprimé ; toute contradiction entre deux sous-sections s'amende d'une phrase de justification, datée.*

| Date | Sous-section amendée | Amendement | Justification |
|---|---|---|---|
| — | — | Aucun amendement à ce jour | Les sous-sections 1, 2 et 3 ne se contredisent pas. |

**Amendement déjà identifié pour plus tard** : quand le périmètre de déploiement ISO sera arrêté filiale par filiale, la sous-section 1 gagnera une phrase mentionnant cet arbitrage — la gouvernance décrite en S1 aura alors produit une décision de plus.
