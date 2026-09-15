# PLAN D'ACTION — Séance 7, TP 1 : atelier 4 détaillé et registre de risques dans CISO Assistant

**Groupe 4 (Translog)** · instance `translog-b` (https://translog-b.lockbay.eu)
**Domaine** `MERIDIAN-LOGISTIQUE` (sous-domaine de `Global`) · **périmètre** `MERIDIAN-LOGISTIQUE-FINAL`
**Étude à rouvrir** : `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1`
**Source du TP** : `../../../../S7 - Sources/TP 1/Detailed Workshop 4 and Risk Register in CISO Assistant _ Lockbay Academy.pdf`
**Matière à saisir** : `../4-Working-notes/Seance-7-TD-S7-03-matrices-de-cotation-et-options-de-traitement.md` (TD 2 — les cotations, la ligne d'acceptation, les quatre décisions) · `../1-CISO-desk/Seance-7-TD-S7-01-chiffrer-le-cout-de-l-inaction.md` (TD 1 — la fourchette du coût de l'inaction) · `../../Session-5/2-Labs/D5-appreciation-initiale-des-risques.md` (**D5 fait foi** pour les échelles et le seuil) · `../../Session-6/2-Labs/D6-tiers-et-projets.md` (fiche projet et exigences tiers) · `../../Session-6/2-Labs/Seance-6-TP-S6-05-feuille-de-travail-ecosysteme-et-scenarios.md` (l'état réel de l'étude à la sortie de la séance 6)

**Ce fichier n'est pas un livrable** : c'est le mode opératoire, écrit **avant** la saisie. Le livrable de la séance 7 est **D7, plan de traitement et risque résiduel (5 points)**, assemblé au **TP 2** ; ce TP-ci fait entrer dans l'outil ce que le TD 2 a décidé sur le papier, et découvre ce que le papier n'avait pas demandé.

> **Règle de la journée, avant tout clic** : *réutiliser, jamais recréer.* L'étude existe depuis la séance 5, les 17 actifs depuis la séance 2, l'audit depuis la séance 4, les 7 événements redoutés et les 5 couples SR/OV depuis la séance 5, les **2 scénarios stratégiques, leurs 3 chemins d'attaque et le premier scénario opérationnel** depuis la séance 6. **Le registre se génère une seule fois** (atelier 5, activité 1) — pas une fois par essai. Trois familles d'objets **nouveaux** aujourd'hui : **deux scénarios opérationnels** de plus, le **registre** et ses décisions, et les **risques résiduels**.

**Durée annoncée par l'énoncé** : 25 + 20 + 25 + 20 = **90 minutes** de saisie, hors captures.

**Compte de connexion** : compte **nominatif**, jamais `admin@lockbay.eu`. Tout objet créé aujourd'hui porte un auteur nommé — c'est la moitié du coefficient individuel. **Répartition proposée**, à noter dans la feuille de travail : les deux scénarios opérationnels et leurs vraisemblances à l'un, le registre et les résiduels à l'autre, relecture croisée avant le contrôle qualité.

> ⚠️ **Le piège du jour, annoncé par l'énoncé** : *« la tentation sera de coter au vu du résultat, c'est-à-dire de partir de la gravité de ce qui arriverait »*. Les deux axes sont séparés depuis ce matin pour cette raison précise. **Un scénario catastrophique et très difficile à réaliser existe, et il se cote comme tel.**

---

## 0. État des prérequis — ce qui est prêt, ce qui ne l'est pas

| Prérequis de l'énoncé | État au dossier |
|---|---|
| **D5** — cadrage, échelles justifiées, socle, valeurs métier et biens supports de la séance 2, couples SR/OV | ✅ `../../Session-5/2-Labs/D5-appreciation-initiale-des-risques.md` |
| **Les scénarios stratégiques de la séance 6 et leurs chemins d'attaque**, notamment ceux qui passent par les tiers critiques | ✅ SS1 (2 chemins), SS2 (1 chemin) dans `translog-b` ; détail dans D6 et la feuille S6-05 |
| **Les cotations et décisions du TD de ce matin** | ✅ **TD 2 fait** : 4 scénarios cotés, ligne d'acceptation tenue, 4 options arrêtées avec porteurs et échéances |
| Un accès à l'instance, avec l'étude ouverte en séance 5 et enrichie en séance 6 | ✅ — *« Rien ne se recrée. Si un objet manque, il se retrouve là où il a été créé. »* |

**Rien ne bloque.** Contrairement aux séances 5 et 6, ce TP n'est **pas** une transcription : l'énoncé prévient que *« l'outil pose des questions que le brouillon n'avait pas posées »*, et la **note d'écart fait partie du livrable**. Ce qui se découvre devant l'écran s'écrit (§5), il ne se corrige pas en silence.

### L'état exact de l'étude avant d'ouvrir

*Relevé sur les compteurs de sortie de la séance 6 (feuille `S6-05` §7). À vérifier à l'écran avant de commencer — un écart ici est un signal, pas un détail.*

| Compteur *Summary* | Valeur attendue | Remarque |
|---|---|---|
| `Assets` | **17** | 4 primaires + 13 supports, aucun recréé depuis la séance 2 |
| `Feared events` | **7** | ER1 à ER7, tous `Selected` — **D5 fait foi**, l'énoncé du TP de la séance 6 disait « six », l'écart est tranché et documenté |
| `Audits` | **1** | `MERIDIAN - ISO/IEC 27001:2022 - initial assessment` |
| `RO/TO couples` | **5** dont **3** `Selected` | n°1 `Organized crime`, n°3 `Avenger`, n°4 `Competitor` |
| `Stakeholders` | **5** créés, **2 `Selected`** | intégrateur **12,0** · APPLICA **8,0** · Santé 1,0 · opérateur 0,5 · client pharma 0,44 |
| `Strategic scenarios` | **2** | SS1 (couple n°1 → ER1, `Critical`) · SS2 (couple n°4 → ER4, `Important`) |
| Chemins d'attaque | **3** | SS1 : `AP.01` APPLICA, `AP.02` intégrateur · SS2 : `AP.01` APPLICA |
| `Operational scenarios` | **1** | sur `AP.01` de SS1, `Very likely`, `Risk level` **`High`** |
| Atelier 5 | **vide** | état attendu avant aujourd'hui |
| Méthode de cotation de l'étude | **`Manual`** | ⚠️ **à reconfirmer** : en `Express`, l'outil recalcule la vraisemblance depuis les modes opératoires et **écrase la saisie** |

---

## 1. Étape 1 — Décliner les chemins d'attaque en scénarios opérationnels (25 min)

**Ce que l'énoncé demande** : *au minimum les deux qui passent par les parties prenantes critiques*, chaque scénario écrit comme un **enchaînement d'actions élémentaires** — connaître, rentrer, trouver, exploiter — où chaque étape **nomme un bien support de l'inventaire de la séance 2** et dit **ce qui s'y oppose aujourd'hui** : mesure du socle, cloisonnement, authentification, journalisation, **ou rien**.

**Un scénario opérationnel existe déjà** (`AP.01` de SS1, via APPLICA). La règle posée en séance 6 — *à chaque chemin d'attaque retenu correspond un scénario opérationnel* — en appelle **deux de plus**, et ce sont exactement les deux qui restent :

| À créer | Chemin | Partie prenante traversée | Événement redouté visé |
|---|---|---|---|
| **OS2** | `AP.02` de **SS1** | **Intégrateur des automates** — dangerosité **12,0**, la plus forte du groupe | **ER1** (`Critical`) |
| **OS3** | `AP.01` de **SS2** | **APPLICA Services** — dangerosité **8,0** | **ER4** (`Important`) |

> **Friction connue, à ne pas redécouvrir** (feuille `S6-05` §5) : un *Operational scenario* se crée **depuis le chemin d'attaque** (`Add operational scenario`), avec un résumé des modes opératoires. **La vraisemblance ne s'y règle pas là** : il faut ensuite ouvrir la fiche et ajouter au moins un **`Operating mode`**, qui porte son propre champ `Likelihood` — et la fiche du scénario en porte **un second, séparé** (`Edit`, « Step 2 »), que l'outil **ne synchronise pas**. **Régler les deux à la main**, sinon le triptyque `Likelihood × Severity = Risk level` ne s'affiche pas.

### OS2 — L'intégrateur des automates : la porte que personne ne regarde

*Pourquoi celui-ci d'abord : c'est la partie prenante la plus dangereuse de l'écosystème (12,0), et son contrat ne porte **ni clause de réversibilité ni aucune exigence de sécurité** (pack §3) — là où APPLICA en a au moins de faibles (`TMA-WMS-2021`, art. 5 et 6).*

| # | Action élémentaire | Bien support | Ce qui s'y oppose **aujourd'hui** |
|---|---|---|---|
| 1 | **Connaître** — l'attaquant identifie l'intégrateur comme mainteneur des automates de tri des sites E2/E3/E4, et ses techniciens comme joignables en direct (chaque chef d'entrepôt a le mobile d'un technicien et l'appelle directement, pack §3). | — *(hors périmètre)* | **Rien.** |
| 2 | **Entrer chez le tiers** — compromission d'un poste ou d'un compte de technicien de l'intégrateur. La maturité et la confiance cotées à l'atelier 3 sont les plus basses de l'écosystème. | *(non inventorié — voir §5)* | **Rien** : aucune exigence de sécurité au contrat, donc aucun engagement de l'intégrateur sur ses propres accès. |
| 3 | **Entrer chez nous** — usage de la **liaison 4G de l'intégrateur, placée hors du réseau supervisé**, installée à la demande du Responsable Exploitation « pour ne plus dépendre de l'informatique quand une machine tombe » (pack §3). | **absent de l'inventaire** — *trou de cartographie, §5* | **Rien** : hors supervision par construction, aucun journal, aucune authentification connue de la filiale. |
| 4 | **Trouver** — reconnaissance depuis les automates de tri ; le réseau industriel n'est pas segmenté du bureautique. | `LOG-SA-03` (automates E2/E3/E4), `LOG-SA-07` (entrepôts) | **Rien** — **C3** de D4, non-conformité **majeure** sur `A.8.22`. |
| 5 | **Élargir** — récupération du **secret du compte de service `LOG-SA-04`**, en clair dans un fichier de configuration, **identique sur les six entrepôts depuis 2019** ; bascule vers le WMS. | `LOG-SA-04`, `LOG-SA-01` | **Rien** — `A.5.17` non couvert (D5 §2). |
| 6 | **Exploiter** — arrêt ou altération du tri et de la préparation sur les sites automatisés, puis chiffrement du WMS et de sa base ; les six entrepôts s'arrêtent. | `LOG-SA-01`, `LOG-SA-03`, `LOG-SA-06` | **Rien de démontré** : les sauvegardes quotidiennes n'ont **jamais été restaurées** depuis la mise en service (constat 4 du pack). |
| 7 | **Rester invisible** — aucune de ces étapes ne remonte au SOC : ni les automates, ni la box 4G, ni le WMS n'y envoient de journal (pack §6). Aucune procédure d'incident n'existe (constat 6). | SOC, `LOG-SA-03` | **Rien.** |

> **Sept maillons, sept fois « rien ».** C'est la phrase à écrire dans la feuille de travail, et c'est elle qui commande la vraisemblance à l'étape 2.

### OS3 — Le concurrent, par APPLICA : exfiltration indistinguable d'une maintenance

*Objectif visé de D5, couple n°4 : obtenir les données d'exploitation et celles du client pharmaceutique (volumes, tournées, relevés de température) pour capter le marché.*

| # | Action élémentaire | Bien support | Ce qui s'y oppose **aujourd'hui** |
|---|---|---|---|
| 1 | **Connaître** — le concurrent identifie APPLICA comme détenteur contractuel des données de stock, de commande et de température (`TMA-WMS-2021`, art. 6). | `LOG-SA-10` (prestataire de TMA) | **Rien** : l'information est commerciale. |
| 2 | **Obtenir l'accès** — soit par un intervenant d'APPLICA approché ou complice, soit par un **sous-traitant d'un développement « sur devis »** (art. 2), **non déclaré et non récusable** : le contrat ne porte aucune maîtrise de la sous-traitance. | `LOG-SA-10` | **C'est le maillon qui résiste.** Le concurrent **ne détient pas** cet accès : il lui faut une complicité ou une chaîne de sous-traitance à remonter. *(Détermine la cotation — voir étape 2.)* |
| 3 | **Entrer** — session avec le **compte de domaine administrateur partagé `svc-applica`**, dont l'accès aux partages est prévu par l'article 3. | `LOG-SA-01`, `LOG-SA-10` | **Rien** : aucune authentification forte (`ACC-01` non appliqué), porteurs inconnus (**C4**, non-conformité majeure). |
| 4 | **Trouver** — extraction depuis la base du WMS : volumes, tournées, commandes du client pharmaceutique. | `LOG-SA-01` | **Rien.** |
| 5 | **Étendre** — relevés de température, via le logiciel des sondes hébergé chez le fournisseur. | `LOG-SA-05` | **Rien de vérifiable** : hébergé hors de notre maîtrise, le Responsable Qualité ne sait pas dire qui y accède (pack §3). |
| 6 | **Exploiter** — la filiale **ne peut pas produire la preuve de qui a accédé aux données** à l'audit ou au questionnaire de sécurité annoncé par le client (**ER4**) ; les données du client sont divulguées (**ER6**). | `LOG-SA-01`, `LOG-SA-05` | **Rien** : aucun journal nominatif, liste des habilités « sur demande » seulement (art. 3). |
| 7 | **Rester invisible** — l'accès étant partagé et non journalisé nominativement, **l'exfiltration est indistinguable d'une intervention de maintenance**. | SOC, `LOG-SA-10` | **Rien.** |

> **À écrire dans la description** : ER6 reste rattaché en **texte** et non en objet — le champ *Focused feared event* de SS2 n'accepte **qu'un seul** événement redouté (friction relevée en séance 6). C'est un point de traçabilité gratuit pour le correcteur.

**Critère de validation de l'énoncé** : *« le scénario opérationnel est complet quand un collègue qui ne connaît pas le dossier peut lire l'enchaînement et dire à quel endroit il faudrait agir. »* Test à faire l'un sur le scénario de l'autre **avant** de passer à l'étape 2.

---

## 2. Étape 2 — Estimer la vraisemblance, maillon par maillon (20 min)

**La règle, et c'est la difficulté du jour** : la vraisemblance ne s'estime **pas globalement, au jugé**. Elle se lit **sur le chemin réellement parcouru** — *« l'étape qui oppose le plus de résistance commande la note de l'ensemble »*. La question à chaque maillon est toujours la même : **qu'est-ce qui, ici, arrêterait quelqu'un ?**

La justification cite au moins un **signal vérifiable** — un écart de l'audit de la séance 4, une pratique observée, **la maturité et la confiance cotées à l'atelier 3 pour la partie prenante traversée**, un incident public au mode opératoire comparable. *« Une justification qui ne contient que des adjectifs n'est pas une justification. »*

| Scénario | Maillon le plus résistant | Note proposée | Justification à saisir |
|---|---|---|---|
| **OS1** *(existant)* | Aucun : sept maillons sans opposition | **V3** `Very likely` — **à vérifier à l'écran**, pas à ressaisir | Déjà justifiée en séance 6 (socle et ses limites, *pourquoi pas V4* sur l'arrêt d'avril). L'énoncé demande seulement, *pour le scénario déjà coté, de vérifier que le niveau affiché correspond à la matrice* : `Very likely × Critical` = **`High`**. |
| **OS2** | Aucun — **sept maillons, sept fois « rien »** | **V3** `Very likely` | D5 définit V3 comme *« une faiblesse **connue et actuelle** rend le scénario réalisable avec les moyens courants de la source »*. Ici : contrat de l'intégrateur **sans aucune exigence de sécurité** (pack §3), **liaison 4G hors du réseau supervisé**, réseaux IT/OT interconnectés (**C3**, majeure), secret de service en clair depuis 2019 (`A.5.17`), **aucun journal OT au SOC** (pack §6). **Cotation de la partie prenante à l'atelier 3 : dangerosité 12,0, la plus élevée de l'écosystème.** *Pourquoi pas V4* : le scénario ne s'est pas réalisé dans le périmètre et sa réalisation dépend encore d'un attaquant. |
| **OS3** | **Maillon 2** — obtenir l'accès chez APPLICA ou par sa sous-traitance | **V2** `Likely` | D5 définit V2 comme *« une faiblesse existe mais son exploitation demande un concours de circonstances **ou un accès que la source n'a pas encore** »*. C'est exactement le cas : une fois entré, le concurrent ne rencontre plus **aucune** résistance (maillons 3 à 7) — mais **il n'a pas l'accès**, et il n'achète pas d'accès initial comme le fait le crime organisé. Signal convergent : D5 cote ce couple `Partially relevant` et le retient sur une justification écrite, pas sur la pertinence calculée. **La partie prenante traversée (APPLICA, 8,0) est critique, mais sa dangerosité mesure l'exposition, pas la facilité d'y entrer pour *cette* source.** |

> **Ce que cette cotation prouve, et qu'il faut écrire** : le portefeuille **hiérarchise**. Si les trois scénarios ressortaient à V3, ce serait le signe qu'on a coté l'importance du scénario et non le chemin. OS3 est **grave et plus difficile** — c'est précisément le cas que l'énoncé décrit : *« un scénario catastrophique et très difficile à réaliser existe, et il se cote comme tel »*.

**Contrôle de cohérence avec la matrice**, à lire et non à calculer de tête :

| Scénario | Gravité *(héritée de l'ER, jamais ressaisie)* | Vraisemblance | Niveau attendu |
|---|---|---|---|
| OS1 | `Critical` (ER1) | `Very likely` | **`High`** |
| OS2 | `Critical` (ER1) | `Very likely` | **`High`** |
| OS3 | `Important` (ER4) | `Likely` | **`Medium`** |

---

## 3. Étape 3 — Constituer le registre de risques (25 min)

**Geste** : atelier 5, **activité 1** → générer l'analyse de risques depuis l'étude. **C'est le registre du périmètre, créé une seule fois.** Un scénario de risque par scénario opérationnel, **auxquels l'outil ajoute les événements redoutés sans scénario** — à coter à leur tour **au regard du socle constaté en séance 4**.

### Ce que l'outil devrait ajouter, et qu'il faut donc avoir préparé

ER1 et ER4 sont portés par les scénarios ; **restent ER2, ER3, ER5, ER6 et ER7**. Soit **3 + 5 = 8 lignes attendues** — *chiffre à vérifier, pas à forcer : si l'outil en produit un autre nombre, c'est la note d'écart qui le dit.*

| Ligne | Gravité (D5) | Vraisemblance proposée, et **pourquoi** | Niveau |
|---|---|---|---|
| **ER2** — données de préparation altérées, expéditions fausses non détectées | **G3** `Important` | **V3** — le couple n°3 (`Avenger`, initié de l'Exploitation) le vise, et le **secret du compte de service est connu de toute l'Exploitation**, en clair, inchangé depuis 2019 : faiblesse connue et actuelle, exploitable avec les moyens courants d'un initié. | **`High`** |
| **ER3** — chaîne du froid rompue ou relevés faussés (E1/E4) | **G4** `Critical` | **V2** — la faiblesse existe (logiciel des sondes hébergé chez le fournisseur, hors supervision, aucun journal, le Responsable Qualité ne sait pas dire qui y accède) mais la réalisation demande un **concours de circonstances** : défaillance ou compromission du fournisseur **et** non-détection. D5 l'annonçait comme un risque d'origine **accidentelle**, mieux couvert par la conformité que par les scénarios. | **`Medium`** *(cellule G4 × V2 — celle qu'on lit deux fois)* |
| **ER5** — réapprovisionnement d'urgence de Santé non assuré | **G4** `Critical` | **V4** `Certain` — **et c'est le constat le plus inconfortable du registre.** D5 réserve `Certain` au scénario *« qui s'est déjà réalisé dans le périmètre ou dont la réalisation ne dépend plus d'un attaquant »*, et cite nommément le **flux vers Santé bloqué depuis trois mois**. Le risque le plus certain du portefeuille est celui que **personne n'attaque**. | **`High`** |
| **ER6** — données de température et d'expédition du client divulguées | **G2** `Significant` | **V2** — même maillon résistant que OS3 (le concurrent n'a pas l'accès) ; ER6 est le second événement visé par SS2, resté en description faute de multi-sélection. | **`Low`** |
| **ER7** — savoir-faire opérationnel des six entrepôts perdu | **G3** `Important` | **V3** — `LOG-SA-09` est le **seul bien support d'une valeur métier entière**, sans support numérique ni physique ; le savoir n'est écrit nulle part, et l'arrêt d'avril l'a prouvé (personne n'a pu tenir de chronologie). **Hésitation à écrire** : V4 se défend (la réalisation ne dépend d'aucun attaquant — un départ suffit), mais le départ reste un **événement futur**, non un état constaté ; on retient **V3** et on note le débat. | **`High`** |

> **Discipline** : ces cinq vraisemblances se cotent **au regard du socle constaté en séance 4** — pas au regard de ce qu'on voudrait avoir mis en place. Chacune cite un fait du diagnostic, pas une impression.

### Les décisions — option, porteur, échéance

*L'option se prend **parmi les statuts de l'outil** — les libellés se lisent à l'écran, ils ne se supposent pas. Correspondance attendue avec les quatre familles du TD 2 : réduire · accepter · éviter · transférer ; **à confirmer, et tout écart de libellé va à la note d'écart**. Les porteurs sont pris dans la **carte du pouvoir du pack §3** : le **Directeur de la filiale** décide budget et **contrats** ; le **Responsable Informatique** (« DSI », trois personnes, sans titre de RSSI) décide réseau bureautique, postes et **comptes de domaine**, mais **ni l'OT ni les contrats** ; le **Responsable Exploitation** décide du **réseau industriel des automates**.*

| Ligne | Option | Mesures | Porteur | Échéance |
|---|---|---|---|---|
| **OS1** — WMS chiffré via APPLICA | **Réduire** | Validation préalable des mises à jour (recette + avenant) · comptes nommés + MFA pour la TMA · segmentation IT/OT · test de restauration avec mesure du RTO | **Directeur de la filiale** (avenants) · **DSI de la filiale** (recette, comptes) | 3 · 4 · 9 · 2 mois *(TD 2, ex. 3)* |
| **OS2** — automates via la liaison 4G de l'intégrateur | **Réduire** | **Raccorder ou supprimer la liaison 4G** et la faire entrer dans le réseau supervisé · **inscrire des exigences de sécurité au contrat de l'intégrateur**, qui n'en porte aucune · segmentation IT/OT *(mesure commune à OS1)* · journaux OT au SOC | **Responsable Exploitation** (la box 4G est son geste, pack §3) · **Directeur de la filiale** (contrat) · **RSSI Groupe** (SOC) | 3 · 6 · 9 · 6 mois |
| **OS3** — exfiltration par le concurrent | **Réduire** | Comptes nommés + **journalisation nominative** *(commune à OS1)* · clause de **maîtrise de la sous-traitance** (famille 5 de D6) | **DSI de la filiale** · **Directeur de la filiale** (avenant) | 4 · 6 mois |
| **ER2** — altération par un initié | **Réduire** | **Rotation du secret de service `LOG-SA-04`** : un secret par site, en coffre, avec rotation | **DSI de la filiale** | 4 mois |
| **ER3** — chaîne du froid | **Accepter** *(formellement)* | Tolérance datée : obtenir du fournisseur des sondes le **journal des accès** et sa réponse au questionnaire de sécurité **avant l'audit annuel du client** | **Responsable Qualité et chaîne du froid** ; signature **Direction Générale** | réexamen **avant l'audit client** |
| **ER5** — réapprovisionnement de Santé | **Réduire** | **La fiche projet de D6** *est* le traitement : reprise sécurisée du flux, six jalons M1-M6 à critère de passage démontré par un fait | Propriétaire unique par jalon, **déjà nommé dans D6** | M1-M6 de D6 |
| **ER6** — divulgation des données client | **Accepter** | `Low` = acceptable en l'état, porté sans mesure spécifique, **revu à la cadence trimestrielle du ComEx** | **Direction Générale** | revue trimestrielle |
| **ER7** — perte du savoir-faire | **Réduire** | Formaliser par écrit l'organisation et les procédures de préparation des six entrepôts — **la seule mesure du plan sans contenu technique, et la plus difficile à tenir** | **Direction de la filiale** (propriétaire de `LOG-SA-09` en D2) | 12 mois |

> **Trois options qui ne sont pas « réduire »** — deux acceptations formelles (ER3, ER6) — et **aucun scénario laissé ouvert**. Si l'un devait l'être en fin de séance, l'énoncé est formel : il porte **au minimum l'explication écrite de son report et le nom de qui décidera**.

**Le contrôle qualité de l'outil passé au vert fait partie du livrable.** Le lancer avant de fermer, et **capturer le résultat**.

---

## 4. Étape 4 — Coter le risque résiduel (20 min)

**Après la décision, et jamais avant** — c'est la **manipulation n° 3** du TD 2. La question : *que changent réellement les mesures ?*

> **Une résistance ajoutée sur le chemin abaisse la vraisemblance. Une réduction de ce qui serait atteint abaisse la gravité. Rarement les deux.**

| Ligne | Actuel | Ce que les mesures changent | Résiduel visé |
|---|---|---|---|
| **OS1** | `High` (G4 × V3) | La recette et les comptes nommés **ajoutent une résistance** aux maillons 3 et 4 : V3 → **V2**. La gravité ne bouge pas — le WMS reste central et mono-site. | **`Medium`** |
| **OS2** | `High` (G4 × V3) | La liaison 4G supervisée et la segmentation ferment les maillons 3 et 4 : V3 → **V2**. Gravité inchangée. | **`Medium`** |
| **OS3** | `Medium` (G3 × V2) | La journalisation nominative rend l'exfiltration **distinguable** et la clause de sous-traitance ferme la voie du sous-traitant non déclaré : V2 → **V1**. | **`Low`** |
| **ER2** | `High` (G3 × V3) | La rotation du secret par site retire l'outil de l'initié : V3 → **V2**. | **`Medium`** |
| **ER3** | `Medium` (G4 × V2) | **Aucune mesure technique** : la tolérance formalisée ne change pas l'exposition. **Le résiduel reste égal à l'actuel**, et c'est la bonne réponse. | **`Medium`** *(inchangé)* |
| **ER5** | `High` (G4 × V4) | Le flux repris sous les six jalons de D6 cesse d'être un état constaté : V4 → **V2**. Gravité inchangée — s'il retombe, l'impact est le même. | **`Medium`** |
| **ER6** | `Low` (G2 × V2) | Aucune mesure ; **inchangé**. | **`Low`** *(inchangé)* |
| **ER7** | `High` (G3 × V3) | Le savoir écrit **survit au départ** : c'est la **gravité** qui baisse, G3 → **G2**, pas la vraisemblance. **Le seul cas du registre où la mesure joue sur l'autre axe** — à écrire, c'est exactement l'illustration que l'énoncé attend. | **`Medium`** |

> **Ce que le refus de l'outil enseigne** — l'outil **refuse un résiduel supérieur au niveau actuel** et rappelle qu'un **scénario sans mesure supplémentaire garde le même niveau**. Ces refus ne sont pas une gêne : ce sont des règles de méthode rendues impossibles à contourner. **Les provoquer une fois délibérément** (tenter un résiduel supérieur sur une ligne, annuler) et **capturer le message** : c'est une pièce de note d'écart, et une phrase de soutenance.

### Confrontation à la ligne d'acceptation

**Résultat attendu : aucun résiduel ne reste `High`.** Deux conséquences, à préparer pour le TP 2 :

1. **Aucune dérogation à demander** — et l'énoncé du TP 2 exige alors qu'on l'**écrive et qu'on dise pourquoi**. Le pourquoi tient en une phrase : toutes les réductions engagées abaissent d'un cran au moins, et aucune ne laisse un scénario au-dessus de la ligne.
2. **Six lignes ressortent `Medium`** — et `Medium`, selon D5, est tolérable **uniquement formalisé** : tolérance datée, surveillée, propriétaire nommé, mesure compensatoire. **À défaut, traité comme `High`.** Ce sont donc **six fiches d'acceptation** à écrire au TP 2, pas zéro. *C'est la découverte que le brouillon du matin n'avait pas faite : le TD 2 n'avait formalisé qu'une acceptation, le registre en appelle six.*

---

## 5. La note d'écart — ce que l'outil fait découvrir

**Elle fait partie du livrable**, et l'énoncé prévient qu'*« une note d'écart vide alors que des objets manquaient »* est le signe que le critère n'est pas atteint. Deux entrées sont **déjà certaines**, écrites avant d'ouvrir l'outil ; les autres se remplissent devant l'écran.

### Trous de cartographie — biens supports absents de l'inventaire de la séance 2

*L'énoncé est explicite : **un bien support absent de l'inventaire est un trou de cartographie à noter, pas un objet à inventer**. Ne rien créer dans `Assets` aujourd'hui.*

| Bien support traversé | Où il apparaît | Pourquoi il manque, et ce que ça coûte |
|---|---|---|
| **La liaison 4G de l'intégrateur** | Maillon 3 d'**OS2** — c'est le **vecteur d'entrée** du scénario | Nommée dans le pack (§3) et dans les **lacunes assumées de D2 (n° 2)** comme plage d'adresses inconnue — mais **elle ne porte aucun `LOG-SA-xx`**. Un vecteur d'entrée qui n'est pas un actif n'a **pas de propriétaire**, donc personne pour le traiter. C'est le trou le plus coûteux du registre. |
| **Les liaisons opérateur entre E1 et E2-E6** | Maillon 5 d'**OS2**, et la propagation d'**OS1** | Le pack les nomme (« les cinq autres entrepôts s'y connectent par les liaisons opérateur ») et l'écosystème cote leur opérateur (PP4, 0,5) — mais **le lien lui-même n'est pas un actif**. `LOG-SA-12` couvre le VLAN du flux Santé, pas ces liaisons. |

> **À faire de ces deux lignes** : elles entrent au **plan de traitement de D7** comme une mesure à part entière — *« inventorier et rattacher à un propriétaire les deux biens supports découverts à l'atelier 4 »* — et elles relèvent de la **règle de tenue déjà écrite dans D2 §8** : tout élément découvert hors inventaire est rattaché **sous trente jours**, et sa découverte est **valorisée, jamais sanctionnée**. Le dossier applique sa propre règle : c'est le genre de cohérence qui se remarque.

### À remplir devant l'écran

- **Libellés divergents** — *« si un libellé cherché porte un autre nom, chercher la fonction correspondante et noter l'écart »*. Précédents : l'axe de gravité s'affiche `Impact` (séance 5), `LOG-SA-13` s'affiche « API » et non « interface » (séance 5).
- **Statuts de traitement** : les libellés réels de l'outil, face aux quatre familles *réduire / accepter / éviter / transférer*.
- **Nombre de lignes du registre** généré, face aux 8 attendues.
- **Message de refus** sur un résiduel supérieur à l'actuel (capture).
- **Contrôle qualité** : ce qu'il signale avant de passer au vert.
- **Champs sans équivalent** : le TD 2 porte une échéance de **réexamen** et une **instance signataire** pour chaque acceptation ; si l'outil n'a pas de champ pour l'une ou l'autre, le dire — elles vivront dans **D7**, comme les descriptions d'échelles vivent dans D5.

---

## 6. Ce qui n'est **pas** fait aujourd'hui, et pourquoi

- **Le plan de traitement et les fiches d'acceptation** — c'est le **TP 2** et le livrable **D7**. Le registre porte les décisions ; le plan les réorganise **par décision** et les chiffre.
- **La saisie des coûts** *build* / *run* sur les mesures appliquées — également TP 2 (section *Coût*, taux journalier de l'instance à **500 €**, à laisser tel quel).
- **Le couple SR/OV n°3** (`Avenger`) reste **sans scénario stratégique** : son chemin ne passe pas par l'écosystème. Choix de méthode posé en séance 6, **reconduit et réécrit aujourd'hui** — mais ses deux événements redoutés, **ER2 et ER7**, sont bien au registre et cotés. Le couple n'a pas de scénario ; son risque n'est pas perdu.
- **Les valeurs résiduelles des parties prenantes** (atelier 3) — elles décrivent la dangerosité après traitement des tiers ; elles se posent avec les mesures de D7, pas avant.

---

## 7. Ce qui sort de ce TP

| Destination | Ce qui part d'ici |
|---|---|
| **TP 2 — livrable `D7`** (5 pts) | Le **registre complet** : 8 lignes, chacune avec option, mesures, porteur, échéance et résiduel — les quatre exigences d'acceptation de D7 se vérifient dessus. **Six fiches d'acceptation** à écrire pour les six résiduels `Medium`, et **une phrase qui dit qu'aucune dérogation n'est demandée, et pourquoi**. Les **mesures communes** sont déjà repérées et se regrouperont au plan : segmentation IT/OT (OS1 **et** OS2), comptes nommés + journalisation (OS1 **et** OS3). La **note d'écart** fournit une mesure de plus : inventorier les deux biens supports découverts. |
| **Sous-section 7 de la note de stratégie** | Deux faits que seul ce TP produit : le risque le plus **certain** du portefeuille (**ER5**) est celui que personne n'attaque — il se traite par un **projet**, pas par une mesure technique ; et le **traitement ne referme aucun risque**, il les fait tous passer de `High` à `Medium`, c'est-à-dire de *inacceptable* à *tolérable sous condition de formalisation*. |
| **Séance 8 — déclaration d'applicabilité** | Chaque mesure du registre est formulée **en objectif vérifiable** pour pouvoir être rapprochée d'une exigence d'ISO/IEC 27001:2022 : `A.8.22` (segmentation), `A.5.19`/`A.8.2` (comptes tiers), `A.5.17` (secrets), `A.8.13`/`A.5.30` (sauvegarde, continuité), `A.8.15` (journalisation), `A.5.22` (surveillance des services fournisseurs). **Pas une seule « renforcer la sécurité des accès ».** |

---

## 8. Critères de validation de l'énoncé — la relecture avant de fermer

| Critère | Atteint quand | Signe que ce n'est pas atteint |
|---|---|---|
| **Continuité avec la séance 6** | Chaque scénario opérationnel se rattache à un **chemin d'attaque existant** | Des scénarios créés de zéro dans l'outil |
| **Ancrage dans la cartographie** | Chaque étape nomme un **bien support de l'inventaire** | Des étapes en termes génériques, sans objet nommé |
| **Échelles reprises** | Les niveaux cités sont ceux de **D5, mot pour mot** | Une échelle réinventée ou des libellés modifiés |
| **Justification des vraisemblances** | Chaque note cite un **signal vérifiable** et la cotation de la partie prenante traversée | Des adjectifs sans source |
| **Complétude du registre** | **Aucun scénario sans décision, aucune mesure sans porteur** | Des scénarios laissés ouverts sans explication |
| **Cohérence du résiduel** | Coté **après** décision, **jamais supérieur** à l'actuel | Un résiduel saisi avant les mesures |
| **Honnêteté de la note d'écart** | Les libellés divergents **et** les biens supports manquants sont notés | Une note d'écart vide alors que des objets manquaient |

---

## 9. Captures à prendre

*Nommage `S7-05-…`, dans `../3-Evidence/`. Le `README` du dossier en porte la liste et la commande de contrôle d'empreintes — **à lancer avant de fermer** : la séance 6 a livré deux paires de fichiers identiques au bit près.*

| Fichier | Ce qu'elle doit montrer |
|---|---|
| `S7-05-ex0-etude-compteurs-avant-saisie` | Les compteurs du *Summary* **avant** de commencer — la preuve que rien n'a été recréé |
| `S7-05-ex1-scenarios-operationnels-liste` | Les **trois** scénarios opérationnels, chacun rattaché à son chemin d'attaque |
| `S7-05-ex1-OS2-detail-kill-chain` | Le détail d'OS2 : l'enchaînement, les biens supports nommés, ce qui s'oppose |
| `S7-05-ex2-vraisemblances-justifiees` | Les trois vraisemblances saisies **avec** leur justification (V3 · V3 · **V2**) |
| `S7-05-ex3-registre-genere` | Le registre généré, avec les événements redoutés ajoutés par l'outil |
| `S7-05-ex3-registre-options-porteurs-echeances` | Chaque ligne avec son option, son porteur, son échéance |
| `S7-05-ex3-controle-qualite-au-vert` | Le contrôle qualité **passé au vert** |
| `S7-05-ex4-residuels-cotes` | Le résiduel par ligne, cohérent avec l'actuel |
| `S7-05-ex4-refus-outil-residuel-superieur` | Le message de refus de l'outil — la méthode rendue visible |
| `S7-05-ecart-libelles` *(si applicable)* | Tout libellé d'écran divergent relevé dans la note d'écart |

---

> **Ce que ce TP transmet à la suite.** L'étude portera un **registre complet** : des scénarios opérationnels ancrés dans les biens supports, des vraisemblances justifiées maillon par maillon, des décisions avec leurs porteurs, et des résiduels cohérents. La dernière séquence de la journée en tire le plan de traitement et le dossier **D7**, et la note de stratégie gagne sa sous-section de traitement du risque. **Garder la note d'écart sous la main** : *« un candidat qui montre ce que la méthode lui a appris est plus crédible qu'un candidat dont le dossier semble n'avoir jamais rencontré de surprise. »*
