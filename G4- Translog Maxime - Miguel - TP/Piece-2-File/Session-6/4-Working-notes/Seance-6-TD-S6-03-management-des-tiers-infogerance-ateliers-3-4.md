# Séance 6 — TD 2 (S6-03) : Management des tiers, infogérance et ateliers 3-4 d'EBIOS RM
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN — appliquées à **MERIDIAN Logistique** (instance `translog-b`)

> Enchaînement de la journée : le TD 1 du matin a **inventorié** seize dépendances tierces et qualifié
> chacune en chemin de pivot ; le CM *Security by Design* a montré que chacune a un **point de naissance —
> un projet** et distingué les trois régimes (acheter / développer / faire faire) ; ce TD 2 **cote** cet
> écosystème (atelier 3) et **amorce** les scénarios (atelier 4), et lit un contrat d'infogérance au
> prisme de la sécurité. Rien ici n'est jetable : le tableau de l'exercice 1 devient les **exigences
> applicables aux tiers** de **D6** (TP 2) ; la carte de dangerosité et le scénario stratégique de
> l'exercice 2 se saisissent dans `translog-b` (TP 1) et alimentent la **sous-section 6** de la note de
> stratégie. Les ateliers 3 à 5 étaient vides dans D5 ; ce TD ouvre l'atelier 3.

**Règle du jour** : valeurs métier et biens supports **repris à l'identique** de D2 (`LOG-PA-01` à `04`,
`LOG-SA-01` à `13`) ; sources de risque, objectifs visés et événements redoutés **repris de D5** —
D5 fait foi. Aucun objet recréé ni renommé.
**Sigles** : **TMA** (tierce maintenance applicative), **WMS** (*warehouse management system*, logiciel de
gestion d'entrepôt), **PAS** (plan d'assurance sécurité), **SR/OV** (source de risque / objectif visé),
**ER** (événement redouté), **SOC** (centre de supervision de la sécurité), **IT/OT** (bureautique /
industriel), **VLAN** (réseau local virtuel), **RTO/RPO** (délai / perte de données maximaux admissibles).
**Corrigé de l'énoncé replié** (« cliquer pour révéler »), non extractible — réponses bâties sur le corpus
(CM S6, énoncé du TD 2, extrait de contrat `TMA-WMS-2021`, pack de filiale, reference pack, D1, D2, D4, D5,
TD 1 de la séance 6).

---

## Rappel du cas

Le matin a produit un **inventaire qualifié** de seize dépendances tierces, mais **aucune échelle
commune** : rien ne mesurait la dépendance réelle à chaque partie prenante, sa pénétration dans le SI, sa
maturité ni la confiance qu'on peut lui accorder, et rien ne reliait une partie prenante à un événement
redouté coté (TD 1, question 5). D5 avait explicitement mis **le couple SR/OV n°2 — « attaquant passant
par l'intégrateur des automates, via la box 4G non supervisée »** — en réserve, au motif qu'il *« relève
d'abord d'un risque de dépendance qui se traite au contrat et qui sera repris comme partie prenante
critique de l'écosystème en séance 6 (atelier 3) »*. C'est ce TD qui tient ce rendez-vous.

Deux entrées de matière nouvelle depuis le matin : le **CM** (trois régimes de projet, six jalons de
sécurité) et l'**extrait du contrat de TMA du WMS** `TMA-WMS-2021` (APPLICA Services, articles 1 à 8),
fourni dans les sources de la séance — c'est *le contrat du prestataire le plus exposé de la filiale sous
revue* que l'exercice 1 demande de lire.

---

## Les trois notions à poser avant de manipuler quoi que ce soit (cadrage, 10 min)

*Le CM a intégré la sécurité aux projets ; ce TD traite des tiers **durablement installés**, ceux que
désigne le régime « faire développer / externaliser », et entre dans les ateliers 3 et 4 par l'angle de
l'écosystème.*

