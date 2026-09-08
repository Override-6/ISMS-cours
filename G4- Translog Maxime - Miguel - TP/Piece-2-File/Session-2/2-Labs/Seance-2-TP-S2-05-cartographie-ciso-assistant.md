# Séance 2 — TP (S2-05) : Entering the mapping into CISO Assistant
### Livrable du Groupe 4 (Translog), instance **translog-b**, filiale d'instruction **MERIDIAN Logistique**

> Rappel de la règle d'or de la saisie : **ne jamais entrer ce qui n'a pas été décidé sur papier.** Tout ce qui suit reprend, sans invention, les valeurs métier, biens supports et notations DICT déjà produits dans `Seance-2-TD-S2-03-valeurs-metier-DICT.md`. Ce TP ne crée pas de contenu, il **transpose**.

---

## Ce que ce TP apporte, et ce qu'il n'apporte pas

Un outil GRC (Governance, Risk, Compliance) centralise dans une base structurée unique ce qui, ce matin-là, vivait dans trois supports incompatibles (export tronqué de Santé, mémoire du Responsable Exploitation de Logistique, tableur d'Éducation & Territoires) : des objets typés, des liens navigables entre eux, des propriétaires nommés, un historique de qui a saisi quoi. **Ce qu'il ne fait jamais : penser à notre place.** Une valeur métier mal formulée reste mal formulée dans CISO Assistant — l'outil structure, il ne corrige pas la méthode.

Correspondance de vocabulaire (identique à l'ISO 27005 / EBIOS RM vus en TD) :

| Vocabulaire du TD | Objet dans CISO Assistant |
|---|---|
| Valeur métier | Actif **primaire** (primary) |
| Bien support | Actif **support**, rattaché à un actif primaire |
| Traçabilité (DICT) | Objectif de sécurité « **preuve** » |

**Nature de l'environnement à noter avant toute saisie** (réflexe du module) : disponibilité haute, intégrité moyenne, confidentialité **basse** — ce n'est pas un outil de production, seul le cas fictif MERIDIAN y est saisi, aucune donnée réelle, aucun nom de personne.

---

## Étape 1 — Créer le périmètre

**Nom (convention de groupe)** : `MERIDIAN-LOGISTIQUE`

**Description utile** (secteur + mission, sans jargon technique) :
> « Filiale logistique du groupe MERIDIAN — six entrepôts (E1 à E6), dont deux dédiés à un client pharmaceutique sous exigence de chaîne du froid — assurant la réception, la préparation et l'expédition des flux du groupe. »

**Ligne de validation à noter** : date/heure de création, auteur = Groupe 4 (Translog), instance translog-b.

*Critère rempli : le nom respecte `MERIDIAN-SUBSIDIARY`, majuscules, sans accents ; la description se comprend sans appeler l'auteur.*

---

## Étape 2 — Les actifs primaires (valeurs métier)

*Reprise exacte de l'Exercice 1 du S2-03 — 4 actifs, phrasés en langage métier, aucun mot technique.*

| Actif primaire | Description (perte, pas fonctionnement) |
|---|---|
| **Exécution des flux logistiques** | Si cet actif est atteint, l'entrepôt ne réceptionne, ne prépare ni n'expédie plus rien — un arrêt de plus de 6 heures bloque 40 % du volume expédié de tout le groupe. |
| **Maintien de la chaîne du froid** | Si cet actif est atteint, le client pharmaceutique perd la garantie de température dirigée exigée par ses audits annuels — un manquement direct au contrat, pas seulement une panne technique. |
| **Savoir-faire opérationnel des six entrepôts** | Si cet actif est atteint (perte du Responsable Exploitation), la connaissance fine de l'organisation de chaque site disparaît d'un coup, sans aucune trace écrite pour la remplacer. |
| **Conformité contractuelle avec le client pharmaceutique** | Si cet actif est atteint, la filiale échoue à son prochain audit ou questionnaire de sécurité, avec des pénalités contractuelles de 12 000 €/jour d'arrêt. |

*Vérification du piège n°1 (« business asset technique ») : le WMS, les scannettes et les automates ne figurent volontairement pas ici — ce sont des biens supports, saisis à l'étape suivante et rattachés, jamais posés en tête de liste.*

*Vérification du piège n°2 (catalog-map) : 4 actifs, pas 15 — le niveau 1 de la trajectoire de maturité de la matinée est respecté.*

---

## Étape 3 — Les biens supports, rattachés, 3 natures couvertes

*Reprise du tableau de l'Exercice 1 du S2-03, transposée en actifs « support » rattachés à leur(s) actif(s) primaire(s), avec un propriétaire pour chacun.*

| Actif support | Nature | Rattaché à | Propriétaire |
|---|---|---|---|
| WMS (2 serveurs + BDD, site E1) | Numérique | Exécution des flux logistiques | DSI filiale (3 pers.) |
| Scannettes d'entrepôt (~300, Wi-Fi) | Numérique | Exécution des flux logistiques | DSI filiale |
| Automates de tri (E2/E3/E4) | Numérique | Exécution des flux logistiques | Intégrateur des automates (exploitation) |
| Compte de service WMS↔automates | Numérique | Exécution des flux logistiques | DSI filiale *(propriétaire à réaffecter en priorité — cf. S2-03 : mot de passe unique depuis 2019)* |
| Logiciel des sondes de température (hébergé fournisseur) | Numérique | Maintien de la chaîne du froid | Responsable Qualité et chaîne du froid |
| Local serveur E1 (climatisation défaillante) | Physique | Exécution des flux logistiques | DSI filiale |
| Entrepôts E1–E6 | Physique | Exécution des flux logistiques | 6 chefs d'entrepôt |
| Chambres froides et remorques réfrigérées | Physique | Maintien de la chaîne du froid | Responsable Qualité et chaîne du froid |
| **Responsable Exploitation** | **Organisationnel** | Savoir-faire opérationnel des six entrepôts | Direction de la filiale *(actif support organisationnel unique — cf. piège n°3 ci-dessous)* |
| Prestataire TMA du WMS | Organisationnel | Exécution des flux logistiques | DSI filiale (contrat) |
| Responsable Qualité (répond aux audits) | Organisationnel | Conformité contractuelle client pharma | Direction de la filiale |

**Vérification du piège n°3 (bien support organisationnel manquant, celui qu'aucun menu ne suggère)** : le **Responsable Exploitation** est très exactement l'exemple canonique cité par le corrigé du TP — seul détenteur du savoir-faire des entrepôts d'après le constat de la séance du matin (S2-01). Il est saisi ici comme actif support organisationnel, faute de quoi la carte resterait, sur ce point précis, aussi incomplète qu'un export d'outil qui ne voit que ce qu'il a été configuré pour voir.

**Les 3 natures sont couvertes** : numérique (WMS, scannettes, automates, compte de service, logiciel de sondes), physique (local serveur, entrepôts, chambres froides), organisationnel (Responsable Exploitation, prestataire TMA, Responsable Qualité). **Aucun actif sans propriétaire.**

---

## Étape 4 — Les besoins de sécurité (DICT / objectifs de sécurité)

*Le TD (S2-03, Exercice 2) n'a noté en DICT que 2 des 4 valeurs métier retenues (« exécution des flux logistiques » et « traçabilité du fret », cette dernière n'étant pas un actif primaire distinct dans notre liste à 4). Le tableau tutoriel étant incomplet pour les 2 autres actifs, nous le complétons ici d'abord, à l'identique de l'échelle relative du TD, avant de le reporter dans l'outil — conformément à la consigne : « une table de TD vide se remplit d'abord ».*

| Actif primaire | Disponibilité | Intégrité | Confidentialité | Traçabilité (« preuve ») | Justification de la note dominante |
|---|---|---|---|---|---|
| Exécution des flux logistiques | **Très important** | **Très important** | Notable | Notable à très important | Un arrêt > 6h bloque 40 % du volume expédié du groupe (S2-03, Ex. 2) |
| Maintien de la chaîne du froid | **Très important** | **Très important** | Notable | **Très important** | Rupture de chaîne du froid = manquement contractuel direct + risque sanitaire pour le client pharma, audité chaque année |
| Savoir-faire opérationnel des six entrepôts | Notable | Notable | Notable | **Très important** *(par absence)* | Rien n'est écrit : la « traçabilité » de cet actif est aujourd'hui nulle, ce qui en fait le besoin le plus criant, pas le plus couvert |
| Conformité contractuelle client pharma | Notable | **Très important** | Notable | **Très important** | Un audit ou un questionnaire de sécurité mal répondu engage directement le contrat ; l'intégrité des preuves fournies est ce qui est vérifié |

*Vérification du piège n°2 bis (fausse précision) : notation conservée à 2 niveaux (notable / très important), comme dans le TD — même si l'outil propose une échelle plus fine, aucun niveau intermédiaire n'est inventé pour l'occasion.*

---

## Étape 5 — Le fil rouge inter-filiales, et la preuve d'état

*Rappel du dossier (S2-03, Exercice 3) : la valeur métier « réapprovisionnement d'urgence » appartient à **Santé**, mais repose sur des biens supports de **Logistique** (scannettes, système de gestion des stocks côté Santé, API, VLAN dédié, pare-feu d'inspection).*

**Ce que notre instance translog-b saisit** (les biens supports qui vivent chez nous) :

| Actif support (côté Logistique) | Description documentant la dépendance inter-filiales |
|---|---|
| Scannettes d'entrepôt (rattachées ici en second rattachement) | « Alimentent également, via l'API d'approvisionnement d'urgence, la valeur métier "réapprovisionnement d'urgence" portée par MERIDIAN Santé (instance medsecure) — flux actuellement bloqué 3 mois à la demande de Santé. » |
| VLAN dédié + pare-feu d'inspection | « Seul cloisonnement réseau du groupe ; sépare le flux Logistique→Santé décrit ci-dessus. Rattachement inter-filiale non représentable nativement dans l'outil : documenté ici en description, faute d'objet "instance croisée". » |
| API d'approvisionnement d'urgence | « Interface partagée avec l'instance Santé (medsecure) ; TLS 1.3 + MFA exigés côté urgence (cf. gouvernance cible, S1-05). » |

**Limite de l'outil, à noter pour le débrief** : chaque instance CISO Assistant étant propre à une seule filiale, l'actif primaire « réapprovisionnement d'urgence » lui-même n'existe que côté Santé (medsecure) — notre instance translog-b ne peut pas le porter, seulement documenter, **dans la description** de nos propres biens supports, qu'ils l'alimentent. C'est exactement la limite annoncée par l'énoncé : *« c'est la description qui porte le lien aujourd'hui »*. Une vraie cartographie de groupe supposerait un objet de niveau supérieur aux instances filiale — un jalon plausible pour la feuille de route triennale (S1-06) plutôt qu'un correctif de cette séance.

**Preuve d'état à produire dans translog-b** (à réaliser dans l'outil, non simulable ici) :
1. Export ou capture d'écran de la liste des actifs de `MERIDIAN-LOGISTIQUE` : 4 actifs primaires + 13 actifs support rattachés (les 11 de l'étape 3 + les 2 actifs réseau/interface de l'étape 5).
2. Export ou capture de la vue « liens » montrant chaque rattachement primaire ↔ support.
3. Horodatage + nom de l'auteur (Groupe 4) conservés — première ligne de l'historique de l'instance.

