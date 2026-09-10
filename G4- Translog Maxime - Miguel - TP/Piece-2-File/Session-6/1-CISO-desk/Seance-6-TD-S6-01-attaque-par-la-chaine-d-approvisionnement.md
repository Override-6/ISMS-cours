# Séance 6 — TD (S6-01) : The CISO's Desk — Supply Chain Attack
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN

> Enchaînement de la journée : ce TD du matin **inventorie** les tiers déjà installés dans le système et
> qualifie chacun comme chemin de pivot ; le CM (*Security by Design*) montre que chacun de ces liens a
> un **point de naissance — un projet** ; l'après-midi (TD 2, ateliers 3 et 4 d'EBIOS RM) **cote** cet
> écosystème et en tire les scénarios stratégiques ; le TP saisit l'écosystème dans `translog-b` et le
> livrable **D6** en sort. Rien de ce qui est écrit ici n'est jetable : le tableau de la question 1 est
> la matière première de l'atelier 3, et la décision de la question 4 devient une exigence contractuelle
> de D6.

**Vocabulaire** : chaîne d'approvisionnement du SI, attaque par rebond (*pivot*), risque tiers — au sens
du TD de la séance 6. Filiale sous revue : **MERIDIAN Logistique** (instance `translog-b`).
Besoins de sécurité notés **DICT** (Disponibilité, Intégrité, Confidentialité, Traçabilité).
Sigles développés au premier emploi : **TMA** (tierce maintenance applicative), **WMS** (*warehouse
management system*, logiciel de gestion d'entrepôt), **SOC** (*security operations center*, centre de
supervision de la sécurité), **API** (interface de programmation), **VLAN** (réseau local virtuel),
**IT/OT** (bureautique / industriel).

---

## Rappel du cas

**Dimanche soir.** La Directrice Générale du groupe transfère au RSSI Groupe une enquête de presse
consacrée aux attaques par la chaîne d'approvisionnement, avec ce message : *« Ce qui est arrivé aux
clients de ce logiciel de comptabilité, est-ce que ça peut nous arriver par un de nos prestataires ? Je
veux que votre briefing de jeudi commence par la réponse. »*

**En main** : la cartographie de la séance 2 et sa vue écosystème (D2), les biens supports et le Top 5,
la gouvernance de la séance 1 (D1), le rapport d'audit de la séance 4 (D4) et l'appréciation des risques
ouverte en séance 5 (D5). **Pas de nouvelle étude avant jeudi** — l'exercice mesure aussi la capacité à
réutiliser la cartographie comme un actif, ce qu'elle est.

**Tâche du matin** : préparer la partie « chaîne d'approvisionnement » du briefing trimestriel au Comité
Exécutif. Pas un cours à la direction : une réponse — *où le groupe est exposé, ce qu'on en sait déjà,
ce que le RSSI Groupe demande*.

---

## Les trois notions, posées avant l'exercice

| Notion | Ce que c'est | Sa mécanique de risque | Sa limite |
|---|---|---|---|
| **Chaîne d'approvisionnement du SI** | L'ensemble des fournisseurs, prestataires et flux entrants dont le SI dépend pour fonctionner : matériels, logiciels, **mises à jour**, services, maintenance | Chaque maillon détient, par construction, un accès ou une influence sur le SI qu'un attaquant extérieur n'aura jamais ; compromettre le maillon revient à hériter de cet accès | Elle ne se lit pas sur un organigramme : la plupart de ces dépendances sont contractées par les métiers, filiale par filiale, sans passer par le RSSI |
| **Attaque par rebond** (*pivot*) | Compromettre d'abord un acteur qui détient un accès légitime à la cible, puis rebondir depuis cet acteur | Logique du moindre effort : pourquoi forcer une porte blindée quand un fournisseur en détient la clé et la protège moins bien ? Trois chemins : le **logiciel** (mise à jour piégée), le **prestataire** (accès de maintenance), l'**interconnexion** (partenaire raccordé) | « Rebond » décrit le **chemin**, pas la **gravité** : un rebond peut finir en vol de données mineur comme en arrêt complet de production |
| **Risque tiers** | La part de risque qui naît avec des acteurs que l'organisation ne contrôle pas directement, mais dont elle a accepté la présence dans son système, par contrat ou par usage | Il se **gère**, il ne s'élimine pas : renoncer à tout tiers, c'est tout réinternaliser, qu'aucune direction ne financera | Déjà mesuré : **35 %** des cyberattaques significatives subies par les entreprises sont passées par une attaque indirecte via un tiers — **3ᵉ vecteur d'entrée** (baromètre CESIN 2026) |

