# Séance 5 — TD 2 (S5-03) : Ateliers 1 et 2 d'EBIOS Risk Manager — socle de sécurité et sources de risque
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN — appliquées à **MERIDIAN Logistique** et à son flux d'approvisionnement d'urgence vers **MERIDIAN Santé**

> Enchaînement de la journée : le CM a donné le vocabulaire du risque et la mécanique des cinq
> ateliers ; le TD 1 du matin a préparé l'**appétence** ; ce TD déroule les **ateliers 1 et 2** sur
> MERIDIAN, dans l'ordre du guide et avec ses livrables. Chaque exercice produit un élément qui entre
> **tel quel** dans le livrable D5 (assemblé au TP 2) — rien ici n'est jetable. Les ateliers 3, 4 et 5
> restent vides aujourd'hui : ils relèvent des séances 6 et 7.

**Règle du jour** : les valeurs métier et les biens supports sont **repris à l'identique** de la
cartographie de la séance 2 (D2) — les recréer ou les renommer serait une faute de méthode.
Références D2 : valeurs métier `LOG-PA-01` à `LOG-PA-04`, biens supports `LOG-SA-01` à `LOG-SA-13`.
Corrigés de l'énoncé repliés (« cliquer pour révéler »), non extractibles — réponses bâties sur le
corpus (CM S5, pack de filiale, reference pack, D1, D2, D4).

---

## Rappel du cas et des deux notions

La Direction Générale du groupe a approuvé le principe d'une appréciation des risques à l'échelle du
groupe, **premier cycle** centré sur la filiale sous revue (celle dont le groupe tient le pack —
MERIDIAN Logistique) et sur sa **principale dépendance inter-filiales du §6 du pack** : le **flux
d'approvisionnement d'urgence** des scannettes de Logistique vers le système de gestion des stocks de
MERIDIAN Santé. Le RSSI Groupe anime l'atelier de cadrage.

- **Source de risque (SR)** : « élément, personne, groupe de personnes ou organisation susceptible
  d'engendrer un risque », caractérisé par sa motivation, ses ressources, ses compétences, ses modes
  opératoires (glossaire EBIOS RM, cité au CM).
- **Objectif visé (OV)** : « finalité visée par une source de risque, selon ses motivations » —
  formulé comme un **résultat concret obtenu aux dépens du groupe**, jamais comme la motivation.
  *« Se faire de l'argent » n'est pas un objectif visé, c'est ce qui pousse la source.*

---

## Exercice 1 — Cadrer l'étude avant toute analyse

### 1. Objectif de l'étude, en une phrase

> **Apprécier et traiter les risques numériques pesant sur MERIDIAN Logistique et sur son flux
> d'approvisionnement d'urgence vers MERIDIAN Santé — premier cycle d'une démarche de groupe — pour
> éclairer les décisions de traitement de la Direction Générale et matérialiser sur la grille le seuil
> d'acceptation dérivé de l'appétence fixée le matin.**

*Finalité retenue parmi celles que reconnaît la méthode : une **étude complète des scénarios de
risque** (les cinq ateliers sur les deux cycles), en vue du **traitement** et du pilotage — pas la
seule identification d'un socle (atelier 1 seul), pas une homologation (le cadrage d'homologation du
WMS de la séance 4 en est un sous-ensemble, pas l'objet ici).*

### 2. Table des participants de l'atelier 1 — les quatre chaises du guide

*Quatre questions, quatre chaises : qui dit ce qui compte pour le métier ; qui dit ce que le SI permet ;
qui dit ce que la sécurité sait de la menace ; qui engage le groupe. Acteurs tirés du §3 (carte des
pouvoirs) du pack et du holding.*