*Ce point de sortie sert directement d'entrée au prochain TP (S2-06, extraction du Top 5).*

---

## Auto-évaluation

| Critère | Notre niveau atteint |
|---|---|
| Périmètre | `MERIDIAN-LOGISTIQUE` créé selon la convention, description compréhensible sans appeler l'auteur |
| Actifs primaires | 4 actifs en langage métier (pas 3 a minima, pas 15), chacun décrit en termes de perte |
| Biens supports | 13 actifs support, 3 natures couvertes, **et** le piège de l'actif support organisationnel manquant (Responsable Exploitation) explicitement traité |
| Besoins de sécurité | DICT reporté sans précision inventée, table tutoriel d'abord complétée pour les 2 actifs non notés en TD, justification en une phrase par actif |
| Fil rouge inter-filiales | Dépendance Logistique→Santé documentée dans les descriptions, **et** la limite structurelle de l'outil (une instance = une filiale) explicitement notée pour le débrief |
| Preuve d'état | Procédure d'export/capture définie, prête à servir d'entrée au S2-06 |
| Saisie dans l'outil | Fiche complète par actif en annexe A : tous les champs du formulaire renseignés, propositions non arbitrées marquées `[À VALIDER]`, champs vides justifiés (dont `DORA specific`) |

---

# Annexe A — Fiches de saisie complètes (formulaire *Asset* de CISO Assistant)