| Notion | Ce que c'est | Sa mécanique | Sa limite |
|---|---|---|---|
| **Le contrat d'infogérance** | *L'externalisation appliquée au domaine des SI* (guide ANSSI *« Maîtriser les risques de l'infogérance »*) : *confier à un tiers tout ou partie d'une activité jusqu'alors réalisée en interne*. Le contrat est l'acte qui gouverne cette délégation. | Une idée que le guide martèle : **ce qui n'est pas exigé au contrat ne sera jamais dû.** Le client apprécie ses risques, en tire des exigences de sécurité, les écrit au cahier des charges, et demande au candidat un **plan d'assurance sécurité (PAS)** décrivant les dispositions qu'il s'engage à mettre en œuvre. **Quatre familles** forment l'ossature d'un contrat d'infogérance sûr : **réversibilité**, **droit d'audit**, **notification d'incident**, **maîtrise de la sous-traitance**. | Un contrat parfait sur le papier ne vaut que le **comité de suivi** qui le tient vivant et les **audits** qui le vérifient. |
| **Atelier 3 d'EBIOS RM** *(déroulé ici et cet après-midi)* | *Disposer d'une vision claire de l'écosystème pour identifier les parties prenantes les plus menaçantes et les présenter à la direction*, puis bâtir des **scénarios stratégiques** (scénarios de haut niveau). | On **estime la dangerosité** de chaque partie prenante, on en **sélectionne les critiques**, puis on trace un **chemin d'attaque** pour chaque couple SR/OV. Une **partie prenante critique** est *susceptible de constituer un vecteur d'attaque pertinent, du fait par exemple de son accès numérique privilégié à l'objet étudié, de sa vulnérabilité ou de son exposition*. Un **scénario stratégique** est un ensemble de *chemins d'attaque allant d'une source de risque à un objectif visé en passant par l'écosystème et les valeurs métier de l'objet étudié* ; il **est estimé en gravité**. C'est l'attaque par rebond du matin, formalisée. | 24 % des entreprises citent le rebond via un prestataire parmi les canaux de transmission des attaques subies (baromètre CESIN 2022) : la partie prenante critique est une **porte d'entrée mesurée**, pas une abstraction. |
| **Atelier 4 d'EBIOS RM** *(amorcé ici, outillé cet après-midi, substance de la séance 7)* | *Construire des scénarios opérationnels [qui] schématisent les modes opératoires que pourraient mettre en œuvre les sources de risque pour réaliser les scénarios stratégiques.* | Un **scénario opérationnel** est *un enchaînement d'actions élémentaires portées sur les biens supports* ; il **est estimé en vraisemblance**. Lien net : *à chaque chemin d'attaque stratégique retenu à l'atelier 3 correspond un scénario opérationnel*. Le stratégique dit **où** l'attaque passe (l'écosystème) ; l'opérationnel dit **comment** techniquement (les biens supports). | Il ne se cote pas ici : la vraisemblance V1-V4 de l'échelle de D5 s'applique à l'atelier 4, séance 7. |

**Régime du prestataire du jour (CM).** APPLICA Services relève du régime **« faire faire / externaliser
l'exploitation »** : le groupe maîtrise *les exigences, la supervision, la réversibilité*, il ne maîtrise
pas *l'exécution quotidienne ni le personnel du prestataire*. Levier de sécurité principal : **le contrat,
le PAS, les audits, les jalons contractuels** — exactement l'objet de l'exercice 1.

---

## Exercice 1 — Le contrat du prestataire le plus exposé de MERIDIAN Logistique

