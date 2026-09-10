# D6 — TIERS ET PROJETS : MERIDIAN LOGISTIQUE

**Émetteur** RSSI Groupe · **Destinataires** Direction Générale du groupe (fixe la règle de contractualisation, accepte le risque résiduel), Comité Exécutif (en fait une condition de signature, arbitre budgets et priorités), Direction Juridique (rend la règle opposable), Direction et DSI de MERIDIAN Logistique + RSSI de MERIDIAN Santé (agissent sur le projet)
**Groupe 4 (Translog)** · instance `translog-b` · étude `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1` · **Séance 6**

> **Livrable D6 — tiers et projets (7 points, le plus lourd du module).** Deux pièces écrites, cohérentes entre elles, plus l'export de l'étude EBIOS RM enrichie de son écosystème coté et de ses scénarios stratégiques (§4).
> **Pièce 1 — la fiche projet** : *Security by Design* appliqué à un projet réel du pack de filiale, cadré comme s'il était lancé aujourd'hui, avec la discipline des six jalons (CM séance 6).
> **Pièce 2 — les exigences de sécurité du contrat d'infogérance du WMS** (APPLICA Services), tracées à un scénario stratégique de l'atelier 3, à un écart gradé de l'audit de la séance 4 ou à un silence du contrat, complétées du dispositif qui les tient vivantes après signature.
> **Le principe des deux pièces, et le critère d'acceptation** : *zéro exigence orpheline.* Un jalon sans critère de passage, une exigence sans justification, est un vœu — la grille d'acceptation le refuse. Chaque critère de passage se démontre par un **fait**, jamais par une déclaration ; on part du risque et on remonte à l'exigence, jamais l'inverse.
> **Objets repris à l'identique** de D2 (`LOG-PA-01…04`, `LOG-SA-01…13`), de D4 (constats `C3`, `C4`, `C7` ; mesures `M1`–`M4`) et de D5 (échelles G1–G4, couples SR/OV, événements redoutés). Rien recréé, rien renommé.

---

## 1. Objet et principe

La séance 6 a montré deux faces d'un même sujet. Le matin (TD 1), **seize dépendances tierces** inventoriées, aucune contractée par un RSSI, treize sans exigence de sécurité écrite. L'après-midi (TD 2, atelier 3), l'écosystème de l'actif le plus critique de la filiale — `LOG-PA-01`, l'exécution des flux logistiques — **coté** : cinq parties prenantes, **deux critiques**, un scénario stratégique à **G4** qui relie un cybercriminel à l'arrêt du flux d'expédition du groupe **en passant par la tierce maintenance du WMS**.

D6 traite ce sujet là où il se décide : **avant la signature**, au cadrage d'un projet, et **dans le contrat** d'un tiers déjà installé. Les deux pièces partagent une règle : *ce qui n'est pas exigé au contrat ne sera jamais dû* (guide ANSSI « Maîtriser les risques de l'infogérance »).

---

## 2. Pièce 1 — Fiche projet : reprise sécurisée du flux d'approvisionnement d'urgence MERIDIAN Logistique → MERIDIAN Santé

*Le projet que le pack de filiale porte, et qui traverse une frontière de filiale — l'équivalent, côté Logistique, du projet de plateforme pédagogique Éducation ↔ Territoires du CM. Le flux est **coupé depuis trois mois** à la demande de la RSSI de Santé (« leur matériel n'est pas fiable ») ; le Pharmacien chef de Santé en demande la reprise (« on gère avec des commandes manuelles, ça ne tiendra pas l'hiver »). La reprise est cadrée ici comme un projet lancé aujourd'hui.*

### 2.1 Objet et périmètre

| Élément | Contenu |
|---|---|
| **Ce que fait le projet** | Rouvrir, sous exigences démontrées, le flux qui porte les mouvements de stock des ~300 scannettes de Logistique (`LOG-SA-02`) vers le système de gestion des stocks pharmaceutiques de MERIDIAN Santé, via l'**interface d'approvisionnement d'urgence** (`LOG-SA-13`) sur le **VLAN dédié + pare-feu d'inspection** (`LOG-SA-12`). |
| **Filiales concernées** | MERIDIAN Logistique (biens supports du flux, équipes d'exploitation) **et** MERIDIAN Santé (la valeur métier « réapprovisionnement d'urgence » lui appartient — D2 §5). |
| **Flux traversant une frontière** | Le seul actif dont **deux filiales** dépendent (reference pack §5.1). Côté Santé, ces mouvements alimentent les commandes de la pharmacie hospitalière, **réapprovisionnement d'urgence des établissements de soin** compris. |
| **Flux vers un tiers** | La **correction** de cette interface relève du contrat `TMA-WMS-2021` d'APPLICA Services (art. 2, l'interface d'approvisionnement d'urgence avec Santé est nommée dans le périmètre) — la pièce 2 s'y applique. |
| **Hors périmètre** | Le renouvellement du WMS lui-même ; la chaîne du froid (`LOG-PA-02`) ; les trois autres filiales. |

