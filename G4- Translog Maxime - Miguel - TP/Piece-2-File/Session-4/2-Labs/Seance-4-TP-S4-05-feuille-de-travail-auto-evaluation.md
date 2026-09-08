# FEUILLE DE TRAVAIL — Séance 4, TP 1 : auto-évaluation de MERIDIAN Logistique dans CISO Assistant

**Groupe 4 (Translog)** · instance `translog-b` (https://translog-b.lockbay.eu) · périmètre `MERIDIAN-LOGISTIQUE/MERIDIAN-LOGISTIQUE-FINAL`
**Évaluation de conformité utilisée** : `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, créée en séance 3 (S3-05), **remplie aujourd'hui** — aucun objet recréé ni renommé.
**Auteurs (comptes nominatifs)** : Miguel.monereodelasota@ynov.com, maximebatista18@gmail.com.
**Correspondance de nom** : le PDF du TP désigne l'évaluation « MERIDIAN-SUBSIDIARY - ISO/IEC 27001:2022 - initial assessment » ; c'est un libellé générique de l'énoncé — l'objet réel du groupe, `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, n'a pas été renommé.

---

## 0. Préalable — gradation TD 2

Fait avant l'ouverture de l'instance : `../4-Working-notes/Seance-4-TD-S4-03-gradation-des-constats.md`. Les trois constats Logistique retenus :

| Réf. | Gradation |
|---|---|
| **C3** | Non-conformité majeure — réseaux bureautique/industriel interconnectés, sans segmentation |
| **C4** | Non-conformité majeure — compte de domaine partagé avec la TMA du WMS, porteurs inconnus |
| **C7** | Conforme *(sur ce flux)* — VLAN + pare-feu Logistique↔Santé, seul cloisonnement du groupe, sur un flux suspendu depuis trois mois |

---

## 1. Cadrage

**Périmètre évalué** : MERIDIAN Logistique — six entrepôts E1–E6, WMS, ~300 scannettes, automates de tri E2/E3/E4, chaîne du froid ; actifs cartographiés en séance 2 (`LOG-PA-01` à `04`, `LOG-SA-01` à `13`). **N'est pas évalué** : les trois autres filiales du groupe, et les 111 exigences ISO/IEC 27001:2022 non retenues dans ce sous-ensemble.

**Critères** : les douze exigences ci-dessous, extraites du référentiel ISO/IEC 27001:2022 importé en séance 3, complétées des directives de la PSSI cadre codifiées en séance 1 — `PSSI-CADRE-ACC-01` (MFA sur tout accès distant et tout privilège d'administration), `ACC-02` (revue trimestrielle des privilèges sur les bases métier), `INC-01` (notification d'incident majeur au RSSI Groupe sous 2 h), `JRN-01` (collecte des journaux vers le SOC centralisé), `COR-01` (correctif critique sous 14 jours).

**Règle de preuve** : aucune exigence déclarée *couverte* sans preuve nommée ; le doute se déclare *non évalué*. Question de contrôle avant chaque « couvert » : *quelle preuve un auditeur indépendant accepterait-il demain matin ?*

---

## 2. Mapping des statuts (relevé à l'écran, `translog-b`)

L'instance croise un **statut d'avancement** et un **résultat** :

| Statut d'avancement (outil) | Utilisé ici |
|---|---|
| To do / In progress / In review / **Done** | **Done** pour les douze exigences évaluées — y compris A.6.3, dont la conclusion honnête est « non évalué » : l'aveu est un résultat de travail, pas une case laissée vide |

| Statut du module | Résultat dans l'outil *(relevé exact)* |
|---|---|
| Couvert | **Compliant** |
| Partiel | **Partially compliant** |
| Non couvert | **Non compliant** |
| Non évalué | **Not assessed** *(avancement passé à Done + justification écrite, pour que l'aveu soit visible)* |
| Non applicable | **Not applicable** |

> Les statuts vont dans l'outil ; les justifications vont dans le champ *Observation* de chaque exigence — c'est ce que voit le correcteur dans l'export.

---

## 3. Les douze exigences — statuts saisis et justifications

| Réf. | Exigence | Statut saisi | Justification (dans le champ Observation de l'outil) | Actifs |
|---|---|---|---|---|
| **A.5.9** | Inventaire des informations et actifs associés | **Partially compliant** | Repérage sans notation (S3-05 Ex.3). Preuve existante : inventaire priorisé et Top 5 des actifs critiques de la séance 2 (S2-01, S2-05). S4-05 : statut confirmé. Manque : aucun inventaire transmis par la filiale, nombre exact de scannettes inconnu, aucun schéma réseau, automates non inventoriés, règle de tenue à 30 jours écrite mais non appliquée | SA-01…SA-13 |
| **A.5.15** | Contrôle d'accès | **Non compliant** | Constat C4 (TD 2, majeure) + pack §5.2 : compte de domaine partagé avec la TMA du WMS, porteurs inconnus ; intégrateur en 4G hors supervision ; aucune revue de privilèges (ACC-02 non tenue) | SA-01, SA-03, SA-10 |
| **A.5.16** | Gestion des identités | **Non compliant** | Constat C4 : l'identité n'est pas unique et attribuable — l'audit interne du holding a demandé la liste nominative des porteurs et a reçu un nom de compte, aucun nom de personne | SA-10 |
| **A.5.17** | Informations d'authentification | **Non compliant** | Pack §5.3 : le compte de service WMS↔automates porte le même mot de passe sur les six entrepôts depuis 2019, en clair dans un fichier de configuration, connu de tous en Exploitation | SA-04 *(rang 2 du Top 5)* |
| **A.5.19** | Sécurité dans les relations fournisseurs | **Non compliant** | Constat C4 + pack §2 : contrat de l'intégrateur sans clause de réversibilité ni exigence de sécurité ; contrat de TMA sans journalisation nominative | SA-03, SA-10 |
| **A.5.22** | Surveillance et gestion des changements des services fournisseurs | **Non compliant** | Pack §4 : « la TMA fait les mises à jour la nuit, quand elle veut, on l'apprend le matin » — aucun contrôle de changement, aucune revue de service ; l'intégrateur traite les réglages des automates comme sa propriété industrielle | SA-01, SA-03 |
| **A.6.3** | Sensibilisation, formation à la sécurité | **NOT ASSESSED** ✅ | Aucune preuve disponible dans un sens ni dans l'autre : ni sensibilisation, ni support, ni feuille d'émargement mentionnés, et la question n'a pas été posée à la filiale. Statut honnête, assumé plutôt qu'estimé | — |
| **A.8.2** | Droits d'accès à privilèges | **Non compliant** | Constat C4 + pack §5.2/5.3 : compte de domaine partagé et compte de service partagé, aucun inventaire des comptes à privilèges, aucune revue trimestrielle (ACC-02) | SA-04, SA-10 |
| **A.8.5** | Authentification sécurisée | **Non compliant** | PSSI-CADRE-ACC-01 exige la MFA sur tout accès distant et tout privilège d'administration : compte partagé pour la TMA, liaison 4G hors supervision pour l'intégrateur, secret de compte de service en clair. Débattu : « non évalué » défendable faute de preuve directe d'absence de MFA, mais un secret partagé en clair suffit à établir l'écart | SA-01, SA-03, SA-04 |
| **A.8.8** | Gestion des vulnérabilités techniques | **Non compliant** | COR-01 (correctif sous 14 jours) n'est ni mesuré ni mesurable : mises à jour du WMS décidées par la TMA sans préavis, automates sous propriété industrielle de l'intégrateur, aucun suivi des vulnérabilités. Débattu : « non évalué » défendable sur le délai ; « non couvert » l'est sur l'absence de processus | SA-01, SA-03 |
| **A.8.15** | Journalisation | **Partially compliant** | Ce qui existe : le SOC du groupe reçoit les journaux du réseau bureautique (JRN-01 amorcée). Ce qui manque : rien des automates, rien de la liaison 4G, rien du WMS lui-même — l'arrêt d'avril l'a prouvé, personne n'a pu tenir de chronologie | SA-01, SA-03 |
| **A.8.22** | Cloisonnement des réseaux | **Non compliant** | Constat C3 (majeure) : réseaux bureautique et industriel interconnectés, sans segmentation, sur les six sites. Nuance écrite : le VLAN + pare-feu du flux Santé (constat C7, conforme sur ce flux) est le seul cloisonnement du groupe, mais il porte sur un flux suspendu depuis trois mois — un point conforme hors périmètre utile ne couvre pas l'exigence | SA-03, SA-12 |

**Contrôle de traçabilité** : C3 → A.8.22 ; C4 → A.5.15 / A.5.16 / A.5.19 / A.8.2 ; C7 → nuance de A.8.22. Les trois constats gradués à midi sont retrouvés dans la grille.

**Résultat de la saisie, vérifié dans l'outil (Table mode / donut de conformité)** : **0 couvert · 2 partiels (16.6 %) · 9 non couverts (75 %) · 1 non évalué (8.3 %)**. Sur les 123 exigences totales du référentiel, cela se lit : 91.06 % non évalué (112, dont les 111 hors périmètre + A.6.3), 7.32 % non conforme (9), 1.62 % partiellement conforme (2) — chiffres confirmés à l'écran, page de présentation de l'audit.

---

## 4. Les quatre mesures appliquées (Exercice 3)

Saisies dans l'outil, chacune rattachée à l'exigence en écart, avec propriétaire (compte nominatif de l'instance) et échéance.

| # | Constat | Type | Rattachée à | Propriétaire (assigné dans l'outil) | Échéance |
|---|---|---|---|---|---|
| **M1** | C3 | **Correction** | A.8.22 | Miguel.monereodelasota@ynov.com *(DSI filiale, avec le Responsable Exploitation)* | 12/7/2027 — date fixe hors pic (le pic dure 10 mois sur 12) |
| **M2** | C3 | **Action corrective** | A.8.22, A.5.19 | maximebatista18@gmail.com + Miguel.monereodelasota@ynov.com *(DSI filiale pour le schéma, Direction de la filiale pour le contrat)* | 8/12/2026 — schéma à 3 mois, clause à l'échéance contractuelle |
| **M3** | Pack §5.3 | **Correction** | A.5.17, A.8.2 | Miguel.monereodelasota@ynov.com *(DSI filiale)* | 8/11/2026 — date fixe, coordonnée avec la TMA |
| **M4** | Pack §5.3 | **Action corrective** | A.8.2, A.5.19, A.5.15 | maximebatista18@gmail.com + Miguel.monereodelasota@ynov.com *(RSSI de filiale pour le registre, DSI filiale pour la TMA)* | 8/11/2026 — registre à 2 mois, première revue au trimestre suivant |

**Contenu SMART de chaque mesure** (texte intégral saisi dans le champ *Description* de l'applied control) :

- **M1** — Placer les automates de E2/E3/E4 sur un VLAN dédié, filtrage en défaut-refus à la frontière IT/OT, matrice de flux documentée. *Mesurable* : 0 route entre VLAN bureautique et VLAN industriel hors matrice, vérifié sur extraction de configuration.
- **M2** — Traiter la cause : produire le schéma réseau des six sites et soumettre tout raccordement d'équipement industriel à un avis d'architecture écrit de la DSI filiale avant mise en service, clause portée au contrat de l'intégrateur. *Mesurable* : schéma daté et versionné + 100 % des raccordements passés par l'avis, contrôlé en revue trimestrielle.
- **M3** — Remplacer le secret partagé par six secrets distincts, retirés des fichiers de configuration en clair, déposés dans un coffre à secrets, rotation à la mise en œuvre. *Mesurable* : 6 secrets distincts, 0 occurrence en clair trouvée par recherche sur les fichiers de configuration des six sites.
- **M4** — Traiter la cause : tenir un registre nominatif des comptes de service et à privilèges (propriétaire, usage, date de dernière rotation), rotation annuelle, revue trimestrielle alignée sur ACC-02 ; exiger contractuellement de la TMA une journalisation par utilisateur nommé. *Mesurable* : registre à jour à chaque revue trimestrielle, écart au calendrier mesuré.

**Test SMART** : les quatre mesures passent — aucune ne se reformule en objectif non mesurable ou non daté (le piège du TP, « sensibiliser les équipes », est évité).
**Distinction correction / action corrective respectée** : M1/M3 font disparaître l'écart constaté ; M2/M4 traitent sa cause. Jamais deux fois la même mesure sur un même constat.

---

## 5. Synthèse et lecture de maturité (Exercice 4)

**a) Comptage par thème** (sur les douze exigences évaluées) :

| Thème | Exigences | Couvert | Partiel | Non couvert | Non évalué |
|---|---|---|---|---|---|
| **Organisationnel (A.5)** | A.5.9 · 5.15 · 5.16 · 5.17 · 5.19 · 5.22 | 0 | 1 | 5 | 0 |
| **Personnes (A.6)** | A.6.3 | 0 | 0 | 0 | 1 |
| **Technologique (A.8)** | A.8.2 · 8.5 · 8.8 · 8.15 · 8.22 | 0 | 1 | 4 | 0 |
| **Total** | 12 | **0** | **2** | **9** | **1** |

**b) Lecture de maturité, en deux phrases** :
*Là où la filiale est outillée* : sur ce que le RSSI Groupe a lui-même construit — la cartographie et le référentiel — pas sur ce qu'elle exploite. *Là où elle vit de déclarations* : la relation fournisseur, les sauvegardes « confirmées par la TMA » et jamais restaurées, l'inventaire « dans la tête du Responsable Exploitation ». *Là où elle est aveugle* : le périmètre industriel — automates, liaison 4G, WMS — dont aucun journal ne remonte au SOC, et la sensibilisation, dont nous ne savons rien.

**c) Le biais de notre propre évaluation** : la ligne la moins certaine est **A.5.9 en « partiel »**. La preuve invoquée est en partie notre propre cartographie, produite par nous et non vérifiée par un tiers, et la règle de tenue à 30 jours qui la maintient est une directive écrite en séance 2, jamais appliquée — une intention, pas un fait observable. Un auditeur indépendant pourrait la rétrograder en « non couvert ». L'écrire nous-mêmes coûte moins cher que de se le faire dire.

---

## 6. Extraction pour le rapport (Exercice 5)

**Liste des écarts** (statuts *non couvert* et *partiel*, avec constat associé et gradation retenue à midi) :

| Exigence | Statut | Constat / pack | Gradation TD 2 |
|---|---|---|---|
| A.5.9 | Partiel | — (cartographie S2) | — |
| A.5.15 | Non couvert | C4 | Non-conformité majeure |
| A.5.16 | Non couvert | C4 | Non-conformité majeure |
| A.5.17 | Non couvert | Pack §5.3 | — (hors TD, retenu séance 2 — Top 5 rang 2) |
| A.5.19 | Non couvert | C4 + pack §2 | Non-conformité majeure |
| A.5.22 | Non couvert | Pack §4 | — (hors TD) |
| A.8.2 | Non couvert | C4 + pack §5.2/5.3 | Non-conformité majeure |
| A.8.5 | Non couvert | ACC-01 + pack §5.3 | — (débattu) |
| A.8.8 | Non couvert | COR-01 | — (débattu) |
| A.8.15 | Partiel | JRN-01 | — (hors TD) |
| A.8.22 | Non couvert | C3 (+ nuance C7) | C3 : Non-conformité majeure · C7 : Conforme (sur ce flux) |

**Liste « angles morts »** (les *non évalué*, à part) :
- **A.6.3** — Sensibilisation et formation. Aucune preuve, ni dans un sens ni dans l'autre. À poser explicitement à la filiale avant le prochain cycle.

**Contrôle de complétude** : les trois constats gradués à midi pour Logistique (**C3, C4, C7**) sont tous retrouvables dans la liste des écarts ci-dessus. Aucun n'est perdu.

---

## 7. Pièges vérifiés

- ☑ Aucun objet des séances 2/3 recréé ou renommé (évaluation, périmètre, actifs retrouvés tels quels)
- ☑ Aucune exigence déclarée « couverte » de manière déclarative — 0 couvert sur les douze
- ☑ Aucun chiffre de risque saisi ni ici ni dans l'outil — la gravité n'entre pas dans la gradation
- ☑ Correction et action corrective jamais confondues (M1/M3 ≠ M2/M4)
- ☑ C7 écrit avec sa limite (conforme sur un flux suspendu, pas sur le périmètre)
- ☑ Aucune gradation TD 2 modifiée entre le matin et cette feuille
- ☑ Tout saisi sous compte nominatif (Miguel.monereodelasota@ynov.com, maximebatista18@gmail.com) — F5 fermé

---

*Feuille de travail remplie le 8 septembre 2026, séance 4, TP 1. Alimente le TP 2 (D4, sections 3/4/5/6) et la 4ᵉ sous-section de la note de stratégie.*