*Prestataire : **APPLICA Services**, TMA du WMS, contrat `TMA-WMS-2021` signé le 8 novembre 2021 par le
Directeur de la filiale, conclu pour quatre ans puis renouvelable par périodes d'un an — donc en
**renouvellement annuel depuis le 8 novembre 2025**, prochaine échéance **8 novembre 2026**. Extrait des
articles 1 à 8 ; « les articles non reproduits ne portent aucune stipulation de sécurité » (mention de
l'extrait). Exigences formulées comme **exigences vérifiables**, pas comme clauses juridiques :
elles se démontrent, preuve datée à l'appui.*

### Ce que l'extrait dit — et ne dit pas

| Article | Ce qu'il stipule | Silence de sécurité |
|---|---|---|
| **1-2 · Objet, prestations** | TMA du WMS (2 serveurs + base, site E1, 6 entrepôts) : correctif, évolutif, support N2-N3 ; **correction de l'interface d'approvisionnement d'urgence avec MERIDIAN Santé** ; **installation des mises à jour correctives et des versions de l'éditeur** ; astreinte 24 h/24 pour les anomalies bloquantes ; développements spécifiques sur devis. | Aucun contrôle de ce qui est livré par une mise à jour ; l'interface Santé (dépendance inter-filiales) est dans le périmètre sans exigence propre. |
| **3 · Modalités d'intervention** | Le client crée un **compte de domaine `svc-applica` avec droits d'administration** sur les serveurs du WMS + accès aux partages ; le prestataire intervient **à distance par le réseau bureautique**, à tout moment pour les bloquantes, et **installe les mises à jour de 22 h à 5 h sans autre formalité** ; il **tient la liste des personnes habilitées et la communique sur demande**. | Compte **partagé** (pas nominatif), fenêtre de mise à jour **non annoncée**, **aucune validation ni retour arrière**, liste des porteurs **« sur demande »** seulement — l'audit interne du holding a demandé et reçu *un nom de compte, aucun nom de personne* (pack §3). |
| **4 · Engagements de service** | Anomalie bloquante : prise en compte 30 min, **rétablissement 6 h**. Majeure : 2 j ouvrés. Mineure : version suivante. Les pénalités de 12 000 €/j au client pharmaceutique **ne sont pas répercutables** au-delà de la remise de l'article 8. | SLA **fonctionnel**, pas de sécurité ; rétablissement « 6 h » **jamais démontré** (sauvegardes quotidiennes jamais restaurées, pack §5.4) ; RTO/RPO non contractualisés (lacune n°5 de D2). |
| **5 · Sécurité** | Le prestataire respecte **« les règles de l'art »** et la **charte informatique** du client ; toute évolution d'architecture à incidence sécurité fait l'objet d'une **information préalable**. | « Règles de l'art » **non vérifiable** ; information préalable **sans avis ni veto** du client ; aucune exigence de journalisation, d'authentification, de gestion des correctifs. |
| **6 · Confidentialité** | Données de stock, de commande et de température, pendant le contrat **+ 3 ans**. | Rien sur la **restitution / destruction** de ces données ni des secrets et accès en fin de contrat. |
| **7-8 · Durée, résiliation, responsabilité** | 4 ans puis renouvellement annuel ; **résiliation à l'échéance, préavis 6 mois** ; remise de 10 % après deux trimestres de manquement ; responsabilité **plafonnée à la redevance annuelle** (132 000 € HT). | « Résiliation » **n'est pas « réversibilité »** : aucun plan de réversibilité, aucun format d'export, aucune assistance de transfert, aucune reprise des développements spécifiques. |

### Les exigences vérifiables manquantes, par famille

| Famille | Exigence(s) vérifiable(s) à écrire au cahier des charges du renouvellement (couverture à démontrer dans le PAS) | Écart corrigé |
|---|---|---|
| **Réversibilité** | 1. **Un plan de réversibilité est annexé au contrat** et **a été exécuté à blanc dans les 12 derniers mois** (rapport daté) : export exhaustif de la base et de la configuration du WMS dans un **format documenté et réimportable**, liste et état des versions et correctifs de l'éditeur appliqués, documentation d'exploitation, **code source des développements spécifiques** (art. 2), le tout couvrant aussi l'**interface d'approvisionnement d'urgence Santé**. 2. **Une restauration complète du WMS depuis les sauvegardes est démontrée au moins une fois par an en présence du client** (délai constaté vs. RTO). 3. **RTO et RPO du WMS et de l'interface Santé sont chiffrés au contrat**, et une **période d'assistance à la réversibilité** d'une durée définie est prévue en fin de contrat. 4. En fin de contrat, **restitution puis destruction certifiée** du compte `svc-applica`, de tous les accès aux partages et de toute donnée/secret détenu, sous X jours. | L'article 8 n'offre qu'un **préavis de 6 mois** : le client ne peut pas *reprendre la gestion de la fonction externalisée, pour l'exploiter lui-même ou la confier à un tiers de son choix* (guide ANSSI). Sans format, sans données, sans restauration testée, sans reprise du compte, le WMS est **captif** — et la reprise n'est **pas démontrée** (ER1 de D5, constat « sauvegardes jamais restaurées » du reference pack, lacune RTO/RPO de D2). |
| **Droit d'audit** | 1. **Le client, ou un tiers qu'il mandate, peut vérifier à tout moment et au moins une fois par an que les exigences de sécurité sont satisfaites** — sur les accès du prestataire au WMS, sur son **processus de mise à jour et de livraison**, et sur son **propre environnement de production et de fabrication** des livrables. 2. **Le prestataire remet chaque année le résultat de son dernier audit indépendant** (certificat ISO/IEC 27001 ou rapport équivalent) et un **test d'intrusion annuel** de la surface exposée du WMS, résultats partagés. 3. **Sur demande et sous X jours ouvrés, il remet sous forme nominative** la liste des personnes ayant accès à `svc-applica` et le journal daté de leurs interventions. | *Le client doit pouvoir, à tout moment, contrôler que les exigences de sécurité sont satisfaites* (guide ANSSI). L'article 5 est une **auto-déclaration** (« règles de l'art ») ; la seule vérification que le dossier montre tentée — la demande de liste nominative de l'audit interne — a **échoué**. Le droit d'audit est aussi le seul moyen de voir la **chaîne de livraison** d'APPLICA, vecteur du mécanisme NotPetya (TD 1, question 3a). |
| **Notification d'incident** | 1. **Le prestataire notifie le client sous 24 heures** : de tout incident de sécurité touchant le WMS ou ses données ; de toute **compromission — suspectée ou avérée — de son propre environnement de production ou de livraison** (vecteur M.E.Doc / SolarWinds) ; de tout usage anormal du compte `svc-applica`. 2. **Un contact nommé de chaque côté et un canal écrit** ; **rapport post-incident sous 5 jours ouvrés avec chronologie**. 3. **Le prestataire transmet en continu les journaux du WMS et de ses interventions au SOC du groupe** dans un format exploitable. | *Le client doit être tenu informé sans délai en cas d'attaque afin de déclencher le circuit de réaction adéquat* (guide ANSSI). Le contrat est **muet** : l'astreinte 24 h/24 de l'article 2 couvre la panne, pas l'attaque. Le SOC ne reçoit **rien** du WMS (pack §6), il n'existe **aucune procédure d'incident** (pack §5.6, arrêt d'avril « chacun a appelé qui il pouvait, personne n'a tenu de chronologie »). C'est la **case vide** du réflexe de méthode du matin, sur l'actif le plus critique. Aligne la directive `PSSI-CADRE-INC-01` (< 2 h en interne) et la **décision demandée au Comité Exécutif** au TD 1 (message 3 : notification sous 24 h d'une compromission chez le prestataire). |
| **Maîtrise de la sous-traitance** | 1. **Le prestataire déclare en annexe la liste de ses sous-traitants** ayant accès — direct ou indirect — au WMS, à ses données ou au compte `svc-applica`, et **la met à jour avant tout changement** ; **le client peut récuser sous X jours** un sous-traitant ne présentant pas de garanties suffisantes. 2. **Toutes les exigences de sécurité du contrat sont répercutées aux sous-traitants**, le prestataire restant **seul responsable** devant le client. 3. **Comptes individuels nominatifs** pour toute personne du prestataire ou de ses sous-traitants intervenant sur le WMS — **aucun compte partagé** ; le client peut vérifier à tout moment que la liste des comptes correspond à la liste nominative. 4. **Aucun accès depuis un lieu non listé ou hors UE** sans autorisation préalable. | *Réserver le droit de récuser tout sous-traitant ne présentant pas les garanties suffisantes* (guide ANSSI). Aujourd'hui un développement spécifique peut être sous-traité « sur devis » **sans visibilité** ; le compte `svc-applica` **partagé** rend le personnel du prestataire et tout sous-traitant **indistinguables et non imputables** (constat **C4**, non-conformité majeure de D4 ; pack §5.2 « un nombre de personnes que nul ne peut établir »). Couvre les contrôles `A.5.19` à `A.5.22` du référentiel (CM S6). |
| **⚑ Ligne libre — le plus urgent** | **Notification sous 24 h d'une compromission de l'environnement d'APPLICA + remontée continue des journaux du WMS au SOC du groupe** (famille *notification d'incident*, points 1 et 3). | C'est la **seule** exigence qui fait passer le client de **aveugle** à **capable de voir** sur l'actif dont l'arrêt > 6 h bloque **40 % du volume expédié du groupe** (ER1, gravité **G4**) ; elle coûte au prestataire un paramétrage, pas une renégociation, et elle est le préalable de toutes les autres — sans journal ni alerte, aucune des trois autres familles n'est vérifiable dans les faits. |

