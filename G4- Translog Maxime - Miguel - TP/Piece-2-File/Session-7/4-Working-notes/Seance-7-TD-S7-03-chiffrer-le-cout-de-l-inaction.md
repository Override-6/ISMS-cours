# Seance 7 — TD 1 (S7-03) : Chiffrer le cout de l'inaction — trois arguments pour le Comite Executif
### Reponses du Groupe 4 (Translog), dans le role du RSSI Groupe de MERIDIAN — appliquees a **MERIDIAN Logistique** (instance `translog-b`)

> Enchainement de la journee : ce TD 1 du matin prepare les **arguments financiers** que le
> RSSI Groupe presentera au Comite Executif pour faire financer le plan de traitement de
> l'apres-midi (TP 1 et TP 2). Le registre de risque de l'etude EBIOS RM porte trois
> familles de scenarios — indisponibilite de l'actif critique, vol ou fuite de donnees
> personnelles, malveillance ou erreur interne — et chacune appelle un chiffrage du cout
> de l'inaction, documente, source, date, presente en fourchette. Les chiffres qui entrent
> dans le dossier proviennent **exclusivement** du briefing du matin et du pack de filiale.

**Regle** : chaque chiffre cite repond a trois questions — *de qui vient-il, de quelle
annee date-t-il, a quel scenario de notre registre se rapporte-t-il ?* Un chiffre qui
echoue a l'une des trois n'entre pas dans le dossier.
**Sigles** : **WMS** (*warehouse management system*), **TMA** (tierce maintenance applicative),
**ER** (evenement redoute), **SR/OV** (source de risque / objectif vise), **CAPEX** (depense
d'investissement), **OPEX** (depense d'exploitation), **SOC** (centre de supervision de la
securite), **IT/OT** (bureautique / industriel).
**Sources utilisees** : le briefing *« Chiffrer le cout de l'inaction »* (session 7, TD 1),
le pack de filiale MERIDIAN Logistique (version 1, 3 septembre 2026), D5 (appreciation
initiale des risques), D6 (tiers et projets).

---

## Rappel du cas

Lundi matin. Le bilan de suivi envoye a la fin de la seance 6 a montre au Comite Executif
l'etat du dossier MERIDIAN, et la reaction a ete immediate : le Directeur Administratif et
Financier (DAF) a demande, en marge de la reunion, *« combien tout cela va-t-il nous couter,
et surtout, combien coute le fait de ne rien faire ? »*. La question est une occasion : c'est
celle qui ouvre les budgets, a condition qu'on y reponde avec des faits.

