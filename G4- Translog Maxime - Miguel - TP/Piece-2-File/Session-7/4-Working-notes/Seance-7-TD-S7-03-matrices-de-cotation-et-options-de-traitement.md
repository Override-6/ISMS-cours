# Séance 7 — TD 2 (S7-03) : Matrices de cotation et options de traitement
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN — appliquées au **groupe MERIDIAN** (les quatre filiales)

> Enchaînement de la journée : le TD 1 du matin a **chiffré le coût de l'inaction** pour le scénario
> d'indisponibilité de l'actif critique de la filiale instruite ; le CM a posé le **processus ISO/IEC
> 27005:2022** et son vocabulaire (appréciation, évaluation, traitement, risque résiduel, registre). Ce
> TD 2 **outille la décision** : il cote les scénarios sur la matrice 4×4, pose la ligne d'acceptation, et
> choisit une option de traitement pour chacun. Rien ici n'est jetable : les quatre cotations de l'exercice 1
> se retrouvent dans le **registre de risques** saisi cet après-midi dans `translog-b` (TP 1) ; les décisions
> de l'exercice 3 — avec leurs porteurs et leurs échéances — deviennent les lignes du **plan de traitement**
> de **D7** (TP 2) ; la position tenue à l'exercice 2 devient la **sous-section 7** de la note de stratégie.
> C'est ici que l'appétence écrite en séance 5 cesse d'être une phrase et devient un arbitrage.

**Règle du jour** : les échelles de gravité **G1-G4** et de vraisemblance **V1-V4**, rédigées et justifiées
dans **D5** (séance 5), sont **reprises telles quelles**. Recoter avec une échelle neuve rendrait
incomparables les risques déjà traités, et c'est exactement ce qu'un auditeur ira vérifier. La matrice est
la `4x4 risk matrix from EBIOS-RM` de la bibliothèque `intuitem`, **en lecture seule** dans l'outil : nous ne
la choisissons pas, nous la lisons.
**Discipline d'atelier** : coter la **gravité avant** la vraisemblance, systématiquement, **sans regarder
l'autre axe**. Ce n'est pas une coquetterie — la gravité se juge sur l'atteinte à la mission, et savoir
qu'un scénario est probable pousse insensiblement à le trouver plus grave.
**Sigles** : **SIH** (système d'information hospitalier), **WMS** (*warehouse management system*, logiciel de
gestion d'entrepôt), **TMA** (tierce maintenance applicative), **SOC** (centre de supervision de la
sécurité), **MFA** (authentification multifacteur), **DLP** (*data loss prevention*, prévention de la fuite
de données), **HDS** (hébergeur de données de santé), **SR/OV** (source de risque / objectif visé),
**ER** (événement redouté), **IT/OT** (bureautique / industriel), **DP** (données personnelles),
**ComEx** (Comité Exécutif).
**Corrigé de l'énoncé replié** (« cliquer pour révéler »), non extractible — réponses bâties sur le corpus :
énoncé du TD 2 *« Matrices de cotation et options de traitement »*, CM de la séance 7 (processus ISO/IEC
27005:2022), TD 1 du matin, reference pack MERIDIAN (version 1, 31 août 2026), pack de filiale MERIDIAN
Logistique (version 1, 3 septembre 2026), D1 (gouvernance et RACI), D4 (constats gradés), D5 (échelles,
socle, seuil d'acceptation), D6 (écosystème coté, scénarios stratégiques).

---

## Rappel du cas

Le cours du matin a posé le processus et son vocabulaire. Il a laissé ouverte la question que la direction
posera dès que des risques lui seront présentés : **sur quoi le RSSI se fonde-t-il pour dire que celui-ci est
plus grave que celui-là, et pourquoi celui-ci mérite un budget quand celui-là attend ?**

Trois faits cadrent la réponse, et aucun n'est nouveau :

- **Les échelles existent déjà.** D5 les a rédigées et justifiées dans les termes du groupe, et la Direction
  Générale a été appelée à confirmer l'appétence dont elles dérivent. Le seuil d'acceptation y est posé sur
  les trois niveaux de la matrice, avec la mention explicite qu'il sera **« appliqué inchangé au registre
  complet en séance 7 »**. Ce rendez-vous, c'est aujourd'hui.
- **Les scénarios existent déjà.** La séance 6 a coté l'écosystème de `LOG-PA-01` (cinq parties prenantes,
  deux critiques : l'intégrateur des automates à 12,0 et APPLICA à 8,0), construit deux scénarios
  stratégiques (SS1 `Critical`, SS2 `Important`) et un scénario opérationnel (`High`).
- **Ce qui manque, c'est l'instrument commun.** Quand cinq personnes examinent le même scénario, elles
  produisent cinq jugements, et rien ne permet de les additionner. C'est un problème d'accord, pas de calcul.

Ce TD se joue à l'échelle du **groupe**, non de la seule filiale instruite : le RSSI Groupe prépare le comité
de sécurité, et les quatre scénarios qu'il doit y présenter viennent des quatre filiales. Celui de Logistique
(le scénario C) se retrouvera dans le registre de `translog-b` cet après-midi ; les trois autres restent au
portefeuille de groupe.

---

## Les deux notions à outiller avant de coter (cadrage, 15 min)

*Le CM les a nommées sans les outiller. Un quart d'heure suffit, à condition d'écrire aussi ce qu'elles ne
font pas.*

| Notion | Ce que c'est | Sa mécanique | Ce qu'elle ne fait **pas** |
|---|---|---|---|
| **La matrice de cotation** | Une grille à deux axes — la gravité d'un côté, la vraisemblance de l'autre — dont **chaque case porte un niveau de risque convenu à l'avance**. | Trois temps : on cote le scénario sur chaque axe **séparément**, on lit la case au croisement, et le niveau qui s'y trouve devient la position du risque dans le portefeuille. Son intérêt n'est pas la précision : c'est de **forcer la séparation de deux questions** que la discussion mélange toujours — *à quel point ce serait grave* et *à quel point c'est probable*. La plupart des désaccords en atelier viennent de deux personnes qui répondent à des questions différentes en croyant se contredire. | Elle **ne calcule rien** : elle applique une convention que quelqu'un a écrite, et deux organisations peuvent placer le même scénario à deux niveaux différents **sans qu'aucune ait tort**. Elle **ne remplace pas le jugement**, elle l'enregistre et le rend discutable. Et elle **ne dit jamais quoi faire** : elle dit où se situe le risque, la décision reste entière. |
| **La ligne d'acceptation** | La frontière, tracée sur la matrice, qui sépare les niveaux que l'organisation **accepte de porter** de ceux qu'elle **refuse**. | Mécanique simple, conséquences qui ne le sont pas : chaque risque au-dessus appelle une décision de traitement, chaque risque en dessous peut rester tel quel — et **déplacer la ligne d'une case déplace le budget de sécurité de l'année**. C'est la notion la plus politique de la journée. | Elle **n'appartient pas au RSSI**. Elle traduit l'appétence, et l'appétence est à la direction. Un RSSI qui fixe seul la ligne prend la place de la direction, et le jour de l'incident il portera seul une décision qu'il n'avait pas la légitimité de prendre. Son rôle : **préparer, éclairer, proposer, et obtenir une décision écrite.** |

**Pourquoi 4×4 et non 5×5.** L'outil propose les deux grilles, et le choix est déjà une décision de méthode.
Le nombre **pair** a une vertu que l'impair n'a pas : *il n'offre pas de milieu*. Sur une échelle à cinq
niveaux, un atelier indécis cote systématiquement au centre, et le portefeuille finit avec tous ses risques
au même endroit — ce qui ne hiérarchise plus rien. Le groupe travaille en **4×4**, cohérent avec les échelles
à quatre niveaux justifiées en séance 5. Ce choix est déjà acté dans D5 et n'est pas rouvert ici.

### Les trois manipulations à savoir reconnaître

*Elles seront tentées — l'exercice 2 en met une en scène. Les trois se repèrent en demandant une seule chose :
**montre-moi ce sur quoi tu t'appuies pour cette note.***

| # | Manipulation | Ce qu'elle produit | Où elle apparaît aujourd'hui |
|---|---|---|---|
| **1** | **La cotation qui justifie** — coter la vraisemblance à la baisse parce que le traitement coûterait cher | La conclusion précède l'analyse ; la cotation devient un exercice de justification | **Exercice 2** : la proposition du Directeur de la Logistique sur le scénario C |
| **2** | **Le risque fragmenté** — découper un gros risque en plusieurs petits, dont aucun ne franchit la ligne | Le risque n'a pas diminué, il a été **morcelé** | **Exercice 1**, évitée : le scénario C reste **un tout** (mise à jour piégée → six entrepôts), au lieu d'être éclaté en six risques par entrepôt qui tomberaient chacun en `Medium` |
| **3** | **Le résiduel anticipé** — coter le risque résiduel avant d'avoir décidé des mesures | On mesure l'effet d'un traitement qui n'existe pas encore | **Exercice 3**, évitée : le registre du TP 1 cote le risque **actuel** d'abord ; le résiduel ne se cote qu'après que chaque mesure a un porteur et une échéance (TP 2) |

---

## La matrice 4×4 et le seuil d'acceptation, relus dans l'instance

### Matrice de cotation — lecture de la cellule à l'intersection

| | **V1** `Unlikely` | **V2** `Likely` | **V3** `Very likely` | **V4** `Certain` |
|---|---|---|---|---|
| **G4** `Critical` | Medium | Medium | **High** | High |
| **G3** `Important` | Low | Medium | **High** | High |
| **G2** `Significant` | Low | Low | **Medium** | High |
| **G1** `Minor` | Low | Low | Medium | Medium |

*Grille **relevée sur la matrice importée dans `translog-b`** — capture
`../../Session-5/3-Evidence/S5-06-matrice-4x4-niveaux-de-risque.jpg` — et non reconstruite de mémoire. Deux
cellules sont contre-intuitives et méritent d'être lues deux fois : **G4 × V2 = `Medium`** (un scénario
critique mais seulement vraisemblable ne monte pas en `High`) et **G1 × V3 = `Medium`** (une conséquence
mineure mais très vraisemblable ne reste pas en `Low`). Aucune des quatre cotations ci-dessous ne tombe dans
ces deux cellules.*

