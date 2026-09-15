# Séance 1 — TD (S1-01) : The CISO's briefing — Trois dossiers sur le bureau du RSSI Groupe
### Réponses du Groupe 4 (Translog)

---

## Rappel du cas

Lundi, premier jour du RSSI Groupe de MERIDIAN. **Aucune PSSI de groupe** : chaque filiale a toujours géré sa sécurité comme elle l'entendait, et le poste a été créé précisément pour y remédier. Sur le bureau, trois dossiers laissés par la Direction Générale, avec ce mot : *« Dites-moi ce que vous en pensez jeudi. »*

- **Dossier 1.** La filiale **Logistique** demande l'ouverture d'un flux permanent entre les scannettes de ses entrepôts et le système de gestion des stocks de la filiale **Santé**, pour fluidifier l'approvisionnement d'urgence des établissements de soin. Santé refuse : *« leur matériel n'est pas de confiance »*. Le projet est **bloqué depuis trois mois**, et chaque filiale campe sur sa position.
- **Dossier 2.** Le **DSI de la filiale Éducation** propose de confier la supervision sécurité des quatre filiales à l'outil qu'il utilise déjà, *« puisque la DSI est déjà mutualisée avec Territoires, autant tout centraliser chez nous, c'est l'option la moins chère »*.
- **Dossier 3.** L'**Auditeur Interne** du groupe, secteur Gouvernance et Audit, signale avoir demandé **trois fois** à la filiale Santé son registre des comptes d'administration, sans réponse, et propose *« d'en reprendre la gestion pour garantir qu'ils restent propres »*.

**La règle du jeu, annoncée par la méthode** : les bonnes réponses techniques ne sont pas dans les dossiers — ce que les dossiers contiennent, ce sont les bonnes **questions de gouvernance**.

---

## Les quatre notions posées avant l'exercice

- **La posture du RSSI** — traduire la sécurité dans la langue de la décision : informer les dirigeants des risques, proposer des options avec leur coût et leurs conséquences, et faire décider **au bon niveau** plutôt que trancher personnellement ce qui n'est pas de son ressort. Sa limite, qui est aussi sa grandeur : le RSSI ne possède **ni le budget ni l'autorité hiérarchique** sur les métiers ; quand il l'emporte, c'est par la qualité de ses dossiers, jamais par décret.
- **Le diagnostic de gouvernance** — l'examen méthodique de la façon dont les décisions de sécurité se prennent, en **trois questions** posées à toute situation : *qui a décidé cela, qui aurait dû, et où est-ce écrit ?* Ce n'est **pas** un audit technique : une organisation peut avoir d'excellents pare-feux et une gouvernance en ruines.
- **L'arbitrage inter-filiales** — la décision prise au niveau groupe, **sous des règles connues d'avance**, quand les intérêts légitimes de filiales s'opposent. Sans règle écrite **AVANT** le conflit, l'arbitrage se fait au rapport de force, et le perdant le conteste. Ce qu'un arbitrage ne fait pas : donner tort à une filiale — il donne la priorité à un intérêt de groupe, ce qui est une autre phrase.
- **Le risque systémique** — un risque est systémique quand une défaillance en un point se propage à l'ensemble, **parce que tout le monde dépend de la même chose**. L'exemple que le monde entier a médité : **SolarWinds, 2020**, où la mise à jour piégée du produit Orion a touché environ **18 000 clients** publics et privés, chacun ayant fait confiance au même fournisseur. À l'échelle d'un groupe comme MERIDIAN, le risque systémique porte des visages plus discrets : une DSI partagée entre deux filiales, un flux entre deux systèmes, un prestataire commun.

---

## Question 1 — Caractériser chaque dossier avec le vocabulaire du jour

*Lequel relève d'abord de l'arbitrage inter-filiales, lequel porte un risque systémique, lequel pose un problème de gouvernance au sens strict — celui du « qui décide » ? Une phrase de justification par dossier ; si un dossier relève de deux catégories, dire laquelle domine.*

