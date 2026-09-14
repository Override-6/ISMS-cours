# Seance 7 — TD 2 (S7-04) : Matrices de cotation et options de traitement
### Reponses du Groupe 4 (Translog), dans le role du RSSI Groupe de MERIDIAN — appliquees au **groupe MERIDIAN** (les quatre filiales)

> Enchainement de la journee : le CM du matin a pose le processus ISO/IEC 27005:2022 et
> son vocabulaire (appreciation, evaluation, traitement, risque residuel, registre) ; le
> TD 1 a chiffre le cout de l'inaction pour le scenario de la filiale d'instruction. Ce
> TD 2 **equipe** la decision : coter les scenarios sur la matrice 4x4, poser la ligne
> d'acceptation, choisir et defendre une option de traitement pour chaque risque. Les
> cotations de cet apres-midi seront saisies dans le registre de `translog-b` (TP 1).

**Regle** : les echelles de gravite G1-G4 et de vraisemblance V1-V4, justifiees dans D5
(seance 5), sont **reutilisees telles quelles** — les redefinir rendrait les risques deja
traites incomparables. La matrice est la `4x4 risk matrix from EBIOS-RM` de la bibliotheque
`intuitem` (lecture seule dans l'outil).
**Discipline d'atelier** : coter la gravite **avant** la vraisemblance, sans regarder l'autre
axe — savoir qu'un scenario est probable pousse imperceptiblement a le trouver plus grave.
**Sources utilisees** : le briefing *« Matrices de cotation et options de traitement »*
(session 7, TD 2), le reference pack MERIDIAN (version 1, 31 aout 2026), le pack de filiale
MERIDIAN Logistique, D5 (echelles et seuil d'acceptation).

---

## Rappel de la matrice 4x4 EBIOS-RM et du seuil d'acceptation

### Matrice de cotation (lecture de la cellule a l'intersection)

| | **V1** `Unlikely` | **V2** `Likely` | **V3** `Very likely` | **V4** `Certain` |
|---|---|---|---|---|
| **G4** `Critical` | Medium | High | **High** | High |
| **G3** `Important` | Low | Medium | **High** | High |
| **G2** `Significant` | Low | Low | **Medium** | High |
| **G1** `Minor` | Low | Low | Low | Medium |

### Seuil d'acceptation (D5, inchange)

| Niveau de risque | Classe d'acceptation | Consequence |
|---|---|---|
| **`Low`** | Acceptable en l'etat | Porte sans mesure specifique, revu trimestriellement au ComEx. |
| **`Medium`** | Tolerable **uniquement** formalise | Tolerance datee, surveillee, proprietaire nomme, mesure compensatoire ; a defaut, traite comme `High`. |
| **`High`** | Inacceptable en l'etat | Decision de traitement avant mise en production ou avant de le porter plus longtemps ; activite suspendue si le traitement n'est pas engage. |

---

## Exercice 1 — Coter quatre scenarios du groupe (15 minutes)

### Scenario

Le RSSI Groupe prepare le comite securite du groupe. Quatre scenarios issus des ateliers
doivent y etre presentes deja cotes, et la Directrice Generale a prevenu qu'elle veut non
pas un tableau de couleurs mais **une phrase de justification par cotation**. Les quatre
scenarios sont ceux du groupe ; celui de la filiale d'instruction se retrouvera dans le
registre cet apres-midi.

---

### Cotation

#### Scenario A — Un attaquant a but lucratif atteint la disponibilite des donnees de soin en passant par l'identifiant partage de telemaintenance de l'editeur du SIH

**Gravite : G4 `Critical`** — L'editeur du SIH (systeme d'information hospitalier) detient un acces
permanent de telemaintenance via un identifiant unique partage entre neuf de ses collaborateurs
(reference pack §3, Sante — constat : « single identifier shared between nine of its people »).
Une compromission de cet identifiant donne un acces privilegie direct aux dossiers patients, aux
machines d'analyse et aux consoles d'imagerie, qui sont **sur le meme plan IP que les postes
d'accueil** (constat 1 de Sante). La mission de soin est remise en cause dans la duree : la
panne de mars, non provoquee, a deja produit 22 actes annules et 2 plaintes de patients en
4 h 10 (constat 6 de Sante). Un chiffrement delibere via l'acces du SIH toucherait les quatre
etablissements ; la consequence sanitaire pour un patient ou un usager est directe — c'est le
critere de **G4** : *« consequence vitale ou sanitaire pour un patient »*.

**Vraisemblance : V3 `Very likely`** — Une faiblesse **connue et actuelle** rend le scenario
realisable avec les moyens courants d'un attaquant a but lucratif : l'identifiant partage est
permanent, sans MFA (constat 2 de Sante), sans tracabilite individuelle, et la filiale n'a
jamais remis le registre des comptes d'administration malgre trois demandes de l'Audit Interne
(constat 4). Le secteur sante reste une cible reguliere — Centre Hospitalier Sud Francilien,
2022, LockBit (contexte de menace de D5). L'hebergeur n'affiche pas de certification HDS
(constat Sante) : le scenario ne bute sur aucune barriere deployee.

**Niveau de risque : G4 x V3 = `High`** — inacceptable en l'etat.

---

#### Scenario B — Un attaquant compromet le poste d'un administrateur du pole Education & Territoires et accede aux donnees administratives de Territoires

**Gravite : G3 `Important`** — Les donnees administratives de Territoires portent des donnees
citoyennes reglementees d'une trentaine de collectivites clientes (reference pack §3,
Territoires). Leur exposition constitue un manquement contractuel — notification dans les
24 heures, rompue si la compromission n'est pas detectee (constat 4 de Territoires : aucune
procedure de notification malgre le delai contractuel). L'echelle de D5 place le scenario en
**G3** : *« engagement contractuel rompu et paye ; donnees personnelles exposees a un tiers non
autorise »*. Ce n'est pas G4 car le projet de connexion aux bases de Territoires a ete refuse
et n'est pas deploye — le perimetre de donnees directement accessible depuis un poste
Education reste limite a l'annuaire partage, pas aux bases metier de Territoires.