### Seuil d'acceptation (D5, inchangé)

| Niveau de risque | Classe d'acceptation | Conséquence |
|---|---|---|
| **`Low`** | Acceptable en l'état | Porté sans mesure spécifique, revu à la cadence trimestrielle du ComEx. |
| **`Medium`** | Tolérable **uniquement** formalisé | Tolérance datée, surveillée, propriétaire nommé, mesure compensatoire ; **à défaut, traité comme `High`**. |
| **`High`** | Inacceptable en l'état | Décision de traitement avant mise en production ou avant de le porter plus longtemps ; activité suspendue si le traitement n'est pas engagé. |

**Coïncidence vérifiée à l'écran** : le texte des trois niveaux de la matrice importée dit déjà, mot pour
mot, *« Acceptable as is » / « Tolerable under control… » / « Unacceptable… »*. Le seuil dérivé de
l'appétence **ne réécrit rien** — il nomme la même ligne dans le vocabulaire du groupe. C'est précisément ce
qui permettra de répondre à l'exercice 2 sans improviser.

---

## Exercice 1 — Coter quatre scénarios du groupe (15 minutes)

### Mise en situation

Le RSSI Groupe prépare le comité de sécurité du groupe. Quatre scénarios issus des ateliers doivent y être
présentés **déjà cotés**, et la Directrice Générale a prévenu qu'elle ne veut pas d'un tableau de couleurs,
mais **d'une phrase de justification par note**. Chaque note renvoie à un **niveau nommé de l'échelle** et à
un **signal** : un écart constaté à l'audit, une pratique observée, un incident public comparable. *Le mot
« important » sans référence à l'échelle ne vaut rien.*

| # | Scénario de risque | Filiale | Ce que les ateliers ont établi |
|---|---|---|---|
| **A** | Un attaquant à but lucratif atteint la disponibilité des données de soins en passant par l'identifiant partagé de télémaintenance de l'éditeur du SIH | Santé | Compte à privilèges partagé, sans traçabilité individuelle ; la filiale porte des activités de soins |
| **B** | Un attaquant compromet le poste d'un administrateur du pôle Éducation & Territoires et accède aux données administratives de Territoires | Pôle Édu-Terr | Annuaire d'identités commun au pôle, comptes d'administration partagés entre les deux équipes, données personnelles d'usagers ; le projet de connexion aux bases de Territoires est **refusé, non déployé** |
| **C** | Une mise à jour piégée appliquée par la TMA du WMS fait entrer un code malveillant chez Logistique | Logistique | Rapproché du modèle NotPetya par la mise à jour d'un tiers ; la TMA applique les siennes la nuit, sans validation ; chaîne d'approvisionnement logicielle |
| **D** | Un agent interne exfiltre par erreur un fichier de données personnelles vers un service en ligne non validé | Groupe | Pas de politique d'usage des services externes ; volumétrie limitée, une filiale |