**Les deux cas de référence, à garder pour toute la journée.**
**NotPetya**, 27 juin 2017 : la page d'alerte de la CISA (agence de cybersécurité des États-Unis)
documente le mécanisme de diffusion — la **mise à jour** d'un logiciel de comptabilité fiscale ukrainien,
*M.E.Doc*, dont l'environnement de l'éditeur avait été compromis. Les victimes n'ont pas été piratées une
à une : elles ont installé, **de bonne foi**, la mise à jour d'un logiciel légitime. Le transporteur
**A.P. Møller-Mærsk** a chiffré dans sa communication financière un impact de **250 à 300 millions de
dollars** sur ses activités *Transport & Logistique* au 3ᵉ trimestre 2017. *Mærsk n'était pas la cible :
il était client du mauvais logiciel, au mauvais moment.*
**SolarWinds**, découvert en décembre 2020 : la déclaration conjointe du FBI, de la CISA, de l'ODNI et de
la NSA situe à **environ 18 000** le nombre de clients publics et privés du produit *Orion* ayant reçu la
mise à jour piégée de cet outil de supervision, un nombre bien plus faible ayant ensuite subi une
activité de l'attaquant. **L'asymétrie à retenir** : une seule compromission chez l'éditeur, des milliers
d'organisations touchées, et l'attaquant choisit ensuite ses vraies cibles dans le lot.

> 💡 **Réflexe de méthode**, appliqué à chaque ligne du tableau ci-dessous : quand un incident « chez un
> fournisseur » est signalé, poser les deux questions **dans cet ordre**. (1) *Que peut faire ce
> fournisseur sur mon SI en temps normal — accès, flux, mises à jour ?* → il mesure l'**exposition**.
> (2) *Qu'est-ce qui m'alerterait si ce pouvoir était utilisé par quelqu'un d'autre ?* → il mesure la
> **capacité de détection**. **Une réponse vide à la seconde est déjà un constat.** C'est le fil de toute
> notre journée : chez nous, la seconde colonne est vide sur nos trois accès de tiers les plus puissants.

---

## Question 1 — Inventaire des dépendances tierces, et question 2 — qualification en chemin de pivot

*Sources : pack de filiale §3 (carte du pouvoir), §4 (inventaire tel qu'envoyé), §5 (constats du
diagnostic), §6 (ce qui franchit la frontière) ; reference pack §5 (dépendances inter-filiales) et §3 ;
les quatre constats rappelés dans l'énoncé. La qualification de la question 2 tient dans la dernière
colonne, comme le demande la méthode de travail. Les références `LOG-SA-xx` sont celles de **D2**.*

### A. MERIDIAN Logistique — la filiale sous revue