| Dossier | Catégorie dominante | Justification en une phrase |
|---|---|---|
| **1** — flux scannettes Logistique → stocks Santé | **Arbitrage inter-filiales** | Deux intérêts **également légitimes** s'opposent — la disponibilité de l'approvisionnement des établissements de soin contre la protection d'un système d'information de santé — et **aucune règle préexistante** ne permet de trancher entre eux, d'où trois mois de blocage. |
| **2** — supervision des 4 filiales sur l'outil d'Éducation | **Risque systémique** | Centraliser la supervision des quatre filiales sur l'outil **d'une seule d'entre elles** crée exactement la dépendance commune dont SolarWinds a montré le prix en 2020, et l'argument économique ne change **rien à la topologie** du risque. |
| **3** — registre des comptes d'administration de Santé | **Gouvernance au sens strict** | Personne ne peut dire **qui doit répondre** du registre des comptes d'administration de Santé, et la preuve en est que l'Auditeur Interne propose de s'en charger lui-même. |

### Le recouvrement de catégories, explicité sur le dossier 1

Le dossier 1 relève **aussi** de la gouvernance stricte : si le flux est bloqué depuis trois mois, ce n'est pas seulement parce que deux filiales sont en désaccord, c'est parce que **personne n'est désigné pour trancher ce désaccord**. Les deux lectures sont vraies, et il faut dire laquelle domine.

**L'arbitrage domine**, pour une raison précise : dans le dossier 3, l'obligation elle-même n'existe pas — il n'y a rien à faire respecter, seulement une règle à créer. Dans le dossier 1, les deux positions sont **déjà formulées, déjà défendues, déjà documentées** par leurs auteurs ; ce qui manque n'est pas la connaissance de qui est responsable de quoi, c'est **la décision** qui départage deux responsables qui font chacun correctement leur métier. Le RSSI de Santé protège son SI de soin : c'est sa mission. Le Directeur de Logistique veut servir les établissements : c'est la sienne. Aucun des deux n'a tort, et c'est précisément la signature d'un arbitrage et non d'un trou de gouvernance.

*(Le dossier 2 porte lui aussi une seconde lecture — qui décide de l'architecture de supervision du groupe ? — mais le risque systémique domine largement : même si le décideur était clairement désigné, la topologie proposée resterait celle d'un point de défaillance unique.)*

---

## Question 2 — Les trois questions du diagnostic appliquées au dossier 3

*Qui a décidé quoi, qui aurait dû, où cela devrait-il être écrit ?*

**Qui a décidé quoi ? Personne — et c'est là toute l'information.**
Le registre n'est **ni tenu ni formellement refusé** : il est ignoré. Trois demandes, trois silences. Aucune décision n'a été prise, aucun responsable n'a arbitré, aucun refus motivé n'a été opposé à l'Auditeur Interne — et pourtant le résultat est parfaitement déterminé : le registre n'existe pas. C'est la formule à retenir du diagnostic : **l'absence de décision EST une décision**, à ceci près qu'elle n'a pas d'auteur et que personne n'a donc à en répondre. Un refus écrit et motivé de la filiale Santé serait une situation *meilleure* que celle-ci, parce qu'il serait attaquable.

**Qui aurait dû décider ? Deux niveaux, et les deux manquent.**
La **filiale Santé** aurait dû décider de tenir le registre — c'est elle qui exploite ses systèmes et ses comptes à privilèges, l'exploitation ne remonte pas au groupe. Mais elle aurait dû le faire **en application d'une règle de groupe qui n'existe pas encore** : rien, aujourd'hui, ne lui impose cette tenue. Le niveau qui a réellement manqué est donc le **niveau groupe**, qui aurait dû décider de l'obligation elle-même — et c'est bien pour cela que le poste de RSSI Groupe vient d'être créé.

**Où cela devrait-il être écrit ? Dans le cadre de gouvernance que l'après-midi construit**, et c'est très exactement ce que notre dossier a produit depuis :
- l'obligation de tenue, avec **propriétaire nommé et fréquence**, sous la forme de la directive `PSSI-CADRE-ACC-02` — *revue trimestrielle des privilèges sur les bases de données métier*, propriétaire **RSSI de filiale**, vérifiable par la date de la dernière revue (D1, directives codifiées) ;
- la répartition des rôles, dans la **matrice RACI** de D1 : *maintien en condition de sécurité* — **A** au RSSI Groupe, **R** aux équipes IT et métier de la filiale ;
- et l'opposabilité de l'ensemble, par l'**article 1 de la charte de gouvernance** de D1, qui adopte ces règles pour les quatre filiales.

