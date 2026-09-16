# Séance 9 — TD (S9-01) : The CISO's Desk — Les indicateurs pour le Comité Exécutif
### Réponses du Groupe 4 (Translog) — appliquées à **MERIDIAN Logistique** (instance `translog-b`)

**Vocabulaire** : reporting exécutif, indicateur stratégique, métrique technique, indicateur de vanité,
tableau de bord stratégique — au sens du TD de la séance 9. Les notions de **KPI** (indicateur de mise en
œuvre, mesure l'efficacité d'une mesure de sécurité) et de **KRI** (indicateur de risque, alerte sur une
exposition) ont été posées en séance 1 : elles sont **reprises ici, pas redéfinies**. Sigles développés au
premier emploi : **SOC** (centre de supervision de la sécurité, *security operations center*), **GRC**
(outil de gouvernance-risque-conformité), **MFA** (authentification multifacteur), **PSSI** (politique de
sécurité des systèmes d'information), **SMSI** (système de management de la sécurité de l'information,
*ISMS*), **WMS** (*warehouse management system*, logiciel de gestion d'entrepôt), **TMA** (tierce
maintenance applicative), **IT/OT** (bureautique / industriel).
**Sources utilisées** : le briefing *« The CISO's Desk: Indicators for the Executive Committee »* (séance 9,
TD 1), le tableau de bord esquissé en séance 1 (D1 et sa feuille de travail, exercice 3), le rapport d'audit
initial de la séance 4 (D4), le plan de traitement de la séance 7 (D7), la déclaration d'applicabilité de la
séance 8 (D8).

---

## Rappel du cas

**Le fil droit du module.** Le Directeur Général du groupe MERIDIAN écrit au RSSI Groupe : *« J'ai reçu le
rapport de suivi mensuel : quarante pages, je n'ai lu que la première. La semaine prochaine, le Comité
Exécutif consacre trente minutes à la sécurité avant la revue budgétaire. Je veux un tableau de bord d'une
page : cinq indicateurs, pas un de plus. Si un indicateur est rouge, je veux savoir quoi décider. À vous de
jouer. »*

L'adjoint du RSSI Groupe, plein de bonne volonté, a préparé une première liste de douze candidats, tirée des
outils du groupe (comptage d'alertes du SOC, couverture MFA, attaques bloquées par les pare-feux,
obsolescence des systèmes, délai moyen de détection, tickets de l'infrastructure, taux de sensibilisation,
volume de journaux collectés, constats d'audit non résolus à 30 jours, couverture de la PSSI-cadre,
disponibilité du site vitrine, respect du délai de notification `INC-01`). Il y joint les relevés du
trimestre pour les **quatre indicateurs cibles que le groupe s'est fixés en séance 1**, calculés **au niveau
du groupe, toutes filiales confondues** :

| Indicateur cible de la séance 1 | Relevé du trimestre, niveau groupe |
|---|---|
| Couverture de la PSSI-cadre | **82 %** |
| Délai moyen de détection | **5 heures** |
| Obsolescence du parc | **9 %** |
| Taux de sensibilisation | **64 %** |

Ces quatre relevés font foi pour tout l'exercice ; les cinq directives codifiées de la PSSI-cadre
(`PSSI-CADRE-ACC-01` à `COR-01`, codifiées en D1 et adoptées par la charte de gouvernance, article 1) font autorité, quel que soit le libellé que le groupe
leur a donné.

**Ce que nous y ajoutons, sans rien y substituer.** L'énoncé désigne lui-même le rapport d'audit de la
séance 4 et l'évaluation initiale de la séance 8 comme le réservoir dans lequel puiser la matière des
indicateurs. Pour Logistique, ce réservoir dit trois choses que la moyenne groupe de 82 %/5 h/9 %/64 % ne
montre pas : le taux de conformité mesuré en D4 n'est que de **9 %**, et seulement sur 13 % de l'annexe A
regardée ; deux non-conformités majeures (`C3` cloisonnement IT/OT, `C4` compte de domaine partagé avec la
TMA) restent ouvertes, traitées par `PT-03` (14/06/2027) et `PT-02` (14/01/2027) ; et la sensibilisation
(`A.6.3`) n'a **jamais été évaluée** chez nous — angle mort assumé dès D4 §6, toujours **non conforme et sans
mesure de traitement** en D8 §2.4, qui désigne explicitement ce trou comme le « chantier documentaire de la
séance 9 ». Le tableau de bord que nous proposons au Comité doit tenir compte de ce que notre propre filiale
sait, et de ce qu'elle ne sait pas encore.