| Rôle attendu par le guide | Acteur MERIDIAN | Ce qu'il apporte que les autres n'ont pas |
|---|---|---|
| **Responsable métier** (valeurs métier) | **Responsable Exploitation** de Logistique, en appui du **Responsable Qualité et chaîne du froid** | La connaissance fine des flux des six entrepôts, non écrite (`LOG-PA-03`), et ce que produit concrètement un arrêt (`LOG-PA-01`) ; le Responsable Qualité seul peut dire ce que vaut une rupture de température vis-à-vis du client pharmaceutique (`LOG-PA-02`, `LOG-PA-04`) |
| **SI / DSI** (ce que le SI permet) | **DSI de la filiale** (ne porte pas le titre de RSSI, 3 personnes) | Ce que permet le réseau bureautique, les postes, les comptes de domaine, la relation à la TMA du WMS — **et son angle mort à acter** : elle ne couvre ni l'OT (automates), ni la télématique, ni la box 4G de l'intégrateur |
| **Cyber / RSSI** (ce que la sécurité sait de la menace) | **RSSI Groupe** (le groupe de travail) | L'état de la menace (128 compromissions rançongiciel connues de l'ANSSI en 2025, chaîne d'approvisionnement), la couverture partielle du SOC, les constats gradés de l'audit S4, le lien avec l'appétence |
| **Décideur** (engage le groupe) | **Directrice Générale du groupe**, représentée en séance par le **Directeur de la filiale Logistique** pour ce qui engage la filiale | La seule instance à pouvoir engager le groupe, fixer l'appétence et **accepter le risque résiduel** ; le Directeur de filiale engage budget et contrats (TMA, intégrateur, client) mais pas le niveau de risque du groupe |

### 3. Responsable de l'acceptation des risques résiduels

> **La Direction Générale du groupe.** La gouvernance de la séance 1 en fait la seule instance qui
> **fixe** l'appétence au risque (le CA l'approuve, le RSSI Groupe la propose sans la fixer) ; accepter
> le risque résiduel au terme de l'étude est la face opérationnelle de cette même prérogative, et le
> guide EBIOS RM impose d'identifier nommément cette personne dès l'atelier 1.

### 4. Temporalité des deux cycles

> **Cycle stratégique : trois ans. Cycle opérationnel : un an.** Référence : la recommandation du guide
> EBIOS RM pour l'homologation de sécurité d'un système d'information (citée au CM S5). Le cycle
> stratégique revisite l'ensemble de l'étude et les scénarios stratégiques ; le cycle opérationnel
> revient sur les scénarios opérationnels à la lumière des incidents survenus, des nouvelles
> vulnérabilités et de l'évolution des modes opératoires. Ces durées s'articulent avec la gouvernance
> D1 : orientations pluriannuelles approuvées par le CA (rythme du cycle stratégique), revue
> trimestrielle du ComEx et point annuel (rythme du cycle opérationnel).

---

## Exercice 2 — De la carte aux événements redoutés

### Table de départ (4 lignes : bien métier, biens supports, besoin dominant)

*Trois valeurs métier de D2 + la dépendance inter-filiales du §6 en quatrième ligne. Objets repris à
l'identique de D2.*

| Réf. | Valeur métier | Biens supports associés (D2) | Besoin de sécurité dominant |
|---|---|---|---|
| `LOG-PA-01` | Exécution des flux logistiques | `SA-01` WMS · `SA-02` scannettes · `SA-03` automates de tri · `SA-04` compte de service WMS↔automates · `SA-06` local serveur E1 · `SA-07` entrepôts E1–E6 · `SA-09` Responsable Exploitation · `SA-10` TMA du WMS · liaisons opérateur inter-entrepôts | **Disponibilité** (et Intégrité) — très important |
| `LOG-PA-02` | Maintien de la chaîne du froid | `SA-05` logiciel des sondes (hébergé fournisseur) · `SA-08` chambres froides et remorques réfrigérées · télématique des remorques · `SA-11` Responsable Qualité | **Disponibilité + Intégrité** — très important ; Traçabilité très important |
| `LOG-PA-04` | Conformité contractuelle avec le client pharmaceutique | `SA-05` logiciel des sondes · portail d'expéditions du client (un compte par entrepôt) · `SA-11` Responsable Qualité · Directeur de la filiale (porte le contrat) | **Traçabilité + Intégrité** — très important (c'est l'intégrité de la preuve fournie à l'audit qui est vérifiée) |
| `§6` | Réapprovisionnement d'urgence Logistique → Santé *(valeur métier propriété de Santé ; biens supports chez nous)* | `SA-02` scannettes · `SA-13` interface d'approvisionnement d'urgence · `SA-12` VLAN dédié + pare-feu d'inspection · système de gestion des stocks côté Santé · équipes d'exploitation des entrepôts | **Disponibilité + Intégrité** — très important (continuité de soin) |