**Vraisemblance : V3 `Very likely`** — Les comptes d'administration sont partages entre les
equipes des deux filiales du pole (constat 1 d'Education ; reference pack §5.2 : « a
compromise on one side spreads to the other ») ; les journaux sont conserves localement, sans
centralisation au SOC du groupe (constat 1 de Territoires) ; aucune detection, aucune analyse
post-incident. L'absence de MFA (constat 2 de Sante generalisable — Education/Territoires
n'en disposent pas non plus) et la mutualisation de l'annuaire sont des faiblesses **connues et
actuelles**, au sens de notre echelle V3.

**Niveau de risque : G3 x V3 = `High`** — inacceptable en l'etat.

---

#### Scenario C — Une mise a jour piegee appliquee par le prestataire de TMA du WMS introduit du code malveillant dans Logistique

**Gravite : G4 `Critical`** — Le WMS pilote les six entrepots de la filiale ; une mise a jour
piegee deployee sur les deux serveurs WMS de E1 se propagerait a tous les sites via les
liaisons operateur (pack de filiale §4 : les cinq autres entrepots se connectent au WMS de E1).
Les reseaux IT et OT etant interconnectes (constat C3 de D4), le code atteindrait aussi les
automates de tri. Arret > 6 h = 40 % du volume expedie du groupe bloque, penalites de
12 000 EUR/jour, flux d'approvisionnement d'urgence vers Sante coupe (deja bloque depuis trois
mois). Le mecanisme est celui de NotPetya chez Maersk (2017, 250-300 M USD) — **la capacite du
groupe a tenir une mission remise en cause dans la duree** = G4.