### Ce qui maintient ces exigences en vie après signature *(préparé pour le TP 2)*

Le guide le dit : le contrat ne vaut que son suivi. À porter dans D6 comme **dispositif de surveillance du
tiers** : trois indicateurs (part des interventions tracées par compte nommé ; délai réel de pose des
correctifs éditeur vs. `PSSI-CADRE-COR-01` ; nombre de comptes `svc-applica` actifs vs. liste nominative),
un **comité de suivi trimestriel** (RSSI Groupe + DSI filiale + APPLICA : revue des incidents, des accès,
du plan de réversibilité), une **preuve annuelle non sollicitée** (rapport d'audit indépendant + PV du
test de restauration), et **ce qui ne se délègue jamais** : l'acceptation du risque résiduel (Direction
Générale), la tenue du registre nominatif des comptes à privilèges (mesure **M4** de D4, échéance
8/11/2026), la décision de reprise de l'interface Santé (arbitrage inter-filiales `ARB-01` de D1).

---

## Exercice 2 — Carte de dangerosité de l'écosystème et un scénario stratégique

### Objet étudié : `LOG-PA-01` **Exécution des flux logistiques**, événement redouté **ER1**

*L'énoncé demande « le premier actif critique de la filiale, la valeur métier dont l'événement redouté est
coté le plus haut dans D5 ».*

Trois événements redoutés de D5 sont cotés **Critique** : **ER1** (`LOG-PA-01`, disponibilité), **ER3**
(`LOG-PA-02`, chaîne du froid), **ER5** (`§6`, réapprovisionnement Santé). L'objet étudié retenu est
**`LOG-PA-01`**, sur critère écrit *avant* le choix :

1. c'est l'objet autour duquel **D5 est cadré** — titre de l'étude, table des participants, **énoncé
   d'appétence n°1** borné sur les six heures d'interruption du flux d'expédition ;
2. `LOG-SA-01` (le WMS, qui porte `LOG-PA-01`) est le **rang 1 du Top 5** des actifs critiques de D2 ;
3. D5 §3 acte lui-même la **« concentration sur `LOG-PA-01` »** (quatre des cinq actifs du Top 5 la
   servent) ;
4. c'est le **seul des trois** dont un couple SR/OV **retenu** en séance 5 vise directement la valeur
   métier : le **couple n°1** (`Organized crime`, *Highly relevant*). ER3 et ER5 restent **sans source de
   risque retenue** (D5 §4) — ils relèvent d'un cycle ultérieur ou de l'approche par conformité.

**Biens supports de `LOG-PA-01` (D2), rappelés pour le chemin d'attaque** : `SA-01` WMS · `SA-02`
scannettes · `SA-03` automates de tri · `SA-04` compte de service WMS↔automates · `SA-06` local serveur
E1 · `SA-07` entrepôts · `SA-09` Responsable Exploitation · `SA-10` TMA du WMS · `SA-12` VLAN dédié ·
`SA-13` interface d'approvisionnement d'urgence · liaisons opérateur inter-entrepôts.