| # | Tiers ou flux entrant | Filiale | Nature de l'accès ou de la dépendance | Ce qu'il peut atteindre | **Q2 — pourquoi c'est un chemin de pivot attirant** |
|---|---|---|---|---|---|
| **T1** | **TMA du WMS** (`LOG-SA-10`) | Logistique | Compte de **domaine partagé**, dont personne n'établit le nombre de porteurs ; contrat prévoyant l'astreinte, **pas** la journalisation nominative | Le WMS et sa base (`LOG-SA-01`), donc `LOG-PA-01` — un arrêt > 6 h bloque **40 % du volume expédié du groupe** ; et, par le compte de domaine, le réseau bureautique de la filiale | Un **seul secret** ouvre le système le plus critique de la filiale, il est déjà partagé hors de nos murs, et son usage n'est imputable à personne : meilleur rapport effort/gain du dossier, et l'intrusion se confond avec l'exploitation normale |
| **T2** | **Flux de mise à jour du WMS** | Logistique | Mises à jour posées **la nuit, quand la TMA le décide**, découvertes le matin (§4) ; ni fenêtre annoncée, ni validation, ni retour arrière documenté | Le WMS **en production sur les six sites simultanément** | C'est le mécanisme **NotPetya** à l'identique : compromettre une fois l'environnement du fournisseur pour être installé, en confiance, sur toutes les cibles — et ici, personne ne regarde ce qui est posé |
| **T3** | **Intégrateur des automates de tri** (`LOG-SA-03`) | Logistique | Accès distant permanent par **box 4G hors du réseau supervisé**, plus interventions sur site ; contrat **sans réversibilité ni exigence de sécurité** ; réglages revendiqués comme propriété industrielle | Les automates d'E2/E3/E4 et — faute de cloisonnement IT/OT (constat **C3** de D4) — le réseau bureautique et le WMS | Un accès qui n'est pas sur notre réseau ne produit **aucun journal chez nous** ; la porte est ouverte en permanence, elle donne sur un réseau plat, et son propriétaire nous refuse déjà la connaissance des réglages |
| **T4** | **Techniciens de l'intégrateur appelés en direct** | Logistique | Canal humain hors DSI : chaque chef d'entrepôt détient le numéro de mobile d'un technicien et l'appelle directement (§3) ; aucune vérification d'identité | La décision d'intervenir sur les automates, et le prétexte d'un accès accordé de bonne foi | Le prétexte est **déjà normal ici** : un appel entrant qui dit « c'est moi, votre technicien » n'a rien d'anormal, et rien ne permet de vérifier que c'en est un |
| **T5** | **Fournisseur des sondes de température** et son logiciel **hébergé chez lui** (`LOG-SA-05`) | Logistique | Logiciel en ligne hors de notre maîtrise ; la Qualité y accède ; rapport mensuel au client pharmaceutique | Les relevés de température = `LOG-PA-02` (chaîne du froid) **et** `LOG-PA-04` (la preuve produite à l'audit annuel, **12 000 €/jour** de pénalités) | Pour atteindre le contrat, l'attaquant n'a pas besoin d'entrer chez nous : **la preuve que le client vérifie est stockée et modifiable ailleurs**, et la Responsable Qualité dit elle-même qu'elle ne saura pas répondre à « qui a accès aux relevés ? » |
| **T6** | **Fournisseur de télématique** (flotte, remorques) | Logistique | Abonnement : *« le fournisseur gère tout, on regarde un écran »* (§3) ; aucune exigence de sécurité formulée | Les données de température **en transport** et la position des véhicules | Dépendance déclarée nulle par le métier, donc **jamais examinée** : c'est la définition d'un angle mort, et elle porte une part de la preuve de chaîne du froid |
| **T7** | **Opérateur des liens entre entrepôts** | Logistique | Les cinq entrepôts hors E1 n'atteignent le WMS que par ses liaisons (§4) | La préparation de commandes des cinq sites — démontré en avril | Pas besoin d'entrer dans le SI : **couper la dépendance suffit** à produire l'effet, et le service est mutualisé, donc atteignable sans nous viser |
| **T8** | **Portail d'expédition du client pharmaceutique** | Logistique → client | **Un compte par entrepôt** (§4), donc six comptes partagés par les équipes, hors de notre annuaire | Nos données d'expédition chez le client, et notre identité vis-à-vis de lui | Un compte partagé **chez un tiers** est un pivot dans les deux sens — vers ses données et vers notre crédibilité contractuelle — sans qu'aucun journal n'existe de notre côté |
| **T9** | **Application en ligne de paie et comptabilité** | Logistique + holding | Service partagé à l'échelle du groupe, piloté par la Directrice Financière du holding, hors décision de la filiale (§4) | Les données de paie et de comptabilité des 2 800 salariés | **Un service unique pour quatre filiales** : une compromission chez l'éditeur touche le groupe entier d'un coup, et la filiale n'a ni le contrat ni le levier pour l'exiger autrement |
| **T10** | **SOC du groupe** *(dépendance interne — capacité de détection)* | Logistique | Reçoit les journaux du **réseau bureautique** ; **rien** des automates, de la box 4G, ni du WMS lui-même (§6) | Ce qui devrait voir passer les neuf lignes précédentes | Ce n'est pas un chemin d'entrée, c'est **ce qui rend les autres durables** : sur nos trois accès de tiers les plus puissants, l'attaquant sait qu'il n'est pas regardé. C'est la **réponse vide** du réflexe de méthode |

### B. Le niveau groupe — dépendances inter-filiales et tiers des autres filiales

*Reference pack §5 (les trois liens qui font du groupe autre chose qu'une somme de filiales), §3 et §6,
et les quatre constats rappelés par l'énoncé. Le RSSI Groupe parle depuis cette chaise : ces lignes sont
à la même table que les précédentes.*

| # | Tiers ou flux entrant | Filiale(s) | Nature de l'accès ou de la dépendance | Ce qu'il peut atteindre | **Q2 — pourquoi c'est un chemin de pivot attirant** |
|---|---|---|---|---|---|
| **T11** | **Flux de réapprovisionnement d'urgence** (scannettes `LOG-SA-02` → interface `LOG-SA-13` → VLAN dédié `LOG-SA-12`) | **Logistique → Santé** | API sur VLAN dédié avec pare-feu d'inspection — **la seule segmentation que le diagnostic ait trouvée dans le groupe** ; **flux coupé depuis trois mois** à la demande de la RSSI de Santé | Le système de gestion des stocks pharmaceutiques de Santé, depuis nos ~300 scannettes Wi-Fi | **Le seul actif dont deux filiales dépendent** : compromettre nos scannettes, c'est écrire dans les commandes d'une pharmacie hospitalière. C'est exactement la raison invoquée par Santé pour couper — *« leur matériel n'est pas fiable »* — et la coupure protège Santé au prix d'un risque sanitaire côté patients (*« ça ne tiendra pas l'hiver »*) |
| **T12** | **Annuaire d'identités du cluster Éducation & Territoires** | Éducation + Territoires | Un annuaire, deux filiales, **comptes d'administration partagés** ; personne ne peut dire qui a fait quoi | Les **45 000 comptes**, dont des mineurs, et par rebond les bases administratives de Territoires | Le pivot est déjà **interne et gratuit** : un compte d'administration obtenu d'un côté vaut de l'autre, et aucune trace ne permettra d'établir par où c'est entré |
| **T13** | **Infogérant du portail d'Éducation** et son **sous-traitant de sauvegarde de second rang, absent du contrat** | Éducation | Hébergement externalisé ; la sauvegarde est confiée à un acteur avec lequel le groupe n'a **aucun lien contractuel** | Le portail des 45 000 comptes **et la copie de ses données** | Un maillon que le groupe ne connaît pas, ne contrôle pas et ne peut pas auditer détient la copie des données : archétype du **rang 2**. Le RGPD compte cette sous-traitance ultérieure comme une obligation, pas comme un détail |
| **T14** | **Onze abonnements en ligne hors inventaire** (dont un outil d'IA générative recevant des copies d'élèves) | Éducation | Souscrits directement par les équipes pédagogiques, hors DSI, **sans contrat ni analyse d'impact** | Des données personnelles de mineurs | Une dépendance qui n'est **dans aucun inventaire** ne peut être ni surveillée ni fermée. Et rien ne dit que les trois autres filiales en soient exemptes : elles n'ont simplement pas cherché |
| **T15** | **Infogérant du mobilier urbain** de Territoires | Territoires | Exploite le parc, **détient les clés de chiffrement des transactions** et a **refusé par écrit** de les rendre ; contrat courant **jusqu'en 2028** ; détient aussi la liste du parc, absent de tout inventaire | La plateforme de services aux citoyens des ~30 collectivités clientes et les données citoyennes régulées ; journaux conservés localement, donc aucune détection | L'attaquant qui compromet cet infogérant hérite **à la fois des clés et de la carte du parc** ; le groupe, lui, ne dispose ni de l'une ni de l'autre, et n'a pas de levier contractuel avant 2028 |
| **T16** | **Projet de plateforme pédagogique Éducation ↔ bases administratives Territoires** | Éducation + Territoires | Dépendance **à naître**, aujourd'hui en arbitrage : Territoires s'y oppose | Les bases administratives à données citoyennes régulées | La seule ligne du tableau qu'on peut encore écrire **avant** qu'elle existe : c'est aujourd'hui une exigence de cadrage qui coûte une réunion, ce sera demain une interconnexion héritée qu'on rattrapera à coups de zone tampon et d'API sécurisées |

**Ce que le tableau apprend, avant même toute cotation.** Sur les seize lignes, **aucune** n'a été
contractée par un RSSI, et **treize** n'ont jamais fait l'objet d'une exigence de sécurité écrite. Les
trois plus puissantes chez nous — T1, T2, T3 — partagent la même propriété : *nous savons ce qu'elles
peuvent faire, nous ne savons pas dire si quelqu'un d'autre s'en sert*.

---

## Question 3 — Transposer les deux cas sur le groupe

*Pour chaque mécanisme : l'endroit du groupe qui lui ressemble le plus, justifié par un élément du
dossier — jamais par une intuition — et la clause contractuelle qui aurait aidé.*

### (a) Mécanisme « mise à jour logicielle piégée » (NotPetya, SolarWinds)

> **L'endroit : le flux de mise à jour du WMS de MERIDIAN Logistique (T2).**

**Justification, pièce par pièce.**
1. *« La TMA fait les mises à jour la nuit, quand elle veut, on l'apprend le matin »* — notes d'entretien,
   pack §4. Le flux est **entrant, automatique et non validé** : c'est la définition du vecteur M.E.Doc.
2. La TMA intervient avec un **compte de domaine partagé dont personne n'établit le nombre de porteurs**
   (pack §3 et §5.2) : une compromission chez elle ne se distingue pas d'une intervention légitime.
3. Le **SOC ne reçoit rien du WMS** (pack §6) : rien ne dirait qu'une mise à jour a fait autre chose que
   ce qu'elle annonçait.
4. Le WMS porte `LOG-PA-01` : un arrêt > 6 h bloque **40 % du volume expédié du groupe**, et les
   sauvegardes quotidiennes **n'ont jamais été restaurées depuis la mise en service** (pack §5.4) — la
   reprise n'est donc pas démontrée.

**La ressemblance n'est pas métaphorique** : le vecteur de NotPetya était la mise à jour d'un logiciel
métier, et la victime la mieux documentée exerçait **notre métier** — transport et logistique, 250 à
300 M$ au 3ᵉ trimestre 2017. Nous sommes, ligne pour ligne, dans la position de Mærsk.

*Au niveau du groupe, le même mécanisme sous sa variante « asymétrie SolarWinds »* : T13 (le
sous-traitant de sauvegarde de second rang d'Éducation, absent du contrat) et T14 (les onze abonnements
hors inventaire) — un fournisseur unique servant beaucoup de monde, dont le groupe ne sait rien.

**La clause qui aurait aidé — clause de gestion des changements et des mises à jour :**
> Toute mise à jour, correctif ou modification de configuration n'est déployée qu'en **fenêtre notifiée à
> l'avance**, accompagnée de la **liste des composants livrés**, avec **procédure de retour arrière
> documentée et testée** ; le prestataire **notifie sous 24 heures toute compromission de son propre
> environnement de production ou de livraison** ; le donneur d'ordre peut **suspendre le flux de mise à
> jour** sans que la suspension constitue un manquement de sa part.

Elle se combine avec ce que le groupe s'impose déjà — `PSSI-CADRE-COR-01` (correctif critique sous
14 jours, D1) — et le corrige : la directive actuelle impose un **délai**, elle ne contrôle pas **ce qui
est posé**. Les deux vont ensemble ; l'une sans l'autre transforme la diligence en vecteur.