**Vraisemblance : V3 `Very likely`** — Le prestataire de TMA applique ses mises a jour la nuit,
**sans validation prealable** de la filiale (« whenever it wants, we find out in the morning » —
pack §4). Il intervient avec un compte de domaine partage dont personne ne connait le nombre
d'utilisateurs (constat C4 de D4). Le scenario est comparable au vecteur NotPetya (mise a jour
piegee d'un logiciel tiers) ; la chaine d'approvisionnement logicielle (*software supply
chain*) est un mode operatoire courant — exemples recents dans le secteur (D5, contexte de
menace). La faiblesse est **connue et actuelle**, aucune barriere ne filtre la mise a jour
avant son deploiement = V3.

**Niveau de risque : G4 x V3 = `High`** — inacceptable en l'etat.

---

#### Scenario D — Un collaborateur interne exfiltre par erreur un fichier de donnees personnelles vers un service en ligne non approuve

**Gravite : G2 `Significant`** — Volume limite, une seule filiale, pas de donnee de sante
nominative. L'echelle de D5 place ce scenario en **G2** : *« au plus une donnee non sensible
exposee a un cercle restreint »* — le fichier est envoye vers un service tiers, pas diffuse
publiquement ; la reprise est possible en quelques jours (contact avec le service, suppression,
notification si necessaire). Ce n'est pas G3 car il n'y a pas de rupture d'engagement
contractuel chiffre ni de retard de soins.

**Vraisemblance : V3 `Very likely`** — Aucune politique d'usage des services externes n'existe
dans le groupe (reference pack §6 — Education, onze abonnements pris hors DSI, dont un outil
d'IA generative ou les enseignants soumettent des evaluations d'eleves pour relecture ; « rien
ne dit que les trois autres filiales en sont exemptes ; elles n'ont simplement pas cherche »).
La faiblesse est **connue et actuelle** : l'absence de politique et de controle rend le scenario
realisable avec les moyens courants de n'importe quel collaborateur. Ce n'est pas V4 `Certain`
car l'exfiltration specifique d'un **fichier de donnees personnelles** (pas de simples
evaluations pedagogiques) n'est pas documentee comme s'etant deja produite — ce qui a ete
observe, ce sont des usages non encadres, pas encore une fuite de donnees personnelles
averee.

**Niveau de risque : G2 x V3 = `Medium`** — tolerable sous controle, formalisable.

---

### Scenario le plus debattu — Scenario B

**L'hesitation** porte sur la **gravite** : G3 ou G4 ? L'argument pour G4 est que Territoires
porte des donnees citoyennes reglementees de **trente collectivites clientes** — une fuite
massive pourrait entrainer la perte de plusieurs delegations de service public, mettant en
cause *« l'existence d'une filiale »* (critere G4). L'argument pour G3, retenu ici, est que
l'acces direct depuis un poste Education est limite par le refus du projet de connexion aux
bases de Territoires (reference pack §5.3 et Territoires constat 5) : l'annuaire partage
donne un pied dans le SI, mais pas un acces immediat aux bases administratives contenant les
donnees citoyennes. **Ce qui changerait la cotation** : si le projet de connexion
Education → Territoires etait deploye (meme partiellement), l'acces aux donnees
administratives deviendrait direct depuis un poste Education compromis, et la gravite
passerait a **G4** — c'est la raison pour laquelle le DSI de Territoires s'y oppose, et c'est
aussi la raison pour laquelle la decision sur ce projet releve du Comite Executif, pas du DSI
seul.

---

## Exercice 2 — La ligne d'acceptation, et qui la trace (10 minutes)

### Scenario

Le RSSI Groupe presente la matrice au comite. Le Directeur de Logistique propose de placer la
ligne d'acceptation de facon que le scenario C tombe juste **en dessous** : *« ce sont des mises
a jour de notre prestataire de maintenance de longue date, on ne va pas bloquer la production
pour ca »*. La Directrice Generale demande l'avis du RSSI Groupe avant de trancher.

---

### Position de la ligne et fondement

La ligne d'acceptation est celle que l'appétence de la seance 5 (D5 §1) a deja posee :

- **`Low`** = acceptable en l'etat.
- **`Medium`** = tolerable uniquement formalise (tolerance datee, surveillee, proprietaire nomme, mesure compensatoire).
- **`High`** = inacceptable en l'etat — decision de traitement.

Cette ligne traduit l'appetence que la **Direction Generale** a ete invitee a confirmer en
seance 5. Elle est coherente avec les classes d'acceptation du guide EBIOS RM (acceptable /
tolerable sous controle / inacceptable). Sur la matrice 4x4, elle separe les cellules
`Medium` (tolerables sous conditions) des cellules `High` (a traiter).