### 2.2 Données traitées et besoins DICT

*Lus dans le pack de filiale (§6) et le reference pack (§5.1). Notés sur l'échelle relative de D2 — négligeable / notable / très important — et rattachés aux événements redoutés de D5.*

| Donnée | D | I | C | T | Justification de la note dominante | ER de D5 |
|---|---|---|---|---|---|---|
| Mouvements de stock (entrées, sorties, références, quantités) transmis à la pharmacie hospitalière | **TI** | **TI** | Notable | **TI** | **Disponibilité** : le réapprovisionnement d'urgence des établissements de soin en dépend — « ça ne tiendra pas l'hiver ». **Intégrité** : un mouvement faux → une commande de pharmacie fausse → risque pour le patient final. **Traçabilité** : établir qui ou quoi a écrit dans les commandes d'une pharmacie hospitalière, **de l'autre côté d'une frontière de filiale**. | **ER5** (§6, Critique) ; **ER2** (`LOG-PA-01`, intégrité, Grave — erreurs en cascade « y compris vers Santé ») |
| Journaux du flux (horodatage, identifiant de scannette, volumétrie) | Notable | **TI** | Notable | **TI** | Sans journal exploitable des deux côtés, ni la détection ni l'analyse post-incident ne sont possibles sur un flux inter-filiales. | — |

**Niveau d'analyse retenu** : **projet sensible** — il traverse une frontière de responsabilité, il porte de la disponibilité et de l'intégrité *très importantes* liées à la continuité de soin. → **parcours de jalons complet** (les six, chacun outillé), pas la version allégée (CM séance 6, jalon J1).

### 2.3 Régime du projet

*Trois régimes du CM : développer / acheter / faire faire. Le projet est **mixte** et le tableau le dit ligne par ligne.*

| Composant | Régime | Ce que le groupe maîtrise / ne maîtrise pas | Levier de sécurité principal |
|---|---|---|---|
| VLAN dédié, pare-feu d'inspection, gestion de parc des scannettes | **Développer / exploiter en interne** (DSI de la filiale) | Maîtrise l'architecture, la configuration, le calendrier ; ne maîtrise pas les compétences internes disponibles (DSI = 3 personnes) | Règles d'architecture, tests d'acceptation, revue de configuration |
| Correction de l'interface d'approvisionnement d'urgence | **Faire faire** (APPLICA, contrat `TMA-WMS-2021` art. 2) | Maîtrise les exigences, la supervision, la réversibilité ; ne maîtrise pas l'exécution quotidienne ni le personnel du prestataire | **Contrat + plan d'assurance sécurité + audits** — c'est la pièce 2 |
| Système de gestion des stocks côté Santé | **Partenaire** (pas un fournisseur — filiale du groupe) | Maîtrise l'accord inter-filiales et le point d'interconnexion ; ne maîtrise pas le SI de Santé (constats propres à Santé : pas de MFA, identifiant du SIH partagé — reference pack §3) | **Accord inter-filiales** : propriétaire du flux, accepteur du risque résiduel, exigences réciproques |

### 2.4 Les six jalons de sécurité

*Chaque jalon : la question posée, le critère de passage **vérifiable** (démontré par un fait), le livrable produit. Un « la sécurité a été prise en compte » n'est pas un critère ; « les besoins DICT sont cotés et la classification est validée par le métier » en est un.*