### (b) Mécanisme « accès de maintenance détourné »

> **L'endroit chez nous : la box 4G de l'intégrateur des automates de MERIDIAN Logistique (T3).**
> **L'endroit qui lui ressemble le plus dans le groupe : l'accès distant permanent de l'éditeur du SIH
> de MERIDIAN Santé, par un identifiant unique partagé entre neuf personnes** (reference pack §3).

**Justification, pièce par pièce (Logistique).**
1. La box 4G a été installée par le Responsable Exploitation *« pour ne plus dépendre de l'informatique
   quand une machine tombe »* (pack §3) : l'accès existe **précisément parce qu'il contourne** le
   contrôle.
2. Elle est **hors du réseau supervisé** et le **SOC n'en reçoit aucun journal** (pack §2, §6) :
   exposition maximale, détection nulle — les deux questions du réflexe de méthode, réponse pleine puis
   réponse vide.
3. Le contrat ne porte **ni clause de réversibilité ni exigence de sécurité** (pack §3, §5) : aucun
   levier pour exiger quoi que ce soit sans renégocier.
4. Les réseaux bureautique et industriel sont **interconnectés sans cloisonnement** (constat **C3** de
   D4, non-conformité majeure) : l'accès ne donne pas sur un automate, il donne sur **tout**.