---

### Scénario A — Attaque du SIH par l'identifiant partagé de l'éditeur en télémaintenance

**Gravité : G4 `Critical`.** L'éditeur du SIH détient un accès permanent de télémaintenance via *« un
identifiant unique partagé entre neuf de ses collaborateurs »* (reference pack §3, Santé). Une compromission
de cet identifiant donne un accès privilégié direct aux dossiers patients, aux machines d'analyse et aux
consoles d'imagerie — lesquelles sont **sur le même plan IP que les postes d'accueil**, avec un compte
d'administration partagé (constat 1 de Santé). La mission de soin est remise en cause dans la durée, et
l'échelle de D5 est explicite sur le critère qui décide : *« conséquence vitale ou sanitaire pour un patient
ou un usager »*. Un chiffrement délibéré par cet accès toucherait les **quatre établissements**.
*Signal de calibrage* : une panne **non provoquée** de 4 h 10 en mars a déjà produit **22 actes annulés et
deux plaintes de patients** (constat 6 de Santé) — et son impact n'a jamais été quantifié.

**Vraisemblance : V3 `Very likely`.** Une faiblesse **connue et actuelle** rend le scénario réalisable avec
les moyens courants d'un attaquant à but lucratif — c'est la définition même de V3 dans D5. L'identifiant est
permanent et partagé, les applications métier tournent sur **mots de passe locaux sans MFA** (constat 2 de
Santé), et la filiale **n'a jamais remis son registre des comptes d'administration malgré trois demandes de
l'Audit Interne** (constat 4) : personne au groupe ne sait donc ce que cet accès ouvre exactement.
L'hébergeur **n'affiche aucune certification HDS**, le contrat se bornant à *« conforme aux exigences
applicables »* (§3). Le secteur santé reste une cible régulière — Centre Hospitalier Sud Francilien, 2022,
LockBit (contexte de menace de D5). Le scénario ne bute sur **aucune barrière déployée**.
*Pourquoi pas V4* : le scénario ne s'est pas réalisé dans le périmètre et sa réalisation dépend encore d'un
attaquant.

> **G4 × V3 = `High`** — inacceptable en l'état.

---

### Scénario B — Compromission d'un poste d'administrateur du pôle, accès aux données de Territoires

**Gravité : G3 `Important`.** Les bases administratives de Territoires portent les **données citoyennes
réglementées d'une trentaine de collectivités clientes** (reference pack §3). Leur exposition est un
manquement contractuel caractérisé : le délai de **notification de 24 heures** à la collectivité est
contractuel, et **aucune procédure de notification n'existe** (constat 4 de Territoires) — le délai serait
donc rompu par construction. C'est mot pour mot le critère G3 de D5 : *« un engagement contractuel rompu et
payé (délai de notification manqué) »*, et *« données personnelles exposées à un tiers non autorisé »*.
*Pourquoi pas G4* : le projet de connexion de la plateforme d'Éducation aux bases de Territoires est
**refusé et non déployé** (reference pack §5, dépendance 3 ; constat 5 de Territoires). Depuis un poste
Éducation compromis, ce qui est directement atteint est **l'annuaire partagé**, pas les bases métier de
Territoires.

