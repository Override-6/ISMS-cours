# Feuille de travail — Séance 6, TP 2 : fiche projet, exigences applicables aux tiers, assemblage de D6

**Groupe 4 (Translog)** · instance `translog-b` (https://translog-b.lockbay.eu)
**Domaine** `MERIDIAN-LOGISTIQUE` · **étude** `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1`
**Date** : 10 septembre 2026 · **compte utilisé pour la vérification et l'export** : `maximebatista18@gmail.com` (compte nominatif, jamais `admin@lockbay.eu`)
**Matière** : TD 2 (`../4-Working-notes/Seance-6-TD-S6-03-management-des-tiers-infogerance-ateliers-3-4.md`), TP 1 (`Seance-6-TP-S6-05-feuille-de-travail-ecosysteme-et-scenarios.md`), extrait de contrat `TMA-WMS-2021`, CM séance 6 (six jalons, trois régimes), énoncé du TP 2 (gabarits), D2, D4, D5.

> **Ce fichier n'est pas le livrable.** C'est la trace du TP 2 : le choix du projet et sa justification, les écarts outil, la répartition nominative, le geste sur la capture manquante de la séance 5. Le livrable est **D6** (`D6-tiers-et-projets.md`), et la note de stratégie gagne sa sous-section 6.

---

## 0. Répartition nominative

| Objet | Fait par |
|---|---|
| Choix du projet de la fiche projet + rédaction de la fiche (pièce 1 de D6) | Maxime |
| Exigences applicables au contrat APPLICA + dispositif de surveillance (pièce 2 de D6) | Maxime |
| Assemblage de D6, traçage des exigences aux objets de l'étude | Maxime |
| Sous-section 6 de la note de stratégie | Maxime |
| Vérification de l'état de l'étude dans `translog-b` + export du rapport pour D6 | Maxime |

TP 1 (saisie de l'écosystème et des scénarios) : fait par Miguel Monereo le 10 septembre 2026 — voir `Seance-6-TP-S6-05-feuille-de-travail-ecosysteme-et-scenarios.md`.

---

## 1. Pièce 1 — Le choix du projet, et pourquoi celui-là

**L'énoncé demande « un projet réel du pack de filiale, celui que le pack porte, cadré comme s'il était lancé aujourd'hui ».** Le CM donne le modèle : pour le cluster Éducation & Territoires, c'est la plateforme pédagogique qui se raccorde aux bases administratives de Territoires — un flux qui **traverse une frontière de filiale** ; *« Santé et Logistique appliqueront la même grille au projet de leur propre pack »*.

**Projet retenu : la reprise sécurisée du flux d'approvisionnement d'urgence MERIDIAN Logistique → MERIDIAN Santé.** Quatre raisons :

1. **C'est le projet que le pack de filiale porte** qui traverse une frontière de filiale — l'exact équivalent, côté Logistique, du cas du CM. Pack §6 « Ce qui franchit la frontière → Vers Santé » ; reference pack §5.1 (« le seul actif dont deux filiales dépendent »).
2. **C'est une décision réelle que le groupe a devant lui** : le flux est **coupé depuis trois mois** à la demande de la RSSI de Santé (« leur matériel n'est pas fiable ») ; le Pharmacien chef de Santé en demande la reprise (« on gère avec des commandes manuelles, ça ne tiendra pas l'hiver »). C'est un arbitrage `ARB-01` de D1.
3. **Security by Design est exactement ce qui manque** : Santé a coupé pour une raison de sécurité ; la reprise doit **démontrer** des exigences, pas les affirmer. Cadrer la reprise comme un projet lancé aujourd'hui, avec les six jalons, répond à l'objection au lieu de la contourner.
4. **Il porte l'événement redouté `ER5` de D5** (Critique, sans source de risque retenue à ce jour — D5 §4). Le traiter comme **projet** est une réponse méthodologiquement propre à cette recommandation de D5, sans forcer un couple SR/OV.

**Projet écarté, et pourquoi** : l'**homologation du WMS et de ses échanges avec le portail du client pharmaceutique**, cadrée mais incomplète en séance 4 (D4 §6). C'est un bon candidat, mais (a) c'est la continuation d'un cadrage déjà ouvert, pas un projet « lancé aujourd'hui », (b) il ne traverse pas une frontière de filiale, et (c) la pièce 2 de D6 traite déjà la relation WMS ↔ APPLICA — la fiche projet apporte plus en couvrant un terrain distinct (le flux inter-filiales). À reprendre en séance 7 si le registre l'exige.

**Régime du projet** : mixte, explicité ligne par ligne dans D6 §2.3 — développer/exploiter en interne (VLAN, pare-feu, parc scannettes), faire faire (correction de l'interface, contrat APPLICA art. 2), partenaire (système de Santé). Aucun des trois régimes du CM ne le décrit seul, et le dire est le critère de l'énoncé.

**Jalon M4 sous forme d'autorisation** : l'énoncé le prévoit — *« pour un système soumis à autorisation, le critère de M4 est la décision d'autorisation prononcée par l'autorité désignée en séance 4 »*. Ici l'autorité n'est pas la DSI d'une filiale mais l'instance qui engage le groupe sur un flux inter-filiales (D6 §2.5) : la décision de reprise signée des deux filiales, sous l'acceptation du risque résiduel par la DG.

---

## 2. Pièce 2 — Les exigences : rien de neuf, tout tracé

Les cinq familles et leurs exigences vérifiables **sont celles du TD 2, exercice 1** (`Seance-6-TD-S6-03-…`, §« Les exigences vérifiables manquantes, par famille »). Le TP 2 ne les réécrit pas : il les **trace**, comme l'énonce le demande (« chaque exigence tracée à un scénario stratégique du TP précédent, un écart de l'audit de la séance 4, ou un silence du contrat consigné dans le pack — la colonne justification est le cœur de l'exercice »).

| Famille | Tracée à… |
|---|---|
| Réversibilité | SS1 (`AP.01`, `ER1` G4 — reprise non démontrée) + D2 lacune n°5 (RTO/RPO) + silence art. 8 (préavis ≠ réversibilité) |
| Droit d'audit | SS1 `AP.01` (NotPetya — chaîne de livraison d'APPLICA) + écart `C4` + silence art. 5 (auto-déclaration) |
| Notification d'incident | SS1 « rien ne le détecte » + écart `A.8.15` (SOC ne reçoit rien du WMS) + `PSSI-CADRE-INC-01` + silence (contrat muet) |
| Traçabilité / comptes nommés | SS1 **et** SS2 (intrusion / exfiltration indistinguables d'une maintenance) + écart `C4` **majeur** + mesure `M4` de D4 (8/11/2026) + silence art. 3 (`svc-applica` partagé) |
| Maîtrise de la sous-traitance | SS2 `AP.01` (sous-traitant d'un développement « sur devis », non déclaré) + silence art. 2 + contrôles `A.5.19`–`A.5.22` |

**Dispositif de surveillance** (indicateurs, comité de suivi, preuve annuelle, ce qui reste au client) : repris du TD 2 §« Ce qui maintient ces exigences en vie après signature », mis au gabarit de l'énoncé (Indicateur 1/2/3, Follow-up committee, Evidence due every year, What stays with the client). Rien inventé : les trois indicateurs sont des métriques de directives déjà écrites (`COR-01`, `INC-01`, la moitié « comptes » de `ACC-02`).

**Le contrat vient à renouvellement le 8 novembre 2026** (art. 7 : 4 ans depuis le 8/11/2021, puis périodes d'un an) — les exigences vont *« au cahier des charges de son renouvellement ou de son avenant »*, exactement la fenêtre de l'énoncé. C'est aussi la date des mesures `M3` et `M4` de D4.

---

## 3. Assemblage de D6 — d'où vient chaque partie

| Section de D6 | Source |
|---|---|
| 1. Objet et principe | TD 1 (16 dépendances) + TD 2 (atelier 3) + guide ANSSI infogérance (cité au TD 2) |
| 2. Fiche projet (M1–M6, responsabilités, arbitrages) | CM séance 6 (six jalons, trois régimes, propriétaire unique) + pack §6, §7 + reference pack §5.1 + D2 §5 + D1 (`ARB-01`, RACI) + D4 §6 (forme d'autorisation) + D5 (`ER5`, `ER2`) |
| 3.1 Exigences vérifiables tracées | TD 2 exercice 1 + extrait de contrat article par article + scénarios SS1/SS2 de l'étude + écarts `C3`/`C4`/`A.8.15`/`A.5.17` de D4 + mesures `M3`/`M4` de D4 |
| 3.2 Dispositif de surveillance | TD 2 § surveillance + gabarit de l'énoncé + directives `PSSI-CADRE` de D1 |
| 4. Étude EBIOS RM à l'appui | Feuille de travail du TP 1 + captures `S6-05-*` + export généré aujourd'hui (§5 ci-dessous) |
| 5. Ce qui reste (S7) | Feuille de travail du TP 1 §6 + D5 §4 |

**Critère « zéro exigence orpheline » relu** : chacune des cinq familles porte une colonne « justification » non vide, adossée à un objet de l'étude, un écart de D4 ou un article du contrat. Chaque jalon M1–M6 porte un critère de passage **démontré par un fait** (test rejoué, PV signé, trace de présence), jamais par « la sécurité a été prise en compte ».

---

## 4. Écarts et points relevés

| # | Point | Traitement |
|---|---|---|
| 1 | L'énoncé du TP 2 parle du projet « du pack de filiale » au singulier — le pack en porte deux lisibles (flux Santé ; homologation WMS). | Choix tranché et **écrit** (§1) : le flux Santé, quatre raisons. L'homologation WMS reste disponible pour la séance 7. |
| 2 | La pièce 2 demande le contrat « du prestataire le plus exposé » — l'atelier 3 du TP 1 classe l'**intégrateur** (12,0) devant **APPLICA** (8,0) en dangerosité. | Pas de contradiction : « exposé » = **exposition** (dépendance × pénétration), et APPLICA a l'exposition la plus forte (**16**). L'intégrateur est le plus **dangereux** (fiabilité au plancher), APPLICA le plus **exposé**. Le module fournit le contrat d'APPLICA (`TMA-WMS-2021`) — c'est celui de la pièce 2. Les deux sont critiques ; l'intégrateur relève de la mesure `M2` de D4 (clause au contrat, 8/12/2026). |
| 3 | `ER5` (réappro Santé, Critique) était sans source de risque retenue dans D5, avec une recommandation d'« ajouter un couple pivot Logistique → Santé avant l'atelier 3 » (D5 §4). Le TP 1 ne l'a pas ajouté. | `ER5` est traité ici comme **projet** (fiche projet, pièce 1), réponse méthodologiquement propre. Le couple SR/OV « pivot Logistique → Santé » et le couple « fournisseur des sondes » (pour `ER3`) restent à trancher en séance 7, comme le note la feuille de travail du TP 1 §6. |
| 4 | Capture `S5-06-rapport-etude-EBIOS-RM-ateliers-1-2.jpg` citée par D5 et par la feuille S5-06, **absente** de `Session-5/3-Evidence/` (relevé au TP 1 §7-§8). | Traité aujourd'hui pendant que l'instance est ouverte — voir §5. |

---

## 5. Instance ouverte — vérification de l'état et export pour D6

*Connexion à `translog-b` le 10 septembre 2026, compte `maximebatista18@gmail.com`. Étude
`c42d064c-efe9-42f6-acdd-ef3b4b4fe636`, méthode `Manual`, domaine `MERIDIAN-LOGISTIQUE`.*

### 5.1 Vérification de l'état de l'étude — les objets du TP 1 sont bien là

| Compteur / objet attendu (feuille de travail TP 1 §7) | Constaté à l'écran | Conforme |
|---|---|---|
| `Assets` = 17 | 17 (carte *Summary* + rapport « Assets 17 ») | ✅ |
| `Feared events` = 7, tous `Selected` | 7 ; gravités : ER1 `Critical`, ER3 `Critical`, ER5 `Critical`, ER2 `Important`, ER4 `Important`, ER7 `Important`, ER6 `Significant` | ✅ (conforme à D5 §4) |
| `Audits` = 1 | 1 — `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, 0 conforme / 2 partiels / 9 non conformes | ✅ |
| `RO/TO couples` = 5, `Selected` sur 1 / 3 / 4 | rapport « RO/TO couples 3 » = les **3 retenus** (Organized crime *Highly relevant*, Avenger *Fairly relevant*, Competitor *Partially relevant*) ; les 5 restent dans l'atelier 2 | ✅ |
| `Stakeholders` = 5 créées, `Selected` sur PP1 (APPLICA) et PP2 (intégrateur) | liste écosystème = **5** ; compteur *Summary* « Stakeholders 2 » = les 2 `Selected` (APPLICA, intégrateur) — pastille verte à l'écran | ✅ |
| Criticités lues : PP2 = 12 · PP1 = 8 · PP5 = 1 · PP3 = 0,5 · PP4 = 0,44 | **exactement** ces cinq valeurs, colonne *Current criticality* ; résiduelles = identiques aux courantes (aucun traitement saisi) | ✅ |
| `Strategic scenarios` = 2 (SS1 → ER1 `Critical` ; SS2 → ER4 `Important`) | SS1 severity `Critical` (affichée depuis ER1), SS2 severity `Important` (depuis ER4) — jamais ressaisies | ✅ |
| Chemins d'attaque `Selected` = 3 (SS1 : `AP.01` APPLICA + `AP.02` intégrateur ; SS2 : `AP.01` APPLICA) | SS1 : « Chemin 1 - APPLICA… » + « Chemin 2 - Integrateur… box 4G » ; SS2 : « Chemin unique - APPLICA, extraction via sous-traitant non declare » | ✅ |
| `Operational scenarios` = 1, rattaché à `AP.01` de SS1, vraisemblance `Very likely` | AP.01 : `Likelihood: Very likely` × `Severity: Critical` = `Risk level: High` ; un *Operating mode* « kill chain complète via APPLICA » | ✅ |
| Atelier 5 vide | pas de registre de risques généré ; le rapport n'affiche que le *Treatment plan* hérité de l'audit (M1–M4 de D4, propriétaires nominatifs, échéances 8/11/2026 – 12/7/2027) | ✅ |

**Rien à corriger dans l'instance.** L'état correspond au TP 1 et au TD 2, chiffre pour chiffre.

### 5.2 Export du rapport de l'étude pour D6

| Geste | Fichier produit | Où |
|---|---|---|
| Capture pleine page du rapport de l'étude (`/ebios-rm/…/report/`) — les cinq ateliers, dont l'écosystème coté, les deux radars *Current / Residual* et les deux scénarios stratégiques avec leurs chemins | `S6-06-rapport-etude-EBIOS-RM-ateliers-3-4.jpg` (partie ateliers 3-5) | `Session-6/3-Evidence/` |
| Capture de la liste écosystème — 5 parties prenantes, colonne *Current criticality*, les 2 `Selected` en vert | `S6-06-ecosystem-criticites-5PP-2-selected.jpg` | `Session-6/3-Evidence/` |

*Le bouton « Export PDF » du rapport ouvre l'impression du navigateur (non exploitable en automatisation) ; la capture pleine page tient lieu d'export, comme l'énoncé l'autorise (« export **ou** capture »).*

### 5.3 Capture manquante de la séance 5 (écart n°4 ci-dessus) — traité

**Décision** : produire la capture, pas corriger la mention. Le rapport de l'étude contient désormais les
cinq ateliers ; sa **partie ateliers 1-2** (cadrage, 17 actifs, 7 événements redoutés cotés, audit
rattaché, les 3 couples SR/OV retenus) a été extraite de la capture pleine page et déposée sous le nom
exact que citent D5 (§ preuves à l'appui) et la feuille `S5-06` :
`Session-5/3-Evidence/S5-06-rapport-etude-EBIOS-RM-ateliers-1-2.jpg`. L'affirmation de D5 est désormais
tenue par une pièce. Aucun texte de D5 n'est modifié.

### 5.4 Doublons dans les captures du TP 1 — corrigés

Contrôle des empreintes des 11 fichiers `S6-05-*.jpg` : **deux paires étaient identiques au bit près** —
`S6-05-ex1-etude-reprise-compteurs.jpg` = `S6-05-atelier5-vide-et-compteurs.jpg`, et
`S6-05-ex2-5-parties-prenantes-liste.jpg` = `S6-05-ex3-carte-dangerosite-classement.jpg` (le même fichier
enregistré deux fois pendant le TP 1). Les quatre captures ont été **reprises** dans `translog-b` le
10/9/2026, chacune distincte : `ex1` = page de l'étude (5 ateliers + compteurs du *Summary*) ; `atelier5`
= cartes ateliers 4-5 montrant l'atelier 5 non généré + compteur *Applied controls (risk assessment) 0* ;
`ex2` = grille des 5 parties prenantes ; `ex3` = fiches de criticité de PP1 et PP2 + le *Ecosystem radar*.
Les objets de l'instance n'ont **pas** changé — seules les captures sont refaites.

---

## 6. Ce qui sort de ce TP

| Sortie | Où | État |
|---|---|---|
| **Livrable D6** `D6-tiers-et-projets.md` | `Session-6/2-Labs/` | fiche projet (M1–M6) + exigences APPLICA (5 familles tracées) + dispositif de surveillance + étude à l'appui + reste S7 |
| **Feuille de travail** (ce fichier) | `Session-6/2-Labs/` | choix du projet justifié, traçage, écarts, répartition nominative |
| **Sous-section 6 de la note de stratégie** | `Piece-1-Strategy-note/MERIDIAN-strategy-note.md` | « tiers et projets », une demi-page, articulée aux sous-sections 1, 2 et 5 ; journal des amendements complété (S6 tient la promesse de S5) |
| **Export de l'étude** | `Session-6/3-Evidence/` | `S6-06-rapport-etude-EBIOS-RM-ateliers-3-4.jpg` + `S6-06-ecosystem-criticites-5PP-2-selected.jpg` — composant « export » de D6 |
| **Capture manquante de la séance 5** | `Session-5/3-Evidence/` | `S5-06-rapport-etude-EBIOS-RM-ateliers-1-2.jpg` produite (écart n°4) |
| **README racine** | `README.md` | séance 6 close côté dossier — reste le CM |

**Fini quand** : D6 porte ses deux pièces cohérentes + l'export ; chaque exigence est tracée ; chaque jalon a un critère de passage factuel ; la sous-section 6 s'articule aux précédentes sans rien supprimer ; l'état de l'étude dans `translog-b` est vérifié et l'export est au dossier.

---

## 7. Critères de validation de l'énoncé — la relecture

- [ ] **Fiche projet** : sections remplies (objet/périmètre, données + DICT, régime, jalons, responsabilités, arbitrages) ; **six jalons** M1–M6, chacun avec **question + critère de passage vérifiable + livrable** ; critère de M4 = décision d'autorisation ; **un propriétaire ultime unique par jalon**
- [ ] Le projet est **réel et tiré du pack** ; le choix entre les deux candidats est **écrit et justifié**
- [ ] **Exigences** : les cinq familles (réversibilité, droit d'audit, notification, traçabilité/comptes nommés, maîtrise de la sous-traitance), **formulation vérifiable** par ligne, **colonne justification non vide** tracée à un scénario / un écart de S4 / un silence du contrat
- [ ] **Dispositif de surveillance** : 3 indicateurs (libellé, source, fréquence), comité de suivi (fréquence, participants, décisions), preuve annuelle non sollicitée, ce qui reste au client
- [ ] Les deux pièces sont **cohérentes entre elles** (le flux Santé de la fiche projet est nommé dans le périmètre du contrat APPLICA — art. 2)
- [ ] **Zéro exigence orpheline** ; on part du risque, on remonte à l'exigence
- [ ] **Export de l'étude** joint à D6 (parties prenantes cotées + scénarios stratégiques)
- [ ] **Sous-section 6** de la note : une demi-page, articulée aux sous-sections 1 (gouvernance), 2 (actifs critiques) et 5 (risques majeurs), **rien supprimé**, contrainte de longueur tenue