5. Ajouter T4 : six chefs d'entrepôt appellent des techniciens sur leur mobile personnel — le détournement
   n'a même pas besoin d'être technique.

*Variante Santé* : un identifiant unique pour neuf personnes chez l'éditeur, en accès permanent à un SI
portant des données de santé — même mécanisme, imputabilité tout aussi inopérante, et l'audit interne du
holding attend depuis trois demandes le registre des comptes d'administration.

**La clause qui aurait aidé — clause d'accès de maintenance à distance :**
> L'accès distant du prestataire s'effectue par **comptes nominatifs individuels**, à travers un **point
> d'accès supervisé par le donneur d'ordre**, avec **journalisation par utilisateur nommé** transmise au
> SOC ; le prestataire tient et communique la **liste nominative des personnes habilitées**, la met à jour
> **au départ de chaque intervenant**, et se soumet à un **droit d'audit** ; le contrat porte une **clause
> de réversibilité** incluant la restitution des configurations, des paramétrages et des secrets.

C'est mot pour mot ce que **D4** a déjà décidé de porter au contrat de l'intégrateur (recommandation 2,
mesure **M2**, échéance 8/12/2026) et d'exiger de la TMA (recommandation 3, mesure **M4**, 8/11/2026), et
ce que l'**énoncé d'appétence n°2 adopté en séance 5** rend non négociable : *« MERIDIAN n'accepte pas
qu'une action d'administration ou d'un prestataire sur un système portant un actif critique reste non
imputable à une personne nommée, ni qu'un contrat de prestation nouveau ou renouvelé omette la
journalisation par utilisateur nommé et une clause de réversibilité. »* Le matin ne découvre donc pas la
règle : il montre **où elle n'est pas encore appliquée**.