### Les parties prenantes de l'écosystème de `LOG-PA-01` (§3 et §6 du pack)

*Cinq parties prenantes, prises parmi les prestataires, les autres filiales et les clients qui figurent au
§3 (carte du pouvoir) et au §6 (ce qui franchit la frontière). Aucune inventée ; toutes reliées à
`LOG-PA-01`. Les acteurs internes (Responsable Exploitation, DSI, chefs d'entrepôt) sont des **biens
supports** de D2, pas des parties prenantes de l'écosystème. Le fournisseur des sondes et le fournisseur
de télématique appartiennent à l'écosystème de `LOG-PA-02` (chaîne du froid) — à cartographier quand
`LOG-PA-02` sera l'objet étudié.*

| Réf. | Partie prenante | Catégorie (outil) | Lien avec `LOG-PA-01` |
|---|---|---|---|
| **PP1** | **APPLICA Services** — TMA du WMS (`SA-10`) | Prestataire | Maintient le WMS et ses interfaces ; compte de domaine administrateur `svc-applica` ; pose les mises à jour |
| **PP2** | **Intégrateur des automates de tri** (`SA-03`) | Prestataire | Maintient les automates d'E2/E3/E4 ; accès distant permanent par box 4G hors réseau supervisé |
| **PP3** | **Opérateur des liaisons inter-entrepôts** | Prestataire / partenaire | Les cinq entrepôts hors E1 n'atteignent le WMS que par ses liaisons |
| **PP4** | **Client pharmaceutique** (portail d'expédition) | Client | Un compte par entrepôt sur le portail du client, hors de notre annuaire ; audits annuels, questionnaire de sécurité annoncé |
| **PP5** | **MERIDIAN Santé** (flux de réapprovisionnement d'urgence, `SA-12`/`SA-13`) | Partenaire (groupe) | Consomme les mouvements de stock des scannettes via l'API sur VLAN dédié ; flux **coupé depuis trois mois** |

### Cotation de la dangerosité — dépendance × pénétration (exposition) / maturité × confiance (fiabilité cyber)

*Méthode du guide, reprise par l'outil : quatre critères notés **1 à 4**, chacun justifié par un **fait du
pack**, jamais par une impression. **Exposition** = dépendance × pénétration (elle **augmente** la
dangerosité) ; **fiabilité cyber** = maturité × confiance (elle la **diminue**) ; **dangerosité** =
exposition / fiabilité. Calcul fait à la main ici, **à recalculer à l'identique dans `translog-b`** au
TP 1.*

| Réf. | Dépendance | Pénétration | **Expo.** | Maturité | Confiance | **Fiab.** | **Dangerosité** | Rang |
|---|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| **PP2 · Intégrateur automates** | 3 | 4 | **12** | 1 | 1 | **1** | **12,0** | **1** |
| **PP1 · APPLICA (TMA WMS)** | 4 | 4 | **16** | 1 | 2 | **2** | **8,0** | **2** |
| **PP5 · MERIDIAN Santé** | 2 | 3 | 6 | 2 | 3 | 6 | 1,0 | 3 |
| **PP3 · Opérateur des liaisons** | 3 | 1 | 3 | 2 | 3 | 6 | 0,5 | 4 |
| **PP4 · Client pharmaceutique** | 2 | 2 | 4 | 3 | 3 | 9 | 0,4 | 5 |

**Justification des notes, ligne par ligne :**

- **PP1 · APPLICA.** *Dépendance 4* — seul mainteneur du WMS et de ses interfaces, y compris l'interface
  Santé (contrat art. 1-2) ; l'astreinte est la seule voie de rétablissement d'une anomalie bloquante
  (art. 4) ; « le WMS, c'est l'affaire de la TMA » (pack §3), aucune compétence interne, système
  centralisé sur un site sans secours (Top 5 de D2). *Pénétration 4* — compte de domaine
  **administrateur** `svc-applica` sur les serveurs du WMS + partages (art. 3), accès distant par le
  réseau bureautique à tout moment, mises à jour posées 22 h-5 h « sans autre formalité », et réseaux
  IT/OT interconnectés (**C3**) : l'accès déborde le WMS. *Maturité 1* — aucune exigence de sécurité
  vérifiable au contrat (art. 5 « règles de l'art »), pas de journalisation nominative (art. 3-4), mises à
  jour non validées et sans retour arrière (pack §4). *Confiance 2* — prestataire installé depuis 2021,
  clause de confidentialité (art. 6), tient une liste des personnes habilitées — mais « sur demande »
  seulement, et elle a produit *un nom de compte, aucun nom de personne* à l'audit interne (pack §3) ;
  nombre de porteurs inconnu (pack §5.2).
- **PP2 · Intégrateur.** *Dépendance 3* — seul installateur/mainteneur des automates d'E2/E3/E4 (pack §2),
  qui portent `LOG-PA-01` ; mais E5/E6 sont manuels et E1 (le plus gros, pharma) tient au WMS, pas aux
  automates — la préparation ne s'arrête pas *entièrement* sans lui. Connaissance des réglages
  **revendiquée comme propriété industrielle** (pack §3-§4) : point de savoir unique. *Pénétration 4* —
  accès distant permanent par **box 4G hors du réseau supervisé** (pack §2), sur un **réseau plat IT/OT**,
  donc l'accès « ne donne pas sur un automate, il donne sur tout », WMS compris (**C3**, TD 1 T3) ; et
  chaque chef d'entrepôt appelle un technicien sur son mobile, sans vérification d'identité (pack §3,
  TD 1 T4). *Maturité 1* — contrat **sans clause de réversibilité ni exigence de sécurité** (pack §2, §3,
  §5) ; aucun journal au SOC (pack §6). *Confiance 1* — **refuse par écrit** de communiquer les réglages
  (pack §3-§4) ; la box 4G a été posée **précisément pour contourner** la DSI de la filiale (pack §3).
- **PP3 · Opérateur des liaisons.** *Dépendance 3* — cinq entrepôts sur six n'atteignent le WMS que par
  ses liaisons ; « si le lien tombe, l'entrepôt s'arrête », démontré en avril (pack §4). *Pénétration 1*
  — transporte le flux, **aucun accès logique** au WMS ni à ses données. *Maturité 2 / Confiance 3* —
  opérateur télécom mutualisé, pratiques de base présumées, mais **aucune exigence de sécurité formulée**
  par la filiale ; service mutualisé « atteignable sans nous viser » (TD 1 T7) ; aucun incident propre.
- **PP4 · Client pharmaceutique.** *Dépendance 2* — le portail sert à saisir les expéditions, mais c'est
  le système du client et le repli papier existe (utilisé pendant la coupure Santé). *Pénétration 2* —
  **un compte par entrepôt partagé par les équipes, hébergé chez le client, hors de notre annuaire**
  (pack §4, TD 1 T8) : pivot dans les deux sens vers nos données chez lui et notre identité
  contractuelle, mais **pas d'accès dans notre WMS**. *Maturité 3* — client qui conduit des audits
  annuels de chaîne du froid et a **annoncé un questionnaire de sécurité** (pack §3) : visiblement plus
  mûr que la filiale. *Confiance 3* — relation contractuelle, intérêts alignés sur la continuité ; le
  risque, c'est nos comptes partagés, pas l'intention du client.
- **PP5 · MERIDIAN Santé.** *Dépendance 2* — pour `LOG-PA-01`, Santé est **en aval** (consomme nos données
  de scannettes) ; nos flux ne dépendent pas de Santé. *Pénétration 3* — l'API de réapprovisionnement sur
  **VLAN dédié + pare-feu d'inspection** (`SA-12`/`SA-13`) relie nos ~300 scannettes Wi-Fi au système de
  stocks de Santé — **seule segmentation du groupe** (**C7**), mais **flux coupé depuis trois mois** à la
  demande de la RSSI de Santé (*« leur matériel n'est pas fiable »*) : compromettre nos scannettes, c'est
  écrire dans les commandes d'une pharmacie hospitalière, et la voie est symétrique. *Maturité 2* — Santé
  a ses propres constats majeurs (mots de passe sans MFA, identifiant unique du SIH partagé entre neuf
  personnes, registre jamais remis — reference pack §3). *Confiance 3* — même groupe, mission alignée ;
  Santé a coupé le flux **par prudence** (signe de sa vigilance, pas d'une hostilité exploitable), le
  Pharmacien chef veut sa reprise.

### Seuil de criticité posé par le groupe, et parties prenantes critiques désignées

> **Seuil écrit, appliqué inchangé au registre complet de l'écosystème en séance 7 :**
> une partie prenante est **critique** lorsque sa **dangerosité ≥ 4,0** — c'est-à-dire lorsque son
> exposition (dépendance × pénétration) vaut **au moins quatre fois** la fiabilité cyber
> (maturité × confiance) qui l'encadre. Règle de lecture jointe, tirée du réflexe de méthode du matin :
> *accès numérique privilégié permanent à un bien support de `LOG-PA-01` + `maturité × confiance ≤ 4`*
> (« ce que le tiers peut faire est fort, et rien ne dirait que quelqu'un d'autre s'en sert »).

Le seuil sépare nettement les valeurs observées : {12,0 ; 8,0} au-dessus, {1,0 ; 0,5 ; 0,4} en dessous.

**Parties prenantes critiques désignées (« Selected » au TP 1) : PP2 · l'intégrateur des automates
(12,0) et PP1 · APPLICA Services (8,0).** C'est la résolution de la mise en réserve du couple n°2 en
séance 5 : l'intégrateur n'entre pas comme couple SR/OV, il entre comme **partie prenante critique** de
l'écosystème, et il porte un **second chemin d'attaque** du scénario ci-dessous. PP1, PP2 sont aussi les
trois accès de tiers « les plus puissants » du matin (T1-T2-T3 du TD 1) : la cotation confirme
l'intuition, chiffres à l'appui.

*Note d'articulation avec l'exercice 1* : le prestataire le **plus exposé** (exposition 16, PP1 · APPLICA
— le contrat lu à l'exercice 1) n'est pas le **plus dangereux** (PP2 · l'intégrateur, 12,0, tiré vers le
haut par une fiabilité de 1). Les deux franchissent le seuil ; les deux appellent un traitement
contractuel en D6.

### Scénario stratégique — couple SR/OV **n°1** (retenu en séance 5), par une partie prenante critique

**Couple SR/OV** (D5 §3, repris à l'identique) — Source de risque : **Cybercriminel (`Organized crime`)**.
Objectif visé : **chiffrer le WMS et sa base pour arrêter le flux d'expédition du groupe et obtenir une
rançon sous menace d'arrêt prolongé.** Pertinence outil : *Highly relevant*. Valeur métier visée :
`LOG-PA-01`.

**Chemin d'attaque principal — par PP1 · APPLICA Services (partie prenante critique) :**

| Étape | Description | Objet |
|---|---|---|
| **Source de risque** | Le cybercriminel acquiert un accès initial chez APPLICA — poste d'un intervenant disposant de `svc-applica`, ou environnement de fabrication/livraison des mises à jour (accès initiaux achetés, écosystème rançongiciel mature — D5 §3). | — |
| **Événement intermédiaire** *(porté sur l'écosystème)* | Une charge malveillante est **embarquée dans la mise à jour du WMS** qu'APPLICA installe de 22 h à 5 h « sans autre formalité » (contrat art. 3) — **mécanisme NotPetya / M.E.Doc à l'identique** (TD 1 Q3a) ; ou le cybercriminel **utilise directement le compte de domaine administrateur `svc-applica`** par le réseau bureautique. Dans les deux cas, **l'intrusion ne se distingue pas d'une intervention légitime** (pack §3, **C4**). | PP1 (`SA-10`) |
| **Propagation** | Depuis les deux serveurs + la base du WMS au site E1, et **par le réseau plat IT/OT** (**C3**), la charge atteint le WMS **utilisé simultanément par les six sites** ; le compte de service `SA-04` (même secret en clair depuis 2019) élargit encore l'emprise vers les automates. | `SA-01`, `SA-06`, `SA-04` |
| **Événement redouté** *(porté sur la valeur métier `LOG-PA-01`)* | **Le WMS et sa base sont chiffrés ; les six entrepôts ne préparent ni n'expédient plus — ER1.** La reprise n'est **pas démontrée** (sauvegardes quotidiennes jamais restaurées — pack §5.4 ; RTO/RPO non contractualisés — D2 ; site unique, pas de secours). Au-delà de six heures : **40 % du volume expédié du groupe** bloqué, **12 000 €/jour** de pénalités au client pharmaceutique, et l'**interface d'approvisionnement d'urgence vers Santé** (contrat art. 2) tombe avec le WMS. | `LOG-PA-01` |
| **Rien ne le détecte** | Le SOC ne reçoit aucun journal du WMS (pack §6) ; aucune procédure d'incident (pack §5.6) ; aucune obligation de notification à la charge d'APPLICA (contrat muet). | `SA-10` / SOC |

**Chemin d'attaque secondaire — par PP2 · l'intégrateur des automates** *(même couple SR/OV, à créer comme
second chemin « Selected » au TP 1)* : le cybercriminel compromet l'intégrateur, entre par la **box 4G
hors réseau supervisé**, atteint par le **réseau plat IT/OT** le WMS et sa base → **ER1**, même événement
redouté, même gravité, pivot différent — celui que D5 avait annoncé.

### Gravité sur l'échelle de D5

> **G4 `Critical` (critique).**

Lecture directe de l'échelle de gravité de D5 §1 et de la cotation d'**ER1** (Critique) : *interruption
d'un service **essentiel** — expédition arrêtée > 6 h (40 % du volume groupe)* ; *un engagement
contractuel rompu et payé (12 000 €/jour)* ; reprise *incertaine ou > plusieurs mois* car la restauration
n'est pas démontrée ; *capacité du groupe à tenir une mission remise en cause dans la durée* si l'arrêt se
prolonge. La **borne des six heures** d'ER1 (énoncé d'appétence n°1) est franchie dès lors que la reprise
dépend d'une restauration jamais testée.

*La **vraisemblance** n'est pas cotée ici : elle relève du scénario opérationnel (actions élémentaires sur
les biens supports), atelier 4, échelle V1-V4 de D5, séance 7. Indices déjà au dossier pour cette
future cotation : secret de service en clair, box 4G hors supervision, aucun journal OT au SOC — les
marqueurs `Very likely` de D5 §1.*

---

## Ce qui entre dans la suite de la journée

| Destination | Ce qui vient d'ici |
|---|---|
| **TP 1** (`translog-b`, ateliers 3-4) | Les **5 parties prenantes** (PP1-PP5) créées et reliées à l'étude, avec leurs **4 notes justifiées** ; la **dangerosité recalculée** par l'outil, **PP1 et PP2 cochées « Selected »** ; **deux scénarios stratégiques** rattachés à des couples SR/OV retenus, chacun avec un chemin d'attaque « Selected » par une partie prenante critique, **gravité affichée depuis l'événement redouté** ; l'amorce d'un **scénario opérationnel** sur le chemin le plus préoccupant (celui par APPLICA). |
| **TP 2 — livrable D6** (7 pts) | Le **tableau des exigences vérifiables** de l'exercice 1 (quatre familles + la plus urgente) devient les **exigences de sécurité du contrat d'infogérance** de D6, chacune tracée à un scénario stratégique de l'exercice 2, à un écart de D4 (C3, C4, A.5.17, A.8.15) ou à un silence de l'extrait `TMA-WMS-2021` ; le **dispositif de surveillance du tiers** (3 indicateurs, comité de suivi, preuve annuelle, ce qui ne se délègue pas) complète la pièce. La **fiche projet** de D6 traitera un projet réel du pack (cadrage de l'homologation du WMS, déjà amorcé en D4). |
| **Sous-section 6 de la note de stratégie** (« tiers et projets ») | La position du groupe : *ce qui n'est pas exigé au contrat ne sera jamais dû* ; **aucun contrat donnant accès à un actif critique n'est signé ni renouvelé sans les trois clauses** — journalisation par utilisateur nommé, notification sous 24 h d'une compromission chez le prestataire, réversibilité (règle de contractualisation demandée au ComEx au TD 1, message 3, qui opérationnalise l'énoncé d'appétence n°2 de D5) ; lien explicite à la gouvernance de la séance 1 (`ARB-01`, acceptation du risque résiduel par la DG) et aux actifs critiques de la séance 2 (Top 5). Une demi-page, sans recopier D6. |

---

## Auto-évaluation (grille du TD)

| Critère | Niveau atteint |
|---|---|
| **Ex. 1 — le contrat, quatre familles** | Tableau à trois colonnes (famille · exigences vérifiables manquantes · écart corrigé), **exigences formulées comme testables** (preuve datée, PV de restauration, liste nominative vérifiable) et **non comme clauses juridiques** ; chaque famille adossée à l'extrait `TMA-WMS-2021` article par article **et** à ce que le pack établit (C3, C4, §3, §5.2, §5.4, §6) ; **ligne libre** = notification 24 h + journaux au SOC, justifiée en une phrase (la seule qui rend les trois autres familles vérifiables) ; régime « faire faire » nommé, PAS et comité de suivi rattachés. |
| **Ex. 2 — carte de dangerosité** | Objet étudié `LOG-PA-01` **choisi sur critère écrit avant le choix** (quatre raisons), tie-break des trois ER Critique assumé ; **5 parties prenantes** de §3 et §6, aucune inventée, acteurs internes écartés comme biens supports ; cotation sur les **quatre critères du guide** (dépendance, pénétration, maturité, confiance), **chaque note justifiée par un fait du pack** ; exposition / fiabilité / dangerosité calculées, **classement** ; **seuil écrit** (dangerosité ≥ 4,0 + règle de lecture), **deux parties prenantes critiques désignées** (intégrateur 12,0 ; APPLICA 8,0), articulation « plus exposé ≠ plus dangereux » explicitée, résolution de la mise en réserve du couple n°2 de D5. |
| **Ex. 2 — scénario stratégique** | Couple SR/OV **n°1 repris à l'identique de D5**, chemin d'attaque en cinq étapes **source de risque → événement intermédiaire (écosystème) → propagation → événement redouté (valeur métier)**, par une **partie prenante critique** (APPLICA), mécanisme NotPetya nommé et justifié ; **second chemin** par l'intégrateur ; **absence de détection** tracée ; **gravité G4** lue sur l'échelle de D5 et sur ER1, vraisemblance explicitement renvoyée à l'atelier 4 / séance 7. |
| **Traçabilité aval** | Ce qui entre dans TP 1, D6 (TP 2) et la sous-section 6 est explicité ligne à ligne ; aucun objet recréé ni renommé. |

*Chaque case vise la colonne « Excellent » de la grille officielle — à confronter en séance avec le
corrigé de référence du module (replié dans l'énoncé, « cliquer pour révéler »).*

---

> **Phrase de passage aux TP.** L'écosystème est coté : deux parties prenantes critiques, un scénario
> stratégique à G4 qui relie un cybercriminel à l'arrêt du flux d'expédition **en passant par la TMA du
> WMS**. Le TP 1 saisit tout cela dans `translog-b` et amorce l'atelier 4 ; le TP 2 transforme le tableau
> de l'exercice 1 en exigences de D6 et rédige la fiche projet ; la sous-section 6 de la note affirme la
> règle des trois clauses. Les échelles de D5 serviront, inchangées, à coter le registre complet en
> séance 7.