Le RSSI Groupe dispose de l'etude EBIOS RM menee depuis la seance 5 : trois couples SR/OV
retenus, sept evenements redoutes cotes, un ecosysteme cote a la seance 6 avec deux parties
prenantes critiques (l'integrateur des automates, dangerosite 12,0 ; APPLICA, dangerosite 8,0),
deux scenarios strategiques (SS1, couple n-1, G4 Critique ; SS2, couple n-4, G3 Important) et
un scenario operationnel (kill chain en sept actions, vraisemblance V3 *Very likely*, niveau
de risque *High*). L'apres-midi, ces risques seront cotes et le plan de traitement construit.
Ce matin, il s'agit de preparer les arguments financiers qui le feront financer.

---

## Question 1 — Relier les references de cout aux scenarios du registre

*Un tableau, une ligne par scenario (indisponibilite de l'actif critique, vol ou fuite de
donnees personnelles, malveillance ou erreur interne), avec la reference documentee du
briefing qui l'eclaire le mieux, la nature du cout qu'elle illustre, le montant, l'annee,
la source, et une phrase expliquant pourquoi elle eclaire ce scenario. Quand aucune
reference ne correspond, l'ecrire dans la ligne : c'est une reponse.*

| Scenario du registre | ER concernes | Reference du briefing | Nature du cout | Montant | Annee | Source | Pourquoi elle eclaire ce scenario |
|---|---|---|---|---|---|---|---|
| **Indisponibilite de l'actif critique** (chiffrement du WMS, arret du flux d'expedition — SS1, couple n-1, G4) | ER1, ER2, ER5 | **A.P. Moller-Maersk, NotPetya** | Interruption d'activite (Transport & Logistics) | **250-300 M USD** | 2017 (Q3) | Communications financieres de Maersk | Le mecanisme est identique a notre scenario strategique SS1 : un rancongiciel destructeur (NotPetya) chiffre le systeme de gestion logistique du groupe, arrete les flux d'expedition sur plusieurs sites pendant des jours. Maersk est un operateur logistique mondial — la difference d'echelle est un facteur 100 en chiffre d'affaires, mais la **nature** de la perte (arret de l'expedition, mode degrade manuel, pertes contractuelles) est la meme. La fourchette du pack de filiale — 12 000 EUR/jour de penalites pharmaceutiques, 40 % du volume expedie bloque — est un sous-ensemble de ce que Maersk a subi. |
| | | **Norsk Hydro, rancongiciel** | Interruption d'activite + remediation | **~800 M NOK (~80 M EUR)** | 2019 (total consolide) | Site web de Norsk Hydro, estimations trimestrielles successives | Un groupe industriel, pas un logisticien, mais le mecanisme est proche : chiffrement des systemes de production, retour au mode manuel pendant des semaines, reconstruction complete. L'ecart d'echelle est moindre qu'avec Maersk ; le **cout de remediation** (reconstruction des systemes) est lisible dans les memes communications — c'est la composante que le pack de filiale ne chiffre pas (sauvegardes jamais restaurees, RTO/RPO non contractualises). |
| **Vol ou fuite de donnees personnelles** (donnees du client pharmaceutique, volumes, tournees, temperatures — SS2, couple n-4, G3) | ER4, ER6 | **France Travail, amende CNIL** | Amende regulateur (donnees personnelles) | **5 M EUR** | 2026 (janvier) | Deliberation de la CNIL | Le scenario vise la confidentialite des donnees du client pharmaceutique (ER6) et la tracabilite (ER4). France Travail illustre ce que coute un defaut de securisation quand des donnees personnelles sont en jeu — 43 millions de personnes potentiellement touchees, amende pour defaut de mesures de securite. Notre filiale ne traite pas des donnees de cette ampleur, mais les donnees de temperature et d'expedition du client pharma sont contractuellement protegees, et le **questionnaire de securite annonce par le client** (pack §2) est l'equivalent d'un controle regulateur dans notre contexte. L'ordre de grandeur sert de plafond, pas de prediction. |
| | | **Equifax, settlement** | Amende et transaction (donnees personnelles) | **>= 575 M USD** | 2019 (settlement) | Accord avec le regulateur federal americain et 50 Etats | Sert de borne haute mondiale : 147 millions de personnes, juridiction americaine. N'est pas transposable a notre perimetre (pas de donnees de sante nominatives directes dans les flux de Logistique), mais rappelle que le **cout des amendes et des transactions** peut depasser de tres loin le cout de la mesure de securite. A utiliser comme argument de disproportion, pas comme prediction. |
| | | **IBM, Cost of a Data Breach 2024 (France)** | Cout moyen d'une violation de donnees | **3,85 M EUR** | 2024 | IBM, Cost of a Data Breach Report 2024 | Ordre de grandeur quand aucun cas sectoriel comparable n'est disponible. Limite : c'est une moyenne, notre incident peut couter dix fois moins ou dix fois plus. |
| **Malveillance ou erreur interne** (alteration des donnees WMS par un initie via le compte de service en clair — couple n-3) | ER2, ER7 | **Aucune reference directe dans le briefing** | — | — | — | — | Le briefing ne fournit pas de reference documentee sur le cout d'un acte malveillant interne dans un contexte logistique. C'est une reponse, pas un oubli. L'impact se mesure indirectement : ER2 (alteration des donnees de preparation) rejoint le scenario d'indisponibilite par ses consequences operationnelles (expeditions fausses, cascade vers Sante) ; ER7 (perte du savoir-faire) n'a pas d'equivalent chiffre dans les references du briefing. **Donnee a demander au DAF** : le cout d'une journee d'expeditions fausses non detectees (credit notes, retours, penalites client), et le cout de reconstruction du savoir operationnel si le Responsable Exploitation partait demain. |

---

## Question 2 — Argumentaire d'investissement pour le scenario d'indisponibilite de l'actif critique

### Reponse au DAF — une phrase

*Le cout du plan de securite est une depense certaine et maitrisee ; le cout de ne rien faire, c'est accepter qu'un incident comparable a ceux que des groupes logistiques et industriels ont documentes — 250 a 300 millions de dollars chez Maersk, 80 millions d'euros chez Norsk Hydro — puisse se produire sur notre propre WMS, dont les faiblesses connues rendent le scenario non pas hypothetique mais plausible, avec des pertes contractuelles certaines de 12 000 euros par jour de penalites et 40 % du volume expedie du groupe bloque.*

### Partie 1 — Le scenario et son chemin

Le registre de risques porte un scenario strategique **SS1**, issu du couple SR/OV n-1 :

- **Source de risque** : cybercriminel (*Organized crime*), pertinence *Highly relevant*.
- **Objectif vise** : chiffrer le WMS et sa base de donnees pour arreter le flux d'expedition du groupe et obtenir une rancon sous menace d'arret prolonge.
- **Valeur metier touchee** : `LOG-PA-01` — l'execution des flux logistiques (40 % du volume expedie du groupe).
- **Evenements redoutes** : **ER1** (flux d'expedition interrompu, gravite Critique des que > 6 h) et **ER2** (donnees de preparation alterees, gravite Grave).
- **Chemin d'attaque** (atelier 3, seance 6) : l'attaquant passe par la **tierce maintenance du WMS** (APPLICA Services, dangerosite 8,0 — partie prenante critique). Mecanisme : compromission du compte de domaine partage de la TMA (porteurs inconnus — constat C4 de D4), ou mise a jour piegee du WMS deployee par la TMA la nuit « quand elle veut » (pack §4), avec propagation laterale aux six sites via le reseau non segmente (constat C3 de D4 — IT/OT interconnectes). Le scenario operationnel (seance 6) detaille la kill chain en sept actions, vraisemblance **V3** (*Very likely*), niveau de risque **High**.
- **Ce qui rend le scenario plausible aujourd'hui** : le compte TMA est partage, la segmentation IT/OT est absente, le mot de passe du compte de service est identique depuis 2019 et en clair dans un fichier de configuration, les sauvegardes n'ont jamais ete restaurees, et le SOC ne recoit rien des automates ni du WMS.

### Partie 2 — Le cout plausible de l'inaction, en fourchette

La fourchette s'exprime en quatre termes : **perte par jour d'arret x duree (basse et haute) + remediation + penalite le cas echeant**.

#### Perte par jour d'arret

- **Penalites contractuelles du client pharmaceutique** : **12 000 EUR/jour** d'arret (pack §2 — contractuel, certain).
- **Chiffre d'affaires bloque** : 40 % du volume expedie du groupe est bloque des que l'arret depasse six heures (pack §2, §5). Le chiffre d'affaires quotidien de Logistique n'est pas dans le pack. **Donnee a demander au DAF** : le chiffre d'affaires moyen expedie par jour, pour chiffrer la perte de marge brute.
- **Credits et retours** : les expeditions fausses non detectees (ER2) generent des retours, des avoirs et des surcouts de reexpedition. Pas chiffre dans le pack. **Donnee a demander au DAF** : le cout moyen d'un retour / avoir sur erreur de preparation.

**Perte minimale documentable par jour d'arret** : **12 000 EUR** (penalites seules), **tres certainement sous-estimee** puisqu'elle n'inclut ni la perte de CA ni les couts de fonctionnement en mode degrade.

#### Duree — fourchette basse et haute

- **Duree basse** (l'arret que la filiale a deja vecu) : **une demi-journee** — l'arret WMS d'avril, resolu en debut d'apres-midi, cause jamais identifiee (pack §4). Cout minimal : 12 000 EUR (une journee entamee = une journee facturee par le client pharma). Mais en avril, rien n'a ete chiffre ni restitue : « chacun a appele qui il pouvait, personne n'a tenu de chronologie » (pack §5, constat 6).
- **Duree haute** (ce que les cas documentes montrent) : **plusieurs jours a plusieurs semaines** de mode degrade. Maersk a mis **dix jours** avant de retrouver un fonctionnement acceptable de ses systemes logistiques (2017) ; Norsk Hydro a fonctionne en mode manuel pendant **plusieurs semaines** (2019). Pour Logistique, la duree haute est bornee par deux faits : les sauvegardes n'ont **jamais ete restaurees** (pack §4, constat 4) — le RTO reel est inconnu — et la reconstruction complete n'a jamais ete testee.

#### Remediation

Le pack ne chiffre pas la remediation (reconstruction, investigation, notification). Le contrat de TMA prevoit l'astreinte et le retablissement en 6 h (contrat art. 4), mais pas la reconstruction apres un chiffrement total. L'ordre de grandeur de reference : **IBM, Cost of a Data Breach Report 2025, cout moyen mondial : 4,44 M USD**, cycle moyen 241 jours (identification + confinement). A utiliser comme **ordre de grandeur** — *« les groupes qui ont documente leurs couts parlent de millions, pas de milliers »* — pas comme prediction.

**Donnee a demander au DAF** : le budget annuel de la TMA (contrat APPLICA) et le cout d'une prestation de reconstruction d'urgence — ces deux chiffres bornent le plancher de la remediation.

#### Penalite

Des donnees personnelles sont-elles en jeu dans ce scenario ? ER4 (tracabilite des acces) et ER6 (confidentialite des donnees pharma) relevent davantage du scenario n-2 (fuite). Mais si l'arret du WMS s'accompagne d'une exfiltration prealable (double extorsion, mode operatoire courant), la CNIL est competente sur les donnees du personnel (2 800 employes) et sur les donnees logistiques du client pharma si elles sont qualifiees de personnelles. Ordre de grandeur : **France Travail, 5 M EUR** (CNIL, 2026). Ajouter **uniquement si** la qualification « donnees personnelles » est confirmee pour les donnees en jeu — **a verifier avec la Direction Juridique**.

#### Synthese en fourchette

| Terme | Fourchette basse | Fourchette haute | Source |
|---|---|---|---|
| Penalites contractuelles | 12 000 EUR (1 jour) | 12 000 EUR x 10 j = **120 000 EUR** | Pack §2 (contrat pharma) |
| Perte de CA / marge | **A chiffrer — DAF** | **A chiffrer — DAF** | Pack §2 (40 % du volume) |
| Remediation | Astreinte TMA (contrat) | Ordre de grandeur : **plusieurs M EUR** | IBM 2025 (4,44 M USD mondial) |
| Penalite CNIL (si donnees personnelles) | 0 (si pas de DP en jeu) | Ordre de grandeur : **5 M EUR** | France Travail, CNIL 2026 |
| **Total documentable** | **>= 12 000 EUR** | **Ordre de grandeur : quelques M EUR** | — |

La fourchette basse est **certainement sous-estimee** : elle ne contient que les penalites contractuelles d'un jour, sans CA perdu ni remediation. La fourchette haute n'est **pas une prediction** : c'est l'ordre de grandeur que les incidents documentes montrent pour des groupes de taille comparable ou superieure, et que nos faiblesses actuelles (pas de restauration testee, pas de segmentation, pas de journalisation OT) rendent **plausible** sur notre perimetre.

### Partie 3 — La nature du traitement a proposer cet apres-midi

Le plan de traitement de l'apres-midi portera sur les mesures qui reduisent la vraisemblance ou la gravite du scenario SS1. Sans les chiffrer encore, on peut distinguer ce qui sera investi **une fois** (CAPEX, *build*) de ce qui sera paye **chaque annee** (OPEX, *run*) :

| Nature de la mesure | Type | Ce qu'elle traite |
|---|---|---|
| **Segmentation IT/OT** : cloisonner le reseau industriel du reseau bureautique sur les six sites | CAPEX (conception, materiel, deploiement) + OPEX (maintien des regles, supervision) | Constat C3 (D4) — empeche la propagation laterale du scenario SS1 ; reduit la gravite en limitant le perimetre de chiffrement. |
| **Comptes nommes pour la TMA** : remplacer le compte de domaine partage par des comptes individuels avec MFA et journalisation | CAPEX (mise en place) + OPEX (gestion des identites, revues trimestrielles) | Constat C4 (D4) — supprime le vecteur d'entree principal du scenario SS1 ; retablit l'imputabilite. |
| **Rotation du secret de service WMS/automates** : remplacer le mot de passe unique de 2019 par un secret par site, stocke dans un coffre, avec rotation | CAPEX (coffre, migration) + OPEX (rotation, supervision) | Pack §4, constat 3 (D5) — empeche la propagation a tous les sites si un site est compromis. |
| **Test de restauration des sauvegardes** : restaurer le WMS dans un environnement isole, mesurer le RTO reel | CAPEX (environnement de test) + OPEX (test periodique, annuel au minimum) | Constat 4 du pack, A.8.13/A.5.30 de D4 — sans cette mesure, la duree haute de la fourchette est **indeterminee**. |
| **Integration des journaux OT et WMS au SOC** : collecter et transmettre les journaux des automates, de la box 4G et du WMS vers le SOC groupe | CAPEX (collecteurs, connecteurs) + OPEX (traitement, alertes, equipe SOC) | Pack §6, JRN-01 de D5 — passe la detection de « rien » a « quelque chose » sur le perimetre OT ; reduit le delai de reaction, donc la duree d'arret. |

**Ce que le RSSI Groupe ne promettra pas** : un retour sur investissement chiffre. La securite produit des incidents evites, qui ne se mesurent pas. L'argument est : *voici ce que des organisations comparables ont perdu, voici ce que les mesures coutent, voici notre appetence — a vous d'arbitrer*.

---

## Question 3 — Repondre au contre-interrogatoire du DAF

*Trois objections que le DAF formulera contre l'argumentaire, telles qu'il les dirait, et pour chacune la reponse du RSSI Groupe en une phrase, appuyee sur une piece du pack de filiale ou sur l'echelle de gravite du groupe, jamais sur une promesse.*

---

**Objection 1 du DAF** — *« Maersk, c'est un geant mondial du transport maritime — nous sommes six entrepots en France. Ces chiffres ne veulent rien dire rapportes a notre echelle. »*

**Reponse du RSSI Groupe** — Les 250-300 millions de Maersk ne sont pas notre prediction ; ils illustrent le **mecanisme** — chiffrement du systeme logistique, arret des expeditions, mode degrade pendant des jours — qui est exactement celui de notre scenario SS1, et dont la vraisemblance chez nous ne depend pas de notre taille mais de nos faiblesses : le compte de service en clair depuis 2019 est le meme sur six sites (pack §4, constat 3), la segmentation IT/OT n'existe pas (constat C3 de D4), et nos sauvegardes n'ont jamais ete restaurees (constat 4) — ce sont des faits de notre diagnostic, pas un emprunt a Maersk.

---

**Objection 2 du DAF** — *« Vous me parlez de millions, mais le seul chiffre contractuel que je connais c'est 12 000 euros par jour. Le reste, ce sont des ordres de grandeur flous. »*

**Reponse du RSSI Groupe** — Les 12 000 euros par jour ne sont que la penalite du client pharmaceutique (pack §2) — ils ne comptent ni la perte de chiffre d'affaires sur 40 % du volume expedie du groupe (pack §2, §5), ni le cout de reconstruction d'un WMS dont la restauration n'a jamais ete testee, ni les avoirs et retours sur expeditions fausses ; je vous demande justement ces trois chiffres pour remplacer les ordres de grandeur par **nos** chiffres, et c'est en les assemblant, terme par terme, que la fourchette sera celle de MERIDIAN, pas celle d'IBM.

---

**Objection 3 du DAF** — *« On a eu une panne en avril, c'est reparti dans l'apres-midi. Le systeme tient. »*

**Reponse du RSSI Groupe** — En avril, personne n'a tenu de chronologie et la cause n'a jamais ete identifiee (pack §4 — « chacun a appele qui il pouvait ») : nous ne savons pas **ce qui a repris** ni **pourquoi**, et l'echelle de gravite du groupe classe un arret de plus de six heures en **G3 Important** ou **G4 Critique** selon les consequences — la seule raison pour laquelle avril n'a pas ete plus grave, c'est que la panne s'est resolue d'elle-meme ; un chiffrement delibere, lui, ne se resout pas d'un redemarrage, et notre absence de test de restauration (constat 4) signifie que nous ne pouvons pas promettre au Comite Executif en combien de temps nous reviendrions.

---

## Methode de travail

- **Question 1** : 15 minutes. Chaque reference citee repond aux trois questions (qui, quelle annee, quel scenario de notre registre). Quand aucune reference du briefing ne correspond a un scenario, l'absence est documentee — c'est l'integrite du chiffrage.
- **Question 2** : 20 minutes. Chaque terme de la fourchette est tire du pack de filiale ou du briefing ; les termes manquants sont nommes comme des donnees a demander au DAF, pas comme des lacunes.
- **Question 3** : 10 minutes. Chaque reponse s'appuie sur un fait du dossier (pack, diagnostic, echelle de gravite), jamais sur une promesse de resultat.