---

## Question 4 — Les trois messages du briefing de jeudi

*Écrits comme ils seront prononcés. Contrainte tenue : rien d'affirmé ne dépasse ce que le dossier
prouve.*

### Message 1 — le fait sourcé qui cadre le sujet

> « Trente-cinq pour cent des cyberattaques significatives subies par les entreprises sont passées par
> une attaque indirecte, via un tiers : c'est le troisième vecteur d'entrée, selon le baromètre CESIN
> publié en 2026. Le sujet n'est ni théorique ni marginal. L'exemple de l'article que vous m'avez
> transféré est réel et il nous concerne directement : en 2017, le transporteur Mærsk n'a pas été
> piraté — il a installé de bonne foi la mise à jour d'un logiciel de comptabilité ukrainien, et il a
> chiffré l'impact entre **250 et 300 millions de dollars** sur ses activités Transport & Logistique
> pour un seul trimestre. En 2020, une seule mise à jour piégée du logiciel de supervision SolarWinds
> Orion a été reçue par **environ 18 000 clients**, l'attaquant choisissant ensuite ses vraies cibles
> dans le lot. »

### Message 2 — la phrase honnête sur l'exposition du groupe

> « Je ne peux pas vous dire aujourd'hui que cela ne peut pas nous arriver, et je vais vous dire
> exactement pourquoi. Notre prestataire de maintenance du WMS pose ses mises à jour la nuit, quand il le
> décide, et nous les découvrons le matin ; il intervient avec un compte de domaine partagé dont nous ne
> savons pas combien de personnes le détiennent — l'audit interne a demandé la liste nominative, il a
> reçu un nom de compte. L'intégrateur de nos automates entre par une box 4G qui n'est pas sur notre
> réseau supervisé, sous un contrat qui ne comporte aucune exigence de sécurité. Et notre SOC ne reçoit
> aucun journal, ni des automates, ni de cette box, ni du WMS lui-même. Autrement dit : sur ces trois
> accès, je sais mesurer **ce qu'ils peuvent faire**, et je ne sais pas dire **si quelqu'un d'autre s'en
> sert**. Je n'ai aucun élément indiquant que ce soit le cas ; je n'ai pas non plus de quoi l'exclure, et
> c'est ce constat-là que je porte devant vous. Il n'est pas propre à Logistique : Éducation confie ses
> sauvegardes à un sous-traitant absent de son contrat, et l'infogérant de Territoires détient des clés
> de chiffrement qu'il a refusé par écrit de rendre, jusqu'en 2028. »