| Jalon | Question | Critère de passage vérifiable | Livrable |
|---|---|---|---|
| **M1 — Cadrage** | Quelles données, quels besoins DICT, quel niveau d'analyse ? | Les besoins DICT du flux (§2.2) sont **cotés et validés par le métier des deux filiales** — Responsable Exploitation + Responsable Qualité côté Logistique, **Pharmacien chef côté Santé** ; la classification des données est signée ; **la RSSI de Santé a siégé au cadrage** (trace d'invitation et de présence), comme le responsable de Territoires aurait dû l'être pour la plateforme d'Éducation (CM). | Fiche projet, section sécurité, classification des données |
| **M2 — Architecture** | Cloisonnement, authentification, journalisation prévus ? | Le dossier d'architecture démontre : le flux **reste sur le VLAN dédié + pare-feu d'inspection** (`C7` conservé, seul cloisonnement du groupe — jamais retiré) ; **identité de chaque scannette** exigée à l'entrée de l'interface — c'est la réponse à « leur matériel n'est pas fiable », la raison même de la coupure ; authentification portée par le protocole de l'API (pas ajoutée après) ; **journalisation du flux prévue vers le SOC du groupe des deux côtés**. Matrice de flux en défaut-refus documentée. | Dossier d'architecture ; exigences de sécurité ajoutées au cahier des charges de l'interface |
| **M3 — Contractualisation** | Les exigences de sécurité sont-elles au contrat, un tiers étant impliqué ? | L'interface d'approvisionnement d'urgence est **nommée dans les exigences de la pièce 2** (réversibilité, droit d'audit, notification, comptes nommés, sous-traitance couvrent l'interface — contrat art. 2) ; **l'accord inter-filiales** est signé : il nomme le **propriétaire du flux** et l'**accepteur du risque résiduel** (D2 §5 : la valeur métier est à Santé, les biens supports sont chez nous — l'accord lève l'ambiguïté). | Avenant au contrat `TMA-WMS-2021` ; accord inter-filiales Logistique–Santé |
| **M4 — Acceptation** | Les exigences sont-elles démontrées, pas seulement déclarées ? | Recette de sécurité, **preuve en main** : un flux non prévu est **bloqué au pare-feu** (test rejoué) ; l'identité de scannette est **refusée si absente** ; les journaux **arrivent au SOC** des deux côtés. **Décision de reprise prononcée** sur le dossier de recette par l'autorité désignée — ici l'instance qui accepte le risque du flux inter-filiales (§2.5) : c'est le critère de passage de M4, la décision d'autorisation elle-même. | Rapport de recette de sécurité ; décision de reprise signée des deux filiales |
| **M5 — Exploitation** | Qui maintient, surveille, corrige, sous quels délais ? | Le flux a **un propriétaire nommé de chaque côté** ; une **procédure d'incident** avec point de contact unique existe — elle répond à la question du Comité Exécutif après l'arrêt d'avril : *« si ça s'arrête pendant six heures, qui appelle qui, et qui décide de prévenir ? »* (pack §7) ; le SOC **reçoit les journaux du flux** ; l'astreinte d'APPLICA (contrat art. 4 : rétablissement 6 h) couvre l'interface ; **revue trimestrielle** au comité de suivi. | Conditions d'exploitation de sécurité ; transfert aux RSSI / DSI des deux filiales |
| **M6 — Fin de vie** | Données restituées ou détruites, accès révoqués, réversibilité exécutée ? | Une **procédure de coupure propre** existe : règle de pare-feu retirée, **clés / jetons de l'API révoqués**, profil « Santé » retiré de la gestion de parc des scannettes, et le **repli papier documenté comme repli assumé** (c'est l'état de fait actuel — il devient un choix, pas une panne). | Procédure de fin de vie et de repli |

> **Pourquoi M4 prend une forme d'autorisation.** Le flux relève d'une décision d'autorisation (approche d'homologation cadrée en séance 4 pour le WMS et ses échanges — D4 §6) : le critère de passage de M4 **est** la décision prononcée sur le dossier de recette par l'autorité désignée. Ici, cette autorité n'est pas la DSI d'une filiale mais l'instance qui engage le groupe sur un flux inter-filiales (§2.5).