> **Pourquoi cette annexe.** Le formulaire réel de l'outil est plus riche que le tableau du TD : il demande un ID, un domaine, une classe, un assigné, un type, **deux sens de dépendance**, des *security targets*, des *disaster recovery objectives* et un bloc *DORA specific*. La règle d'or ne change pas pour autant : **on ne saisit que ce qui a été décidé sur papier**. Chaque champ ci-dessous est donc dans l'un de ces trois états, et jamais un quatrième :
> - **valeur reprise** du S2-01 / S2-03 / S2-05 → saisie telle quelle ;
> - **proposition** non encore arbitrée → saisie préfixée `[À VALIDER]`, pour qu'un lecteur ne la confonde jamais avec une décision ;
> - **champ vide assumé** → laissé vide, avec la raison écrite ici (un champ vide documenté vaut mieux qu'un champ rempli au jugé).

## A.0 — Conventions de saisie, une fois pour toutes

| Champ du formulaire | Ce que l'outil attend | Notre règle de groupe |
|---|---|---|
| **ID** | Référence courte, unique, stable | `LOG-PA-nn` pour les actifs primaires (*Primary Asset*), `LOG-SA-nn` pour les supports (*Supporting Asset*). Numérotation dans l'ordre des étapes 2, 3 puis 5 — jamais renumérotée ensuite, même si un actif est retiré. |
| **Name** | Libellé court | Exactement le libellé des étapes 2 et 3, sans reformulation (la carte doit rester diffable d'une séance à l'autre). |
| **Description** | Texte libre | Primaire : la **perte**, pas le fonctionnement (déjà rédigé à l'étape 2). Support : nature + périmètre physique + faiblesse connue du dossier + dépendance inter-filiales le cas échéant. |
| **Domain** | Domaine/dossier propriétaire | **`Global`** — la valeur normale de l'instance. ⚠️ *Correction du 8 sept. 2026 : cette ligne demandait d'y mettre `MERIDIAN-LOGISTIQUE` et de « ne jamais laisser Global ». C'était une confusion entre deux champs distincts — le **domaine** est le dossier organisationnel, le **périmètre** est ce qui rattache l'actif à notre filiale. C'est le périmètre qui porte le cloisonnement, pas le domaine.* |
| **Class** | Liste fermée propre à l'instance | Choisir l'entrée la plus proche de la **nature** indiquée dans chaque fiche (numérique / physique / organisationnel). Si la liste ne propose aucun équivalent, **laisser vide** et garder la nature en première ligne de description — ne pas forcer un libellé pour remplir. |
| **Assigned to** | Un **compte utilisateur** de l'instance | L'environnement est en confidentialité basse et le cas est fictif : **aucun nom de personne réelle**. On assigne aux comptes du Groupe 4 (translog-b) ; le **propriétaire métier** (un rôle, jamais une personne) reste écrit dans la fiche et en tête de description. |
| **Type** | `Primary` / `Supporting` | Primaire = valeur métier (étape 2). Support = bien support (étapes 3 et 5). Aucun actif technique en primaire — c'est le piège n°1. |
| **Is a dependency of ↑** | Les actifs **soutenus par** celui-ci | Rempli **uniquement sur les actifs support** (il pointe vers le ou les primaires portés). |
| **Depends on ↓** | Les actifs qui **soutiennent** celui-ci | Laissé vide à la saisie : le lien est réciproque, l'outil le reconstitue depuis le sens ci-dessus. **Une seule passe de saisie, un seul sens** — c'est ce qui évite les doublons de liens. |
| **Security targets** | Objectifs C/I/D (+ preuve) | Renseignés **sur les actifs primaires seulement** : un besoin de sécurité est une propriété de la valeur métier, jamais de la machine qui la porte (S2-03). Sur les supports : vide, assumé. |
| **Disaster Recovery objectives** | RTO / RPO / durée max tolérée | Renseignés **seulement là où le dossier donne un chiffre**. Partout ailleurs : vide, ou `[À VALIDER]` explicite. |
| **DORA specific** | Bloc réglementaire secteur financier | **Vide partout** : MERIDIAN n'est ni une entité financière ni un prestataire TIC d'entité financière (le client sensible de la filiale est pharmaceutique). Remplir ce bloc serait de la conformité décorative. |

**Échelle des *security targets*** — le TD note en 3 niveaux (négligeable / notable / très important) et l'outil propose une échelle plus fine. Correspondance fixée **une fois** et appliquée sans exception, pour ne pas fabriquer de la fausse précision (piège n°2 bis) :

| Note du TD | Valeur saisie dans l'outil |
|---|---|
| Négligeable | niveau le plus bas de l'échelle de l'instance |
| Notable | niveau **médian** |
| Très important | niveau **le plus haut** |

*Cas « notable à très important » (traçabilité de l'exécution des flux) : on saisit **notable**, la valeur effectivement décidée, et la révision à la hausse proposée en S2-03 Q3 est écrite en description comme demande d'arbitrage. On ne saisit pas dans l'outil une décision que le comité n'a pas prise.*

---

## A.1 — Actifs primaires (4)

### LOG-PA-01 — Exécution des flux logistiques
- **Type** : Primary — **Domain** : MERIDIAN-LOGISTIQUE — **Class** : *(métier / service — le plus proche dans la liste)*
- **Description** : « Réception, préparation et expédition sur les six entrepôts E1–E6. Si cet actif est atteint, l'entrepôt ne réceptionne, ne prépare ni n'expédie plus rien — un arrêt de plus de 6 heures bloque 40 % du volume expédié de tout le groupe. Propriétaire métier : Direction de la filiale. »
- **Assigned to** : compte Groupe 4 (translog-b)
- **Is a dependency of ↑** : *(vide — actif primaire, sommet de la chaîne)*
- **Depends on ↓** : reconstitué par les liens des supports LOG-SA-01 à 04, 06, 07, 10, 12, 13
- **Security targets** : Disponibilité **très important** · Intégrité **très important** · Confidentialité **notable** · Traçabilité/preuve **notable** *(demande d'arbitrage inscrite en description : passage à « très important » proposé au vu de l'absence totale de journaux automates/WMS au SOC — S2-03 Q3)*
- **Disaster Recovery objectives** : durée max tolérée **6 h** *(fait du dossier : au-delà, 40 % du volume groupe est bloqué)* · RTO `[À VALIDER] 4 h` · RPO **24 h de fait** (sauvegardes quotidiennes) — **objectif non démontré : aucune restauration n'a jamais été testée depuis la mise en service**
- **DORA specific** : vide

### LOG-PA-02 — Maintien de la chaîne du froid
- **Type** : Primary — **Domain** : MERIDIAN-LOGISTIQUE
- **Description** : « Température dirigée en entrepôt et en transport pour le client pharmaceutique. Si cet actif est atteint, le client perd la garantie de température exigée par ses audits annuels — un manquement direct au contrat, pas seulement une panne technique. Propriétaire métier : Responsable Qualité et chaîne du froid. »
- **Is a dependency of ↑** : *(vide)* — **Depends on ↓** : LOG-SA-05, LOG-SA-08
- **Security targets** : D **très important** · I **très important** · C **notable** · Traçabilité **très important**
- **Disaster Recovery objectives** : `[À VALIDER]` — aucune durée contractuelle n'est documentée dans le dossier ; seul repère chiffré : **12 000 €/jour d'arrêt** de pénalité, qui donne un coût connu à toute interruption de plus de 24 h. RTO/RPO à fixer en comité avec le client, pas ici.
- **DORA specific** : vide

### LOG-PA-03 — Savoir-faire opérationnel des six entrepôts
- **Type** : Primary — **Domain** : MERIDIAN-LOGISTIQUE
- **Description** : « Connaissance fine de l'organisation de chaque site, aujourd'hui non écrite. Si cet actif est atteint (absence ou départ du Responsable Exploitation), elle disparaît d'un coup, sans aucune trace écrite pour la remplacer — constaté lors de l'arrêt du WMS d'avril, où personne n'a pu tenir de chronologie. Propriétaire métier : Direction de la filiale. »
- **Is a dependency of ↑** : *(vide)* — **Depends on ↓** : LOG-SA-09 *(un seul support, et c'est le constat)*
- **Security targets** : D **notable** · I **notable** · C **notable** · Traçabilité **très important** *(par absence : la traçabilité de cet actif est aujourd'hui nulle)*
- **Disaster Recovery objectives** : **sans objet, volontairement** — un savoir-faire non écrit ne se restaure pas par un plan technique ; le seul « RTO » réaliste serait le délai de réécriture d'une documentation qui n'existe pas. Écrit ici pour que le vide ne passe pas pour un oubli.
- **DORA specific** : vide

### LOG-PA-04 — Conformité contractuelle avec le client pharmaceutique
- **Type** : Primary — **Domain** : MERIDIAN-LOGISTIQUE
- **Description** : « Réponse aux audits annuels, respect des engagements de pénalité, futur questionnaire de sécurité. Si cet actif est atteint, la filiale échoue à son prochain audit ou questionnaire, avec des pénalités contractuelles de 12 000 €/jour d'arrêt. Propriétaire métier : Direction de la filiale, instruit par le Responsable Qualité. »
- **Is a dependency of ↑** : *(vide)* — **Depends on ↓** : LOG-SA-11
- **Security targets** : D **notable** · I **très important** · C **notable** · Traçabilité **très important** *(c'est l'intégrité des preuves fournies à l'audit qui est vérifiée)*
- **Disaster Recovery objectives** : sans objet (actif de conformité, pas de service à redémarrer)
- **DORA specific** : vide

---

## A.2 — Actifs support (13)

*Tous : **Type** = Supporting, **Domain** = MERIDIAN-LOGISTIQUE, **Depends on ↓** laissé vide, **Security targets** vides (portées par le primaire), **DORA specific** vide. Seuls les champs qui varient sont listés.*

| ID | Name | Nature (→ Class) | Is a dependency of ↑ | Propriétaire à écrire en description | Description : ce qui doit y figurer | DR objectives |
|---|---|---|---|---|---|---|
| LOG-SA-01 | WMS (2 serveurs + BDD, site E1) | Numérique | LOG-PA-01 | DSI filiale (3 pers.) | Cœur applicatif centralisé sur E1 ; maintenu par une TMA externe ; **sauvegardes quotidiennes jamais restaurées** ; aucun journal transmis au SOC groupe. | RPO 24 h **de fait**, non démontré ; RTO `[À VALIDER] 4 h` — hérités de LOG-PA-01 |
| LOG-SA-02 | Scannettes d'entrepôt (~300, Wi-Fi) | Numérique | **LOG-PA-01** *(+ dépendance inter-filiales, voir description)* | DSI filiale | « Alimentent également, via l'API d'approvisionnement d'urgence, la valeur métier "réapprovisionnement d'urgence" portée par MERIDIAN Santé (instance medsecure) — flux bloqué depuis 3 mois à la demande de Santé. » Le second rattachement **n'est pas représentable** dans l'outil : une instance = une filiale. | vide |
| LOG-SA-03 | Automates de tri (E2/E3/E4) | Numérique | LOG-PA-01 | Intégrateur des automates (exploitation) | Réseau OT interconnecté au bureautique, **sans cloisonnement** ; intégrateur connecté par **box 4G hors réseau supervisé** ; contrat sans clause de réversibilité ni exigence de sécurité ; aucun journal au SOC. | vide |
| LOG-SA-04 | Compte de service WMS↔automates | Numérique | LOG-PA-01 | DSI filiale — **propriétaire à réaffecter en priorité** | **Même mot de passe sur les six entrepôts depuis 2019, en clair dans un fichier de configuration, connu de « tout le monde » sur site.** Bien support le plus préoccupant de la filiale (S2-03 Ex. 1 Q3). | vide |
| LOG-SA-05 | Logiciel des sondes de température | Numérique (hébergé fournisseur) | LOG-PA-02 | Responsable Qualité et chaîne du froid | Hébergement externe ; porte la preuve de température exigée aux audits annuels du client pharmaceutique. | vide |
| LOG-SA-06 | Local serveur E1 | Physique | LOG-PA-01 | DSI filiale | Héberge le WMS ; **climatisation défaillante** ; point de concentration physique de la disponibilité de toute la filiale. | vide |
| LOG-SA-07 | Entrepôts E1–E6 | Physique | LOG-PA-01 | 6 chefs d'entrepôt | Six sites, dont **E2/E3/E4** équipés d'automates de tri et **deux dédiés au client pharmaceutique**. | vide |
| LOG-SA-08 | Chambres froides et remorques réfrigérées | Physique | LOG-PA-02 | Responsable Qualité et chaîne du froid | Température dirigée en entrepôt **et** en transport — la chaîne se rompt aussi bien à l'arrêt qu'en roulage. | vide |
| LOG-SA-09 | Responsable Exploitation | **Organisationnel** | LOG-PA-03 | Direction de la filiale | **Seul détenteur du savoir-faire des six entrepôts** ; unique bien support de LOG-PA-03, sans aucun support numérique ni physique — le point de défaillance le plus fragile du dossier (piège n°3 du TP). | vide |
| LOG-SA-10 | Prestataire TMA du WMS | Organisationnel | LOG-PA-01 | DSI filiale (contrat) | **Compte de domaine partagé**, nombre d'utilisateurs inconnu, **pas de journalisation nominative au contrat** ; séparation des comptes = jalon 12 mois de la feuille de route (S1-06). | vide |
| LOG-SA-11 | Responsable Qualité (répond aux audits) | Organisationnel | LOG-PA-04 | Direction de la filiale | Interlocuteur des audits annuels et du futur questionnaire de sécurité du client. | vide |
| LOG-SA-12 | VLAN dédié + pare-feu d'inspection | Numérique / infrastructure | LOG-PA-01 | DSI filiale | « Seul cloisonnement réseau du groupe ; sépare le flux Logistique→Santé. Rattachement inter-filiale non représentable nativement dans l'outil : documenté ici en description, faute d'objet "instance croisée". » | vide |
| LOG-SA-13 | API d'approvisionnement d'urgence | Numérique | LOG-PA-01 | DSI filiale (interface partagée avec Santé) | « Interface partagée avec l'instance Santé (medsecure) ; TLS 1.3 + MFA exigés côté urgence (gouvernance cible, S1-05). Flux bloqué depuis 3 mois. » | vide |

**Note de cohérence** : les actifs **LOG-SA-12** et **LOG-SA-13**, introduits à l'étape 5 pour porter le fil rouge inter-filiales, sont des biens supports à part entière — l'inventaire de l'instance en compte donc **13**, et non les 11 de l'étape 3 seule.

---

## A.3 — Les trois champs qu'on laisse vides, et pourquoi c'est une décision

1. **`Depends on ↓` sur les actifs primaires** — le lien est réciproque dans l'outil. Le saisir des deux côtés produirait deux fois le même lien à maintenir, et donc, à la première modification, deux versions différentes de la même carte.
2. **`Security targets` sur les actifs support** — un besoin de sécurité qualifie une valeur métier. Le porter aussi sur le support inviterait, à la séance suivante, à noter la disponibilité d'un serveur plutôt que celle du service rendu : exactement l'inversion que le TD demande d'éviter.
3. **`DORA specific` partout** — DORA s'applique aux entités financières et à leurs prestataires TIC. MERIDIAN Logistique n'est ni l'une ni l'autre. Le champ existe dans l'outil parce que l'outil sert aussi des banques ; le remplir ici produirait une conformité affichée que rien n'oblige et que personne n'auditerait — le contraire de la sélection de référentiel travaillée en séance 3.