### Six événements redoutés, cotés en gravité

*Échelle générique à quatre niveaux du matin, alignée sur la « Matrice 4x4 EBIOS-RM » de l'outil :
**mineure / significative / grave / critique** (correspondance présumée dans l'outil : Minor /
Significant / Important / Critical — **à vérifier à l'import de la matrice au TP 1**, elle n'est pas
encore constatée à l'écran). Gravité justifiée par la nature des impacts : missions, réglementation/contrat, personnes,
image. Le TP 2 remplacera cette échelle générique par une échelle décrite dans les termes du groupe.*

| Réf. | Événement redouté (valeur métier atteinte + besoin touché) | Gravité | Justification (nature des impacts) |
|---|---|---|---|
| **ER1** | `LOG-PA-01` — le **flux d'expédition du groupe est interrompu** : le WMS ou la liaison inter-entrepôts tombe, les six entrepôts ne préparent plus les commandes (**Disponibilité**) | **Critique** | Missions : un arrêt > 6 h bloque **40 % du volume expédié du groupe** ; contrat : pénalités de 12 000 €/jour ; aggravation : la reprise n'est **pas démontrée** — sauvegardes quotidiennes jamais restaurées depuis la mise en service |
| **ER2** | `LOG-PA-01` — les **données de préparation et de stock du WMS sont altérées** (mise à jour TMA de nuit non contrôlée, ou compromission via le compte de service en clair) : les entrepôts expédient des commandes fausses sans le savoir (**Intégrité**) | **Grave** | Missions + client : erreurs d'expédition en cascade, y compris vers Santé ; partiellement détectable et rattrapable ; pas de risque vital direct |
| **ER3** | `LOG-PA-02` — la **chaîne du froid est rompue ou ses relevés sont faussés** sur un entrepôt pharma (E1/E4) : sondes ou logiciel hébergé n'assurent plus la température dirigée, ou remontent des valeurs fausses (**Disponibilité + Intégrité**) | **Critique** | Contrat : manquement direct aux engagements du client pharmaceutique et à l'audit annuel de chaîne du froid ; **personnes** : risque sanitaire pour le patient final ; image |
| **ER4** | `LOG-PA-04` — la filiale **ne peut pas produire, à l'audit annuel ou au questionnaire de sécurité du client, la preuve de qui accède** aux relevés de température et aux systèmes (**Traçabilité**) | **Grave** | Contrat : échec probable de l'audit / du questionnaire annoncé → risque de perte du contrat ; image ; le compte de la TMA est partagé, porteurs inconnus, aucun journal nominatif — le Responsable Qualité « ne pourra pas répondre » |
| **ER5** | `§6` — le **réapprovisionnement d'urgence de la pharmacie hospitalière de Santé n'est plus assuré** : le flux (scannettes → interface → VLAN) reste indisponible — il l'est déjà, bloqué depuis trois mois (**Disponibilité**) | **Critique** | **Personnes** : réapprovisionnement d'urgence des établissements de soin ; missions inter-filiales ; le Pharmacien chef de Santé : « on gère avec des commandes manuelles, ça ne tiendra pas l'hiver » |
| **ER6** | `LOG-PA-02` — les **données de température et d'expédition du client pharmaceutique sont divulguées** : accès non maîtrisé chez un fournisseur hors supervision (logiciel des sondes hébergé, portail client) (**Confidentialité**) | **Significative** | Contrat : violation d'une clause de confidentialité client ; image ; pas de donnée de santé nominative directe — la confidentialité n'est jamais notée « très important » dans D2 |

### Événement redouté dont une durée change la cotation

**ER1** (atteinte à la disponibilité de `LOG-PA-01`). Le pack porte le cas quantifié : *« un arrêt de
plus de six heures bloque 40 % du volume expédié du groupe »*.

> **Spécification proposée** : ER1 atteint le niveau **Critique** à partir de **six heures**
> d'interruption **non planifiée** du flux d'expédition du groupe. En deçà — incident résolu sous six
> heures, ou arrêt **planifié** dans une fenêtre hors pointe annoncée — il reste **Grave**.

Cette borne est exactement celle de l'énoncé d'appétence n°1 rédigé le matin : l'appétence et
l'événement redouté se lisent sur la même ligne des six heures.

---

## Exercice 3 — Le socle de sécurité (étape D de l'atelier 1)

*Assemblage rigoureux : le choix de référentiel de la séance 3 et le rapport d'audit de la séance 4
**sont** l'« état d'application » que demande la méthode. Les directives PSSI-cadre codifiées en séance 1
(`ACC-01` à `COR-01`) font foi quel que soit le libellé.*

| Type et nom du référentiel | État d'application | Écarts | Justification des écarts |
|---|---|---|---|
| **PSSI-cadre du groupe** (S1 — directives `ACC-01`, `ACC-02`, `INC-01`, `JRN-01`, `COR-01`) | Établie récemment, déclinaison filiale à six mois ; appliquée à la marge sur Logistique | `ACC-01` (MFA sur accès distant et privilèges) : **non appliqué** — secret de compte de service en clair, pas de MFA sur les accès WMS/automates. `ACC-02` (revue trimestrielle des privilèges) : **non appliqué** — porteurs du compte TMA inconnus. `INC-01` (notification < 2 h) : **non appliqué** — arrêt d'avril, « chacun a appelé qui il pouvait ». `JRN-01` (journaux → SOC) : **partiel** — le SOC reçoit le réseau bureautique, rien de l'OT, de la box 4G ni du WMS. `COR-01` (correctif < 14 j) : **ni mesuré ni mesurable** — la TMA met à jour « quand elle veut ». | Les directives existent (S1) ; l'outillage et les preuves de mise en œuvre n'existent pas encore côté Logistique, dont l'inventaire vivait dans une mémoire. |
| **Guide d'hygiène informatique de l'ANSSI** (v2, 42 mesures — retenu en S3 comme outil d'application immédiate) | Non déroulé formellement ; quelques mesures satisfaites de fait | Mesure 4 (actifs sensibles + **schéma réseau**) : **aucun schéma réseau de la filiale n'existe** (lacune n°1 de D2). Cloisonnement / séparation des usages : réseaux IT et OT interconnectés sur les six sites. Comptes d'administration : compte de domaine partagé avec la TMA. Sauvegarde : sauvegardes quotidiennes **jamais restaurées**. | Le guide a été retenu en S3 comme mesure d'urgence, pas comme référentiel de conformité ; le chantier « schéma réseau » est inscrit à la trajectoire (M2 de D4, échéance 8/12/2026). |
| **ISO/IEC 27001:2022** (référentiel colonne vertébrale du groupe, S3) | Auto-évaluation outillée S4 sur 12 exigences : **aucune pleinement couverte**, 2 partielles, 9 non couvertes ; pas de SMSI (clauses 4–10) | **C3 — `A.8.22`** (cloisonnement) : **non-conformité majeure** — réseaux IT/OT interconnectés sur la totalité du périmètre. **C4 — `A.5.19` / `A.8.2`** (fournisseurs / droits d'accès) : **non-conformité majeure** — compte de domaine partagé avec la TMA, porteurs inconnus, imputabilité inopérante. `A.5.17` (secrets) : non couvert — secret du compte de service identique depuis 2019, en clair. `A.5.22` (surveillance des services fournisseurs), `A.8.5`, `A.8.8`, `A.8.15` : non ou partiellement couverts. `A.8.13` / `A.5.30` (sauvegarde / continuité TIC) : sauvegardes jamais restaurées, RTO/RPO non contractualisés — **hors des douze exigences auto-évaluées en S4**, écart repris directement du pack §5(4) et de la lacune n°5 de D2, non gradé à ce jour. **C7 — `A.8.22`** sur le flux Logistique↔Santé : **conforme** (seul cloisonnement du groupe), mais **flux suspendu depuis trois mois**. | Référentiel choisi en S3, auto-évaluation en S4 ; écarts majeurs concentrés sur le cloisonnement et la gouvernance des comptes tiers, héritage de onze ans d'acquisitions sans intégration des SI. Le seul point conforme porte sur un flux à l'arrêt. |
| **Obligations propres de la filiale — exigences contractuelles du client pharmaceutique** (§2 du pack : pénalités 12 000 €/j, audits annuels de chaîne du froid, questionnaire de sécurité annoncé) | Partiellement tenu : la chaîne du froid est opérée (sondes, logiciel fournisseur, rapport mensuel) ; la maîtrise des accès et la preuve associée manquent | La filiale ne peut pas répondre au questionnaire de sécurité annoncé (« qui a accès aux relevés de température ? ») ; un compte par entrepôt sur le portail du client, sans gestion nominative ; aucun journal. | L'exigence est contractuelle et connue, mais n'a jamais été traduite en mesures internes ni en preuves ; le client a annoncé qu'il la contrôlerait au prochain audit. |

> **Correspondance avec les deux constats du reference pack.** Le tableau des constats du reference pack
> (§4) porte **deux lignes** pour Logistique : *« réseaux bureautique et industriel interconnectés,
> compte de domaine partagé avec le prestataire »* et *« sauvegardes du WMS jamais restaurées »*. La
> première est reprise ici **scindée en deux**, telle que le rapport d'audit de la séance 4 l'a gradée :
> **C3** (cloisonnement, `A.8.22`) et **C4** (compte partagé, `A.5.19` / `A.8.2`), toutes deux en
> non-conformité majeure. La seconde — les sauvegardes jamais restaurées — figure aux lignes « guide
> d'hygiène » et « ISO 27001 » ci-dessus, mais **n'a reçu aucune gradation en séance 4** : elle ne
> faisait pas partie des huit constats gradés le matin ni des douze exigences auto-évaluées l'après-midi.
> Elle entre donc dans le socle comme **écart connu et non gradé**, à qualifier au prochain cycle d'audit.

### Décision sur la suite à donner, en trois phrases

Le guide ouvre deux voies quand le socle présente des écarts — **suspendre l'appréciation et renforcer
le socle d'abord**, ou **poursuivre en considérant la non-conformité**, les scénarios venant exploiter
ces fragilités.

> 1. Le groupe **poursuit l'appréciation en intégrant la non-conformité** : les écarts du socle
>    deviennent des données d'entrée de l'étude, pas un motif de suspension.
> 2. C'est la seule voie raisonnable ici — l'appétence fixée le matin traite déjà ces écarts comme des
>    **tolérances à formaliser** avec une remédiation datée (M1 à M4 de D4), et suspendre priverait la
>    Direction Générale de la priorisation par le risque qu'elle a explicitement demandée.
> 3. Conséquence sur les ateliers suivants : les scénarios stratégiques et opérationnels de la séance 6
>    seront construits **sur ces fragilités** — interconnexion IT/OT, compte TMA partagé, secret de
>    service en clair, absence de journalisation OT — comme chemins d'attaque privilégiés, et les
>    niveaux de risque calculés en séance 7 refléteront l'**état actuel** du socle, non un état cible.

---

## Exercice 4 — Sources de risque et objectifs visés (atelier 2)

*Contexte de menace (CM / TD 2) : 128 compromissions par rançongiciel portées à la connaissance de
l'ANSSI en 2025 ; le secteur santé reste une cible régulière (Centre Hospitalier Sud Francilien, 2022,
rançongiciel revendiqué par LockBit). Piège annoncé : ne pas confondre l'objectif visé avec la
motivation.*

### 1. Cinq couples SR/OV candidats (acteurs des §3 et §6 du pack)

| # | Source de risque (catégorie outil) | Objectif visé (résultat aux dépens du groupe) | Valeur métier ciblée |
|---|---|---|---|
| **1** | **Cybercriminel** (*Crime organisé*) | Chiffrer le WMS et sa base, **arrêter le flux d'expédition du groupe** et obtenir une rançon sous menace d'arrêt prolongé | `LOG-PA-01` (via `SA-01`) |
| **2** | **Attaquant passant par l'intégrateur des automates** — compromission de la chaîne d'approvisionnement (*Autre / initié tiers*) | Atteindre le réseau industriel et les automates **via la box 4G non supervisée**, et prendre la main sur les réglages | `LOG-PA-01` (via `SA-03`) |
| **3** | **Initié de l'Exploitation, mécontent ou partant** (*Vengeur*) | Altérer les données de préparation et de stock via le **compte de service en clair** connu de tous, et emporter le savoir-faire opérationnel non écrit | `LOG-PA-01` (intégrité, via `SA-04`) **et** `LOG-PA-03` (via `SA-09`) |
| **4** | **Concurrent** (*Concurrent*) | Obtenir les **données d'exploitation et les données du client pharmaceutique** (volumes, tournées, relevés) pour capter le marché | `LOG-PA-04` et `LOG-PA-02` (confidentialité, via `SA-05` et le portail client) |
| **5** | **Militant / hacktiviste** (*Activiste*) | Interrompre publiquement l'activité d'un entrepôt ou **exposer une défaillance de la chaîne du froid** pour nuire à l'image du groupe et de son client pharmaceutique | `LOG-PA-02` (via `SA-05`, `SA-08`) |

### 2. Évaluation de chaque couple (motivation / ressources / activité — échelle à trois positions)

*Correspondance outil : bas = Low/Limited, moyen = Significant/Moderate, haut = Strong/Important. La
colonne activité est justifiée par un élément observable.*

| # | Motivation | Ressources | Activité | Élément observable justifiant l'activité |
|---|---|---|---|---|
| **1** | **haute** — gain financier direct, cible à fort levier (40 % du groupe + pénalités) | **hautes** — écosystème rançongiciel mature, accès initiaux achetés | **haute** | 128 compromissions rançongiciel connues de l'ANSSI en 2025 ; secteur logistique/santé régulièrement ciblé (CHSF 2022) |
| **2** | **moyenne** — intérêt à verrouiller la relation, pas à détruire | **hautes** — accès natif à distance par la box 4G, connaissance exclusive des réglages | **moyenne** | Contrat sans clause de réversibilité ni exigence de sécurité ; l'intégrateur qualifie déjà les réglages de « propriété industrielle » (position écrite, pack §3) ; box 4G hors réseau supervisé |
| **3** | **moyenne** — rancune, départ ; pas de gain structuré | **moyennes** — le secret est en clair, connu de « tout le monde en Exploitation » | **basse à moyenne** | Aucun incident interne connu à ce jour ; mais aucune procédure de départ, et l'accès est trivial |
| **4** | **basse à moyenne** — marché concurrentiel, mais risque juridique dissuasif | **moyennes** | **basse** | Aucun signal d'espionnage concurrentiel observé ; données dispersées mais aucune tentative constatée |
| **5** | **basse** — pas de cause emblématique attachée à la logistique sous température | **basses à moyennes** | **basse** | Aucune campagne ni revendication visant la filiale ou son client ; surface technique exposée mais pas de ciblage observé |

### 3. Trois couples retenus

*Règle de sélection du guide : des couples **suffisamment distincts** qui **n'atteignent pas tous la
même valeur métier**.*

| # | Retenu ? | Raison |
|---|---|---|
| **1** — Cybercriminel → arrêt WMS sous rançon | ✅ **retenu** | Pertinence la plus élevée (motivation × ressources) ; l'événement redouté le plus grave de la filiale (ER1) ; menace de référence du secteur |
| **3** — Initié → intégrité des flux + savoir-faire | ✅ **retenu** | Catégorie d'origine distincte (initié) ; **seul couple atteignant `LOG-PA-03`** (savoir-faire) ; jeu d'événements redoutés différent de la paire 1 (ER2, pas ER1) |
| **4** — Concurrent → captation de données client / preuve | ✅ **retenu** | Catégorie distincte (concurrent) ; **seul couple atteignant `LOG-PA-04` et la confidentialité** (ER4, ER6) — sans lui, toute la moitié « confiance / conformité contractuelle » du métier resterait sans adversaire dans l'étude, malgré une pertinence modérée |
| **2** — Intégrateur / chaîne d'approvisionnement → prise de contrôle des automates | ⬜ **écarté — sous surveillance** | Redouble `LOG-PA-01` déjà porté par la paire 1 ; sa finalité relève d'abord d'un **risque de dépendance et de gouvernance** qui se traite au contrat (réversibilité, `ARB-01`) et qui sera repris comme **partie prenante critique de l'écosystème en séance 6 (atelier 3)** — c'est sa juste place méthodologique, pas l'atelier 2 |
| **5** — Hacktiviste → image chaîne du froid | ⬜ **écarté — sous surveillance** | Le plus bas sur les trois critères, **aucune activité observable** ; conservé en veille en raison de la cible symbolique (client pharmaceutique) |

### 4. Confrontation des couples retenus avec les événements redoutés de l'exercice 2

| Couple retenu | Événements redoutés associés |
|---|---|
| **1** — Cybercriminel → arrêt WMS | **ER1** (`PA-01` disponibilité, Critique), **ER2** (`PA-01` intégrité, Grave) |
| **3** — Initié → intégrité + savoir-faire | **ER2** (`PA-01` intégrité, Grave) — et `LOG-PA-03` : **aucun événement redouté dans la table de l'exercice 2** |
| **4** — Concurrent → données client / preuve | **ER4** (`PA-04` traçabilité, Grave), **ER6** (`PA-02` confidentialité, Significative) |

**Signalements — à porter dans D5 :**

1. **ER3 (chaîne du froid, Critique) et ER5 (réapprovisionnement Santé, Critique)** — deux des
   événements les plus graves du dossier — restent **sans source de risque retenue**. Ce n'est pas un
   oubli à corriger en forçant la sélection : ce sont d'abord des risques d'origine **accidentelle**
   (défaillance du fournisseur du logiciel des sondes, panne d'une liaison opérateur, blocage
   inter-filiales non résolu) que l'approche par conformité couvre mieux que l'approche par scénarios.
   **Recommandation** : réintégrer la paire 5 (ou une variante « fournisseur du logiciel des sondes
   compromis ») en couple secondaire sous surveillance pour ER3, et ajouter un couple « attaquant
   pivotant Logistique → Santé » pour ER5, avant l'atelier 3 de la séance 6.
2. **La paire 3 vise `LOG-PA-03` (savoir-faire), qui n'a pas d'événement redouté** dans la table de
   l'exercice 2 (trois valeurs métier retenues sur quatre). **Recommandation** : ajouter à D5 un
   événement redouté pour `LOG-PA-03` — « la connaissance opérationnelle des six entrepôts est perdue :
   départ ou absence du Responsable Exploitation, aucune trace écrite » (Traçabilité, gravité **Grave**)
   — cohérent avec le rang 3 du Top 5 de D2.
3. **Concentration sur `LOG-PA-01`** : trois candidats sur cinq visent l'exécution des flux. Ce n'est
   pas un biais d'analyse — c'est une propriété réelle de la filiale (quatre des cinq actifs critiques
   du Top 5 de D2 servent `LOG-PA-01`), et c'est ce que l'appétence du matin protège en priorité.

---

## Ce qui entre dans le livrable D5 (assemblé au TP 2)

| Section D5 | Ce qui vient d'ici |
|---|---|
| 1. Cadrage de l'étude | Objectif (ex. 1.1), table des participants (ex. 1.2), responsable de l'acceptation des risques résiduels (ex. 1.3), durées des deux cycles (ex. 1.4) — + échelles justifiées de gravité et de vraisemblance (TP 2, ex. 1) |
| 2. Socle de sécurité | La table à quatre colonnes de l'exercice 3 + la décision de poursuite en trois phrases |
| 3. Sources de risque | Les trois couples SR/OV retenus (ex. 4.3), chacun motivé en une phrase, + la liste des couples secondaires sous surveillance (2 et 5) |
| 4. Événements redoutés | Les six événements redoutés cotés de l'exercice 2, adossés aux valeurs métier de D2, + les deux ajouts recommandés (ER `PA-03`, couple ER3/ER5) |

**Critères d'acceptation de D5 à vérifier** : valeurs métier et biens supports **identiques** à D2
(aucun recréé, aucun renommé) ; chaque couple SR/OV motivé en une phrase ; échelles réutilisables
telles quelles en séance 7.

---

## Auto-évaluation (grille officielle du TD)

| Critère | Niveau atteint |
|---|---|
| **Ex. 1 — cadrage** | Objectif en une phrase adossé à une finalité reconnue de la méthode ; quatre chaises du guide, chacune incarnée par un acteur du §3 avec ce qu'il apporte en propre, angle mort de la DSI (OT) acté ; accepteur du risque résiduel = DG, justifié par la gouvernance S1 ; deux cycles 3 ans / 1 an avec la référence du guide |
| **Ex. 2 — événements redoutés** | Table de départ à 4 lignes reprise à l'identique de D2 (dépendance §6 incluse) ; six événements redoutés couvrant les **quatre** besoins DICT, un par ligne au minimum, cotés sur l'échelle générique du matin avec justification par nature d'impact ; ER1 signalé comme l'événement dont la durée (6 h) change la cotation, borne alignée sur l'appétence |
| **Ex. 3 — socle** | Table à quatre colonnes couvrant PSSI-cadre, guide d'hygiène, ISO 27001:2022 et obligations contractuelles du client ; écarts repris de l'audit S4 avec leur gradation (C3, C4 majeures ; C7 conforme sur flux à l'arrêt), et correspondance explicite avec les **deux** constats du reference pack — dont les sauvegardes jamais restaurées, assumées comme écart connu **non gradé** ; décision « poursuivre en intégrant la non-conformité » en trois phrases, avec sa conséquence sur les ateliers 3 à 5 |
| **Ex. 4 — SR/OV** | Cinq couples variant les catégories (crime organisé, chaîne d'approvisionnement, initié, concurrent, activiste), objectifs formulés en **résultats** et non en motivations ; évaluation motivation/ressources/activité avec un observable par ligne ; trois couples retenus **distincts et sur des valeurs métier différentes** (`PA-01`, `PA-03`, `PA-04`/`PA-02`) ; deux couples écartés avec raison, dont l'intégrateur explicitement **routé vers l'atelier 3** ; confrontation avec les événements redoutés produisant trois signalements honnêtes (ER3/ER5 sans origine retenue, `PA-03` sans événement, concentration sur `PA-01`) |

*Chaque case vise la colonne « Excellent » de la grille officielle — à confronter en séance avec le
corrigé de référence du module.*

---

> **Phrase de passage à la séance 6** : les couples source de risque / objectif visé et les événements
> redoutés arrêtés aujourd'hui deviennent la matière première de la séance 6, qui construira les
> scénarios stratégiques puis opérationnels à travers l'écosystème du groupe, ses prestataires et ses
> projets ; les échelles fixées au TP 2 serviront, inchangées, à coter le registre complet en séance 7.
