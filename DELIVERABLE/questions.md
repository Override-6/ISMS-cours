# Questions — ce qui est demandé, séance par séance

Résumé fidèle des **TD** (travaux dirigés, dont le « bureau du RSSI ») et des **TP** (travaux pratiques / labs) du module
**M2-01-4-ISMS — Gouvernance de la sécurité et cartographie du SI** (Lockbay Academy), tel que les énoncés sources le
demandent.

- **Rôle tenu** : RSSI Groupe de **MERIDIAN** (holding 150 pers. + 4 filiales : Santé 3 200, Logistique 2 800,
  Éducation 900, Territoires 650 ; Éducation & Territoires partagent une DSI mutualisée).
- **Rythme d'une séance** : CM le matin (théorie, non détaillé ici), TD, puis TP l'après-midi, et **15 min de note de
  stratégie** pour clore la journée.
- **Produits** : dossier MERIDIAN cumulatif, livrables numérotés **D1 → D9** (un par séance), et la **note de stratégie**
  (3 à 5 pages de texte, cumulative : la version de la séance N contient les sous-sections 1 à N ; *rien ne se supprime,
  tout s'amende avec une phrase de justification*).
- **Outil** : CISO Assistant (GRC open source, instance par groupe de travail).
- Chaque énoncé porte en plus un corrigé et une grille d'évaluation — non repris ici : ce fichier ne garde que
  **ce qui est demandé**.

> Sources : `Seance-1/`, `S2 - Sources/` … `S8 - Sources/`. Les titres anglais sont ceux des PDF d'origine.

---

## Séance 1 — Gouverner la sécurité : niveaux, acteurs, principes

*CM : « Decision levels and role distribution » (niveaux de décision, matrice RACI, appétence).*

### TD 1 — *Introduction to the module and The CISO's briefing* (S1-01)

**Cas** : premier lundi du RSSI Groupe, aucune PSSI groupe, trois dossiers laissés par la Direction Générale.
*(1)* Logistique veut un flux permanent scanners d'entrepôt → SI de gestion des stocks de Santé ; Santé refuse
(« matériel non de confiance »), blocage depuis 3 mois. *(2)* Le DSI d'Éducation propose de centraliser la supervision
sécurité des 4 filiales sur son outil, « c'est le moins cher ». *(3)* L'Auditeur Interne n'obtient pas le registre des
comptes d'administration de Santé et propose d'en **reprendre la gestion**.

Questions guidées :
1. **Caractériser chaque dossier** avec le vocabulaire du jour : lequel relève de l'**arbitrage inter-filiales**, lequel
   porte un **risque systémique**, lequel pose un problème de **gouvernance au sens strict** (« qui décide ») ?
   Une phrase de justification par dossier ; si un dossier relève de deux catégories, dire laquelle domine.
2. Appliquer les **trois questions du diagnostic** au dossier 3 : qui a décidé quoi, qui aurait dû, où cela devrait-il
   être écrit ?
3. Analyser le dossier 2 : l'argument coût est réel, la DSI mutualisée existe — que ferait néanmoins la proposition au
   **profil de risque** du groupe ?
4. Formuler la **réponse de posture** pour jeudi : pour chaque dossier, une phrase disant ce que le RSSI Groupe propose
   que la Direction **DÉCIDE**, sans trancher personnellement ce qui n'est pas de son ressort.

**Méthode** : 15 min seul, 10 min en binôme, 5 min de mise en commun. *Une réponse à la Q4 contenant un terme de
configuration réseau signale un changement de métier en cours de route.*

### TD 2 — *Structuring principles and anchoring activity* (S1-03)

Notions : défense en profondeur, moindre privilège, cloisonnement réseau, et la **grille de maturité à 4 niveaux**
(1 absentes · 2 informelles · 3 formalisées · 4 pilotées).

**Exercice 1 — MERIDIAN Santé, l'imagerie sur le réseau de tout le monde** *(12 min)*
Constats : analyseurs de laboratoire et consoles d'imagerie sur la même plage IP que la bureautique ; compte
administrateur local identique sur tout le parc.
1. Identifier le ou les principes violés par chaque constat, une phrase par principe (*le 2e constat en viole deux, dont
   un subtilement*).
2. Décrire le scénario que la combinaison rend possible, en **trois étapes au plus**, du poste bureautique compromis
   jusqu'aux équipements de soin.
3. Formuler la recommandation en langage de gouvernance : quelle décision, à quel niveau (stratégique, tactique,
   opérationnel), et qui est **A** dans le RACI correspondant ?

**Exercice 2 — MERIDIAN Logistique, le prestataire qui tient les clés du domaine** *(12 min)*
Constats : réseaux IT et OT interconnectés sans segmentation ; compte administrateur de domaine partagé entre la TMA et
l'administrateur système de la filiale.
1. Analyser le partage de compte au regard du **moindre privilège** : dresser la liste de tout ce que ce constat rend
   **impossible** (*traçabilité, révocation, imputabilité — pas seulement le risque d'intrusion*).
2. Expliquer pourquoi l'interconnexion IT/OT **aggrave spécifiquement** ce constat, au regard du cloisonnement.
3. Proposer la **séquence de remédiation dans le bon ordre**, et pourquoi cet ordre.

**Exercice 3 — Le pôle Éducation & Territoires, arbitrer un projet avec des principes** *(15 min)*
Projet de plateforme pédagogique d'Éducation devant se connecter aux bases administratives de Territoires (données
citoyennes régulées, trentaine de collectivités clientes).
1. Examiner le cas avec les trois principes : une phrase par principe.
2. **Arbitrer** : formuler une décision qui autorise **SOUS CONDITIONS**, en précisant les garanties exigées, en trois
   phrases au plus.
3. **Activité d'ancrage du module** : coter la maturité SSI des **quatre filiales** sur la grille, une phrase de
   justification par filiale, à partir des constats rappelés. *Cette grille sert de point de départ à tout le module.*

### TP 1 — *Framing the MERIDIAN case and target governance* (S1-05)

À produire dans l'heure : l'analyse d'écart du groupe, la gouvernance cible écrite, le premier tableau de bord.

**Exercice 1 — L'analyse d'écart du groupe** *(20 min)*
1. Construire le **tableau d'analyse d'écart** couvrant les 4 filiales à partir de tous les constats du jour
   (colonnes : filiale · écart observé · principe ou règle cible violé · priorité 1-3 et justification en une ligne).
2. **Prioriser sans égalitarisme** : au plus **deux écarts en priorité 1** pour tout le groupe, et chaque priorité
   justifiée par la **MISSION** de la filiale, pas par la seule gravité technique.
3. Repérer l'écart qui n'appartient à **aucune filiale** : lequel des constats du jour est un écart de **gouvernance du
   groupe lui-même** ? L'ajouter sur une ligne « Groupe ».

**Exercice 2 — Rédiger la gouvernance cible** *(25 min)* — document de 2 pages max, « Gouvernance cible de la sécurité
du groupe MERIDIAN », 4 sections :
1. Reporter en §1 les instances et la répartition des rôles sur l'appétence, en §2 la grille RACI des processus clés ;
   la recopie est permise, mais **chaque tableau est suivi d'une phrase disant ce qu'il empêche** (les trois dossiers de
   lundi sont l'étalon : la gouvernance doit rendre chacun impossible, et le dire).
2. Rédiger en §3 les **directives codifiées** du groupe : **au moins cinq**, sous la codification `[PSSI-CADRE-XXX-nn]`,
   couvrant obligatoirement : authentification des accès distants et privilèges d'administration · revue des privilèges
   sur les bases métier · notification des incidents majeurs au RSSI Groupe · collecte des journaux · traitement des
   correctifs critiques. Chaque directive passe **le test du sceptique** : vérifiable, propriétaire identifiable, délai
   ou fréquence.
3. Rédiger en §4 les **règles d'arbitrage inter-filiales**, sous forme de **trois règles** : le pouvoir du RSSI Groupe
   face à un désaccord entre filiales (*un arbitrage qui suspend sans enterrer*) ; le pouvoir d'urgence d'un RSSI de
   filiale sur un flux inter-filiales en cas de compromission avérée ; le circuit de dérogation à la PSSI cadre, avec
   son délai de validation.

**Exercice 3 — Le premier tableau de bord du RSSI Groupe** *(15 min)*
1. Construire le tableau de bord de direction : **au plus 4 KRI**, chacun avec sa cible et son seuil d'alerte, couvrant
   quatre expositions différentes (*ce que le SOC ne voit pas · le vieillissement du parc · les comptes qui ne désignent
   personne · le facteur humain*).
2. Définir **3 à 5 KPI** de mise en œuvre, chacun rattaché à **UNE** directive de l'exercice 2, avec sa valeur cible.
3. Vérifier la cohérence d'ensemble : **chaque priorité 1** de l'analyse d'écart doit être surveillée par au moins un
   indicateur. *Sinon, l'un des deux documents ment.*

### TP 2 — *Drafting the scoping documents and the strategy note* (S1-06)

**Exercice 1 — La note de cadrage du RSSI Groupe** *(15 min)* — une page, cinq sections.
1. Rédiger la note : **objet** (pourquoi ce poste existe, deux phrases ancrées dans la situation du groupe) ·
   **périmètre** (4 filiales, pôle à DSI mutualisée, flux inter-filiales) · **prérogatives** (en citant les trois règles
   d'arbitrage, sans les réécrire) · **interlocuteurs** (les instances, chacune avec ce qui lui est dû : proposition,
   reporting, alerte) · **limites**.
2. Soigner la section limites : **au moins trois exclusions** réalistes et utiles (*ce que le RSSI n'a PAS le droit de
   faire à la place des autres est le meilleur point de départ*).

**Exercice 2 — La feuille de route et son budget** *(15 min)* — trajectoire à 3 ans, 6 semestres, 3 axes imposés :
socle de confiance, résilience OT/IT, culture de sécurité.
1. Construire la feuille de route : un objectif principal par semestre, et **trois jalons vérifiables à 12, 24 et
   36 mois**, cohérents avec les priorités 1 et 2 de l'analyse d'écart.
2. Proposer la **pondération budgétaire** des trois axes, en pourcentages, une ligne de justification par axe, et en
   **PRÉCISANT la base** de chaque chiffre avancé.
3. Trancher **deux arbitrages** soumis par la Direction : Santé et Éducation demandent chacune un renfort immédiat sur
   une enveloppe exceptionnelle réservée à ces deux-là ; et une part des enveloppes existantes doit être réallouée à la
   modernisation d'infrastructures obsolètes. Justifier chacun des deux chiffres par un élément du dossier.

**Note de stratégie** *(15 min)* — ouverture du document, sous-section 1 : **« Contexte et gouvernance cible »**,
une demi-page max, trois contenus seulement : le contexte · la gouvernance cible **citée par renvoi à la charte, jamais
recopiée** · l'engagement de trajectoire (adaptation de la PSSI cadre par chaque filiale sous six mois).
*Deux disciplines à prendre dès maintenant : la note renvoie aux documents du dossier, elle ne les duplique pas ;
chaque affirmation doit rester vraie dans le temps ou être amendable en une phrase.*

---

## Séance 2 — Cartographie du système d'information

*CM : « The ANSSI mapping methodology » (les six vues de la cartographie).*

### TD 1 — *The CISO's Desk: Asset Inventory*

**Cas** : trois réponses reçues à la demande d'inventaire. **Santé** envoie un export d'outil de gestion de parc daté du
mois dernier, **sans les analyseurs de laboratoire ni les consoles d'imagerie**. **Logistique** répond que « c'est dans
la tête du Responsable Exploitation ». Le pôle **Éducation & Territoires** envoie un tableur honnête accompagné d'un
mail gêné : onze abonnements à des services en ligne souscrits directement par les équipes pédagogiques, hors DSI,
dont un **outil d'IA générative** où des enseignants font relire des évaluations d'élèves.

Questions guidées :
1. **Analyser les trois réponses** : pour chacune, ce qu'elle révèle de la maturité d'inventaire de la filiale et le
   risque principal qu'elle laisse ouvert (*les trois mots porteurs de la définition : tenu à jour, décrit, propriétaire*).
2. **Distinguer**, parmi les onze découvertes, ce qui relève du **shadow IT** ordinaire et ce qui relève du **shadow AI**,
   et expliquer en quoi le second cas aggrave la question des données.
3. Proposer le **traitement des onze services** : lesquels documenter et régulariser, lesquels superviser, lesquels
   fermer — et **par quel critère générique** (pas service par service : le critère).
4. Attribuer les responsabilités d'inventaire dans un **mini-RACI** : qui est R, qui est A, qui est consulté, qui est
   informé, aux trois niveaux de la séance 1. *Un seul A par ligne, et attention au réflexe de tout charger sur le RSSI
   Groupe.*
5. Formuler la **règle de gouvernance** à proposer jeudi, en **une seule phrase**, applicable aux quatre filiales,
   traitant à la fois de la tenue de l'inventaire et du sort de ce qui n'y figure pas.

**Méthode** : 10 min (Q1-2), 10 min (Q3-4), 5 min (Q5). *On travaille en RSSI Groupe, pas en auditeur.*

### TD 2 — *Business assets, supporting assets and DICT needs*

Vocabulaire EBIOS RM v1.5 : valeur métier, bien support (numérique / physique / organisationnel), besoin de sécurité
**DICT**, cotation en **position relative** sur 3 niveaux (négligeable, notable, très important).

**Exercice 1 — Les valeurs métier de la filiale étudiée** *(12 min)* — travail sur le **subsidiary pack** du groupe.
1. Identifier **entre trois et cinq valeurs métier**, formulées en langage métier, en s'en tenant à ce que le pack
   établit (*penser aussi aux informations et savoir-faire, pas seulement aux services rendus*).
2. Rattacher à chaque valeur métier ses **biens supports**, en couvrant les **trois natures** (numérique, physique,
   organisationnel) — l'inventaire brut en contient de chaque nature, aucun n'est étiqueté. Nommer pour chaque valeur
   métier **la fonction qui en répond**, prise dans la carte du pouvoir du pack.
3. Repérer le bien support que les constats de diagnostic rendent **le plus inquiétant** pour cette filiale, et
   justifier en une phrase avec le vocabulaire du TD, pas celui de l'audit.
*Livrable : un tableau à deux colonnes, prêt à être saisi tel quel l'après-midi.*

**Exercice 2 — Coter les besoins DICT, calibration par les faits** *(15 min)*
1. Retenir **deux** des valeurs métier de l'exercice 1, les deux plus contrastées.
2. Coter les **quatre besoins DICT** de chacune sur l'échelle à trois niveaux, en position relative, avec une ligne de
   justification par cotation ancrée dans le métier (*ce qui arrête l'activité, ce qui fausse les décisions, ce qui
   intéresse un tiers, ce qui empêche de comprendre un incident après coup*).
3. Comparer les cotations entre les deux valeurs métier et contre l'un des quatre faits de calibration (CH Simone Veil
   de Cannes 2024, amende CNIL Free 42 M€, France Travail 43 M de personnes, ENISA 32 % d'opérateurs énergie sans
   supervision OT) : **quelle cotation mériterait révision** s'il fallait défendre le classement devant le directeur de
   la filiale, et pourquoi ?
*Règle du jeu : aucune cotation sans justification, et aucune ligne où tout serait « très important ».*

**Exercice 3 — La chaîne complète sur une dépendance inter-filiales** *(10 min)* — exercice de synthèse.
1. Dérouler la chaîne complète du vocabulaire sur la dépendance du pack (§ « ce qui franchit la frontière ») : la
   valeur métier concernée (**à qui appartient-elle, d'ailleurs ?**), ses besoins DICT cotés, et ses biens supports,
   **y compris ceux qui vivent dans l'autre filiale**.
2. Décrire, **sans employer le terme technique de la séance 5**, ce qui se passerait si l'**intégrité** de ce qui
   transite était altérée (données de stock d'un côté, comptes et droits de l'autre) — première rencontre avec ce que
   la méthode appellera un **événement redouté**.
3. Expliquer en deux phrases pourquoi ce cas justifie une **cartographie de niveau groupe**, et pas seulement quatre
   cartographies de filiales.

### TP 1 — *Entering the mapping into CISO Assistant*

But : à la fin de l'heure, la carte de la filiale étudiée existe dans l'outil. *Règle d'or : ne jamais saisir ce qui
n'a pas été décidé sur le papier.*

**Étape 1 — Créer le domaine et poser la convention** *(10 min)*
1. Créer le domaine de la filiale (Organization > Domains > « Add domain »), nommé selon la convention groupe :
   `MERIDIAN-SANTE`, `MERIDIAN-LOGISTIQUE`, `MERIDIAN-EDUCATION` ou `MERIDIAN-TERRITOIRES` (majuscules, sans accents).
2. Renseigner sa **description en une phrase utile** (secteur et mission de la filiale).
3. Créer les **propriétaires** qui porteront les actifs (Organization > Users), une adresse fictive par fonction issue
   de la carte du pouvoir ; First name = la fonction, Last name = la direction ou l'entité. *Ce sont des étiquettes de
   responsabilité, pas des accès.*
4. Noter sur la feuille de validation l'heure de création et l'auteur.

**Étape 2 — Saisir les valeurs métier** *(15 min)*
1. Créer en actifs de type **Primary** les valeurs métier du TD, **au moins trois**, en conservant leur formulation
   métier exacte ; renseigner Name, Domain, Type, Class (« Business Process » ou « Data ») et « Assigned to ».
2. Renseigner pour chacune une description d'une à deux phrases : **ce que la filiale perdrait** si cet actif était
   atteint.
3. **Résister à la tentation d'en saisir quinze** : une poignée de valeurs métier bien choisies plutôt qu'un catalogue.

**Étape 3 — Rattacher les biens supports** *(15 min)*
1. Créer les actifs de type **Supporting** et rattacher chacun à la ou les valeurs métier qu'il porte via le champ
   « Is a dependency of ↑ ». *C'est ce lien, pas la liste, qui fait une cartographie.*
2. Couvrir les **trois natures** (au moins un numérique, un physique, un organisationnel) et le dire par le champ
   « Class ». *L'organisationnel — l'équipe qui administre, le prestataire qui exploite — est celui que tous les outils
   laissent filer.*
3. Vérifier la règle d'inventaire sur chaque objet : **un propriétaire nommé** dans « Assigned to ».

**Étape 4 — Renseigner les besoins de sécurité** *(10 min)*
1. Reporter sur chaque valeur métier les cotations DICT du TD dans « Security targets » (traçabilité sous le libellé
   **Proof**) ; activer chaque ligne par son toggle avant de saisir la valeur.
2. Conserver l'échelle relative du TD sans la raffiner : correspondance fixée **avant** la première saisie —
   négligeable 1, notable 2, très important 3, le 4e niveau restant vide.
3. Indiquer dans la description de l'actif, en une phrase, la **justification de la cotation dominante**.
4. Observer dans la liste des actifs que chaque bien support affiche désormais les cibles **héritées** de sa valeur
   métier, et la plus exigeante lorsqu'il en porte deux.

**Étape 5 — Le fil rouge inter-filiales et la preuve d'état** *(10 min)*
1. Créer un **second domaine** nommé d'après l'entité de l'autre côté de la frontière, sa description disant qu'il
   n'existe que pour ce qui franchit la frontière, et **n'y saisir rien d'autre**.
2. Rattacher via « Is a dependency of ↑ » : le lien **traverse les domaines**, et la liste affiche sur le bien support
   les cibles héritées des deux côtés.
3. **Exporter ou capturer l'état final** de l'instance (liste des actifs et leurs liens) : c'est la preuve de fin de TP
   et le point de départ du TP suivant. Utiliser « Export » (CSV/Excel), « Assets by class » et « Inspect »
   (Assets explorer).

### TP 2 — *Identifying the Top 5 assets and the strategy note*

**Exercice — Le Top 5 du groupe, par confrontation**
1. **Extraire** de l'instance de la filiale le **candidat** au Top 5 du groupe : une valeur métier avec ses biens
   supports décisifs, choisie sur les cotations DICT et non sur l'intuition. L'argument tient en **trente secondes** :
   *ce qui serait perdu, pour qui, et pourquoi c'est pire que le reste de la filiale.*
2. **Confronter en plénière les huit candidatures** (deux groupes par filiale, qui n'ont pas conféré) : chaque groupe
   présente, les autres attaquent. Trois critères d'arbitrage **dans cet ordre** : gravité métier · dépendances
   inter-filiales (un actif dont deux filiales dépendent pèse plus que son équivalent isolé) · exposition du secteur
   (panorama ANSSI 2025 : éducation et recherche en tête, ~1/3 ; ministères et collectivités 24 % ; santé 10 %).
3. **Arrêter le Top 5 du groupe**, cinq lignes portant chacune : l'actif · la ou les filiales concernées · la
   justification en une phrase mobilisant **au moins deux des trois critères** · le propriétaire qui en répondra,
   par fonction.
*Temps : 8 min extraction, 12 min confrontation, 5 min formalisation. Chaque ligne doit survivre à la question
« pourquoi celui-là et pas le mien ? ».*

**Note de stratégie** *(15 min)* — sous-section 2 : **« Actifs critiques »**, une demi-page max.
Contient : le Top 5 arrêté en tableau serré · la méthode en deux phrases · **la phrase de contrepartie** (ce qui est
prioritaire et ce qui l'est moins). Critère le plus discriminant : **l'articulation explicite avec la sous-section 1**
(rattacher le Top 5 aux instances qui en répondront). Ne contient PAS : la liste complète des actifs, les cotations
détaillées, ni la moindre promesse de plan d'action.

---

## Séance 3 — Choix du référentiel

*CM : « Overview of standards and the regulatory framework » (les quatre familles de référentiels, carte réglementaire
des filiales).*

### TD 1 — *The CISO's Desk: NIS 2 Applicability*

**Cas** : lundi 8h40, la Directrice Générale, après un article sur la loi « Résilience » : *« Sommes-nous parmi elles ?
Il paraît que les dirigeants sont personnellement responsables. Je veux une réponse au Comité Exécutif de jeudi. »*

Questions guidées :
1. **Classer chaque filiale au regard du premier filtre, le secteur** : pour chacune, l'annexe candidate (I, II, ou hors
   annexes) et l'intitulé sectoriel le plus proche. Pour **MERIDIAN Logistique, trouver DEUX lectures possibles** et
   garder les deux à ce stade (*ce qui distingue une activité « transport » d'une activité « courrier »*).
2. **Appliquer le second filtre, la taille** : pour chaque filiale retenue, dire si elle franchit le seuil des entités
   **essentielles** ou celui des entités **importantes**, en citant le critère utilisé.
3. **Caractériser chaque filiale à titre provisoire** : essentielle, importante, hors périmètre, ou « dépend d'un choix
   encore ouvert ». Une phrase de justification chacune.
4. Rédiger les **trois phrases** à livrer jeudi à la Directrice Générale en réponse à « sommes-nous parmi elles ? », en
   tenant compte de l'**état réel de la transposition française**. *Contrainte : aucune des trois phrases ne doit
   pouvoir être démentie si la loi est promulguée dans les six mois.*
5. Relier cette caractérisation à la **cartographie de la séance 2** : que l'article 3 de la directive imposera-t-il de
   communiquer à l'autorité nationale si la filiale est dans le périmètre, et **que l'inventaire de la séance 2
   peut-il déjà fournir** ?

**Méthode** : filiale par filiale, dans l'ordre **Santé, Logistique, Territoires, Éducation** (difficulté croissante).
Pour chacune : le **fait**, puis la **règle**, puis la **conclusion**. *Savoir dire « cela dépend d'un choix que la
France n'a pas encore fait » est une compétence.* 20 min (Q1-3), 10 min (Q4-5).

### TD 2 — *Selecting a framework and mapping tables*

**Exercice 1 — La grille de sélection du groupe** *(15 min)* — trois candidats : ISO/IEC 27001:2022, le **ReCyF**, et le
**guide d'hygiène informatique** de l'ANSSI. Grille à cinq critères (caractère obligatoire actuel ou à venir ·
couverture du périmètre · preuve opposable aux tiers · maturité et stabilité du texte · outillage et charge).
1. **Compléter la grille** : poser les pondérations et les justifier par le contexte MERIDIAN établi depuis la séance 1
   (*combien pèse le fait que Santé sera très probablement entité essentielle ? combien pèsent les trente collectivités
   clientes de Territoires ?*). Notes de 0 à 3, **une ligne de justification écrite par note**.
2. **Identifier le critère** qui, dans le contexte du groupe, mériterait un **droit de veto** plutôt qu'une pondération,
   et expliquer pourquoi une moyenne pondérée peut masquer un critère disqualifiant.
3. **Analyser la sensibilité** du résultat : quelle pondération devrait changer, et de combien, pour que le classement
   bascule entre les deux premiers candidats ? Que dit cette fragilité (ou cette robustesse) de la solidité de la
   recommandation ?

**Exercice 2 — Trois exigences, trois correspondances** *(20 min)* — trois exigences réelles :
**A** — NIS 2 réf. 1.1-EI/EE (l'entité liste l'ensemble de ses activités et services, identifie un propriétaire par
entrée et liste les SI qui la supportent) · **B** — objectif de sécurité 2 du ReCyF (cadre de gouvernance de la sécurité
numérique : organisation, rôles et responsabilités, processus de conformité, PSSI) · **C** — mesure 4 du guide d'hygiène
(identifier les informations et serveurs les plus sensibles, maintenir un schéma réseau).
Pour **chaque** exigence :
1. **Désigner l'élément correspondant côté ISO/IEC 27001:2022** : le bloc (clauses 4 à 10, ou annexe A) et, si c'est
   l'annexe A, le thème le plus pertinent parmi les quatre (*l'exigence organise-t-elle un pilotage ou déploie-t-elle
   un contrôle ?*).
2. **Qualifier la relation** par l'un des trois verdicts : **équivalence, intersection, absence de correspondance** ;
   puis justifier en une phrase ce que la source exige que la cible n'exige pas, ou l'inverse.
3. **Repérer ce que le groupe possède DÉJÀ** pour la filiale étudiée qui satisfait tout ou partie de l'exigence source,
   en citant précisément le livrable de la séance 1 ou 2 concerné.
4. **Conclure en deux phrases** : que dit cet exercice de l'idée « nous serons conformes NIS 2 puisque nous appliquons
   ISO 27001 » ? S'appuyer sur l'un des trois cas.
*Piège annoncé : la tentation de cocher « équivalence » partout où les sujets se ressemblent. La relation se juge sur ce
que les textes EXIGENT, pas sur ce dont ils parlent.*

**Exercice 3 — La recommandation en dix lignes** *(10 min)*
Rédiger un paragraphe de **dix lignes au plus**, adressé au Comité Exécutif, qui : nomme le référentiel **colonne
vertébrale** recommandé · donne les **deux arguments décisifs** tirés de la grille · énonce explicitement **ce que ce
choix NE couvre PAS** et comment le reste sera traité · se termine par **la décision demandée** au comité.
*Contrainte de réalisme : le paragraphe doit rester vrai que la loi Résilience soit promulguée dans trois mois ou dans
dix-huit.*

### TP 1 — *Qualifying and importing the framework into the tool*

**Exercice 1 — Établir la fiche d'identité du référentiel groupe** *(10 min)*
Fiche d'ISO/IEC 27001:2022 : nom exact et éditeur · édition et date de publication · amendement en vigueur · titre
français officiel · **statut pour MERIDIAN** (obligatoire / volontaire, et pourquoi) · **ce que la fiche ne dit pas**
(une ligne d'honnêteté).
1. Compléter chaque champ, en n'écrivant que ce qui peut être justifié par une source du matin ou par l'écran de l'outil.
2. Justifier le champ « statut » en une phrase qui distingue **ce qui est vrai aujourd'hui** de ce qui le deviendra une
   fois la loi de transposition promulguée.
*(Point de vocabulaire à tenir : « qualifier » ici = vérifier l'identité du document ; la **qualification ANSSI** est un
label officiel délivré à des produits et prestataires — personne ne « qualifie » un référentiel, et surtout pas soi-même.)*

**Exercice 2 — Importer et prouver l'import** *(15 min)*
1. **Localiser** dans la liste des bibliothèques celle du référentiel choisi (plus de 200 entrées : chercher « 27001 »).
2. **Importer** cette bibliothèque dans l'instance du groupe de travail.
3. **Prouver l'import** par trois observations numérotées : le **nombre total d'exigences évaluables** créées · le
   **nombre de contrôles du bloc annexe A** · leur **répartition sur les quatre thèmes**.
*Critères de validation : le référentiel apparaît dans la liste des référentiels actifs ; l'arbre montre deux blocs
(clauses 4-10 / annexe A) ; les trois lectures donnent **123 exigences évaluables**, dont **93 contrôles d'annexe A**
répartis en **37, 8, 14 et 34** (organisationnel, humain, physique, technologique). Si les comptes diffèrent, l'import
est incomplet ou ce n'est pas la bonne bibliothèque.*
*(À noter au passage : l'outil nomme le bloc annexe A « Déclaration d'applicabilité » — grand œuvre de la séance 8.)*

**Exercice 3 — Créer l'évaluation de conformité de la filiale étudiée** *(15 min)*
1. **Créer une évaluation de conformité** adossée au référentiel importé, rattachée au domaine de la filiale créé en
   séance 2, via un **périmètre** créé pour cela dans ce domaine, et nommée selon la convention :
   `MERIDIAN-FILIALE - ISO/IEC 27001:2022 - évaluation initiale`.
2. **Parcourir l'arbre** de l'évaluation pour vérifier qu'il reproduit bien les deux blocs, **sans évaluer aucune
   exigence** : l'évaluation reste vierge aujourd'hui, c'est son état normal.
3. **Repérer, sans rien coter, trois exigences** que le travail des séances 1 et 2 satisfait déjà au moins partiellement,
   et noter pour chacune le **livrable existant qui servirait de preuve** (*partir de ce que le groupe possède, pas de
   ce qui lui manque*).
*Ces trois couples exigence-livrable seront les trois premières preuves de l'audit de la séance 4.*

**Exercice 4 — Reconnaître et trier** *(10 min)*
1. **Trouver** dans la liste des bibliothèques, **sans les importer**, les quatre entrées : « ANSSI - Guide d'hygiène
   informatique » · « Digital Operational Resilience Act (DORA) » · « HDS v2.0 » · « Référentiel Général de Sécurité 2.0
   - Annexe B2 ».
2. **Trier** chacune dans une famille de l'exposé du matin, en notant l'éditeur affiché et une ligne de justification.
3. **Chercher « ReCyF »** : relever le **nom exact** de l'entrée du référentiel, son éditeur et le **millésime** qu'elle
   porte. Puis ouvrir la correspondance publiée par l'ANSSI du ReCyF vers ISO/IEC 27001:2022, lire sa colonne
   « relation », et dire en deux phrases **ce qu'elle confirme** de l'exposé du matin et **ce qu'elle interdit de
   conclure**.

### TP 2 — *Drafting the business case note and peer review*

**Gabarit imposé de la note de business case** (deux pages max) : §1 Contexte et déclencheur (1/3 page) · §2 Options
examinées (1/6 page) · §3 Recommandation argumentée (1/2 page) · §4 Limites et angles morts (1/3 page) · §5 Décision
demandée (3 lignes).

**Rédaction** *(20 min)*
1. **Rédiger la note complète**, sections 1 à 5, en respectant le gabarit et les critères d'acceptation.
2. **Tracer chaque argument de la §3 à sa source** du jour, par un mot entre parenthèses en fin de phrase :
   `(grille)`, `(correspondances)`, `(import)`, `(applicabilité)`.
3. **Relire une fois à voix basse** avant de rendre, avec la seule question qui compte : *sans avoir suivi cette
   journée, un lecteur pourrait-il décider avec ces deux pages ?*
*Critères d'acceptation appliqués tels quels : deux pages max · aucune affirmation chiffrée qui ne vienne d'une source
du jour · **les options perdantes traitées avec les mêmes égards que la gagnante** · §4 non vide · décision demandée
répondable par oui ou non · robustesse temporelle vérifiée.*

**Revue par les pairs** *(10 min)* — protocole :
1. **Échanger** sa note avec celle du binôme, de préférence d'une autre filiale.
2. **Relire** la note reçue **avec la grille**, en notant pour chaque ligne un constat précis, **citation à l'appui**,
   jamais une impression générale.
3. **Restituer en trois minutes** : les deux constats les plus utiles d'abord ; **l'auteur note tout et ne se défend
   pas** pendant la restitution.
4. **Traiter les constats reçus** sur sa propre note : chaque constat reçoit une correction ou **un refus motivé en une
   ligne**, avant remise finale.

*Grille de revue* : chaque affirmation chiffrée a-t-elle une source du jour ? · les options perdantes sont-elles traitées
honnêtement ? · la section limites dit-elle quelque chose de substantiel ? · la décision demandée est-elle décidable ? ·
la note survit-elle aux **deux calendriers** ?

**Note de stratégie** *(15 min)* — sous-section 3 : **« Choix du référentiel »**, une demi-page max, qui **ne réécrit
RIEN** de la note de business case. Contient : le référentiel retenu et la date de la décision · en une phrase, pourquoi
celui-là (version stratégique des arguments) · ce que ce choix engage pour la suite. **Articulation exigée** : renvoi à
la sous-section 1 (la décision est un produit de cette gouvernance) et à la sous-section 2 (le référentiel est la langue
dans laquelle ces actifs seront désormais évalués).

---

## Séance 4 — Audit · valeur de la certification

*CM : « Audit methodology and typology » (la chaîne critère → preuve → constat → écart → non-conformité).*

### TD 1 — *The CISO's Desk: The Value of ISO 27001 Certification*

**Cas** : deux messages contradictoires. Le **Directeur de la filiale** transmet le questionnaire d'un tiers qui s'ouvre
sur *« Êtes-vous certifiés ISO/IEC 27001 ? Si oui, joignez le certificat et son périmètre. Sinon, décrivez la preuve
équivalente. »* La **Directrice Générale**, elle : *« Le comité a approuvé votre norme. Allons au bout : je veux le
groupe certifié, toutes filiales, et vite. Dites-moi ce qui nous en empêche. »*

Questions guidées :
1. **Analyser la question du tiers** : que cherche-t-il à obtenir en demandant le certificat **ET** son périmètre, et
   pourquoi la formule « preuve équivalente » est-elle une **sortie honorable** pour MERIDIAN ? Lister **trois preuves
   existantes** du groupe qui peuvent en tenir lieu aujourd'hui.
2. **Évaluer la demande de la Directrice Générale** : quelles sont les **deux hypothèses discutables** de la phrase
   « le groupe certifié, toutes filiales, et vite » ? S'appuyer sur ce que coûte un périmètre et sur ce qui reste inconnu
   de l'état réel du groupe.
3. Proposer un **séquencement de périmètre** défendable en comité : quelle filiale ou quelle activité est la première
   candidate, et pourquoi ? Justifier par la cartographie de la séance 2 et le contexte réglementaire de chaque filiale,
   **pas par une préférence**.
4. **Corriger l'enthousiasme du Directeur Financier** qui conclut : « Si nous sommes certifiés, NIS 2 est réglé, autant
   le budgéter comme un projet de conformité. » Rédiger la mise au point en **trois phrases**, juridiquement exactes et
   utilisables en comité.
5. **Formuler la réponse au tiers** en un paragraphe : sans certificat aujourd'hui, sans promettre de date, mais sans
   laisser la case vide.

**Méthode** : traiter dans l'ordre. Pour chaque réponse, distinguer systématiquement ce que le groupe **PEUT** prouver
aujourd'hui, ce qu'il **POURRA** prouver après l'état des lieux du jour, et ce qui relève d'une décision non encore
prise. 20 min (Q1-3), 10 min (Q4-5).

### TD 2 — *Grading deviations and the security authorization process*

Notions : gradation des écarts (**conforme, non-conformité majeure, non-conformité mineure, observation**) · règle de
cumul · **correction** (faire disparaître l'écart) vs **action corrective** (faire disparaître la cause), méthode SMART ·
**homologation de sécurité** (démarche en 4 temps, 3 niveaux — simplifié / intermédiaire / renforcé — autorité
d'homologation, avis pouvant être défavorable ou favorable sous réserves, durée ≤ 3 ans).

**Exercice 1 — Grader les constats du programme d'audit** *(15 min)*
Huit constats **C1 à C8** issus des quatre filiales (Santé : mots de passe locaux sans MFA + accès TMA partagé à neuf ;
Santé : équipements biomédicaux sur la plage bureautique + compte admin unique ; Logistique : IT/OT interconnectés ;
Logistique : compte de domaine partagé avec la TMA du WMS ; Éducation : comptes d'administration partagés entre les deux
filiales du pôle ; Territoires : journaux conservés localement, non transmis au SOC ; flux inter-filiales Logistique-Santé :
VLAN dédié et pare-feu d'inspection, seul cloisonnement du groupe, flux suspendu depuis 3 mois ; Éducation : onze
abonnements hors DSI sans contrat ni analyse d'impact). Critères : annexe A d'ISO/IEC 27001:2022 **et** directives
`ACC-01`, `ACC-02`, `INC-01`, `JRN-01`, `COR-01` de la séance 1.
1. **Grader chacun des huit constats** : conforme, non-conformité majeure, non-conformité mineure, ou observation.
2. **Justifier chaque gradation** en une phrase **citant l'exigence et l'étendue de l'écart**, jamais une impression de
   gravité.
3. **Signaler les deux constats** dont la gradation peut légitimement être débattue, et écrire en une ligne l'argument
   de chaque camp.

### TP 1 — *Self-assessment of the subsidiary in CISO Assistant*

Échelle de statuts du module : **Couvert** (preuve vérifiable) · **Partiel** (preuve de ce qui existe **et** description
de ce qui manque) · **Non couvert** · **Non évalué** (aveu explicite, qui vaut mieux qu'une estimation) ·
**Non applicable** (justification écrite, jamais un confort).

**Exercice 1 — Cadrer l'auto-évaluation** *(10 min)*
1. **Délimiter le périmètre** : la filiale étudiée, avec ses systèmes cartographiés en séance 2.
2. **Poser les critères** : les douze exigences de l'exercice 2, extraites du référentiel importé en séance 3, complétées
   des directives de la PSSI cadre applicables.
3. **Fixer la règle de preuve** : aucune exigence déclarée « couvert » sans preuve nommée ; le doute se déclare
   « non évalué ».

**Exercice 2 — Évaluer douze exigences, preuve en main** *(35 min)*
Sous-ensemble imposé : **A.5.9, A.5.15, A.5.16, A.5.17, A.5.19, A.5.22, A.6.3, A.8.2, A.8.5, A.8.8, A.8.15, A.8.22**.
1. **Retrouver** les douze exigences dans l'évaluation de conformité, par référence ou par titre.
2. **Renseigner le statut** de chacune selon l'échelle du module, dans l'outil.
3. **Justifier chaque statut** sur la feuille : la preuve nommée, ou le constat cité, ou l'aveu « aucune preuve
   disponible ».
4. **Respecter la règle d'or** : *au moins un « non évalué » assumé vaut mieux que douze « couvert » déclaratifs.*
*Validation : les 12 exigences portent un statut ; chaque ligne porte sa justification ; les constats gradés à midi se
retrouvent dans les « non couvert » ; **aucun objet des séances 2 ou 3 n'a été recréé ou renommé**.*

**Exercice 3 — Porter le plan d'action dans l'outil** *(15 min)*
Sur les **deux constats les plus graves** de la filiale (le plus grave du TD, plus un constat du pack que le TD ne
reprend pas) :
1. Créer pour chaque constat **la correction**, en contrôle appliqué rattaché à l'exigence évaluée, avec propriétaire et
   échéance.
2. Créer pour chaque constat **l'action corrective**, second contrôle appliqué : le geste qui traite la cause et
   prévient le retour, avec propriétaire et échéance.
3. **Passer chaque contrôle au test SMART** et reformuler ce qui échoue (*« sensibiliser les équipes » échoue sur M et
   sur T*).
*Attendu : quatre contrôles appliqués, deux par constat.*

**Exercice 4 — Synthétiser et lire la maturité** *(15 min)*
1. **Compter les statuts par thème** du référentiel (organisationnels A.5, humains A.6, technologiques A.8) en
   distinguant couvert / partiel / non couvert / non évalué.
2. **Formuler en deux phrases** la lecture de maturité de la filiale au sens de la grille de la séance 1 : *où est-elle
   outillée, où vit-elle de déclarations, où est-elle aveugle ?*
3. **Repérer le biais de sa propre évaluation** : identifier le statut le moins certain et écrire pourquoi (*chercher
   celui dont la preuve est une intention, un projet ou une directive, pas un fait observable*).

**Exercice 5 — Extraire la matière du rapport** *(10 min)*
1. **Lister à part** tous les « non couvert » et « partiel », avec pour chacun l'exigence, le constat associé s'il existe,
   et la gradation retenue à midi.
2. **Ajouter les « non évalué »** dans une liste distincte intitulée **« angles morts »**.
3. **Vérifier** que la liste contient tout ce que le TD a gradé pour cette filiale (*un rapport qui perd des constats en
   route fabrique de la fausse assurance*).

### TP 2 — *Initial audit report and strategy note*

**Gabarit imposé du rapport d'audit** : §1 Cadrage (périmètre, critères, méthode, **limites assumées**) · §2 Synthèse
pour décision (l'état en cinq phrases) · §3 Constats gradués (tableau : constat, critère cité, preuve, gradation) ·
§4 Recommandations (priorisées par gradation, chacune tracée à son constat, exprimées **en résultat**) · §5 Plan d'action
correctif (lignes SMART, corrections et actions correctives distinguées) · §6 Angles morts et suites.

**Exercice 1 — Préparer l'homologation du système exposé de la filiale** *(15 min)*
1. **Déterminer le niveau de la démarche** : évaluer la criticité du système pour la filiale et ses usagers externes,
   puis son exposition aux sources de risque, et croiser les deux dans la matrice du guide. Une phrase de justification
   par évaluation.
2. **Composer la commission d'homologation** : qui l'anime, quels profils y siègent, et **qui n'y décide pas**.
3. **Identifier l'autorité d'homologation** : qui, chez MERIDIAN, peut prononcer cette décision, et **pourquoi ni le RSSI
   Groupe ni l'auditeur ne le peuvent**.
4. **Inventorier les pièces** du dossier d'homologation que le groupe possède déjà grâce aux séances 1 à 3, celles que
   la journée produit, et **celle qui manquera encore ce soir**.
5. **Anticiper l'avis** : compte tenu des constats gradés et de la pièce manquante, quel **avis honnête** la commission
   peut-elle viser à court terme, et avec quelle **durée d'homologation** cible ?

**Exercice 2 — Écrire le rapport d'audit initial** *(25 min)*
1. **Écrire le rapport complet**, sections 1 à 6, en respectant le gabarit et les critères d'acceptation.
2. **Tracer chaque recommandation à son constat** par sa référence, un mot entre parenthèses en fin de ligne.
3. **Relire la synthèse seule** : la Directrice Générale, qui n'a pas vécu la journée, peut-elle décider avec ces cinq
   phrases ? Toute phrase qui présuppose un souvenir du TD est à réécrire.
*Critères d'acceptation : **aucune gradation changée** entre le TD et le rapport sans justification écrite · chaque
recommandation tracée · §6 non vide · synthèse lisible par qui n'a pas suivi la journée · **nulle part une cotation de
risque, une gravité ou une vraisemblance chiffrée**, qui n'existent pas encore.*

**Exercice 3 — Réparer trois recommandations** *(5 min)*
Trois recommandations irrecevables : **R1** « Il faut faire très attention à la gestion des mots de passe dans toutes
les filiales. » · **R2** « Déployer un SIEM de dernière génération pour régler le problème des journaux. » ·
**R3** « La sécurité des fournisseurs doit devenir une priorité absolue pour le groupe. »
1. **Diagnostiquer** pour chacune la discipline violée : rattachement, résultat vérifiable, ou hiérarchie.
2. **Réécrire** chacune en recommandation recevable, rattachée à un constat de la journée.

**Note de stratégie** *(15 min)* — sous-section 4 : **« État des lieux »**, une demi-page max, qui **ne recopie RIEN** du
rapport d'audit. Contient : qu'un état des lieux mesuré existe désormais, contre quel référentiel et sur quel périmètre ·
la forme du résultat en une phrase écrite à neuf (*« fondations documentées, application non prouvée, angles morts
identifiés »*) · ce que cet état engage pour la suite. **Articulation exigée** avec les sous-sections 1, 2 et 3 et avec
la feuille de route de la séance 1.

---

## Séance 5 — Risques majeurs · EBIOS RM ateliers 1 et 2

*CM : « Risk concepts and the EBIOS Risk Manager method » (vocabulaire du risque, mécanique des cinq ateliers).*

### TD 1 — *The CISO's Desk: Risk Appetite*

Notions distinguées : **appétence** (niveau de risque qu'un dirigeant accepte de prendre — ANSSI/AMRAE 2019) ·
**seuil d'acceptation** (la ligne au-delà de laquelle un risque appelle un traitement) · **tolérance** (l'écart
temporaire accepté entre appétence et réalité : **daté, surveillé, et qui se referme**).

**Cas** : mardi 17h30, la Directrice Générale après la présentation du rapport d'audit : *« Logistique dit que personne
ne touche aux automates en période de pointe, et la pointe dure dix mois sur douze. Le Directeur Médical dit qu'une
authentification de plus sur un poste de soin, c'est du temps pris au patient. L'Audit Interne dit que nous jouons avec
les données patient. Ils ont tous raison, et je ne vais pas arbitrer trente fois par an. Donnez-moi de quoi poser une
règle une fois pour toutes : ce que le groupe accepte, ce qu'il n'accepte pas. Jeudi. Je la porte au Conseil. »*

Questions guidées :
1. **Classer trois phrases** entendues au dernier Comité Exécutif selon qu'elles expriment une **appétence**, une
   **tolérance** ou un **seuil d'acceptation**, une phrase de justification chacune : *« Aucun projet ne sera bloqué plus
   de 48 heures pour une revue de sécurité »* · *« Nous gardons l'interconnexion IT/OT jusqu'à la prochaine fenêtre
   creuse, avec surveillance renforcée, et nous rouvrons le sujet au prochain trimestre »* · *« Tout risque coté au-delà
   du niveau élevé sur notre future grille devra être traité avant mise en production »*.
2. **Rédiger deux énoncés d'appétence** : un premier sur l'actif à protéger de la filiale étudiée (§2 du pack), un
   second **transverse au groupe**, valable pour les quatre filiales. *Contrainte : chaque énoncé doit permettre de
   trancher au moins une décision concrète que le groupe a devant lui, en disant laquelle.*
3. **Confronter chacun des quatre écarts d'audit** aux énoncés rédigés : lesquels sont clairement au-dessus de la ligne,
   lesquels relèvent d'une **tolérance à formaliser**, et **que manque-t-il encore** à chaque tolérance pour en être une ?
4. **Attribuer les rôles pour jeudi** : qui fixe l'appétence, qui l'approuve, qui valide son déploiement budgétaire, et
   **ce qui reste exactement dans les mains du RSSI Groupe** ? Identifier le **piège de posture** contenu dans la phrase
   de la Directrice Générale.
5. **Analyser la décision Norsk Hydro de 2019** avec le vocabulaire du matin : formuler en deux phrases l'appétence
   implicite révélée par le refus de payer, et à quoi cette décision aurait ressemblé s'il avait fallu l'improviser sans
   appétence préalable.
*Temps : 10 min (Q1), 15 min (Q2-3), 5 min (Q4-5).*

### TD 2 — *EBIOS RM Workshops 1 and 2: Baseline and risk origins*

*Règle du jour : les objets de la cartographie de la séance 2 sont **réutilisés tels quels** ; les recréer serait une
faute de méthode. Chaque exercice produit un élément qui entre **tel quel** dans le livrable D5.*

**Exercice 1 — Cadrer l'étude avant toute analyse** *(15 lignes max à produire)*
1. **Formuler l'objectif de l'étude** en une phrase, en choisissant parmi les finalités reconnues de la méthode celle
   qui correspond à la demande de la Direction.
2. **Assembler le tableau des participants** de l'atelier 1 : les **quatre rôles** attendus par le guide, chacun incarné
   par un acteur de la carte du pouvoir (§3 du pack) ou du holding, avec pour chacun **ce qu'il apporte que les autres
   n'apportent pas**. *(Indice : qui peut dire ce qui compte pour le métier, qui peut dire ce que le SI permet, qui peut
   dire ce que la sécurité sait de la menace, qui peut engager le groupe.)*
3. **Désigner le responsable de l'acceptation des risques résiduels** en fin d'étude, en une phrase de justification
   ancrée dans la gouvernance du groupe.
4. **Poser le cadre temporel** : la durée des deux cycles, avec la référence qui justifie ce choix.

**Exercice 2 — Du patrimoine cartographié aux événements redoutés**
Point de départ : trois valeurs métier de la cartographie + en quatrième ligne la **dépendance inter-filiales** du §6 du
pack, chaque ligne portant ses biens supports et son besoin de sécurité dominant.
1. **Formuler six événements redoutés**, au moins un par ligne du tableau, dépendance inter-filiales comprise, chacun
   en une formule courte **nommant la valeur métier atteinte et le besoin de sécurité touché**. *Parcourir les quatre
   besoins DICT pour ne pas produire six variantes du même événement.*
2. **Coter la gravité** de chacun sur l'échelle à quatre niveaux (mineure → critique), en justifiant chaque cotation par
   la nature des impacts : **missions, réglementation, personnes, image**.
3. **Signaler l'événement redouté pour lequel préciser une durée change la cotation**, et proposer cette précision.

**Exercice 3 — Le socle de sécurité, ou l'audit qui trouve sa place**
À produire : le **tableau du socle de sécurité** du périmètre, à quatre colonnes — **type et nom du référentiel · état
d'application · écarts · justification des écarts** — couvrant la PSSI cadre du groupe (séance 1), le guide d'hygiène
informatique de l'ANSSI, ISO/IEC 27001:2022 (séance 3) et les obligations propres de la filiale (§2 du pack). Les écarts
à reporter sont les deux constats du reference pack pour cette filiale, tels que le rapport d'audit de la séance 4 les a
gradés.
Puis, **en trois phrases** : **la décision sur la suite à donner**. Le guide ouvre deux voies lorsque le socle présente
des écarts, et **une seule est raisonnable ici — laquelle, et pourquoi ?** Et **quelle conséquence** cette décision
aura-t-elle sur les ateliers suivants ?

**Exercice 4 — Sources de risque et objectifs visés**
1. **Inventorier cinq couples candidats source de risque / objectif visé** pour le périmètre, en s'appuyant sur les
   acteurs des §3 et §6 du pack et en **variant les catégories** (cybercriminels, concurrents, activistes, internes).
   Une ligne par couple : la source, son objectif visé **formulé en résultat**, la valeur métier visée.
2. **Évaluer la pertinence** de chaque couple contre les trois critères du guide — **motivation, ressources, activité** —
   sur une échelle qualitative à trois positions, en justifiant la colonne « activité » par un **élément observable**.
3. **Sélectionner les trois couples retenus**, en respectant la règle de sélection du guide : des couples suffisamment
   **distincts**, qui n'impactent pas tous la même valeur métier.
4. **Confronter les couples retenus aux événements redoutés** de l'exercice 2 : construire le tableau de correspondance,
   et **signaler tout événement redouté grave resté sans source plausible**, ou tout couple retenu sans événement
   redouté associé.
*Piège annoncé : ne pas confondre l'objectif visé avec la motivation. « S'enrichir » n'est pas un objectif visé.*

### TP 1 — *Entering Workshops 1 and 2 into CISO Assistant*

**Exercice 1 — L'inventaire de ce qui existe déjà** *(10 min)*
Vérifier **avant toute saisie**, en notant pour chacun le **nom exact observé** : *(1)* le domaine de la filiale créé en
séance 2, le second domaine portant l'autre bout de la dépendance, et le périmètre associé · *(2)* les actifs saisis en
séance 2, valeurs métier et biens supports, dépendance inter-filiales comprise · *(3)* le référentiel importé en séance 3,
l'évaluation de conformité créée avec lui, et l'audit de la séance 4 avec ses statuts · *(4)* le module EBIOS RM
(Risk > EBIOS RM > EBIOS RM studies), **liste vide, comme attendu**.
*À produire : un tableau de quatre lignes — objet attendu, présent ou absent, nom exact observé. Si un objet manque, **ne
pas le recréer en silence** : le noter, le signaler, et continuer avec ce qui existe.*

**Exercice 2 — Importer la matrice de risque** *(10 min)*
Importer « **4x4 risk matrix from EBIOS-RM** » depuis la bibliothèque, puis l'ouvrir et l'examiner :
*(1)* l'axe vraisemblance à quatre niveaux V1 « Unlikely » → V4 « Certain » · *(2)* l'axe conséquence à quatre niveaux
G1 « Minor » → G4 « Critical » (*noter le mot « Consequence » choisi par l'outil là où le guide dit « gravité »*) ·
*(3)* le croisement produisant trois niveaux : Low, Medium, High.
*À produire : trois phrases — quelle cellule correspond au risque le plus élevé, de quelle couleur est la diagonale, et
surtout **les libellés de cette matrice sont-ils exactement ceux de l'échelle d'exemple du guide vue au TD ?** Regarder
de près les niveaux V4 et G3 avant de répondre.*

**Exercice 3 — Créer l'étude et poser le cadre (atelier 1, activités 1, 2 et 4)** *(15 min)*
Nom selon la convention : `Étude EBIOS RM MERIDIAN - [filiale étudiée] et [dépendance du §6] - cycle 1`. Domaine : celui
de la filiale, **jamais le domaine racine**. Matrice : celle importée. Méthode de cotation : **« Manual »** (avec
« Express », l'outil recalculerait la vraisemblance et écraserait la saisie).
1. **Cadrer** (activité 1 « Define the study framework ») : renseigner la description avec le cadrage du TD — objectif en
   une phrase, participants et rôles, durées des deux cycles, responsable de l'acceptation des risques résiduels.
2. **Relier** (activité 2 « Define business and technical perimeter ») : **cocher** les valeurs métier et biens supports
   saisis en séance 2, dépendance comprise. *Ne pas toucher au bouton d'ajout d'actif : ne rien créer, ne rien renommer,
   relier.*
3. **Ancrer** (activité 4 « Determine the security foundation ») : rattacher à l'étude l'audit de la séance 4.
*À produire : l'étude créée, son cadre en description, ses actifs reliés, son audit rattaché ; carte « Summary » affichant
les compteurs Assets et Audits.*

**Exercice 4 — Saisir les six événements redoutés (atelier 1, activité 3)** *(20 min)*
1. **Nommer** chaque événement redouté avec la formulation du TD ; renseigner l'ID **ER1 à ER6**.
2. **Relier l'actif** : la valeur métier concernée (*un événement redouté se rattache aux valeurs métier, pas aux biens
   supports*).
3. **Qualifier le besoin de sécurité** touché parmi les qualifications de l'outil : Availability, Integrity,
   Confidentiality, et **« Proof » pour la traçabilité**.
4. **Coter la gravité** : Minor / Significant / Important / Critical (correspondance à noter sur la feuille).
5. **Justifier la cotation** dans le champ Justification, et cocher **« Selected »**.
*À produire : six événements redoutés, compteur à 6.*

**Exercice 5 — Saisir les couples SR/OV (atelier 2)** *(25 min)*
1. **Identifier** (activité 1) : la source de risque parmi les catégories de l'outil (le cybercriminel se saisit en
   **« Organized crime »**, l'interne malveillant en **« Avenger »**), puis l'objectif visé formulé en finalité, avec les
   mots du TD.
2. **Évaluer** (activité 2) : motivation, ressources et niveau d'activité, puis la justification de l'activité par son
   élément observable.
3. **Sélectionner** (activité 3) : cocher « Selected » sur les **trois** couples retenus, laisser les deux autres
   décochés ; **relier chaque couple, retenu ou non, aux événements redoutés qu'il vise**.
4. **Lire la colonne Pertinence** que l'outil calcule seul (motivation × ressources, l'activité n'y entrant pas) :
   **noter l'écart avec la pertinence du TD sur la feuille, sans changer la sélection pour lui plaire** — la
   justification écrite prévaut.
*À produire : cinq couples, trois « Selected », chacun relié à au moins un événement redouté.*
*Ce qui n'est PAS fait aujourd'hui, et pourquoi : les ateliers 3, 4 et 5 restent vides — c'est un état normal.*

### TP 2 — *Risk scales, deliverable D5 and the strategy note*

**Exercice 1 — Les échelles du groupe** *(15 min)*
- **Échelle de gravité** : quatre niveaux **G1 à G4** alignés sur la matrice importée. Pour chaque niveau, une
  description d'une à deux phrases répondant à **trois questions** : quel effet sur les missions du groupe, quel effet
  sur les personnes, et **le groupe s'en relève-t-il, en combien de temps** ? Traduire sur les réalités du groupe
  (sécurité des soins côté Santé, continuité des flux côté Logistique, conformité et confiance côté Territoires et
  Éducation).
- **Échelle de vraisemblance** : les libellés V1 à V4 **ne sont pas à réécrire** ; écrire pour chacun une **phrase
  d'interprétation propre au groupe**, disant **sur quels signaux** on cote à ce niveau. *Sans ces phrases, deux
  participants coteront la même situation V2 et V3.*
- **Le seuil** : reporter sur la grille le **seuil d'acceptation** qui traduit l'appétence formulée le matin. Dire lequel
  des niveaux **Faible / Moyen / Élevé** l'appétence rend **inacceptable en l'état**, lequel est **tolérable sous
  conditions**, lequel est **acceptable**, avec une phrase de justification chacun.

**Exercice 2 — Assembler le livrable D5** *(15 min)* — une à deux pages hors tableaux, quatre sections :
§1 Cadrage de l'étude (objectif, périmètre, participants et rôles, responsable de l'acceptation, cycles, **échelles de
gravité et de vraisemblance justifiées**) · §2 Socle de sécurité · §3 Sources de risque (couples retenus et priorisés,
chacun motivé, plus la liste des couples secondaires sous surveillance) · §4 Événements redoutés cotés en gravité.
*Critères d'acceptation de D5 : les valeurs métier et biens supports du dossier sont **IDENTIQUES** à ceux de la
cartographie de la séance 2, réutilisés, ni recréés ni renommés · chaque couple SR/OV est **motivé en une phrase** ·
les échelles sont **réutilisables telles quelles en séance 7** (aucune retouche à prévoir).*

**Note de stratégie** *(15 min)* — sous-section 5 : **« Risques majeurs »**, une demi-page max, **contenu de direction,
pas de technicien** : les trois couples SR/OV retenus, une ligne chacun en langage compréhensible par un administrateur ·
l'événement redouté le plus grave du dossier et ce qui le rend crédible · **le seuil d'acceptation dont on demande la
confirmation à la Direction**. Articulation exigée avec les sous-sections 1, 2 et 4 — *et si l'un des couples retenus ne
menace aucun des actifs critiques de la sous-section 2, l'une des deux sous-sections a tort, et il faut dire laquelle.*

---

## Séance 6 — Tiers et projets · EBIOS RM ateliers 3 et 4

*CM : « Security by Design and integration into projects » (six jalons de sécurité, régimes acheter / développer /
faire développer).*

### TD 1 — *The CISO's Desk: Supply Chain Attack*

Notions : **chaîne d'approvisionnement** du SI · **attaque par rebond (pivot)** · **risque tiers** (35 % des
cyberattaques significatives passent par un tiers — baromètre CESIN 2026). Cas de référence : **NotPetya** (mise à jour
piégée de M.E.Doc, Maersk 250-300 M$) et **SolarWinds** (~18 000 clients Orion).

**Cas** : dimanche soir, la Directrice Générale transfère une enquête de presse sur les attaques de la chaîne
d'approvisionnement : *« Ce qui est arrivé aux clients de ce logiciel de comptabilité, cela peut nous arriver par un de
nos prestataires ? Je veux que votre briefing de jeudi commence par la réponse. »*

Questions guidées :
1. **Inventorier les dépendances tierces** de la filiale étudiée (§3 et §6 de son pack) plus les dépendances de niveau
   groupe (§5 du reference pack) : construire un **tableau à quatre colonnes** — tiers ou flux entrant · filiale
   concernée · nature de l'accès ou de la dépendance · ce qu'il peut atteindre. *Ne pas s'arrêter aux prestataires
   contractualisés : un flux de mise à jour logicielle est aussi une dépendance.*
2. **Qualifier chaque ligne** du tableau en une phrase : **qu'est-ce qui en ferait un chemin de rebond attractif** pour
   un attaquant ? Raisonner en logique de moindre effort, **du point de vue de l'attaquant**.
3. **Transposer les deux cas de l'exposé sur le groupe** : pour le mécanisme « mise à jour logicielle piégée », désigner
   l'endroit du groupe qui lui ressemble le plus ; pour le mécanisme « accès de maintenance détourné », faire de même.
   Justifier chaque choix par un élément du dossier, **pas par une intuition**. Pour chacun des deux mécanismes,
   **nommer la clause contractuelle qui aurait aidé**.
4. **Rédiger les trois messages du briefing de jeudi** : un **fait sourcé** qui cadre le sujet, une **phrase honnête** sur
   l'exposition du groupe, une **décision demandée** au Comité Exécutif. *Contrainte : rien d'affirmé qui dépasse ce que
   la matière prouve.*
5. **Formuler ce que l'analyse du matin ne permet pas encore de faire** : que manque-t-il pour passer de « voici nos
   dépendances » à « voici celles qu'il faut traiter en premier » ? *(deux phrases)*
*Temps : 10 min (Q1-2), 10 min (Q3), 10 min (Q4-5). Réponse écrite individuelle, notée sur 10.*

### TD 2 — *Third-party management, IT outsourcing and EBIOS RM (Workshops 3-4)*

Notions : **contrat d'infogérance** et ses quatre familles d'exigences (**réversibilité, droit d'audit, notification
d'incident, maîtrise de la sous-traitance**) + le **Plan d'Assurance Sécurité** · **atelier 3** (dangerosité de
l'écosystème, parties prenantes critiques, scénarios stratégiques cotés en **gravité**) · **atelier 4** (scénarios
opérationnels cotés en **vraisemblance**).

**Exercice 1 — Le contrat du prestataire le plus exposé de la filiale étudiée** *(15 min)*
À partir de l'extrait de contrat fourni (`Outsourcing-contracts` du reference pack), et des **quatre familles**
d'exigences : établir **les exigences vérifiables qui manquent** à ce contrat et **l'écart que chacune corrige**, en
s'appuyant sur l'extrait et sur ce que le pack établit. *Formuler des exigences vérifiables, pas des clauses juridiques.*
*À produire : un tableau à trois colonnes — famille · exigence vérifiable · écart corrigé — plus une ligne libre pour
**l'exigence la plus urgente**, justifiée en une phrase.*

**Exercice 2 — La carte de dangerosité et un scénario stratégique** *(20 min)*
**Objet étudié** : l'actif critique n°1 de la filiale, la valeur métier dont l'événement redouté est **le plus haut coté
dans D5**.
1. Lire son écosystème dans les §3 et §6 du pack et **retenir au moins quatre parties prenantes**.
2. **Estimer la dangerosité** de chacune sur **exposition** et **fiabilité cyber**, les **classer**, puis **désigner la ou
   les parties prenantes critiques** selon **un seuil que le groupe pose et écrit**.
3. **Tracer, pour le couple SR/OV retenu en séance 5, un scénario stratégique qui passe par une partie prenante
   critique**, et **coter sa gravité** sur l'échelle de D5 (G1 mineure → G4 critique).
*À produire : la carte de dangerosité classée avec ses parties prenantes critiques désignées, et un scénario stratégique
coté en gravité.*

### TP 1 — *Ecosystem analysis and scenarios in CISO Assistant*

*L'outil modélise chaque partie prenante avec **quatre critères** en valeur courante et résiduelle — **dépendance** et
**pénétration** (exposition), **maturité** et **confiance** (fiabilité) — et **calcule seul la criticité**
(dépendance × pénétration ÷ (maturité × confiance)). La dangerosité ne se calcule donc pas à la main : elle se **justifie
par les quatre notes**, et le résultat se **lit**.*

**Exercice 1 — Reprendre l'étude EBIOS RM de la séance 5** *(5 min)*
Ouvrir l'étude et **vérifier que ses ateliers 1 et 2 reflètent D5, sans rien ressaisir** — **D5 fait foi**. Compléter
dans l'étude tout objet manquant ou divergent.
*À produire : la page d'étude dont les compteurs montrent les actifs de la filiale, un audit, six événements redoutés et
cinq couples SR/OV dont trois retenus, identiques à D5.*

**Exercice 2 — Saisir l'écosystème en parties prenantes** *(10 min)*
Reprendre l'objet étudié du TD et identifier son écosystème depuis la cartographie de la séance 2 et les §3 et §6 du
pack : **au moins quatre parties prenantes**, prises parmi les prestataires, les autres filiales et les clients qui y
figurent. Créer chacune dans le module EBIOS RM et lui donner une catégorie parmi celles de l'outil.
*À produire : au moins quatre parties prenantes rattachées à l'étude, **chacune correspondant à un acteur nommé au §3 ou
au §6, aucune inventée**.*

**Exercice 3 — Coter la dangerosité et lire la criticité** *(15 min)*
Renseigner pour chaque partie prenante les **quatre critères courants**, en adossant **chaque note à un fait du pack et
non à une impression**. **Lire la criticité calculée** par l'outil, repérer la ou les parties prenantes les plus
critiques et cocher **« Selected »** sur chacune.
*À produire : au moins quatre parties prenantes cotées, chaque note justifiée par une ligne adossée à un fait, la
criticité lue pour chacune, et les parties prenantes critiques cochées.*
*Si le résultat surprend, ce ne sont pas les mathématiques qu'il faut contester, ce sont les notes qu'il faut réexaminer
et rejustifier.*

**Exercice 4 — Créer deux scénarios stratégiques et leurs chemins d'attaque** *(15 min)*
Prendre **deux** des trois couples SR/OV retenus en atelier 2 et, pour chacun, créer un **scénario stratégique** rattaché
au couple et à l'**événement redouté focalisé**. Y créer **au moins un chemin d'attaque passant par une partie prenante
critique**, rattacher cette partie prenante et cocher **« Selected »** sur le chemin. **Décrire chaque chemin en
distinguant l'événement intermédiaire** (porté sur l'écosystème) **de l'événement redouté** (porté sur la valeur métier) ;
lire la gravité sur l'échelle de D5.
*À produire : deux scénarios stratégiques, chacun avec un chemin d'attaque « Selected » relié à une partie prenante
critique, gravité affichée depuis l'événement redouté.*

**Exercice 5 — Commencer l'atelier 4 avec un scénario opérationnel** *(10 min)*
Choisir **le chemin d'attaque le plus inquiétant** et créer le **scénario opérationnel** correspondant : décrire la
**séquence d'actions élémentaires sur les biens supports**, estimer sa **vraisemblance globale** sur l'échelle de D5
(V1 à V4) et le rattacher à son chemin d'attaque, coché « Selected ».
*À produire : au moins un scénario opérationnel rattaché à un chemin d'attaque, avec sa description de modes opératoires
et **sa vraisemblance justifiée par le socle de sécurité et ses limites**.*

### TP 2 — *Third-party requirements and project sheet (D6)*

**Livrable D6** = deux pièces écrites cohérentes + l'export ou la capture de l'étude EBIOS RM saisie au TP précédent.
*Principe commun : rien n'y est affirmé qui ne soit tracé à un risque identifié ou à un écart observé. Un jalon sans
critère de passage, ou une exigence sans justification, est un vœu, et la grille le refuse.*

**Pièce 1 — La fiche projet** *(15 min)* — appliquer le Security by Design à un **projet réel** de la filiale étudiée,
cadré comme s'il devait être lancé aujourd'hui. Sections à remplir : **objet et périmètre** · **données et besoins DICT**
(lues dans le pack) · **régime du projet** (développer, acheter ou faire développer, et ce que ce choix implique) ·
**jalons de sécurité** · **responsabilités** (un propriétaire ultime unique par décision) · **points d'arbitrage**
(désaccords prévisibles et instance qui tranche).
Tableau des **six jalons** à compléter, chacun avec son **critère de passage vérifiable** (démontré par un fait, jamais
par une déclaration) et son **livrable** : **M1 Qualification** (quelles données, quels besoins DICT, quel niveau
d'analyse ?) · **M2 Architecture** (cloisonnement, authentification, journalisation prévus ?) · **M3 Contractualisation**
(exigences de sécurité au contrat, si un tiers intervient ?) · **M4 Recette** (exigences démontrées, et pas seulement
déclarées ?) · **M5 Exploitation** (qui maintient, surveille, corrige, sous quels délais ?) · **M6 Fin de vie** (données
restituées ou détruites, accès révoqués ?).
*Pour un système soumis à homologation, le critère de M4 est **la décision d'homologation prononcée par l'autorité
désignée en séance 4**, et la fiche le dit en toutes lettres.*

**Pièce 2 — Les exigences du contrat d'infogérance** *(15 min)*
Reprendre le contrat travaillé au TD et **rédiger le jeu d'exigences de sécurité** à inscrire au cahier des charges de
son renouvellement ou de son avenant, dont le prestataire devra démontrer la couverture dans son **Plan d'Assurance
Sécurité**. Cinq familles à remplir en **formulation vérifiable** : **réversibilité · droit d'audit · notification
d'incident · traçabilité et comptes nommés · maîtrise de la sous-traitance**. *Chaque exigence est tracée à un **scénario
stratégique** du TP précédent, à un **écart de l'audit de la séance 4**, ou à un **silence du contrat** relevé dans le
pack : **la colonne justification est le cœur de l'exercice**.*
Compléter par le **dispositif de surveillance du tiers** : **trois indicateurs** (libellé, source de données, fréquence
de lecture) · le **comité de suivi** (fréquence, participants, ce qui s'y décide) · la **preuve annuelle** que le
prestataire remet sans qu'on la demande · **ce qui reste au client** (les décisions et contrôles jamais délégués).
*Méthode : pour la fiche projet, commencer par M1 ; pour les exigences, **partir du scénario stratégique et remonter vers
l'exigence, jamais l'inverse**.*

**Note de stratégie** *(15 min)* — sous-section 6 : **« Tiers et projets »**, une demi-page max, sans rien recopier de
D6. Porte la position du groupe sur ses tiers et ses projets et **renvoie explicitement** à la gouvernance de la
séance 1 et aux actifs critiques de la séance 2.

---

## Séance 7 — Traitement du risque · EBIOS RM atelier 4 + registre

*CM : « The ISO/IEC 27005:2022 process and its steps » (appréciation, évaluation, traitement, risque résiduel, registre).*

### TD 1 — *The CISO's Desk: Pricing the cost of inaction*

Notions : **coût de l'inaction** · décomposition de l'**impact financier** en quatre composantes (interruption
d'activité · remédiation · sanctions et transactions · confiance) · **argument d'investissement** (scénario du registre /
coût plausible de l'inaction en fourchette sourcée / coût du traitement, **CAPEX build vs OPEX run**).
Références mobilisables : Maersk 250-300 M$ (T3 2017) · Norsk Hydro ~800 MNOK (2019) · Equifax ≥ 575 M$ (2019) ·
CNIL / France Travail 5 M€ (janvier 2026) · IBM : 3,85 M€ France 2024, 4,44 M$ monde 2025, **241 jours** de cycle de vie
moyen d'une violation.

**Cas** : lundi matin, le Directeur Financier en marge du comité : *« Combien tout cela va-t-il nous coûter, et surtout,
combien coûte le fait de ne rien faire ? »*

Questions guidées :
1. **Rattacher les références de coût aux scénarios du registre** de la filiale étudiée : un tableau, **une ligne par
   scénario** (indisponibilité de l'actif critique · vol ou fuite de données personnelles · malveillance ou erreur
   interne), avec la référence documentée qui l'éclaire le mieux, la nature du coût qu'elle illustre, le montant,
   l'année, la source, et **une phrase disant pourquoi elle éclaire ce scénario**. *Quand aucune référence ne colle,
   l'écrire dans la ligne : c'est une réponse.*
2. **Rédiger l'argument d'investissement** pour le scénario d'indisponibilité de l'actif critique. Il s'ouvre par **la
   réplique au Directeur Financier, une seule phrase** posant l'alternative sans dramatiser ni minimiser. Il continue en
   trois parties : **le scénario et son chemin** · **le coût plausible de l'inaction, en fourchette basse et haute**,
   calculé avec les quatre termes (perte par jour d'arrêt tirée du pack × durée basse et haute, + remédiation,
   + sanction s'il y a lieu), borné par les références — *et quand le pack ne chiffre pas un terme, **nommer la donnée à
   demander au Directeur Financier*** · **la nature du traitement** à proposer l'après-midi, en disant déjà ce qui sera
   investi une fois et ce qui sera payé chaque année, **sans le chiffrer encore**.
3. **Répondre au contre-interrogatoire du Directeur Financier** : formuler **les trois objections** qu'il opposera à
   l'argument, **telles qu'il les dirait**, et pour chacune la réponse du RSSI Groupe en une phrase, adossée à un élément
   du pack ou à l'échelle de gravité du groupe, **jamais à une promesse**.
*Temps : 15 / 20 / 10 min. **Écarter tout chiffre qui ne vient pas de l'exposé ou du pack** : l'exercice évalue la
discipline de sourçage autant que l'argumentation.*

### TD 2 — *Rating matrices and treatment options*

Notions : **matrice de cotation** (ce qu'elle calcule et ce qu'elle ne calcule pas ; pourquoi le **4×4** — pas de
milieu — plutôt que le 5×5) · **ligne d'acceptation** (elle traduit l'appétence, **et l'appétence n'appartient pas au
RSSI**) · les **trois manipulations** à reconnaître (coter la vraisemblance à la baisse parce que le traitement coûte
cher · découper un gros risque en petits · coter le résiduel avant d'avoir décidé les mesures).

**Exercice 1 — Coter quatre scénarios du groupe** *(15 min)*
Quatre scénarios : **A** attaquant lucratif atteignant la disponibilité des données de soin **via l'identifiant de
télémaintenance partagé de l'éditeur du SIH** · **B** compromission du poste d'un administrateur du pôle Éducation &
Territoires donnant accès aux données administratives de Territoires · **C** mise à jour piégée appliquée par la TMA du
WMS introduisant du code malveillant chez Logistique · **D** exfiltration par erreur d'un fichier de données personnelles
vers un service en ligne non approuvé.
**Coter les quatre scénarios sur les deux axes**, gravité puis vraisemblance, **avec les échelles G1-G4 et V1-V4 de D5
telles quelles**, puis **lire leur niveau sur la matrice 4×4**. Chaque cotation tient en une phrase **renvoyant à un
niveau nommé de l'échelle et à un signal** (un écart de l'audit, une pratique observée, un incident public comparable).
*Le mot « significatif » sans référence à l'échelle ne vaut rien.* Pour le scénario qui a le plus fait hésiter, **dire ce
qui changerait la cotation**.
*Méthode : coter la gravité avant la vraisemblance, systématiquement, et sans regarder l'autre axe.*

**Exercice 2 — La ligne d'acceptation, et qui la trace** *(10 min)*
Le Directeur de la Logistique propose de placer la ligne d'acceptation de sorte que le **scénario C** passe juste
en dessous : *« ce sont des mises à jour de notre mainteneur historique, nous n'allons pas bloquer la production pour
ça »*. La Directrice Générale demande l'avis du RSSI avant de décider.
1. **Dire où placer la ligne et sur quelle base**, en s'appuyant sur les **classes d'acceptation** du guide plutôt que
   sur l'intuition.
2. **Répondre au comité en trois phrases** : ce qu'impliquerait concrètement la ligne proposée par la Logistique · ce que
   le RSSI recommande · **ce que le RSSI demande par écrit**.
3. **Nommer qui signe cette décision** chez MERIDIAN, avec la répartition des rôles de la séance 1, et **dire pourquoi ce
   n'est pas le RSSI**.
*Les deux erreurs symétriques : céder en silence (ce qui fabrique une acceptation que personne n'a signée) et décider à
la place de la direction.*

**Exercice 3 — Choisir et défendre une option de traitement** *(20 min)*
1. Pour **chacun des quatre scénarios**, trancher **une option parmi réduire, accepter, éviter, transférer**, justifiée
   en une phrase ; **au moins une des quatre n'est pas « réduire »**, sinon les autres familles n'ont pas été examinées.
2. Chaque réduction porte **sa mesure, son propriétaire nommé et son échéance** (*une mesure sans propriétaire est un
   vœu*).
3. Pour le **scénario A**, dire **ce que l'assurance cyber proposée couvrirait réellement et ce qu'elle ne couvre pas**.
4. Pour le **scénario D**, **rédiger l'acceptation en bonne et due forme** : le niveau qui la signe, ce qu'elle contient,
   l'échéance de son réexamen.
*Formuler chaque décision telle qu'un tiers la lira dans deux ans, sans son auteur dans la pièce : la phrase dit-elle
qui a décidé, quoi, pourquoi et jusqu'à quand ?*

### TP 1 — *Workshop 4 in detail and the risk register in CISO Assistant*

**Étape 1 — Dériver les scénarios opérationnels des chemins d'attaque** *(25 min)*
Dériver **chaque scénario stratégique retenu en séance 6** en un scénario opérationnel, enregistré dans l'atelier 4 et
**relié à son chemin d'attaque** ; **au moins les deux qui passent par les parties prenantes critiques**. Le scénario
s'écrit en **séquence d'actions élémentaires — connaître, entrer, trouver, exploiter** — où chaque étape **nomme un bien
support de l'inventaire de la séance 2**, l'action pratiquée sur lui, et **ce qui s'y oppose aujourd'hui** (une mesure du
socle, du cloisonnement, de l'authentification, de la journalisation, ou rien). *Un bien support absent de l'inventaire
est **un trou de cartographie à noter**, pas un objet à inventer.*
*Validation : un collègue qui ne connaît pas le dossier doit pouvoir lire la séquence et dire où il faudrait agir.*

**Étape 2 — Estimer la vraisemblance, maillon par maillon** *(20 min)*
Estimer la vraisemblance de chaque scénario opérationnel, **V1 à V4, avec l'échelle de D5 telle quelle**, et la saisir
dans l'outil avec sa justification. *La vraisemblance se lit sur le chemin réellement emprunté : **l'étape qui offre le
plus de résistance gouverne la cotation de l'ensemble**.* La justification **nomme ses appuis** : un écart de l'audit de
la séance 4, une pratique observée, la **maturité et la confiance cotées en atelier 3** pour la partie prenante
traversée, un incident public de mode opératoire comparable — **pas une impression, et pas la gravité de ce qui
arriverait**.
*Piège : coter en regardant le résultat. Un scénario catastrophique et très difficile à réaliser existe, et se cote comme
tel.*

**Étape 3 — Construire le registre des risques** *(25 min)*
**Générer l'appréciation des risques depuis l'étude** (atelier 5, activité 1) : c'est **le registre du périmètre, créé une
seule fois**, avec un scénario de risque par scénario opérationnel, auquel l'outil ajoute **les événements redoutés sans
scénario**, à coter à leur tour contre le socle observé en séance 4. Pour chaque scénario, **trancher l'option de
traitement** ; un scénario laissé ouvert porte **au minimum l'explication écrite de son report et le nom de qui
décidera**. Chaque **réduction** porte ses **contrôles appliqués**, leur **propriétaire pris dans la carte du pouvoir
(§3)** et leur **échéance** ; chaque **acceptation**, sa **justification**, son **échéance de réexamen** et **l'instance
qui la signera**. *Le contrôle qualité de l'outil passé au vert fait partie du livrable.*

**Étape 4 — Coter le risque résiduel** *(20 min)*
Coter le résiduel de chaque scénario traité, **après la décision et jamais avant**, en se demandant **ce que les mesures
changent réellement** : une résistance ajoutée sur le chemin fait baisser la **vraisemblance**, une réduction de ce qui
serait atteint fait baisser la **gravité**, **rarement les deux**. *L'outil refuse un résiduel supérieur au niveau
courant et rappelle qu'un scénario sans mesure supplémentaire garde le même niveau : ces refus font partie de la
méthode.* Puis **confronter chaque résiduel à la ligne d'acceptation** : s'il reste au-dessus, **renforcer le traitement
ou préparer la demande d'acceptation dérogatoire** auprès de l'instance légitime.
*Note d'écarts à tenir : ce que l'outil a fait apparaître que le brouillon ne contenait pas (libellés d'écran divergents,
biens supports manquants).*

### TP 2 — *Treatment plan, residual risk (D7) and strategy note*

**Les quatre exigences d'acceptation de D7**, vérifiées une à une : *(1)* **aucun risque du registre sans décision** ·
*(2)* **tout résiduel dépassant l'appétence porte une dérogation justifiée** · *(3)* **les cotations sont cohérentes avec
les échelles de D5, jamais recréées** · *(4)* **chaque risque porte son option, ses mesures, son propriétaire, son
échéance et son résiduel coté**.

**Étape 1 — Construire le plan de traitement** *(25 min)*
**Extraire le registre et le réorganiser en plan de traitement, par DÉCISION et non par scénario** — ce qui est réduit,
évité, transféré, accepté : *un comité arbitre des décisions, pas des scénarios*. Chaque ligne de réduction est
complète : **risque visé · mesure · propriétaire nommé · échéance · charge estimée · effet attendu sur la cotation**
(qui justifie le résiduel). **Regrouper les mesures qui traitent plusieurs risques à la fois** : ce sont les meilleures.
**Séparer visiblement ce qui relève d'une décision de direction** (engager un budget, renoncer à une activité, accepter
un risque) **de ce qui relève de l'exécution**.
**Chiffrage dans l'outil**, sur chaque contrôle appliqué, section « Cost » : pour le **build**, « Fixed cost » en euros
et « People days required for implementation » ; pour le **run**, le « Fixed cost » annuel et les « People days required
annually » ; puis l'« Amortization period (years) » du build. *(TJM de l'instance : 500 € par défaut, à laisser tel quel.)*
Le plan reporte pour chaque mesure ses **jours-homme** et son **coût annuel**, **CAPEX build et OPEX run distingués** ;
le total se lit dans l'aperçu budgétaire de l'onglet « Plan d'action ».
*À produire : le plan de traitement du groupe, **priorisé sur trois ans**, chaque mesure avec sa charge et son coût annuel
lus dans l'outil, décisions de direction distinguées de l'exécution, et **le coût annuel total du plan mis en regard de la
fourchette de coût de l'inaction du matin**.*
*Test de lisibilité : faire lire une ligne au hasard à quelqu'un qui n'a pas suivi l'étude ; s'il ne peut dire qui a
décidé quoi, pourquoi et jusqu'à quand, la ligne est à réécrire.*

**Étape 2 — Formaliser les acceptations** *(20 min)*
Écrire une décision **pour chaque risque accepté en l'état** et **pour chaque résiduel restant au-dessus de la ligne**
après traitement — **deux documents différents**.
- **L'acceptation simple** tient en **cinq éléments** : le risque tel que coté · la raison de l'accepter · l'instance qui
  accepte · la date · l'échéance de réexamen.
- **La dérogation** ajoute : pourquoi le traitement supplémentaire n'est pas entrepris · ce qu'il faudrait pour
  l'entreprendre · **sous quelle condition la dérogation tomberait**.
**Vérifier l'instance** : une acceptation se signe **au niveau où l'appétence a été posée**, une dérogation à ce niveau
ou au-dessus, **jamais par un directeur de filiale sur un risque de niveau groupe**.
*À produire : une fiche d'acceptation par risque accepté et une demande de dérogation par résiduel au-dessus de la ligne,
chacune avec son instance signataire et son échéance de réexamen ; **s'il n'y a aucune dérogation à demander, l'écrire et
dire pourquoi**.*
*La phrase à ne jamais écrire : « Risque accepté par le RSSI. »*

**Étape 3 — La sous-section de la note de stratégie** *(15 min)*
Sous-section 7 : **« Traitement du risque »**, sans réécrire les précédentes. Trois choses suffisent : **la position du
groupe sur l'acceptabilité du risque** · **les décisions structurantes prises ce jour** · **ce qui reste ouvert, avec
l'échéance à laquelle ce sera tranché**. **Relire les sous-sections antérieures : si l'appétence de la séance 5 ne
résiste pas à ce qui vient d'être coté, l'amender et dire pourquoi.**

*Vérification avant remise, qui prépare la séance 8 : **chaque mesure du plan de traitement est-elle formulée de manière
à pouvoir être rattachée à une exigence du référentiel** ? « Renforcer la sécurité des accès » ne se rattache à rien ;
« supprimer les comptes d'administration partagés au profit de comptes nominatifs tracés » se rattache directement.*

---

## Séance 8 — Périmètre du SMSI · business case de certification

*CM : « ISO 27001:2022 Architecture and the Role of Top Management ».*
*Note : cette séance **n'a pas de TD 2** — il est remplacé par un **temps de projet encadré de 120 minutes** (voir fin de
séance).*

### TD 1 — *The CISO's Desk: The certification case*

Notions : le **business case de certification** (ce que le certificat prouverait / ce qu'il ne prouverait pas / la charge
et la trajectoire / la décision demandée) · la **valeur métier du SMSI** (confiance démontrable, constance, arbitrages
éclairés, réutilisation — *à condition que le système vive*).

**Cas** : le Directeur de la filiale transmet une exigence reçue d'un tiers, sous la forme d'une clause d'une ligne :
*« La filiale devra démontrer une certification ISO/IEC 27001 valide couvrant les services fournis à ce tiers, ou une
démarche documentée équivalente. »* Message d'accompagnement : *« Dites-moi qu'on a ça. »* — **Le groupe ne l'a pas** :
il a un référentiel choisi (séance 3), importé, un audit interne (séance 4) et un plan de traitement (séance 7). *Une
démarche existe. Un certificat, non.* La Directrice Générale cadre la semaine : *« Jeudi, au Comité Exécutif, je veux
votre recommandation : lançons-nous une démarche de certification, sur quel périmètre, et que répond-on à ce tiers en
attendant. Pas de lyrisme, des faits. »*

Questions guidées :
1. **Analyser la clause transmise** : qu'exige-t-elle exactement, et quelle est la portée des mots **« couvrant les
   services fournis à ce tiers »** et **« ou une démarche documentée équivalente »** ? **Au moins deux lectures**, avec
   leurs conséquences pour la réponse du groupe.
2. Établir la colonne **« ce que le certificat prouverait »** : à quelles **audiences** (prises dans les §3 et §6 du
   pack), sur quel objet, avec quelle valeur au regard de ce que la séance 3 a établi. **Trois audiences au minimum, un
   bénéfice par audience.**
3. Établir la colonne symétrique **« ce que le certificat ne prouverait pas »** : **trois limites au minimum**, chacune
   en une phrase, **dont une sur la conformité réglementaire et une sur la sécurité réelle des systèmes**.
4. **Proposer un périmètre de certification** pour le groupe et le **défendre en cinq lignes** : tout le groupe, la
   filiale étudiée seule, ou seulement les services visés par le tiers ? S'appuyer sur la cartographie de la séance 2 et
   sur les écarts constatés en séance 4.
5. **Rédiger la décision demandée au Comité Exécutif, en trois phrases au plus** : la recommandation · ce qu'elle engage ·
   **la réponse proposée au tiers dans l'intervalle**. *Contrainte : **aucune date de certification promise, aucun coût
   improvisé**.*
*Temps : 5 min de relecture des travaux antérieurs, 15 min (Q1-4), 10 min (Q5) — la seule que la direction lira.*
*Piège à surveiller : pour chaque affirmation, se demander si elle décrit **la démarche du groupe, qui existe**, ou **le
certificat, qui n'existe pas**.*

### TP 1 — *ISO 27001 assessment and SoA in CISO Assistant* *(50 min)*

*Vocabulaire à fixer d'abord : chaque exigence porte un **ÉTAT D'AVANCEMENT** (à faire, en cours, en revue, fait — il
parle de **l'évaluateur**) et un **RÉSULTAT** (conforme, partiellement conforme, non conforme, non applicable, non
évalué — il parle du **groupe**). **Règle du groupe : aucun résultat « non conforme » ou « non applicable » sans une
observation d'au moins une phrase, tracée à une pièce du dossier.***

**Étape 1 — Retrouver l'évaluation et vérifier son état** *(5 min)*
1. **Retrouver** dans l'instance l'évaluation de conformité initiale, quel que soit son nom, rattachée au périmètre créé
   en séance 3 et au référentiel importé le même jour.
2. **Vérifier avant toute saisie** que l'arbre affiche bien **les deux blocs** (clauses 4 à 10 / « Déclaration
   d'applicabilité »), que les clauses 4-10 sont à leur état initial, et que l'annexe A porte déjà les **douze statuts**
   saisis en séance 4.
3. **Noter le comptage de départ** : **123 exigences évaluables**, dont **93 contrôles d'annexe A**. *Si les comptes
   diffèrent, s'arrêter et corriger l'import avant d'évaluer quoi que ce soit.*
*Validation : savoir dire, sans ouvrir l'aide, quelle information de l'écran est un avancement et laquelle est un
résultat.*

**Étape 2 — Évaluer les clauses 4 à 10 avec les preuves du dossier** *(30 min)*
Parcourir les exigences évaluables des clauses dans l'ordre et, pour chacune : **chercher la pièce du dossier MERIDIAN
qui en répond**, décider le résultat, écrire l'observation quand la règle du groupe l'exige, et passer l'avancement à
« fait ». Guide de lecture (preuves à confronter / question à poser) :
| Clauses | Preuves du dossier | Question à poser |
|---|---|---|
| 4.1-4.4, contexte | cartographie séance 2, contexte réglementaire séances 1 et 3 | le contexte est-il décrit, à jour, et le périmètre est-il **ÉCRIT** quelque part ? |
| 5.1-5.3, leadership | gouvernance séance 1 (note de cadrage, RACI), appétence (séances 1 et 5) | l'engagement est-il visible et documenté, ou vécu et informel ? |
| 6.1-6.3, planification | appréciation séances 5 et 7, plan de traitement, registre | chaque risque a-t-il un traitement décidé, un propriétaire, une échéance ? |
| 7.1-7.5, support | budget séance 1, outil GRC, livrables documentés | les ressources existent, mais l'information documentée est-elle **gérée, versionnée, retrouvable** ? |
| 8.1-8.3, opération | mise en œuvre du plan de traitement dans les filiales | le plan est-il **en exécution réelle**, ou seulement approuvé ? |
| 9.1-9.3, évaluation | rapport d'audit interne séance 4 | qui mesure quoi, à quelle fréquence, et la direction revoit-elle le système ? |
| 10.1-10.2, amélioration | traitement des écarts entrepris en séance 7 | les non-conformités déclenchent-elles des actions correctives tracées ? |
1. **Évaluer les 30 exigences évaluables des clauses**, résultat et avancement, **avec une observation pour chaque
   résultat non conforme**.
2. **Bannir deux facilités** : le « conforme » de politesse (*si la pièce n'existe pas, le résultat descend*) et le
   « non applicable » sur une clause (*les clauses s'appliquent en totalité ; ce résultat n'a de sens que sur l'annexe A*).
3. **Noter au fil de l'eau les deux clauses qui ressortent le plus mal** : ce constat servira l'après-midi et la séance 9.
*Validation : aucune exigence de clause laissée en « non évalué » · chaque « non conforme » porte son observation ·
aucun « non applicable » dans le bloc des clauses.*

**Étape 3 — Marquer l'applicabilité sur l'annexe A** *(15 min)* — limitée aux **quinze contrôles déjà instruits**
(les huit du CM + les douze de la séance 4, cinq étant communs). *Les 78 autres sont marqués en temps de projet encadré ;
D8 n'exige que les contrôles instruits, avec leur taux de couverture.*
1. **Reporter d'abord les huit statuts construits au CM**, observations comprises : ils donnent le ton et le niveau
   d'exigence des justifications.
2. **Confirmer ensuite les douze contrôles saisis en séance 4** avec les règles du jour : soit un « non applicable »
   **avec justification écrite** si la réalité du périmètre le rend sans objet, soit un résultat de mise en œuvre honnête
   (conforme, partiellement conforme, non conforme), adossé autant que possible à un écart d'audit ou à une ligne du plan
   de traitement.
3. **Justifier chaque exclusion en trois lignes**, dans l'observation du contrôle mis en « non applicable » : **le FAIT**
   qui fonde l'exclusion · **la VÉRIFICATION** de ce fait (qui l'a confirmé, et quand) · **la CONDITION de réexamen**
   (l'événement qui rouvrirait la question). *Sans le fait, l'exclusion est une opinion ; sans la vérification, une
   opinion documentée ; sans la condition de réexamen, une décision qui survivra à sa propre validité. **Une exclusion
   dont le fait n'a pas été instruit ne s'écrit pas** : le contrôle reste inclus, non conforme s'il le faut.*
4. **Appliquer la discipline** : **aucune exclusion de confort** ; en cas d'hésitation entre « non conforme » et
   « non applicable », c'est presque toujours « non conforme » — *l'exclusion exige une **absence d'objet**, pas une
   absence de mise en œuvre*.
5. **Relever les comptages** pour la feuille : nombre de contrôles par résultat sur les quinze instruits, et **la liste
   nommée des contrôles non applicables avec leur justification en une ligne**.

### TP 2 — *Justifying the exclusions (D8) and the strategy note* *(35 min + 120 min de projet encadré)*

**Livrable D8** — le premier livrable du module qu'un **auditeur externe lirait tel quel**. *Tout acronyme est développé
à sa première occurrence, tout renvoi nomme sa cible, toute affirmation porte sa preuve.* Gabarit :
§1 **Périmètre du SMSI** · §2 **Déclaration d'applicabilité** (contrôles instruits + **taux de couverture sur 93** ;
statut, justification d'inclusion ou d'exclusion, état de mise en œuvre, renvoi au contrôle en place ou au plan) ·
§3 **Registre des exclusions** · §4 **Synthèse pour la direction** (dix lignes).
*Critères d'acceptation : **chaque exclusion justifiée par une absence d'objet vérifiable, jamais par un coût ou une
préférence** · **chaque contrôle inclus tracé à un risque du registre D7 ou à une exigence légale ou contractuelle
nommée** · **le périmètre de la §1 cohérent avec la cartographie de la séance 2** (mêmes valeurs métier, mêmes biens
supports, mêmes interfaces, aucun objet inventé ni oublié). Le taux de couverture s'affiche en tête de §2 et les
contrôles non encore instruits sont listés comme tels, **jamais comptés comme conformes**.*

**Étape 1 — Écrire le périmètre** *(10 min)*
1. **Rédiger la §1 en une demi-page structurée en quatre paragraphes** : les **activités couvertes** (à partir des valeurs
   métier cartographiées en séance 2) · les **entités et systèmes** (à partir des biens supports) · les **interfaces**
   (celles du §6 du pack, avec le mécanisme qui les contrôle **ou son absence**) · les **exclusions de périmètre**,
   c'est-à-dire **ce que le SMSI ne couvre pas encore, nommé honnêtement**.
2. **Passer le test du tiers** : une personne extérieure au groupe, lisant cette seule demi-page, saurait-elle dire si
   tel système est dedans ou dehors ? Toute phrase qui échoue est à réécrire.

**Étape 2 — Lire les comptages dans l'outil** *(5 min)*
1. **Relever dans l'outil les comptages de l'annexe A** — contrôles instruits, résultats par statut, **taux de couverture
   sur 93** — et les porter en §2. *La ligne de traçabilité de chaque contrôle est son observation dans l'outil : D8 la
   cite, il ne la réécrit pas.*
2. **Vérifier la cohérence croisée** : chaque **risque du registre D7 dont le traitement est « réduire »** doit conduire à
   **au moins un contrôle inclus** ; chaque **écart majeur du rapport d'audit de la séance 4** à un contrôle inclus non
   conforme ou partiel. *L'outil montre les liens, il ne fait pas la vérification : **noter sur la feuille tout orphelin
   découvert**.*

**Étape 3 — Lire ce que l'évaluation raconte, et la synthèse pour la direction** *(5 min)*
1. **Comparer le profil des clauses** : lesquelles tiennent grâce au travail des huit dernières semaines, lesquelles
   restent nues ? *Si l'évaluation est honnête, contexte et planification ressortent mieux que support et mesure de la
   performance.*
2. **Écrire la §4 de D8**, synthèse de **dix lignes** : le profil de l'évaluation initiale · le taux de couverture · les
   **deux clauses les plus faibles** · le chantier désigné · la décision attendue.

**Note de stratégie** *(15 min)* — sous-section 8 : **« Périmètre du SMSI »**, une demi-page max, sans rien réécrire des
sept précédentes. Contient : **le périmètre choisi en deux phrases**, avec le choix assumé du périmètre initial et son
extension visée · **la décision de certification recommandée**, celle du cas du matin, avec sa réponse intérimaire au
tiers · **le constat de l'évaluation initiale en une phrase honnête**. Articulation qui pèse : la sous-section 2 (actifs
critiques) **justifie le périmètre choisi**, à citer ; la sous-section 7 (traitement et risque résiduel) **fonde la
Déclaration d'applicabilité**, à dire en une phrase.

**Temps de projet encadré** *(120 min — remplace le second TD de la séance et une partie des TP)*, par ordre de priorité :
1. **Finir D8** : relire la synthèse pour la direction, le registre des exclusions au test de l'auditeur, le taux de
   couverture en tête de la déclaration.
2. **Relire la note de stratégie de bout en bout**, sous-sections 1 à 8, pour qu'elle se lise comme **un seul document** :
   même périmètre, mêmes chiffres, mêmes décisions d'une sous-section à l'autre.
3. **Classer le rendu par séance** : dans chacune, le bureau du RSSI écrit de chaque membre du groupe et les livrables
   **D1 à D8**.
4. **Étendre la Déclaration d'applicabilité aux 78 contrôles restants**, pour les groupes qui veulent la déclaration
   complète — *le meilleur usage du temps restant, pas une obligation*.
5. **Poser au Directeur Financier ou à la Directrice Générale les questions que le dossier laisse ouvertes**, plutôt que
   d'en inventer la réponse.

*Reste pour la séance 9 : le livrable **D9**, la neuvième sous-section de la note et le support de soutenance.*

---

## Récapitulatif — livrables et rituels

| Séance | Thème | TD 1 (bureau du RSSI) | TD 2 | TP 1 (outil) | TP 2 (rédaction) | Livrable | Sous-section de la note |
|---|---|---|---|---|---|---|---|
| **1** | Gouvernance : niveaux, acteurs, principes | Trois dossiers sur le bureau | Principes structurants + grille de maturité | Analyse d'écart, gouvernance cible, tableau de bord | Note de cadrage, feuille de route et budget | **D1** | 1 · Contexte et gouvernance cible |
| **2** | Cartographie du SI | L'inventaire des actifs (shadow IT / AI) | Valeurs métier, biens supports, DICT | Saisie de la cartographie dans CISO Assistant | Top 5 du groupe par confrontation | **D2** | 2 · Actifs critiques |
| **3** | Choix du référentiel | Applicabilité NIS 2 | Grille de sélection + tables de correspondance | Fiche d'identité, import, évaluation, bibliothèque | Note de business case + revue par les pairs | **D3** | 3 · Choix du référentiel |
| **4** | Audit · valeur de la certification | La valeur de la certification ISO 27001 | Gradation des constats + homologation | Auto-évaluation de 12 exigences + plan d'action | Rapport d'audit initial + homologation | **D4** | 4 · État des lieux |
| **5** | Risques majeurs | Appétence au risque | EBIOS RM ateliers 1 et 2 | Saisie des ateliers 1 et 2 | Échelles du groupe + assemblage de D5 | **D5** | 5 · Risques majeurs |
| **6** | Tiers et projets | Attaque de la chaîne d'approvisionnement | Infogérance + ateliers 3 et 4 | Écosystème, scénarios stratégiques et opérationnel | Fiche projet + exigences contractuelles | **D6** | 6 · Tiers et projets |
| **7** | Traitement du risque | Chiffrer le coût de l'inaction | Matrices de cotation + options de traitement | Atelier 4 détaillé + registre + résiduels | Plan de traitement + acceptations | **D7** | 7 · Traitement du risque |
| **8** | Périmètre du SMSI | Le business case de la certification | *(remplacé par le temps de projet encadré)* | Évaluation clauses 4-10 + Déclaration d'applicabilité | Périmètre, D8, synthèse direction | **D8** | 8 · Périmètre du SMSI |
| 9 | *(non tenue)* | — | — | — | — | D9 | 9 |

**Barème du module (100 points)** : 9 quiz de fin de matinée 20 · oral individuel sur un point de gouvernance
(séance 6, sujet tiré au sort) 15 · oral collectif d'avancement (séance 6) 10 · rapport de groupe 30 · **note de
stratégie 10** · soutenance finale (séance 10) 15.