### 2.5 Responsabilités — un propriétaire ultime unique par jalon (gouvernance de la séance 1)

| Jalon | Propriétaire ultime (décide) | Qui prépare et atteste | Qui valide côté métier |
|---|---|---|---|
| M1 Cadrage | **RSSI Groupe** (le cadrage traverse une frontière — il l'arbitre) | RSSI Groupe | Directions des deux filiales ; Pharmacien chef de Santé |
| M2 Architecture | **DSI de MERIDIAN Logistique** (les biens supports du flux sont chez elle) | DSI filiale + RSSI Groupe | RSSI de Santé (point d'interconnexion côté Santé) |
| M3 Contractualisation | **Comité Exécutif** (arbitre budgets et contrats — RACI de D1) ; Direction Juridique pour l'opposabilité | RSSI Groupe | Direction de la filiale (porte le contrat APPLICA) |
| M4 Acceptation | **Direction Générale du groupe**, représentée pour ce qui engage le flux par les deux Directions de filiale — c'est elle qui **accepte le risque résiduel** (D5 §1, guide EBIOS RM) | RSSI Groupe (prépare et atteste, **ne décide pas**) | — |
| M5 Exploitation | **DSI de MERIDIAN Logistique** + **RSSI de MERIDIAN Santé**, conjointement, chacun sur son côté du flux | RSSI Groupe (tient le registre) | — |
| M6 Fin de vie | **RSSI Groupe** (une coupure inter-filiales relève de `ARB-01`) | DSI filiale | — |

### 2.6 Points d'arbitrage prévisibles, et l'instance qui tranche

| Désaccord | Instance qui tranche |
|---|---|
| **Rouvrir ou non, et sur quel calendrier** — la RSSI de Santé (« leur matériel n'est pas fiable ») contre le Pharmacien chef de Santé (« ça ne tiendra pas l'hiver ») | `ARB-01` de D1 : **véto suspensif du RSSI Groupe sous 72 h**, puis décision du ComEx ou de la DG. Le projet est le moyen de lever l'objection de la RSSI de Santé — pas de la contourner. |
| **Qui accepte le risque résiduel d'un flux inter-filiales** — la valeur métier est à Santé, les biens supports sont chez Logistique (D2 §5, limite structurelle) | **Direction Générale du groupe** (D5 §1) ; l'accord inter-filiales de M3 le formalise. Une cartographie de groourpe supposerait un objet au-dessus des instances de l'outil (D2 §5) — l'accord y supplée. |
| **Coût de l'identité de scannette pour ~300 terminaux** contre « pas de budget nouveau la première année » (reference pack §7) | ComEx (arbitre priorités et budgets, RACI de D1). Piste sans budget : profil de gestion de parc et certificat par lot, pas un renouvellement du parc. |

---

## 3. Pièce 2 — Exigences de sécurité du contrat d'infogérance du WMS (APPLICA Services)

*Contrat `TMA-WMS-2021`, signé le 8/11/2021, conclu pour quatre ans puis renouvelable par périodes d'un an — **prochaine échéance de renouvellement : 8 novembre 2026**. Prestataire : APPLICA Services, **partie prenante critique n°2** de l'écosystème (exposition 16, la plus forte du groupe — atelier 3). Exigences à écrire au cahier des charges du renouvellement, dont APPLICA devra démontrer la couverture dans son **plan d'assurance sécurité (PAS)**. Formulées comme **exigences vérifiables**, pas comme clauses juridiques : elles se démontrent, preuve datée à l'appui. On part du scénario ou de l'écart, on remonte à l'exigence.*

### 3.1 Exigences vérifiables tracées

| Exigence | Formulation vérifiable | Justification — scénario stratégique (atelier 3), écart d'audit (séance 4), ou silence du contrat |
|---|---|---|
| **Réversibilité** | Un **plan de réversibilité** est annexé au contrat et a été **exécuté à blanc dans les 12 derniers mois** (rapport daté) : export de la base et de la configuration du WMS dans un **format documenté et réimportable**, état des versions et correctifs de l'éditeur appliqués, documentation d'exploitation, **code source des développements spécifiques** (art. 2), **interface d'approvisionnement d'urgence Santé comprise**. Une **restauration complète du WMS depuis les sauvegardes est démontrée au moins 1×/an en présence du client** (délai constaté vs. RTO). **RTO et RPO du WMS et de l'interface Santé sont chiffrés au contrat**. En fin de contrat : **restitution puis destruction certifiée** du compte `svc-applica`, des accès aux partages et de toute donnée détenue, sous 30 jours. | **Scénario stratégique SS1** (chemin `AP.01` — chiffrement du WMS par la TMA, `ER1` gravité **G4**) : la reprise n'est **pas démontrée** — sauvegardes quotidiennes **jamais restaurées** (pack §5.4), RTO/RPO **non contractualisés** (D2, lacune n°5). **Silence du contrat** : l'art. 8 ne porte qu'un préavis de résiliation de 6 mois — le client ne peut pas *reprendre la gestion de la fonction externalisée pour l'exploiter lui-même ou la confier à un tiers de son choix* (guide ANSSI). |
| **Droit d'audit** | Le client, ou un tiers qu'il mandate, peut **vérifier à tout moment et au moins 1×/an** que les exigences de sécurité sont satisfaites — sur les accès d'APPLICA au WMS, sur son **processus de mise à jour et de livraison**, et sur son **propre environnement de production et de fabrication** des livrables. APPLICA **remet chaque année** le résultat de son **dernier audit indépendant** (certificat ISO/IEC 27001 ou rapport équivalent) et le résultat d'un **test d'intrusion annuel** de la surface exposée du WMS. Sur demande et **sous 5 jours ouvrés, il remet sous forme nominative** la liste des personnes ayant accès à `svc-applica` et le journal daté de leurs interventions. | **Scénario SS1** chemin `AP.01` : **mécanisme NotPetya** — la charge malveillante transite par la **chaîne de livraison d'APPLICA** ; sans droit d'audit sur cet environnement, le client ne peut pas le vérifier. **Écart `C4`** (non-conformité majeure de D4) : compte de domaine partagé, imputabilité inopérante ; l'audit interne du holding a demandé la liste nominative — il a reçu *un nom de compte, aucun nom de personne* (pack §3). **Silence** : l'art. 5 est une auto-déclaration (« règles de l'art »). |
| **Notification d'incident** | APPLICA **notifie le client sous 24 heures** : tout incident de sécurité touchant le WMS ou ses données ; toute **compromission — suspectée ou avérée — de son propre environnement de production ou de livraison** ; tout **usage anormal du compte `svc-applica`**. **Contact nommé de chaque côté et canal écrit** ; **rapport post-incident sous 5 jours ouvrés avec chronologie**. APPLICA **transmet en continu les journaux du WMS et de ses interventions au SOC du groupe** dans un format exploitable. | **Scénario SS1** — « rien ne le détecte » : le SOC ne reçoit **aucun journal du WMS** (pack §6), **aucune procédure d'incident** n'existe (pack §5.6, arrêt d'avril « chacun a appelé qui il pouvait, personne n'a tenu de chronologie »). **Écart `A.8.15`** (D4, partiellement couvert). **Directive `PSSI-CADRE-INC-01`** (< 2 h en interne). **Silence** : le contrat est muet — l'astreinte 24 h/24 de l'art. 2 couvre la panne, pas l'attaque. |
| **Traçabilité et comptes nominatifs** | **Comptes individuels nominatifs** pour toute personne d'APPLICA ou de ses sous-traitants intervenant sur le WMS — **aucun compte partagé**. **Journalisation par utilisateur nommé** transmise au SOC. La liste des porteurs est **vérifiable à tout moment** contre les comptes réellement actifs. Le client tient un **registre nominatif des comptes de service et à privilèges, revu trimestriellement**. | **Scénarios SS1 et SS2** : l'intrusion (SS1) comme l'exfiltration (SS2) sont **indistinguables d'une intervention de maintenance** tant que le compte est partagé et non journalisé nominativement. **Écart `C4`** (non-conformité **majeure**). **Mesure `M4` de D4**, déjà votée (propriétaires Maxime + Miguel, échéance **8/11/2026**). **Énoncé d'appétence n°2 de D5**. **Silence** : l'art. 3 crée `svc-applica` partagé, liste « sur demande » seulement. |
| **Maîtrise de la sous-traitance** | APPLICA **déclare en annexe la liste de ses sous-traitants** ayant accès — direct ou indirect — au WMS, à ses données ou au compte `svc-applica`, et la **met à jour avant tout changement**. Le client peut **récuser sous 15 jours** un sous-traitant ne présentant pas de garanties suffisantes. **Toutes les exigences du contrat sont répercutées** aux sous-traitants, APPLICA restant **seul responsable** devant le client. **Aucun accès hors UE ou depuis un lieu non listé** sans autorisation préalable. | **Scénario SS2** chemin `AP.01` : l'accès passe par un **sous-traitant d'un développement spécifique « sur devis »** (art. 2), **non déclaré et non récusable** aujourd'hui. **Silence** : l'art. 2 ouvre les développements spécifiques « sur devis » sans aucun encadrement. **Référentiel** : contrôles `A.5.19` à `A.5.22` (relations fournisseurs, accord de sécurité, chaîne d'approvisionnement TIC, surveillance des services fournisseurs — CM séance 6). |

### 3.2 Dispositif de surveillance du tiers — ce qui tient les exigences vivantes après signature

*Le guide le dit : un contrat parfait sur le papier ne vaut que le comité de suivi qui le tient vivant et les audits qui le vérifient.*

| Élément | Contenu attendu |
|---|---|
| **Indicateur 1** | *Part des interventions d'APPLICA tracées par compte nommé.* Source : journaux transmis au SOC. Fréquence : mensuelle. Cible : 100 % ; toute valeur < 100 % ouvre un point au comité de suivi. |
| **Indicateur 2** | *Délai réel de pose des correctifs de l'éditeur du WMS,* mesuré de la publication à l'installation, vs. `PSSI-CADRE-COR-01` (< 14 jours). Source : rapports d'intervention d'APPLICA + inventaire des versions. Fréquence : trimestrielle. |
| **Indicateur 3** | *Écart entre le nombre de comptes actifs sur `svc-applica` et la liste nominative fournie par APPLICA.* Source : annuaire du client + liste APPLICA. Fréquence : trimestrielle. Cible : 0. |
| **Comité de suivi** | Trimestriel. Participants : RSSI Groupe, DSI de la filiale, responsable de compte APPLICA ; Audit interne du holding en invité. Y sont décidés : la revue des incidents et des accès du trimestre, l'avancement du plan de réversibilité, l'**escalade au ComEx si un indicateur dérive deux trimestres consécutifs** (art. 8 : remise de 10 % au deuxième trimestre de manquement — le comité en est le déclencheur documenté). |
| **Preuve due chaque année** *(sans être demandée)* | Le rapport du dernier audit indépendant d'APPLICA (ISO/IEC 27001 ou équivalent) ; le PV du **test de restauration complète du WMS** ; la liste nominative à jour des intervenants ; le journal annuel des mises à jour livrées (composants, dates, retours arrière éventuels). |
| **Ce qui reste au client** *(jamais délégué, même sous infogérance partielle)* | L'**acceptation du risque résiduel** (Direction Générale). La tenue du **registre nominatif des comptes de service et à privilèges** (mesure `M4`). La décision de **reprise ou de coupure de l'interface Santé** (`ARB-01`). La **validation des changements d'architecture** du WMS (l'art. 5 actuel ne prévoit qu'une information préalable — l'exigence la transforme en avis avec possibilité de refus). Le choix de **suspendre le flux de mise à jour** sans que la suspension constitue un manquement du client. |

---

## 4. L'étude EBIOS RM à l'appui (atelier 3, saisi au TP 1)

*Composant de D6 : l'export de l'étude enrichie de son écosystème coté et de ses scénarios stratégiques. Détail de la saisie : `Seance-6-TP-S6-05-feuille-de-travail-ecosysteme-et-scenarios.md`. État vérifié dans `translog-b` le 10/9/2026 (feuille `Seance-6-TP-S6-06-…` §5). Captures : `../3-Evidence/S6-05-*` (saisie) et `../3-Evidence/S6-06-rapport-etude-EBIOS-RM-ateliers-3-4.jpg` + `S6-06-ecosystem-criticites-5PP-2-selected.jpg` (rapport de l'étude).*

| Objet | État dans `translog-b` |
|---|---|
| **Parties prenantes** | **5** créées et cotées sur les quatre critères du guide (`Dependency`, `Penetration`, `Maturity`, `Trust`), criticité calculée par l'outil : PP2 · intégrateur des automates = **12,0** ; PP1 · APPLICA = **8,0** ; PP5 · Santé = 1,0 ; PP3 · opérateur des liaisons = 0,5 ; PP4 · client pharmaceutique = 0,44. **Seuil de criticité écrit** : dangerosité ≥ 4,0 → **PP1 et PP2 cochées `Selected`**. |
| **Scénarios stratégiques** | **SS1** (couple SR/OV n°1, `Organized crime`) → **ER1**, gravité **`Critical` / G4** affichée depuis l'événement redouté ; deux chemins d'attaque `Selected` : `AP.01` (par APPLICA, mécanisme NotPetya), `AP.02` (par l'intégrateur, box 4G — **résolution de la mise en réserve du couple n°2 de D5**). **SS2** (couple SR/OV n°4, `Competitor`) → **ER4**, gravité **`Important` / G3** ; un chemin `AP.01` par APPLICA. |
| **Scénario opérationnel** | **1**, rattaché au chemin `AP.01` de SS1 (le plus préoccupant), sept actions élémentaires sur les biens supports nommés, vraisemblance **V3 `Very likely`** justifiée par le socle de D5 et ses limites. Amorce de l'atelier 4 ; le complet est la substance de la séance 7. |

**Chaque exigence de la pièce 2 se trace à un objet de cette étude** : c'est la colonne « justification » du §3.1, et c'est le critère « zéro exigence orpheline ».

---

## 5. Ce qui reste — séance 7

- **Atelier 4 complet** : un scénario opérationnel pour chaque chemin d'attaque `Selected` (aujourd'hui : un seul, sur `AP.01` de SS1).
- **Atelier 5** : le registre complet des risques coté sur les échelles **inchangées** de D5 (§1), le seuil `Low`/`Medium`/`High` appliqué, le plan de traitement chiffré sur trois ans — c'est **D7**.
- **Valeurs résiduelles des parties prenantes** : à renseigner quand les mesures de maîtrise du tiers (les exigences de la pièce 2, l'accord inter-filiales) seront décidées et datées.
- **Couple SR/OV n°3 (`Avenger`)** et **événements redoutés ER3 / ER5 sans source de risque retenue** (D5 §4) : ER5 est traité ici comme **projet** (pièce 1) ; ER3 (chaîne du froid) et le couple n°3 restent à reprendre en séance 7.

---

> **Preuves à l'appui** : fiche de travail `Seance-6-TP-S6-06-fiche-projet-et-exigences-tiers.md` (méthode, répartition nominative, écarts outil, vérification de l'instance) · TD 2 `../4-Working-notes/Seance-6-TD-S6-03-management-des-tiers-infogerance-ateliers-3-4.md` (la carte de dangerosité longue et le scénario stratégique) · TD 1 `../1-CISO-desk/Seance-6-TD-S6-01-attaque-par-la-chaine-d-approvisionnement.md` (les seize dépendances) · extrait de contrat `../../../../S6 - Sources/Extrait-contrat-Logistique-TMA-WMS.pdf` · CM `../../../../S6 - Sources/CM/Security by Design and Integration into Projects _ Lockbay Academy.pdf` · étude EBIOS RM dans `translog-b` (5 parties prenantes cotées, 2 scénarios stratégiques, 3 chemins d'attaque, 1 scénario opérationnel) · captures `../3-Evidence/S6-05-*` (saisie du TP 1) et `../3-Evidence/S6-06-*` (rapport de l'étude, atelier 3-4).