### Ce que la proposition de l'Auditeur Interne dit en creux

La proposition de *« reprendre la gestion de ces comptes »* part d'une bonne intention et pointe vers la faute que le CM du matin a nommée : **un contrôleur qui devient l'opérateur de ce qu'il contrôle cesse de pouvoir le contrôler**. Si l'Auditeur Interne tient le registre, qui audite le registre ? C'est exactement ce que la ligne *évaluation de conformité et audits* de notre matrice RACI rend impossible — l'auditeur y est **R et A sur son seul processus d'évaluation**, jamais sur un processus qu'il est chargé de contrôler. La réponse à lui faire n'est donc pas « non », c'est : *votre constat est juste, votre remède vous disqualifierait.*

---

## Question 3 — Analyser le dossier 2 : que ferait la proposition au profil de risque du groupe ?

*L'argument du coût est réel, la DSI mutualisée existe. Ce n'est donc pas une mauvaise idée qu'il faut démonter, c'est une bonne idée dont il faut montrer qu'elle change de nature.*

**Ce que la proposition transforme.** Elle convertit un **choix budgétaire** en une **concentration de risque** : une seule équipe, un seul outil, un seul point de défaillance pour la visibilité sécurité des quatre filiales. Le jour où cet outil tombe, est compromis, ou simplement cesse d'être financé par la filiale qui le porte, les quatre filiales deviennent aveugles **en même temps** — et c'est la définition même du risque systémique posée ce matin : tout le monde dépend de la même chose.

**L'aggravation propre à MERIDIAN**, qui ne figure pas dans l'énoncé mais dans le dossier : la DSI d'Éducation est **mutualisée avec Territoires**. La proposition ferait donc de cette DSI à la fois **l'exploitant** de deux filiales **et le superviseur** des quatre — y compris d'elle-même. Une équipe qui supervise sa propre exploitation ne signale pas ses propres écarts : ce n'est pas une question d'honnêteté, c'est une question de structure, exactement la même que celle du dossier 3 avec l'Auditeur Interne. Les deux dossiers, en apparence sans rapport, portent la **même erreur de conception**.

**Et le détail qui achève l'argument.** Éducation est la filiale dont la gestion des accès est la plus faible des quatre — comptes d'administration partagés entre les équipes du pôle, dans un contexte de **moyens limités** (contraintes de D1) ; c'est la seule filiale que notre grille de maturité note **2 tendant vers 1 sur la gestion des accès** (TD S1-03, exercice 3). Concentrer la détection de tout le groupe sur la filiale la moins bien tenue en matière d'accès, c'est le contraire exact de la défense en profondeur.

**Ce que le diagnostic ne dit pas.** Il ne dit **pas « non »**. Il dit que la décision **n'est pas de nature économique mais de nature risque**, et qu'elle doit être éclairée comme telle avant d'être prise. Si le groupe centralise, ce sera **en connaissance de cause, avec des garde-fous**, et non parce que c'était l'option la moins chère.

### La nuance que notre propre gouvernance cible oblige à écrire

Notre dossier a retenu, l'après-midi même, une directive qui **centralise** : `PSSI-CADRE-JRN-01`, *collecte des journaux vers le SOC centralisé du groupe*. Il faut dire pourquoi ce n'est pas la proposition du dossier 2 sous un autre nom — sinon la gouvernance cible contredirait le diagnostic du matin.

La différence n'est pas le degré de centralisation, elle est la **topologie** et le **niveau de décision** :

| | Proposition du dossier 2 | `PSSI-CADRE-JRN-01` (D1) |
|---|---|---|
| Qui porte l'outil | **Une filiale**, qui s'exploite et se supervise elle-même | Le **groupe**, propriétaire `RSSI Groupe (SOC)` |
| Qui décide de son financement | Le budget d'une filiale — donc ses priorités à elle | Le Comité Exécutif, **A** sur l'arbitrage des budgets sécurité |
| Ce qui arrive si le porteur est compromis | Les quatre filiales perdent la vue **et** l'attaquant est déjà dans l'une d'elles | Le SOC est un actif de groupe, distinct des périmètres exploités |
| Nature de la décision | Économique, prise par un DSI | Risque, arbitrée au niveau qui engage le groupe |