---

## Les trois notions posées avant l'exercice

| Notion | Ce que c'est | Ce qu'elle n'est pas |
|---|---|---|
| **Reporting exécutif** | La discipline qui convertit le flux du SOC, de l'outil GRC et des filiales en quelques informations décidables ; elle part des décisions que le Comité peut prendre (budgets, arbitrages, priorités, acceptations de risque) et **remonte** vers les données, jamais l'inverse | Ce n'est pas ce qui est disponible qui monte au Comité, c'est ce qui informe une décision à son niveau ; il agrège, donc il perd du détail — un bon reporting **assume** cette perte et donne le chemin vers le détail, il ne prétend pas le contenir |
| **Indicateur stratégique / métrique technique / indicateur de vanité** | Un indicateur stratégique répond à une question que la direction se pose réellement (*sommes-nous plus exposés que le trimestre dernier ? l'argent investi réduit-il le risque ? respectons-nous nos obligations ?*) ; une métrique technique répond à la question d'un ingénieur et **nourrit** l'indicateur sans monter telle quelle ; un indicateur de vanité rassure sans informer | **Le test d'appartenance** : si l'indicateur passe au rouge, le Comité sait-il quoi décider ? S'il ne peut que froncer les sourcils et demander un rapport, l'indicateur n'était pas à son étage |
| **Tableau de bord stratégique** | L'assemblage ordonné d'indicateurs, chacun avec une cible, un seuil d'alerte et une **tendance** — le mot important, parce qu'une valeur isolée ne dit presque rien ; il est construit pour durer, mêmes indicateurs, mêmes définitions, mois après mois | Sa limite est connue de tout RSSI : un tableau de bord ne mesure que ce qu'on a décidé d'y mettre, et il peut être vert pendant qu'un angle mort brûle — c'est exactement le risque que porte le taux de sensibilisation à 64 % du groupe pendant que `A.6.3` reste non évalué chez nous |

> **Règle d'or du reporting exécutif** : tout indicateur du tableau de bord doit se présenter en une phrase
> de la forme *« ce chiffre vous dit si…, et s'il franchit le seuil, la décision à prendre est… »*. Si la
> phrase ne peut pas se terminer, l'indicateur redescend d'un étage.

---

## Question 1 — Classer les douze candidats

*Trois familles — indicateur stratégique présentable en l'état, métrique technique à agréger ou traduire
avant présentation, indicateur de vanité à écarter — chaque classement justifié en une demi-phrase.*

| # | Candidat | Famille | Justification |
|---|---|---|---|
| 1 | Alertes traitées par le SOC dans le mois | **Métrique technique** | Un volume opérationnel : plus d'alertes ne dit ni mieux ni moins bien protégé, ça nourrit une capacité SOC, pas une décision de comité |
| 2 | Comptes à privilèges protégés par MFA | **Métrique technique** | Granularité d'une seule directive (`ACC-01`) parmi cinq : elle alimente l'indicateur de couverture PSSI (candidat 10), elle ne le remplace pas |
| 3 | Attaques bloquées par les pare-feux | **Indicateur de vanité** | Rassure sans informer : un chiffre qui monte peut vouloir dire « plus attaqués » comme « mieux détectés », et ne commande aucune décision — objet de la question 5 |
| 4 | Systèmes sur OS obsolète | **Indicateur stratégique, présentable en l'état** | C'est le KRI d'obsolescence déjà posé en séance 1 (cible < 5 %, seuil d'alerte > 15 %, feuille de travail S1-05 exercice 3) ; franchi, il commande un arbitrage budgétaire déjà esquissé (réallocation de 15 % vers la modernisation, S1-06) |
| 5 | Délai moyen de détection des incidents | **Métrique technique à traduire** | Une durée en heures est un langage d'ingénieur ; c'est l'objet même de la question 4 avant qu'elle ne monte au Comité |
| 6 | Tickets ouverts par l'équipe infrastructure | **Indicateur de vanité (hors sujet)** | Ni rassurant ni informatif sur l'exposition ou la conformité : c'est un indicateur de charge du support IT, pas de sécurité — à écarter, pas seulement à redescendre |
| 7 | Salariés ayant suivi la sensibilisation sur douze mois | **Métrique technique à vérifier avant agrégation** | Un candidat naturel de comité en principe, mais chez Logistique, l'exigence sous-jacente (`A.6.3`) n'a **jamais été évaluée** (D4 §6, D8 §2.4) — la moyenne groupe de 64 % peut très bien masquer un zéro chez nous sans que personne ne l'ait décidé |
| 8 | Volume de journaux collectés par jour vers le SOC centralisé | **Métrique technique** | Un volume ne dit rien de la couverture ; c'est la brique qui nourrit le KRI du « périmètre non supervisé » déjà posé en séance 1, pas un indicateur en soi |
| 9 | Constats d'audit critiques non résolus après 30 jours | **Indicateur stratégique, présentable en l'état — sous une définition précisée** | Directement lisible sur `C3`/`C4` de D4 et leurs échéances `PT-03`/`PT-02` de D7 ; **mais** pris tel quel, il classerait aujourd'hui Logistique en échec, puisque ces échéances dépassent largement 30 jours alors qu'elles sont datées et approuvées — la question 3 précise donc « sans plan daté et sans propriétaire », pas « pas encore clos » |
| 10 | Filiales couvertes par la PSSI-cadre du groupe | **Indicateur stratégique, présentable en l'état** | C'est l'indicateur de couverture PSSI de la séance 1 lui-même (82 % ce trimestre), et répond mot pour mot à la question « respectons-nous nos obligations ? » |
| 11 | Disponibilité du site vitrine du groupe | **Indicateur de vanité** | Rassurant sur le mauvais système : l'enjeu du groupe posé en D1 est l'arrêt du WMS (40 % du volume expédié, six heures de tolérance), pas la vitrine institutionnelle — un site vitrine disponible à 99,9 % ne dit rien de cette exposition-là |
| 12 | Incidents majeurs notifiés au RSSI Groupe sous 2 h (`INC-01`) | **Indicateur stratégique, présentable en l'état** | Directive datée et nommée (D1), et le seul incident majeur connu du dossier — l'arrêt du WMS d'avril 2026 — n'a **justement pas** de chronologie tenue (constat `A.5.24`, D8 §2.2) : on ne sait même pas s'il aurait respecté ce seuil |