### Message 3 — la décision demandée au Comité Exécutif

> « Je demande au Comité une décision en deux volets, dont aucun ne requiert de budget nouveau cette
> année.
> **Premier volet, la règle** : aucun contrat de prestation donnant accès à un actif critique n'est signé
> ni renouvelé sans trois clauses — **journalisation par utilisateur nommé**, **notification sous 24
> heures d'une compromission chez le prestataire**, **réversibilité**. C'est l'application directe de
> l'appétence que la Direction Générale a fixée et que le Conseil approuve ; je demande au Comité d'en
> faire une condition de signature, opposable par la Direction Juridique.
> **Deuxième volet, deux applications immédiates et une date** : le contrat de l'intégrateur des automates,
> qui ne porte aucune de ces clauses et vient à renouvellement, et la liste nominative des porteurs du
> compte de la TMA, que l'audit interne attend — ce sont les mesures M2 et M4 de notre plan d'action, déjà
> votées. Et je demande que la recommandation n°5 de l'audit — remonter au SOC les journaux du WMS, de la
> box 4G et des automates — reçoive **une date et un propriétaire aujourd'hui** : c'est la seule des cinq
> recommandations qui n'en a pas, et c'est celle qui remplit la case vide dont je viens de vous parler.
> Ce que je ne demande pas : arrêter quoi que ce soit, ni changer de prestataire. »

**Ce que ces trois messages ne disent pas, volontairement** : aucune affirmation qu'une compromission a
eu lieu (nous n'en avons aucun élément), aucun chiffrage de notre exposition en euros (l'appréciation des
risques n'est pas achevée — elle l'est cet après-midi), aucune promesse de délai sur le cloisonnement
IT/OT au-delà de ce que D4 a déjà daté.

---

## Question 5 — Ce que l'analyse du matin ne sait pas encore faire