La centralisation n'était donc pas le problème : **le propriétaire l'était.**

---

## Question 4 — La réponse de posture, pour jeudi

*Pour chaque dossier, une phrase disant ce que le RSSI Groupe propose que la Direction Générale **DÉCIDE**, sans trancher personnellement ce qui n'est pas de son ressort.*

> **Dossier 1** — *« Je propose que le groupe adopte une règle d'arbitrage des flux inter-filiales, et que ce flux en soit le premier cas d'application ; je présente la règle jeudi. »*

> **Dossier 2** — *« Je propose de caractériser le risque de concentration avant toute décision : j'apporte une analyse d'ici la fin du mois ; la question du coût viendra après la question du risque. »*

> **Dossier 3** — *« Je propose que la tenue du registre soit une obligation de la filiale avec un propriétaire nommé, et que l'audit reste dans un rôle de contrôle ; je soumets la règle correspondante au prochain comité. »*

### Pourquoi ces trois phrases tiennent

- **Chacune désigne une DÉCISION et son NIVEAU.** Aucune ne décrit un état, aucune ne se contente d'alerter : les trois se terminent sur quelque chose que la Direction Générale peut approuver ou refuser jeudi.
- **Aucune ne configure quoi que ce soit.** Le test annoncé par la méthode — *une réponse à la question 4 qui contient un terme de configuration réseau signale un changement de métier en cours de route* — est passé : ni VLAN, ni pare-feu, ni règle de filtrage, ni outil n'apparaît dans les trois phrases. Les garanties techniques du flux du dossier 1 viendront, mais elles viendront **après** la règle et **sous** elle.
- **Chacune annonce la pièce qui viendra l'appuyer** — la règle jeudi, l'analyse d'ici la fin du mois, la règle au prochain comité. Une proposition sans échéance se transforme en conversation.
- **Aucune ne prend la décision à la place de la Direction.** C'est la limite de la posture, et c'est ce qui rend les trois phrases acceptables : le RSSI Groupe ne s'attribue ni le veto sur le dossier 1, ni l'arbitrage budgétaire du dossier 2, ni l'autorité hiérarchique sur la filiale Santé du dossier 3.

---

## Ce que ces trois dossiers deviennent dans la suite de la journée

Le TP de l'après-midi construit la gouvernance cible, et l'étalon qui lui est imposé est précisément celui-ci : **la gouvernance doit rendre chacun des trois dossiers impossible, et le dire.**

| Dossier | Ce qui le rend impossible dans D1 |
|---|---|
| **1** | `ARB-01` — véto suspensif du RSSI Groupe, **arbitrage rendu sous 72 h** : un désaccord inter-filiales a désormais un arbitre et un délai, là où celui-ci a duré trois mois. Complété par `ARB-02` (droit d'isolement d'urgence) pour le cas où le flux, une fois ouvert, tournerait mal — Santé obtient la garantie qui fondait son refus. |
| **2** | La ligne **« Groupe »** de l'analyse d'écart — *l'absence de PSSI-cadre et de règles d'arbitrage est l'écart de gouvernance dont découlent tous les autres* — et le choix de topologie inscrit dans `PSSI-CADRE-JRN-01` : un SOC **de groupe**, propriétaire RSSI Groupe, et non l'outil d'une filiale. Surveillé par le KRI *part du périmètre non supervisé par le SOC* (cible < 5 %, seuil > 20 %). |
| **3** | La **matrice RACI** (l'auditeur A sur sa seule évaluation, jamais sur un processus qu'il contrôle) et la directive `PSSI-CADRE-ACC-02` (revue trimestrielle des privilèges, propriétaire RSSI de filiale, vérifiable par la date de la dernière revue). |

---

*Note collective du TD 1 de la séance 1, consolidée le 15 septembre 2026 à partir du travail de la séance du 1er septembre 2026 et des pièces qui en sont issues (`D1`, TP `S1-05`, TD `S1-03`). Les deux pages individuelles du bureau du RSSI de la séance 1 traitent un angle distinct — « de quoi un conseil d'administration a-t-il réellement besoin de son RSSI ? » — et ne se substituent pas à cette note.*