---

## Question 2 — Sélectionner les cinq indicateurs pour le Comité

*Contrainte de construction : au moins un indicateur de conformité aux règles du groupe, au moins un
indicateur d'exposition au risque, au moins un indicateur centré sur la réponse à incident.*

**Sélection retenue : candidats 10, 4, 9, 5 et 12.**

| Indicateur retenu | Famille couverte |
|---|---|
| **10** — Couverture de la PSSI-cadre | Conformité aux règles du groupe |
| **4** — Obsolescence du parc | Exposition au risque |
| **5** — Délai moyen de détection | Réponse à incident |
| **12** — Respect du délai de notification `INC-01` | Réponse à incident **et** conformité |
| **9** — Constats critiques sans plan daté après 30 jours | Gouvernance du traitement — referme la boucle ouverte par D4/D7/D8 |

Les trois contraintes sont couvertes, avec une marge délibérée sur la réponse à incident (5 **et** 12) : l'un
mesure la vitesse de détection, l'autre la discipline de notification une fois détecté — deux moments
distincts du même incident, tous deux nommément en défaut au dossier de Logistique (aucune collecte
automate/WMS avant `PT-07`, aucune chronologie tenue pour l'arrêt d'avril 2026).

**Ce que nous laissons dehors, et pourquoi.**
- **Candidat 2** (MFA) reste une métrique qui nourrit le candidat 10 — le Comité n'a pas besoin de la
  granularité par directive, il a besoin de savoir si le corps de règles est appliqué.
- **Candidat 7** (sensibilisation) reste hors sélection **tant que sa fiabilité n'est pas vérifiée
  filiale par filiale** : le remonter en l'état reviendrait à présenter au Comité un chiffre dont un quart
  des filiales (la nôtre, au minimum) n'a pas produit la mesure sous-jacente. C'est précisément le risque
  que la notion de tableau de bord nomme plus haut : « vert pendant qu'un angle mort brûle ».
- **Candidats 1, 3, 6, 8, 11** sont écartés comme métriques d'alimentation ou indicateurs de vanité (question
  1).

---

## Question 3 — Compléter les cinq indicateurs

*Cible, seuil d'alerte et phrase de la règle d'or pour chacun, en s'appuyant sur les cibles déjà posées en
séance 1 quand elles existent.*