> Ce matin produit un **inventaire qualifié** de dépendances — seize lignes, chacune avec ce qu'elle peut
> atteindre et pourquoi elle attire un attaquant — mais aucune **échelle commune** : rien ici ne mesure la
> dépendance réelle à chaque partie prenante, sa pénétration dans notre SI, sa maturité ni la confiance
> qu'on peut lui accorder, et rien ne relie encore une partie prenante à un **événement redouté** coté.
>
> Pour passer de « voici nos dépendances » à « voici celles à traiter en premier », il manque exactement
> l'**atelier 3 d'EBIOS RM** de cet après-midi — la cartographie de menace de l'écosystème et les
> **scénarios stratégiques** qui relient une source de risque à un événement redouté **en passant par un
> tiers** —, puis l'**atelier 4** et le **seuil d'acceptation** posé sur la grille 4×4 de D5, qui seuls
> transforment un classement en décision de traitement.

*Le dossier avait d'ailleurs prévu ce rendez-vous* : D5 a explicitement mis en réserve le **couple SR/OV
n°2 — « attaquant passant par l'intégrateur des automates, via la box 4G non supervisée »** — au motif
qu'il *« relève d'abord d'un risque de dépendance qui se traite au contrat et qui sera repris comme partie
prenante critique de l'écosystème en séance 6 (atelier 3) »*. C'est ce matin qui vient d'en faire la
démonstration ; c'est cet après-midi qui le cotera.

---

## Auto-évaluation (grille du TD, sur 10)

| Critère | Niveau atteint |
|---|---|
| **Q1 — inventaire** | Seize lignes en quatre colonnes, tirées de §3, §4, §5 et §6 du pack de filiale et de §3 et §5 du reference pack, sans s'arrêter aux prestataires contractés : un **flux de mise à jour** (T2), un **canal humain** (T4), une **dépendance de détection** (T10) et une **dépendance à naître** (T16) figurent au tableau ; les quatre constats de l'énoncé sont tous repris |
| **Q2 — qualification** | Une phrase par ligne, en logique de moindre effort et du point de vue de l'attaquant, tenue dans une colonne du tableau comme le demande la méthode |
| **Q3 — transposition** | Les deux mécanismes désignés à un endroit précis du groupe, chacun justifié par **quatre à cinq éléments cités du dossier** (§ du pack, constat de D4), la variante groupe nommée pour chacun, et **une clause contractuelle rédigée** par mécanisme, raccordée aux mesures M2/M4 de D4 et à l'énoncé d'appétence n°2 de D5 |
| **Q4 — trois messages** | Fait sourcé (CESIN 2026 · Mærsk · SolarWinds), phrase d'exposition honnête et bornée (« je sais ce qu'ils peuvent faire, je ne sais pas dire si quelqu'un d'autre s'en sert »), décision demandée en deux volets sans budget nouveau, plus la liste explicite de ce qui **n'est pas** affirmé |
| **Q5 — la limite** | Deux phrases : l'absence d'échelle de danger de l'écosystème et de lien aux événements redoutés, et le renvoi nommé à l'atelier 3, à l'atelier 4 et au seuil d'acceptation de D5 — avec la mise en réserve du couple n°2 comme preuve d'articulation |

*Chaque case vise la colonne « Excellent » de la grille officielle — à confronter en séance avec le
corrigé de référence du module (replié dans l'énoncé, « cliquer pour révéler »).*

---

> **Suite immédiate.** Le tableau de la question 1 est la **liste des parties prenantes** saisie à
> l'atelier 3 (TP 1, `translog-b`) ; les deux clauses rédigées à la question 3 entrent dans les
> **exigences de sécurité applicables aux tiers** du livrable **D6** (TP 2) ; la décision de la question 4
> devient la règle de contractualisation que D6 porte et que la **sous-section 6 de la note de stratégie**
> affirme ; la limite de la question 5 est le sujet du TD 2 de l'après-midi.