**Fondement** : on ne la redessine pas a la lumiere des resultats — c'est exactement la
premiere manipulation du briefing (*« la cotation qui justifie : la conclusion precede
l'analyse »*). L'appetence se fixe **avant** de connaitre les cotations ; la bouger apres
pour qu'un scenario passe en dessous revient a decider du traitement avant d'avoir examine
le risque.

---

### Reponse au comite — trois phrases

**1. Ce qu'implique concretement la proposition de Logistique.** Placer la ligne d'acceptation
de facon que le scenario C (G4 `Critical` x V3 `Very likely` = `High`) tombe en dessous, c'est
accepter comme tolerable sans traitement un scenario de type NotPetya sur notre WMS — le meme
mecanisme qui a coute 250-300 millions de dollars a Maersk — alors que notre prestataire de
TMA deploie ses mises a jour la nuit sans validation prealable, avec un compte partage dont
personne ne connait les porteurs ; et en deplacant la ligne assez haut pour exclure C, on
exclut aussi le scenario A (attaque du SIH via l'identifiant partage de l'editeur, meme
cellule G4/V3), ce qui revient a accepter en silence un risque sur la mission de soin.

**2. Ce que le RSSI Groupe recommande.** Maintenir la ligne d'acceptation telle que l'appetence
de la seance 5 l'a posee — `High` est inacceptable en l'etat — et traiter le scenario C par
les mesures que l'etude a identifiees : validation des mises a jour avant deploiement, comptes
nommes pour la TMA, integration des journaux du WMS au SOC ; ces mesures ne bloquent pas la
production, elles l'encadrent.

**3. Ce que le RSSI Groupe demande par ecrit.** Que le Comite Executif **confirme par ecrit** le
seuil d'acceptation pose en seance 5, ou, s'il choisit de le modifier, qu'il **signe la
nouvelle ligne et les risques qu'elle fait basculer dans la zone acceptable** — nommement, les
scenarios A et C ; un seuil que personne n'a signe est un seuil que personne ne porte le jour
de l'incident.

---

### Qui signe cette decision, et pourquoi ce n'est pas le RSSI Groupe

La decision est signee par la **Direction Generale du groupe**, representee par la Directrice
Generale, sur proposition du Comite Executif — c'est la repartition des roles de la
gouvernance de la seance 1 (D1, matrice RACI : la Direction Generale fixe l'appetence, le
Conseil d'Administration l'approuve, le RSSI Groupe la propose sans la fixer).

**Pourquoi ce n'est pas le RSSI Groupe** : l'appetence au risque ne lui appartient pas. Un RSSI
qui fixe la ligne seul se substitue a la direction ; le jour de l'incident, il portera seul
une decision qu'il n'avait pas la legitimite de prendre. Le role du RSSI est de *preparer,
informer, proposer et obtenir une decision ecrite* — pas de decider a la place de la
direction.

---

## Exercice 3 — Choisir et defendre une option de traitement (20 minutes)

### Scenario

Les quatre scenarios sont cotes et la ligne est reglee. Pour chaque risque au-dessus d'elle,
il faut une decision, un proprietaire et une echeance. Le DAF assistera a la reunion et posera
la meme question a chaque ligne : *combien, et pourquoi maintenant ?*

---

### Scenario A — Attaque du SIH via l'identifiant partage de l'editeur (G4/V3, `High`)

**Option retenue : Reduire + Transferer**

**Reduction** — Supprimer le vecteur principal (l'identifiant partage) et retablir la detection.

| Mesure | Proprietaire | Echeance | Ce qu'elle traite |
|---|---|---|---|
| Remplacement de l'identifiant partage de telemaintenance du SIH par des **comptes nommes avec MFA** et journalisation individuelle | **DSI de MERIDIAN Sante** (porte la relation avec l'editeur du SIH) | **6 mois** (negociation contractuelle + deploiement technique) | Constat 1 de Sante (identifiant partage entre 9 personnes) ; retablit l'imputabilite et bloque l'acces par un identifiant vole seul. |
| **Segmentation reseau** : isoler les machines d'analyse et les consoles d'imagerie du plan IP bureautique | **DSI de MERIDIAN Sante** | **9 mois** (etude d'architecture + deploiement par site) | Constat 1 de Sante (machines d'analyse sur le plan IP bureau) ; limite la propagation laterale d'une compromission. |
| Integration des **journaux du SIH au SOC du groupe** | **RSSI Groupe** (le SOC est un actif groupe) | **3 mois** (le SOC recoit deja les logs de Sante, il s'agit d'y ajouter les journaux du SIH) | Retablit la detection sur le vecteur de telemaintenance. |

**Transfert** — Souscription d'une **assurance cyber** en complement (pas en remplacement) de la reduction.

**Ce que l'assurance cyber couvrirait reellement** :
- Les frais de **gestion de crise et d'investigation** (forensics, notification, communication de crise).
- La **perte d'exploitation** pendant l'interruption, dans la limite d'un plafond et d'une franchise — a negocier sur la base des 22 actes annules en 4 h 10 du precedent de mars.
- Les **frais juridiques et amendes** reglementaires (couverture variable selon les juridictions et les polices ; les amendes CNIL ne sont pas toujours assurables en droit francais).

**Ce que l'assurance cyber ne couvrirait pas** :
- La **mission de soin elle-meme** : un patient non soigne a temps n'est pas un sinistre financier couvert par une police cyber — c'est une responsabilite medicale.
- La **vulnerabilite qui a permis l'incident** : l'assurance indemnise les consequences, pas la cause ; le compte partage restera un risque meme apres indemnisation.
- La **confiance** : la relation avec les patients, les tutelles et les partenaires hospitaliers ne se reconstruit pas avec une indemnite.
- Le risque de **resiliation ou d'exclusion** : un assureur qui decouvre que l'identifiant partage etait connu et non corrige peut invoquer un manquement aux obligations de securite de l'assure.

**Conclusion** : l'assurance est un complement utile pour les pertes financieres residuelles **apres** que les mesures de reduction ont ete deployees — pas un substitut. Souscrire sans corriger l'identifiant partage, c'est assurer un batiment dont on sait que la porte est ouverte.

---

### Scenario B — Compromission d'un poste admin du pole Education & Territoires (G3/V3, `High`)

**Option retenue : Reduire**

| Mesure | Proprietaire | Echeance | Ce qu'elle traite |
|---|---|---|---|
| **Separation des comptes d'administration** entre Education et Territoires : chaque equipe recoit ses propres comptes, avec un perimetre de droits limite a sa filiale | **DSI du pole Education & Territoires** (la DSI partagee est le probleme et la solution ; le Comite Executif arbitre si la DSI ne s'auto-corrige pas — point d'arbitrage du RACI de D1) | **4 mois** (migration des comptes, revision des groupes Active Directory, tests) | Constat 1 d'Education (comptes partages) ; reference pack §5.2 (« a compromise on one side spreads to the other ») — coupe le chemin de propagation. |
| **Integration des journaux du pole au SOC du groupe** | **RSSI Groupe** | **6 mois** (le SOC ne recoit aujourd'hui rien du pole — constat 1 de Territoires ; il faut connecter, calibrer les alertes, former les analystes) | Retablit la detection et l'analyse post-incident ; prerequis au respect du delai de notification de 24 h (constat 4 de Territoires). |

**Pourquoi maintenant** (reponse au DAF) : le pole porte 45 000 comptes dont des donnees de mineurs (Education) et des donnees citoyennes reglementees de trente collectivites (Territoires). Chaque jour sans separation des comptes est un jour ou une compromission cote Education donne un acces administrateur cote Territoires, sans qu'aucune alerte ne soit generee — et le delai contractuel de notification de 24 h aux collectivites ne peut pas etre respecte si on ne detecte rien.

---

### Scenario C — Mise a jour piegee du WMS par la TMA (G4/V3, `High`)

**Option retenue : Reduire**

| Mesure | Proprietaire | Echeance | Ce qu'elle traite |
|---|---|---|---|
| **Validation prealable des mises a jour** : toute mise a jour du WMS est deployee d'abord dans un environnement de recette, validee par la DSI de la filiale, avant deploiement en production ; clause a inscrire a l'avenant du contrat `TMA-WMS-2021` | **DSI de MERIDIAN Logistique** (porte la relation avec APPLICA) | **3 mois** (negociation de l'avenant + mise en place de l'environnement de recette) | Coupe le vecteur principal : la TMA ne deploie plus « quand elle veut » la nuit sans validation (pack §4). |
| **Comptes nommes pour le personnel de la TMA** avec MFA et journalisation — remplacement du compte de domaine partage | **DSI de MERIDIAN Logistique** | **4 mois** (avenant contractuel + migration technique) | Constat C4 de D4 (compte partage, porteurs inconnus) ; retablit l'imputabilite et permet au SOC de distinguer une action legitime d'une action malveillante. |
| **Segmentation IT/OT** sur les six sites | **DSI de MERIDIAN Logistique** + **Responsable Exploitation** (l'OT est sous sa responsabilite — pack §3) | **9 mois** (conception, materiel, deploiement site par site, tests de non-regression sur les automates) | Constat C3 de D4 (IT/OT interconnectes) ; limite la propagation laterale — un code malveillant dans le WMS n'atteint pas directement les automates. |
| **Test de restauration des sauvegardes** du WMS | **DSI de MERIDIAN Logistique** | **2 mois** (premier test) puis **annuel** | Constat 4 du pack (sauvegardes jamais restaurees) ; transforme la duree haute de la fourchette du TD 1 d'un « inconnu » en un « mesure ». |

**Pourquoi maintenant** (reponse au DAF) : le prestataire applique ses mises a jour la nuit sans prevenir ; si l'une d'elles est piegee — mecanisme NotPetya, 2017 — les six entrepots s'arretent, les penalites courent a 12 000 EUR/jour, et nous ne pouvons pas dire en combien de temps le WMS serait restaure parce que nous n'avons **jamais teste la restauration**. La premiere mesure (validation prealable des mises a jour) coute un environnement de recette et une clause contractuelle ; elle ne bloque pas la production, elle la protege.

---

### Scenario D — Exfiltration accidentelle de donnees personnelles vers un service non approuve (G2/V3, `Medium`)

**Option retenue : Accepter (formellement)**

Le scenario se situe au niveau `Medium` — tolerable sous controle selon le seuil d'acceptation
de D5. Les quatre conditions de la tolerance formelle sont remplies ci-dessous.

#### Decision d'acceptation en bonne forme

| Element | Contenu |
|---|---|
| **Niveau qui signe** | **Direction Generale du groupe**, sur proposition du RSSI Groupe, apres avis du Comite Executif — conformement a la gouvernance de D1 (la Direction Generale est responsable de l'acceptation du risque residuel, D5 §1). |
| **Ce que la decision contient** | Le risque est **accepte au niveau `Medium`** : un collaborateur peut exfiltrer par erreur un fichier de donnees personnelles de volume limite vers un service en ligne non approuve, faute de politique d'usage des services externes. L'impact est borne a une filiale, sans donnee de sante nominative, sans rupture de la mission de soin ni de la continuite d'expedition. |
| **Mesure compensatoire** | Redaction et diffusion d'une **politique d'usage des services en ligne externes** a l'ensemble du groupe — encadrement, pas interdiction — avec un volet specifique sur les donnees personnelles et les donnees de mineurs (Education). **Proprietaire** : RSSI Groupe. **Echeance** : 6 mois. La politique ne supprime pas le risque (elle ne cree pas de controle technique) mais elle etablit la regle dont l'absence est aujourd'hui la faiblesse documentee (reference pack §6 : onze abonnements hors DSI, dont un outil d'IA generative recevant des evaluations d'eleves). |
| **Echeance de reexamen** | **12 mois** a compter de la signature, ou plus tot si un incident d'exfiltration de donnees personnelles est signale dans le groupe. Au reexamen, si la politique est en place et qu'un controle technique (DLP, blocage des services non approuves) a ete deploye, le risque pourra etre recote. |

**Pourquoi accepter et non reduire** : la reduction technique (DLP, filtrage des services
externes) a un cout disproportionne par rapport a l'impact borne du scenario (`G2`), dans un
contexte ou le groupe n'a pas de budget de securite identifie en premiere annee (reference pack
§7) et ou trois scenarios `High` mobilisent deja les ressources. La mesure compensatoire
(politique ecrite) traite la cause a moindre cout et permet une recotation ulterieure. Ce
n'est pas du confort : c'est un arbitrage explicite entre quatre risques, dont trois sont
inacceptables et un est tolerable — le DAF comprend cette hierarchie.

---

## Synthese du portefeuille de risques du groupe

| # | Scenario | Gravite | Vraisemblance | Niveau | Decision | Proprietaire |
|---|---|---|---|---|---|---|
| **A** | SIH Sante — identifiant partage editeur | G4 | V3 | **High** | **Reduire + Transferer** | DSI Sante / RSSI Groupe |
| **B** | Pole Edu-Terr — comptes admin partages | G3 | V3 | **High** | **Reduire** | DSI du pole / RSSI Groupe |
| **C** | WMS Logistique — mise a jour TMA piegee | G4 | V3 | **High** | **Reduire** | DSI Logistique |
| **D** | Groupe — exfiltration accidentelle DP | G2 | V3 | **Medium** | **Accepter** | Direction Generale |

### Les trois manipulations a reconnaitre (rappel du briefing)

1. **La cotation qui justifie** — *la conclusion precede l'analyse* : c'est exactement la proposition du Directeur de Logistique sur le scenario C (« on ne va pas bloquer la production ») — il veut abaisser la vraisemblance ou deplacer la ligne parce que le traitement couterait.
2. **Le risque fragmente** — *eclate en morceaux dont aucun ne franchit la ligne* : on l'evite ici en gardant le scenario C comme un tout (mise a jour piegee → chiffrement des six entrepots), sans le decouper en six risques par entrepot qui tomberaient chacun en `Medium`.
3. **Le residuel anticipe** — *cote avant que les mesures soient decidees* : le registre de cet apres-midi (TP 1) cotera le risque **brut** d'abord ; le risque residuel ne sera cote qu'apres que le plan de traitement aura ete construit (TP 2) et que chaque mesure aura un proprietaire et une echeance.

---

## Methode de travail

- **Exercice 1** : 15 minutes. Gravite cotee avant vraisemblance, chaque cotation en une phrase avec un niveau nomme de l'echelle et un signal (constat d'audit, pratique observee, incident public comparable). Pour le scenario le plus debattu, deux lignes sur ce qui changerait la cotation.
- **Exercice 2** : 10 minutes. La ligne s'appuie sur les classes d'acceptation du guide et sur l'appetence de D5, pas sur l'intuition ni sur le cout du traitement. La decision est celle de la Direction Generale, pas du RSSI.
- **Exercice 3** : 20 minutes. Chaque decision formulee pour etre lue dans deux ans par un tiers sans son auteur dans la salle : *qui a decide, quoi, pourquoi, jusqu'a quand*. Au moins une option n'est pas « reduire » (ici : transferer sur A, accepter sur D).