| Indicateur | Cible | Seuil d'alerte | Phrase de la règle d'or |
|---|---|---|---|
| **Couverture de la PSSI-cadre** | 100 % des quatre filiales | **< 75 %** *(une filiale de moins que la totalité)* | Ce chiffre vous dit si le socle de règles du groupe est réellement adopté là où l'exposition vit — pas seulement écrit là où siège le RSSI Groupe — et s'il passe sous 75 %, la décision est de réorienter l'appui du RSSI Groupe vers la filiale en retard avant le jalon des six mois de la charte (D1, article 3) |
| **Obsolescence du parc** | **< 5 %** *(reprise identique du KRI de séance 1)* | **> 15 %** *(reprise identique)* | Ce chiffre vous dit quelle part du parc technique du groupe tourne sur un logiciel non maintenu — la même classe d'exposition que le secret partagé WMS↔automates resté en clair depuis 2019 — et s'il franchit 15 %, la décision est de réallouer le budget vers la modernisation, comme déjà proposé à hauteur de 15 % des enveloppes existantes (feuille de route S1-06) |
| **Délai moyen de détection** | **< 2 h** | **> 4 h** | Ce chiffre vous dit combien de la fenêtre de six heures avant qu'un arrêt du WMS ne bloque 40 % du volume expédié du groupe s'écoule avant même qu'on sache qu'il y a un problème, et s'il franchit 4 h, la décision est de financer le raccordement des journaux OT/WMS au SOC (`PT-07`, déjà budgété chez Logistique) partout où il manque encore |
| **Respect du délai de notification `INC-01`** | **100 %** *(directive ferme, pas une aspiration)* | **< 100 %** *(tout manquement à une directive datée compte)* | Ce chiffre vous dit si chaque incident majeur a bien atteint le RSSI Groupe dans les deux heures que `PSSI-CADRE-INC-01` exige — la même fenêtre que l'arrêt du WMS d'avril 2026 a testée sans que personne n'en ait tenu la chronologie —, et s'il passe sous 100 %, la décision est d'exiger de la filiale en cause une dérogation formelle et bornée dans le temps sous `ARB-03`, plutôt que de laisser un manquement répété devenir un droit acquis sans circuit |
| **Constats critiques sans plan daté après 30 jours** | **0 %** | **> 0 %** *(tout constat majeur sans propriétaire ni échéance après 30 jours déclenche l'alerte)* | Ce chiffre vous dit si un constat majeur comme `C3` ou `C4` chez Logistique avance sous un plan daté et porté par un nom, ou s'il traîne sans personne dessus, et dès qu'un constat franchit ce seuil, la décision est d'escalader la propriété au Comité sécurité groupe |

---

## Question 4 — Traduire le candidat 5 (délai moyen de détection)

*Trois phrases au plus, sans le mot « journaux », ce qu'il mesure, pourquoi il compte, ce qui est décidé
s'il dérive.*

> Ce chiffre mesure le temps qui s'écoule entre le début réel d'un incident de sécurité et le moment où le
> groupe s'en aperçoit. Il compte parce que le seul scénario chiffré à ce jour — un arrêt du WMS qui bloque
> 40 % du volume expédié du groupe au-delà de six heures — ne laisse quasiment plus de marge pour contenir
> et réparer si la détection à elle seule en consomme déjà quatre. S'il dérive au-delà de ce seuil, la
> décision est de financer, filiale par filiale, le raccordement des sources qui manquent encore à la
> supervision centralisée du groupe.

---

## Question 5 — Répondre à l'adjoint sur le candidat 3

*Deux phrases : le défaut fondamental de l'indicateur, ce qui est proposé à la place.*

> Le nombre d'attaques bloquées par nos pare-feux ne passe pas le test de ce matin, parce qu'il ne dit rien
> d'univoque — une hausse peut signifier davantage d'attaques comme une détection mieux réglée — et qu'aucun
> seuil de ce chiffre ne dirait au Comité quoi décider. Je propose de le retirer et de garder à sa place
> l'obsolescence du parc, déjà cotée depuis la séance 1 : elle répond, elle, à la vraie question — sommes-nous
> devenus plus faciles à attaquer — et sait dire ce qu'il faut financer si elle franchit son seuil.

---

*Note collective du TD 1. Matière première des pages individuelles du bureau du RSSI
(`S9-bureau-du-RSSI-Maxime.md`, `S9-bureau-du-RSSI-Miguel-Monereo.md`) et du livrable **D9** (politique,
procédures, indicateurs) à venir en TP.*