**Vraisemblance : V3 `Very likely`.** Les comptes d'administration sont **partagés entre les équipes des deux
filiales**, conséquence directe de la DSI mutualisée, et *« personne ne peut dire qui a fait quoi »*
(constat 1 d'Éducation) ; le reference pack §5 le dit sans détour pour l'annuaire commun : *« une
compromission d'un côté se propage à l'autre »*. Côté détection, **le SOC du groupe ne reçoit rien du
pôle** — les journaux restent locaux, *« aucune détection, aucune analyse post-incident »* (constat 1 de
Territoires ; couverture SOC : deux filiales sur quatre, §2). Faiblesses **connues et actuelles**, au sens
de V3.
*Précision de sourçage* : nous n'invoquons **pas** l'absence de MFA pour ce scénario. Le constat 2 qui la
documente est propre à **Santé** ; le pack ne dit rien de l'authentification du pôle Éducation & Territoires,
et l'étendre serait une extrapolation — exactement ce que la discipline de cotation interdit.

> **G3 × V3 = `High`** — inacceptable en l'état.

---

### Scénario C — Mise à jour piégée du WMS appliquée par la TMA

**Gravité : G4 `Critical`.** Le WMS pilote la préparation, l'expédition et le stock des **six entrepôts**. Il
*« tourne sur deux serveurs à E1 plus une base ; les cinq autres entrepôts s'y connectent par les liaisons
opérateur »* (pack §4) : une mise à jour piégée déployée à E1 se propage à tout le périmètre. Les réseaux IT
et OT étant **interconnectés sans segmentation** (constat 1 du pack, **C3 de D4**, non-conformité *majeure*
sur `A.8.22`), le code atteindrait aussi les automates de tri. Conséquences chiffrées : arrêt > 6 h = **40 %
du volume expédié du groupe** bloqué (constat 5), **12 000 €/jour** de pénalités pharmaceutiques (§2), et le
flux d'approvisionnement d'urgence vers Santé — déjà coupé depuis trois mois — durablement compromis. C'est
le critère G4 de D5 : *« la capacité du groupe à tenir une de ses missions est remise en cause dans la
durée »*.
*Signal* : le mécanisme est celui de NotPetya chez Mærsk (T3 2017, **250-300 M$** sur les activités
*Transport & Logistics*), référence documentée du TD 1 de ce matin.

**Vraisemblance : V3 `Very likely`.** La TMA *« fait les mises à jour la nuit, quand elle veut, on s'en rend
compte le matin »* (pack §4, entretien du Responsable Exploitation) : **aucune validation préalable**, aucune
recette. Elle intervient avec un **compte de domaine partagé dont personne ne peut établir le nombre
d'utilisateurs** (constat 2 du pack, **C4 de D4**, non-conformité *majeure*) — le Responsable Informatique de
la filiale le reconnaît lui-même (§3). La chaîne d'approvisionnement logicielle est un mode opératoire
courant et documenté (TD 1 de la séance 6 : NotPetya, SolarWinds). Faiblesse **connue et actuelle**, aucune
barrière ne filtre la mise à jour avant déploiement.
*Pourquoi pas V4* : l'arrêt WMS d'avril relève d'une cause jamais identifiée, pas d'un chiffrement délibéré ;
le scénario **ne s'est pas encore réalisé** dans le périmètre.

> **G4 × V3 = `High`** — inacceptable en l'état.

---

### Scénario D — Exfiltration accidentelle de données personnelles vers un service non approuvé

**Gravité : G2 `Significant`.** Volumétrie limitée, une seule filiale, pas de donnée de santé nominative.
L'échelle de D5 place là *« au plus une donnée personnelle non sensible exposée à un cercle restreint »* : le
fichier part vers un service tiers, il n'est pas diffusé publiquement, et la reprise est possible en quelques
jours (contact avec le service, suppression, notification si nécessaire).
*Pourquoi pas G3* : pas de rupture d'engagement contractuel chiffré, pas de retard de soins, pas de donnée de
mineur établie dans le scénario tel qu'il est énoncé.

**Vraisemblance : V3 `Very likely`.** **Aucune politique d'usage des services en ligne externes n'existe dans
le groupe.** Le fait est documenté et daté : l'inventaire du pôle Éducation & Territoires a mis au jour
**onze abonnements** souscrits directement par les équipes enseignantes, hors DSI, *« dont un outil d'IA
générative auquel des enseignants soumettent des évaluations d'élèves pour relecture »*, et **aucun ne porte
de contrat ni d'analyse d'impact** (reference pack §6). Le même paragraphe étend le raisonnement au groupe
entier : *« rien ne dit que les trois autres filiales en sont exemptes ; elles n'ont simplement pas
cherché »*. L'absence de règle **et** de contrôle rend le scénario réalisable avec les moyens courants de
n'importe quel collaborateur.
*Pourquoi pas V4* : ce qui est **observé**, ce sont des usages non encadrés — pas une exfiltration avérée de
fichier de données personnelles. `Certain` exigerait que le scénario se soit déjà réalisé dans le périmètre,
ou que sa réalisation ne dépende plus de personne.

> **G2 × V3 = `Medium`** — tolérable **sous contrôle**, et seulement formalisé.

---

### Le scénario le plus débattu — **B**, et ce qui ferait changer la note

**L'hésitation porte sur la gravité, G3 ou G4 — pas sur la vraisemblance.**

**L'argument pour G4** : Territoires opère une **délégation de service public** pour une trentaine de
collectivités, sur des données citoyennes réglementées. Une fuite massive pourrait entraîner la perte de
plusieurs délégations — et G4 vise exactement *« la perte d'un contrat ou d'une délégation »*, jusqu'à
*« l'existence d'une filiale menacée »*.

**L'argument pour G3, retenu** : le chemin décrit part d'un **poste d'administrateur du pôle**, et ce qu'il
atteint directement est l'**annuaire commun**, non les bases administratives. Le projet qui relierait les
deux est **refusé et non déployé** (§5, dépendance 3). La gravité se cote sur ce que le scénario atteint
aujourd'hui, pas sur ce qu'il atteindrait dans une architecture qui n'existe pas.

> **Ce qui ferait changer la note** : si le projet de plateforme d'apprentissage Éducation → Territoires
> était déployé, **même partiellement**, l'accès aux bases administratives deviendrait direct depuis un poste
> Éducation compromis, et la gravité passerait à **G4** — le niveau du risque ne bougerait pas (`High` dans
> les deux cas), mais sa **place dans le portefeuille**, oui. C'est la raison pour laquelle le responsable
> informatique de Territoires s'y oppose (constat 5), et la raison pour laquelle **cette décision
> d'architecture relève du Comité Exécutif et non de la DSI du pôle** — d'autant que le directeur
> informatique du pôle *« parle pour les deux filiales sans aucun mandat écrit »* (reference pack §2).

---

## Exercice 2 — La ligne d'acceptation, et qui la trace (10 minutes)

### Mise en situation

Le RSSI Groupe présente sa matrice au comité. **Le Directeur de la Logistique propose de placer la ligne
d'acceptation de sorte que le scénario C tombe juste en dessous** : *« ce sont des mises à jour de notre
prestataire de maintenance historique, on ne va pas bloquer la production pour ça »*. La Directrice Générale
demande l'avis du RSSI **avant de trancher**.

> *La position est cohérente avec ce que le pack lui prête : « 12 000 € par jour est le seul chiffre que je
> regarde », et aucune intervention sur les automates en période de pointe, « soit dix mois sur douze »
> (§3). Ce n'est pas de la mauvaise volonté : c'est un directeur qui optimise ce dont il répond.*

### Position de la ligne, et sur quelle base

**La ligne ne se trace pas aujourd'hui — elle a été tracée en séance 5, et elle tient.** D5 §1 l'a posée sur
les trois niveaux de la matrice, dérivée de l'appétence que la Direction Générale a été appelée à confirmer :
`Low` acceptable en l'état · `Medium` tolérable **uniquement formalisé** · `High` inacceptable en l'état. Sur
la grille, elle sépare les cellules `Medium` des cellules `High`.

**Base, et non intuition.** Cette ligne s'adosse aux **classes d'acceptation du guide** rappelées ce matin —
*acceptable en l'état / tolérable sous contrôle / inacceptable* — dont le texte est déjà, mot pour mot, celui
des trois niveaux de la matrice importée. Elle ne doit rien à la cotation d'aujourd'hui, et c'est sa
propriété la plus importante : **l'appétence se fixe avant de connaître les résultats.** La déplacer
maintenant pour qu'un scénario passe en dessous, c'est la **manipulation n° 1** du cadrage — la conclusion
qui précède l'analyse — et c'est décider du traitement avant d'avoir examiné le risque.

### Réponse au comité — trois phrases

**1 · Ce que la ligne proposée par la Logistique impliquerait concrètement.** Placer la ligne de sorte que le
scénario C (G4 `Critical` × V3 `Very likely` = `High`) tombe en dessous, c'est accepter comme tolérable *sans
traitement* un scénario de type NotPetya sur notre WMS — le mécanisme qui a coûté 250 à 300 millions de
dollars à Mærsk — alors que notre prestataire déploie ses mises à jour la nuit sans validation, avec un
compte partagé dont personne ne connaît les porteurs ; et comme une ligne est une ligne, la déplacer assez
haut pour exclure C **exclut du même geste le scénario A** (même cellule G4 × V3), ce qui reviendrait à
accepter en silence un risque portant sur la mission de soin.

**2 · Ce que le RSSI Groupe recommande.** Maintenir la ligne telle que l'appétence de la séance 5 l'a posée —
`High` inacceptable en l'état — et traiter le scénario C par les mesures que l'étude a identifiées :
validation des mises à jour avant déploiement, comptes nommés pour la TMA, journaux du WMS au SOC ; **ces
mesures n'arrêtent pas la production, elles l'encadrent**, et la recette préalable est précisément ce qui
évite l'arrêt non planifié que le Directeur de la Logistique redoute.

**3 · Ce que le RSSI Groupe demande par écrit.** Que le Comité Exécutif **confirme par écrit** le seuil posé
en séance 5 ; ou, s'il choisit de le modifier, qu'il **signe la nouvelle ligne et nomme les risques qu'elle
fait basculer dans la zone acceptable** — nommément A et C — parce qu'un seuil que personne n'a signé est un
seuil que personne ne porte le jour de l'incident.

### Qui signe cette décision chez MERIDIAN, et pourquoi ce n'est pas le RSSI Groupe

**La Direction Générale du groupe**, représentée par la Directrice Générale, sur proposition du Comité
Exécutif et après instruction du RSSI Groupe. C'est la répartition arrêtée en séance 1 et inscrite à la
matrice RACI de **D1** : la Direction Générale **fixe** l'appétence, le Conseil d'Administration l'**approuve**,
le RSSI Groupe la **propose sans la fixer** — D5 §1 le redit pour l'acceptation du risque résiduel, qui en
est « la face opérationnelle ». La règle d'arbitrage **`ARB-01`** donne de surcroît au RSSI Groupe un **veto
suspensif sur toute décision de filiale engageant la sécurité du groupe, arbitrage rendu sous 72 heures** :
c'est précisément l'instrument prévu pour la situation de ce comité — il **suspend sans enterrer**, et fait
remonter la décision là où elle se signe au lieu de la laisser se prendre en séance.

**Pourquoi pas le RSSI Groupe.** L'appétence au risque ne lui appartient pas. Un RSSI qui trace seul la ligne
se substitue à la direction et, le jour de l'incident, porte seul une décision qu'il n'avait pas qualité pour
prendre. **Pourquoi pas le Directeur de la Logistique non plus** : le scénario C engage 40 % du volume
expédié **du groupe** et le réapprovisionnement d'urgence de Santé — un directeur de filiale ne peut pas
accepter un risque qui déborde sa filiale.

> **Les deux erreurs symétriques**, et nous n'en commettons ni l'une ni l'autre : **céder en silence**, ce qui
> fabrique une acceptation que personne n'a signée ; **trancher à la place de la direction**, ce qui met le
> RSSI en position intenable.

---

## Exercice 3 — Choisir et défendre une option de traitement (20 minutes)

### Mise en situation

Les quatre scénarios sont cotés et la ligne est arrêtée. Pour chaque risque au-dessus d'elle, il faut **une
décision, un porteur et une échéance**. Le Directeur Financier assistera à la séance et posera la même
question à chaque ligne : **combien, et pourquoi maintenant ?**

*Contrainte de l'énoncé : au moins une des quatre options n'est pas « réduire », faute de quoi les autres
familles n'ont pas été examinées. **Ici, deux ne le sont pas** — un transfert partiel sur A, une acceptation
formelle sur D. Les porteurs sont pris dans la carte du pouvoir (pack §3 pour Logistique, reference pack §2
et §3 pour les autres filiales) : **une mesure sans porteur est un souhait.** Chaque décision est écrite pour
être lue par un tiers dans deux ans, sans son auteur dans la pièce — le test étant : la phrase dit-elle qui a
décidé, quoi, pourquoi et jusqu'à quand ?*

---

### Scénario A — SIH de Santé (G4 × V3, `High`) · **Réduire + Transférer**

**Réduire** — supprimer le vecteur principal et rétablir la détection.

| Mesure | Porteur | Échéance | Ce qu'elle traite |
|---|---|---|---|
| Remplacer l'identifiant partagé de télémaintenance du SIH par des **comptes nommés, avec MFA et journalisation individuelle** ; clause portée à l'avenant du contrat éditeur | **DSI de MERIDIAN Santé** (porte la relation éditeur), avec la **Direction de la filiale** pour l'avenant contractuel | **6 mois** (négociation + déploiement) | Constat 1 et §3 de Santé (identifiant unique partagé entre neuf personnes) ; rétablit l'imputabilité, et un identifiant volé seul ne suffit plus |
| **Segmenter** le plan IP : isoler machines d'analyse et consoles d'imagerie du réseau bureautique | **DSI de MERIDIAN Santé** | **9 mois** (étude d'architecture + déploiement par établissement) | Constat 1 de Santé (équipements joignables depuis n'importe quel poste d'accueil) ; limite la propagation latérale |
| Intégrer les **journaux du SIH au SOC du groupe** | **RSSI Groupe** (le SOC est un actif de groupe) | **3 mois** | Le SOC **reçoit déjà les journaux de Santé** (reference pack §2) : il s'agit d'y ajouter ceux du SIH, pas d'ouvrir un chantier. Rétablit la détection sur le vecteur de télémaintenance |
| Obtenir et tenir à jour le **registre des comptes d'administration** de la filiale | **DSI de MERIDIAN Santé**, sur demande de l'**Audit Interne** | **1 mois** | Constat 4 (jamais remis malgré trois demandes) ; sans lui, on ne sait pas ce que l'accès ouvre |

**Transférer** — souscrire une **assurance cyber**, en complément et **non en remplacement** de la réduction.

| Ce que l'assurance couvrirait réellement | Ce qu'elle ne couvrirait pas |
|---|---|
| Les frais de **gestion de crise et d'investigation** — forensique, notification, communication | La **mission de soin elle-même** : un patient non soigné à temps n'est pas un sinistre financier, c'est une responsabilité médicale |
| La **perte d'exploitation** pendant l'interruption, **dans la limite d'un plafond et d'une franchise** — à négocier sur la base du précédent de mars (22 actes annulés en 4 h 10) | La **cause** : l'assurance indemnise les conséquences ; le compte partagé reste un risque après indemnisation |
| Les **frais juridiques**, et les amendes selon la police et la juridiction — **les amendes CNIL ne sont pas toujours assurables en droit français** | La **confiance** : la relation aux patients, aux tutelles et aux partenaires hospitaliers ne se reconstruit pas avec une indemnité |
| — | Le risque d'**exclusion ou de résiliation** : un assureur qui découvre que l'identifiant partagé était connu et non corrigé peut invoquer un manquement de l'assuré à ses obligations de sécurité |

> **Conclusion sur l'assurance** : elle couvre les **pertes financières résiduelles**, *après* déploiement des
> mesures de réduction — jamais à leur place. Souscrire sans corriger l'identifiant partagé, c'est assurer un
> bâtiment dont on sait que la porte est ouverte, et c'est aussi le meilleur moyen de se voir refuser la
> garantie le jour du sinistre.

**Pourquoi maintenant** (réponse au Directeur Financier) : neuf personnes extérieures partagent un accès
permanent et non tracé à des dossiers patients, et nous ne savons même pas dire ce que cet accès ouvre — la
filiale n'a jamais remis son registre. La troisième mesure coûte trois mois de raccordement d'un SOC que nous
payons déjà.

---

### Scénario B — Pôle Éducation & Territoires (G3 × V3, `High`) · **Réduire**

| Mesure | Porteur | Échéance | Ce qu'elle traite |
|---|---|---|---|
| **Séparer les comptes d'administration** entre Éducation et Territoires : comptes propres par équipe, droits limités au périmètre de sa filiale | **DSI du pôle Éducation & Territoires**, **sous arbitrage du Comité Exécutif** — la DSI mutualisée est à la fois le problème et la solution, et son directeur « parle pour les deux filiales sans aucun mandat écrit » (reference pack §2) ; à défaut d'auto-correction, le **veto suspensif `ARB-01`** de D1 fait remonter la décision sous 72 h | **4 mois** (migration des comptes, révision des groupes d'annuaire, tests) | Constat 1 d'Éducation (« personne ne peut dire qui a fait quoi ») et §5 (« une compromission d'un côté se propage à l'autre ») ; **coupe le chemin de propagation** |
| Intégrer les **journaux du pôle au SOC du groupe** | **RSSI Groupe**, avec la DSI du pôle | **6 mois** — le SOC **ne reçoit rien** du pôle aujourd'hui : il faut connecter, calibrer les alertes, former les analystes | Constat 1 de Territoires (journaux locaux, aucune détection, aucune analyse post-incident) ; **prérequis du délai contractuel de notification de 24 h** |
| **Écrire la procédure de notification** aux collectivités, avec seuils, circuit et modèle de courrier | **Direction de MERIDIAN Territoires**, appui juridique du holding | **2 mois** | Constat 4 de Territoires : le délai de 24 h est contractuel et **aucune procédure n'existe** — la mesure la moins chère du plan |

**Pourquoi maintenant** (réponse au Directeur Financier) : le pôle porte **45 000 comptes**, dont des données
de mineurs côté Éducation, et les données citoyennes réglementées d'**une trentaine de collectivités** côté
Territoires. Chaque jour sans séparation des comptes est un jour où une compromission côté Éducation ouvre un
accès d'administration côté Territoires **sans qu'aucune alerte ne soit produite** — et le délai contractuel
de 24 h ne peut pas être tenu quand on ne détecte rien et qu'aucune procédure n'existe. Il faut noter que la
filiale Éducation *« fonctionne sur des ressources tendues, son enveloppe de sécurité est la plus faible du
groupe et aucun recrutement n'est prévu »* (constat 2 d'Éducation) : la séparation des comptes se fera **avec
les moyens actuels ou pas du tout**, ce qui est un argument pour l'arbitrage du ComEx, pas contre la mesure.

---

### Scénario C — Mise à jour piégée du WMS (G4 × V3, `High`) · **Réduire**

*Attention au porteur : la carte du pouvoir (pack §3) est nette — le **Responsable Informatique** de la
filiale (trois personnes, sans titre de RSSI) décide du réseau bureautique, des postes, des comptes de
domaine et de la relation à la TMA, mais **pas des contrats** ; le **Directeur de la filiale** décide budget
et contrats ; le **Responsable Exploitation** décide du réseau industriel des automates. Toute mesure qui
touche l'avenant contractuel ou l'OT a donc **deux porteurs et un arbitre**.*

| Mesure | Porteur | Échéance | Ce qu'elle traite |
|---|---|---|---|
| **Validation préalable des mises à jour** : tout correctif du WMS est déployé d'abord en environnement de recette et validé par la filiale ; clause portée à l'**avenant du contrat `TMA-WMS-2021`** | **Directeur de la filiale Logistique** (signe l'avenant, §3) · **DSI de la filiale** (tient la recette) | **3 mois** (négociation de l'avenant + montage de la recette) | Coupe le vecteur principal : la TMA ne déploie plus « quand elle veut » la nuit (pack §4). C'est aussi la mesure qui **répond à l'objection** du Directeur de la Logistique : la recette protège la production au lieu de l'arrêter |
| **Comptes nommés pour le personnel de la TMA**, avec MFA et journalisation, en remplacement du compte de domaine partagé | **DSI de la filiale Logistique** (les comptes de domaine sont de son ressort, §3) · avenant porté par le **Directeur de la filiale** | **4 mois** | Constat 2 du pack / **C4 de D4** (porteurs inconnus) ; rétablit l'imputabilité et permet au SOC de distinguer une action légitime d'une action malveillante |
| **Segmentation IT/OT** sur les six sites | **DSI de la filiale** (réseau bureautique) **et Responsable Exploitation** (réseau industriel) · la fenêtre d'intervention remonte au **Comité Exécutif**, au besoin par le **veto suspensif `ARB-01`** (72 h) | **9 mois** (conception, matériel, déploiement par site, tests de non-régression sur les automates) | Constat 1 du pack / **C3 de D4** (IT et OT interconnectés, non-conformité majeure) ; un code malveillant dans le WMS n'atteint plus directement les automates. **Point de friction à arbitrer** : le Directeur de la filiale refuse toute intervention sur les automates en période de pointe, « dix mois sur douze » (§3) — la fenêtre doit être décidée, pas négociée site par site |
| **Test de restauration des sauvegardes** du WMS en environnement isolé, **avec mesure du RTO réel** | **DSI de la filiale Logistique**, avec la TMA (le WMS relève du prestataire, §3) | **2 mois** pour le premier test, puis **annuel** | Constat 4 du pack (sauvegardes quotidiennes **jamais restaurées** depuis la mise en service) ; transforme la **durée haute** de la fourchette du TD 1 d'un *inconnu* en un *mesuré* — c'est la seule mesure du plan qui produise un chiffre pour le Directeur Financier |

**Pourquoi maintenant** (réponse au Directeur Financier) : le prestataire applique ses mises à jour la nuit
sans prévenir ; si l'une d'elles est piégée — mécanisme NotPetya, 2017 — les six entrepôts s'arrêtent, les
pénalités courent à 12 000 €/jour, et **nous sommes incapables de dire en combien de temps le WMS serait
restauré, parce que nous n'avons jamais testé la restauration**. La première mesure coûte un environnement de
recette et une clause contractuelle.

---

### Scénario D — Exfiltration accidentelle de DP (G2 × V3, `Medium`) · **Accepter formellement**

Le scénario est au niveau `Medium` : **tolérable sous contrôle**, et seulement si les quatre conditions de la
tolérance formelle de D5 sont réunies — tolérance **datée**, **surveillée**, **propriétaire nommé**, **mesure
compensatoire**. À défaut, D5 impose de le traiter comme `High`. La fiche ci-dessous les réunit.

#### Décision d'acceptation, en bonne et due forme

| Élément | Contenu |
|---|---|
| **Le risque tel qu'il est coté** | Un collaborateur exfiltre par erreur un fichier de données personnelles de volumétrie limitée vers un service en ligne non approuvé, faute de politique d'usage des services externes. **G2 `Significant` × V3 `Very likely` = `Medium`.** Impact borné à une filiale, sans donnée de santé nominative, sans rupture de la mission de soin ni de la continuité d'expédition. |
| **La raison de l'accepter** | Le traitement technique (DLP, filtrage des services externes) a un coût disproportionné au regard d'un impact borné à `G2`, dans un groupe où la Direction Générale attend une gouvernance **« sans budget nouveau la première année »** (reference pack §7) et où **trois scénarios `High`** mobilisent déjà les ressources. Arbitrage explicite entre quatre risques, pas confort. |
| **L'instance qui accepte** | **Direction Générale du groupe**, sur proposition du RSSI Groupe et après avis du Comité Exécutif — le niveau **où l'appétence a été fixée** (D1, D5 §1). *Jamais « risque accepté par le RSSI ».* |
| **La date** | Date de la séance du Comité Exécutif qui l'entérine ; portée au registre de `translog-b` et au plan de traitement de D7. |
| **L'échéance de réexamen** | **12 mois**, ou **plus tôt** si un incident d'exfiltration de données personnelles est signalé dans le groupe, ou si la volumétrie ou la nature des données en jeu change (donnée de mineur, donnée de santé). |
| **La mesure compensatoire** | Rédaction et diffusion d'une **politique d'usage des services en ligne externes** — *encadrement, pas interdiction* — avec un volet spécifique sur les données personnelles et les données de mineurs. **Propriétaire : RSSI Groupe. Échéance : 6 mois.** Elle ne supprime pas le risque (elle ne crée aucun contrôle technique) mais elle **établit la règle dont l'absence est aujourd'hui la faiblesse documentée** : onze abonnements hors DSI, dont un outil d'IA générative recevant des évaluations d'élèves, aucun contrat, aucune analyse d'impact (§6). |
| **La surveillance** | Revue trimestrielle au ComEx, avec un indicateur simple : nombre d'abonnements hors DSI découverts par filiale. Le §6 avertit que les trois autres filiales « n'ont simplement pas cherché » — l'indicateur sert d'abord à les faire chercher. |

**Au réexamen** : si la politique est en place et qu'un contrôle technique a été déployé, le risque se
recote. S'il est toujours `Medium` **sans** tolérance formalisée à jour, D5 impose de le traiter comme `High`.

---

## Synthèse du portefeuille de risques du groupe

| # | Scénario | Gravité | Vraisemblance | Niveau | Décision | Porteur principal |
|---|---|---|---|---|---|---|
| **A** | SIH Santé — identifiant partagé de l'éditeur | **G4** | **V3** | **`High`** | **Réduire + Transférer** | DSI de Santé · RSSI Groupe |
| **B** | Pôle Édu-Terr — comptes d'administration partagés | **G3** | **V3** | **`High`** | **Réduire** | DSI du pôle (arbitrage ComEx) · RSSI Groupe |
| **C** | WMS Logistique — mise à jour piégée de la TMA | **G4** | **V3** | **`High`** | **Réduire** | Directeur de la filiale · DSI de la filiale · Responsable Exploitation |
| **D** | Groupe — exfiltration accidentelle de DP | **G2** | **V3** | **`Medium`** | **Accepter** (formellement) | Direction Générale · RSSI Groupe (mesure compensatoire) |

**Trois `High` et un `Medium`, tous à V3** — et ce n'est pas un artefact de paresse : les quatre reposent sur
des faiblesses que le diagnostic a **constatées**, pas supposées, ce qui est exactement la définition de V3
dans D5. Le portefeuille ne hiérarchise donc pas par la vraisemblance ; il hiérarchise **par la gravité et
par ce que chaque mesure coûte**, et c'est le plan de traitement de cet après-midi qui tranchera l'ordre.

**Ce que l'exercice a produit et qu'aucune couleur ne dit** : deux décisions qui ne sont pas « réduire », un
risque accepté **par la bonne instance**, et une ligne d'acceptation qui a résisté à une demande de la
direction d'une filiale — sans que le RSSI se substitue à la direction pour autant.

---

## Ce qui entre dans la suite de la journée

| Destination | Ce qui vient d'ici |
|---|---|
| **TP 1** — atelier 4 et registre dans `translog-b` | Les **cotations des quatre scénarios**, dont le scénario **C** qui est celui de la filiale instruite : sa gravité G4 et sa vraisemblance V3 sont à **vérifier contre l'affichage de l'outil** (l'énoncé du TP le demande explicitement pour le scénario déjà coté au TD). Le **seuil d'acceptation** s'applique inchangé au registre complet, **y compris aux événements redoutés sans scénario** que l'outil ajoutera — chez nous **ER3** (chaîne du froid) et **ER5** (réapprovisionnement de Santé), signalés dans D5 comme restés sans source de risque retenue. Les **options de traitement** de l'exercice 3 se saisissent comme statuts, et **les porteurs pris dans la carte du pouvoir §3** sont déjà nommés, avec la distinction contrat / réseau bureautique / réseau industriel qui évite de confier un avenant à quelqu'un qui ne signe pas les contrats. |
| **TP 2 — livrable D7** (5 pts) | Les quatre décisions deviennent les lignes du **plan de traitement**, organisé **par décision et non par scénario**, avec l'effet attendu sur la cotation qui justifiera le résiduel. La fiche d'acceptation du scénario **D** est déjà écrite aux **cinq éléments** exigés (risque coté, raison, instance, date, réexamen) et porte en plus sa mesure compensatoire. Les **mesures transversales sont identifiées et se regrouperont** : l'intégration au SOC sert A **et** B ; les comptes nommés avec MFA servent A **et** C. Le **test de restauration du WMS** est nommé comme la mesure qui transformera la borne haute de la fourchette du TD 1 en chiffre — c'est le raccord direct entre le coût de l'inaction du matin et le total budgétaire du plan. |
| **Sous-section 7 de la note de stratégie** | La position du groupe sur l'**acceptabilité du risque** : la ligne d'acceptation est celle de la séance 5, **elle n'a pas bougé** — et l'épisode de l'exercice 2 est ce qui le prouve, puisqu'on a refusé de la déplacer sous la pression d'une direction de filiale. Les **décisions structurantes** : trois réductions engagées, un transfert assurantiel **encadré** (complément, jamais substitut), une acceptation formelle signée au niveau où l'appétence est fixée. Ce qui **reste ouvert** : la fenêtre d'intervention sur les automates — que le Directeur de la filiale refuse « dix mois sur douze », et qui remontera au ComEx, au besoin par le veto suspensif `ARB-01` — et la décision d'architecture sur le projet Éducation → Territoires, dont le déploiement ferait passer le scénario B en G4. Une demi-page, sans recopier D7. |

---

## Auto-évaluation (grille du TD)

| Critère | Niveau atteint |
|---|---|
| **Ex. 1 — les quatre cotations** | Gravité cotée **avant** la vraisemblance et sans regarder l'autre axe ; chaque note renvoie à un **niveau nommé de l'échelle de D5, cité verbatim**, et à un **signal vérifiable** — constat numéroté du reference pack, pratique observée dans le pack de filiale, écart gradé de D4, ou incident public (Mærsk/NotPetya, CHSF/LockBit). Chaque vraisemblance porte en plus son **« pourquoi pas le niveau au-dessus »**. Une extrapolation a été **écartée explicitement** (l'absence de MFA, documentée pour Santé seulement, n'est pas invoquée pour le pôle). Échelles reprises telles quelles, aucune redéfinition. |
| **Ex. 1 — le scénario le plus débattu** | **B** traité en deux temps : l'argument G4 et l'argument G3 exposés l'un contre l'autre, l'arbitrage rendu **sur ce que le scénario atteint aujourd'hui** et non sur une architecture non déployée ; **ce qui ferait changer la note** est nommé (déploiement même partiel du projet Éducation → Territoires), avec sa conséquence sur la place au portefeuille et sur l'instance légitime à décider. |
| **Ex. 2 — la ligne et sa base** | La ligne n'est **pas retracée** : elle est celle de D5 §1, adossée aux **classes d'acceptation du guide** dont le texte coïncide mot pour mot avec les trois niveaux de la matrice importée — vérifié à l'écran, pas supposé. La demande de la Logistique est nommée comme la **manipulation n° 1** du cadrage. Les **trois phrases** au comité sont distinctes et font ce qu'elles doivent : la première chiffre l'implication **et** montre l'effet de bord sur le scénario A, la deuxième recommande en désamorçant l'objection (« encadrer, pas bloquer »), la troisième demande un **écrit** et nomme les risques que le ComEx signerait. |
| **Ex. 2 — l'instance signataire** | **Direction Générale du groupe**, sur proposition du ComEx, avec renvoi à la RACI de **D1** et au point d'arbitrage `ARB-01` ; **deux** exclusions argumentées, pas une — ni le RSSI Groupe (l'appétence ne lui appartient pas), ni le Directeur de la Logistique (le risque déborde sa filiale). Les deux erreurs symétriques de l'énoncé — céder en silence, trancher à la place — sont nommées et évitées. |
| **Ex. 3 — les quatre décisions** | Quatre options arrêtées, **deux** qui ne sont pas « réduire » (transfert partiel sur A, acceptation formelle sur D) là où l'énoncé en exige une. **Chaque réduction porte mesure, porteur nommé et échéance** ; les porteurs sont pris dans la **carte du pouvoir** (pack §3, reference pack §2-§3) avec la distinction qui compte — *qui signe un contrat*, *qui tient le réseau bureautique*, *qui tient le réseau industriel* — et les points d'arbitrage sont désignés là où deux pouvoirs se rencontrent. Chaque bloc se clôt par un **« pourquoi maintenant »** adressé au Directeur Financier. |
| **Ex. 3 — l'assurance sur A** | Portée réelle traitée en **deux colonnes** (couvert / non couvert), avec les limites qui ne se devinent pas : plafond et franchise, **non-assurabilité fréquente des amendes CNIL en droit français**, et le **risque d'exclusion** si l'assureur découvre une faiblesse connue et non corrigée. Conclusion explicite : complément après réduction, jamais substitut. |
| **Ex. 3 — l'acceptation de D** | Fiche aux **cinq éléments** de l'énoncé du TP 2 (risque coté, raison, instance, date, réexamen), complétée par la **mesure compensatoire** et la **surveillance** qu'exige la classe `Medium` de D5 — sans quoi D5 impose de traiter le risque comme `High`, et c'est écrit. La phrase interdite (*« risque accepté par le RSSI »*) est évitée par construction. |
| **Traçabilité amont et aval** | Amont : échelles, seuil, couples SR/OV et événements redoutés **repris de D5** ; constats gradés repris de **D4** ; écosystème et scénarios stratégiques repris de **D6** ; références chiffrées reprises du **TD 1** du matin. Aval : ce qui entre dans TP 1, D7 et la sous-section 7 est explicité ligne à ligne, mesures transversales identifiées d'avance. **Aucun objet recréé ni renommé.** |

*Chaque case vise la colonne « Excellent » de la grille officielle — à confronter en séance avec le corrigé de
référence du module (replié dans l'énoncé, « cliquer pour révéler »).*

---

> **Phrase de passage aux TP.** Les quatre scénarios du groupe ont une place sur la grille, une décision, un
> porteur et une échéance ; la ligne d'acceptation a tenu, et c'est la Direction Générale qui la signe. Le
> **TP 1** fait entrer tout cela dans `translog-b` — atelier 4 décliné maillon par maillon, registre généré,
> résiduels cotés **après** décision — parce qu'un risque qui n'est pas au registre est un risque que
> personne ne suivra. Le **TP 2** en tire le plan de traitement et le dossier **D7**, et met son coût annuel
> **en face de la fourchette du coût de l'inaction chiffrée ce matin** : c'est l'arbitrage promis au
> Directeur Financier, un coût certain contre une perte plausible.
