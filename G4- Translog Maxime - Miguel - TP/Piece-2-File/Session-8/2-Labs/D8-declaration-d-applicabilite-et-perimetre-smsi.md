# D8 — PÉRIMÈTRE DU SMSI ET DÉCLARATION D'APPLICABILITÉ

**Émetteur** RSSI Groupe · **Destinataires** Comité Exécutif (décision jeudi), Direction Générale de MERIDIAN Logistique, client pharmaceutique (extrait pour la réponse écrite)
**Groupe 4 (Translog)** · instance `translog-b` · domaine `MERIDIAN-LOGISTIQUE` · **Séance 8**

> **Note de lecture.** Ce document est le premier du dossier qu'un auditeur externe pourrait lire tel quel : le rapport d'audit de la séance 4 était interne, le registre de la séance 7 est un outil de pilotage, mais le périmètre et la déclaration d'applicabilité sont des pièces maîtresses d'un dossier de certification. Chaque sigle est développé à son premier emploi, chaque renvoi nomme sa cible, chaque affirmation porte sa preuve — MERIDIAN Logistique est désigné en toutes lettres partout où « la filiale » suffirait en interne.

---

## 1. Périmètre du système de management de la sécurité de l'information (SMSI)

**Activités couvertes.** Le périmètre initial couvre les activités de MERIDIAN Logistique qui servent le client pharmaceutique sous exigence de chaîne du froid : l'entreposage et l'expédition sous température dirigée (valeur métier `LOG-PA-02`, maintien de la chaîne du froid) et la conformité contractuelle qui en découle — pénalités de 12 000 € par jour d'arrêt, audit annuel du client, questionnaire de sécurité annoncé pour le prochain cycle (valeur métier `LOG-PA-04`). L'exécution générale des flux logistiques du groupe (`LOG-PA-01`, les six entrepôts) n'entre pas dans ce périmètre : seule la part qui sert ce client y entre.

**Entités et systèmes.** Deux sites sur les six exploités par la filiale : **E1** (le plus grand, salle serveurs du système de gestion d'entrepôt — *warehouse management system*, WMS) et **E4**, tous deux réservés au client pharmaceutique. Les biens supports couverts : le WMS et sa base (`LOG-SA-01`), le logiciel des sondes de température, hébergé chez son fournisseur (`LOG-SA-05`), les chambres froides et remorques réfrigérées (`LOG-SA-08`), et le rôle de Responsable Qualité qui répond aux audits du client (`LOG-SA-11`).

**Interfaces avec l'extérieur du périmètre.** Trois interfaces franchissent la frontière, chacune avec son mécanisme de contrôle ou son absence, constatés au pack de filiale : le portail d'expédition du client pharmaceutique, où la filiale saisit les expéditions avec un compte par entrepôt, sans annuaire nominatif de notre côté — aucun mécanisme de contrôle documenté ; le logiciel des sondes de température, hébergé et exploité par son fournisseur, avec un rapport mensuel transmis au client — le contrôle existe côté fournisseur, non vérifié par nous ; les interventions de la tierce maintenance applicative (TMA) du WMS, par un compte de domaine partagé dont le nombre de porteurs n'est pas établi — interface à haut risque, déjà tracée au registre de la séance 7 (`PT-01`, `PT-02`, `PT-08`).

**Exclusions de périmètre, assumées par écrit.** Quatre exclusions, chacune datée et motivée, aucune de confort :
1. **L'automatisation de tri d'E4** et le réseau bureautique/industriel qui la porte restent hors périmètre : E4 est à la fois dédié au client pharmaceutique et équipé d'automates de tri, sur un réseau interconnecté sans cloisonnement (constat `C3` de D4, non-conformité majeure sur la totalité du périmètre) — aucun périmètre incluant l'industriel ne serait honnêtement déclarable avant la segmentation IT/OT (`PT-03` de D7, échéance 14/06/2027). Réexamen à cette date.
2. **Les quatre autres entrepôts** (E2, E3, E5, E6) et leurs automates : le client pharmaceutique ne reçoit aucun service de ces sites.
3. **L'interface de réapprovisionnement d'urgence vers MERIDIAN Santé** (scannettes, VLAN dédié, pare-feu d'inspection) : elle sert une relation interne au groupe, sans rapport avec l'exigence du client pharmaceutique qui déclenche ce dossier ; elle est traitée comme projet en D6, pas ici.
4. **Les trois autres filiales du groupe** (Santé, Éducation, Territoires) : une extension à leur périmètre est à étudier, non décidée à ce jour (décision demandée en séance 8, question 5 du TD 1).

**Test du tiers, appliqué.** Une personne extérieure au groupe qui lirait ce seul paragraphe peut dire, pour tout système nommé au pack de filiale, s'il est dans le périmètre : la chaîne du froid et le WMS d'E1/E4, oui ; les automates de tri, non ; le flux vers Santé, non ; les trois autres filiales, non.

---

## 2. Déclaration d'applicabilité (Statement of Applicability, SoA)

**Taux de couverture, affiché honnêtement en tête** : **15 contrôles investigués sur 93** (16,1 %) — les douze retenus à l'auto-évaluation de la séance 4, complétés par trois contrôles calibrés au CM de ce matin, cinq contrôles étant communs aux deux listes. **Les 78 contrôles restants ne sont pas comptés comme conformes : ils sont non évalués**, matière du temps de projet supervisé de cet après-midi si le groupe va plus loin.

*Chaque ligne cite l'observation telle que saisie dans `translog-b` — elle n'est pas réécrite ici.*

| Contrôle | Statut | Justification (risque du registre D7 ou exigence nommée) | État | Preuve / renvoi |
|---|---|---|---|---|
| **A.5.9** Inventaire des informations et des actifs associés | Applicable | Exigence de connaître le SI, socle de la démarche | Partiellement conforme | Cartographie D2 ; lacunes D2 §7 (schéma réseau, plages IP, porteurs TMA) ; `PT-13`, `PT-05` (D7) |
| **A.5.15** Contrôle d'accès | Applicable | Constat `C4` de D4 (non-conformité majeure) | Non conforme | Compte de domaine partagé, porteurs inconnus ; `PT-02` (D7, 14/01/2027, pas encore effective) |
| **A.5.16** Gestion des identités | Applicable | Constat `C4` de D4 | Non conforme | Identité non unique/attribuable, audit interne du holding sans réponse nominative ; `PT-02` |
| **A.5.17** Informations d'authentification | Applicable | Directive `ACC-01` + constat D4 | Non conforme | Secret de service identique depuis 2019, en clair ; `PT-09` (D7, 14/01/2027) |
| **A.5.19** Sécurité de l'information dans les relations avec les fournisseurs | Applicable | Constat `C4` de D4 + écosystème coté en séance 6 (D6) | Non conforme | Compte TMA partagé ; contrat de l'intégrateur (dangerosité 12,0) sans clause de sécurité ; `PT-02`, `PT-06`, `PT-08` |
| **A.5.22** Surveillance, revue et gestion des changements des services fournisseurs | Applicable | Pack de filiale (mises à jour TMA non contrôlées) | Non conforme | « La TMA fait les mises à jour la nuit, quand elle veut » ; `PT-01` (D7, 14/12/2026) |
| **A.5.24** Planification et préparation de la gestion des incidents | Applicable | Directive `INC-01` (PSSI-cadre) | Non conforme | Notification sous 2 h jamais tenue (arrêt d'avril) ; aucune procédure d'incident (D2 §7) ; **aucune mesure D7 ne la couvre — chantier non budgété à ouvrir** |
| **A.6.3** Sensibilisation, apprentissage et formation à la sécurité | Applicable | Directive de groupe (PSSI-cadre) | Non conforme | D4 l'avait laissée non évaluée ; aucune preuve de programme depuis, angle mort tranché ce jour ; **aucune mesure D7 ne la couvre** |
| **A.7.4** Surveillance de la sécurité physique | Applicable | Réalité des sites (pack §2, §4) | Partiellement conforme | Aucune mesure de surveillance nommée pour les six entrepôts ni la salle serveur d'E1 (deux pannes de climatisation) ; à investiguer site par site ; **aucune mesure D7 ne la couvre** |
| **A.8.2** Droits d'accès privilégiés | Applicable | Constat `C4` de D4 | Non conforme | Même compte à privilèges partagé ; `PT-02` |
| **A.8.5** Authentification sécurisée | Applicable | Directive `ACC-01` + pack de filiale | Non conforme | MFA non déployée, secret en clair ; `PT-02`, `PT-09` |
| **A.8.8** Gestion des vulnérabilités techniques | Applicable | Directive `COR-01` (PSSI-cadre) | Non conforme | Correctif sous 14 jours ni mesuré ni mesurable ; `PT-01` |
| **A.8.15** Journalisation | Applicable | Pack de filiale §6 | Partiellement conforme | Le SOC groupe ne reçoit que le réseau bureautique ; `PT-07` (D7, 14/03/2027) |
| **A.8.22** Cloisonnement des réseaux | Applicable | Constat `C3` de D4 (non-conformité majeure) | Non conforme | Réseaux bureautique et industriel interconnectés sur les six sites ; `PT-03` (D7, 14/06/2027, la mesure la plus coûteuse du plan) |
| **A.8.28** Codage sécurisé | **Non applicable** | Absence d'objet — voir registre des exclusions, §3 | — | — |

**Total sur les quinze contrôles investigués** : 11 non conformes, 3 partiellement conformes, 1 non applicable, 0 conforme.

### Cohérence croisée, vérifiée dans l'outil (exigée par l'énoncé)

**Sens 1 — chaque écart majeur de l'audit de séance 4 mène à un contrôle inclus et non conforme.** Vérifié sans écart : `C3` → `A.8.22` (non conforme, inclus) ; `C4` → `A.5.15`, `A.5.16`, `A.5.19`, `A.8.2` (les quatre non conformes, inclus). **Aucun orphelin de ce côté.**

**Sens 2 — chaque mesure « réduire » du plan de traitement de séance 7 mène à au moins un contrôle inclus.** Neuf des treize mesures s'appuient sur au moins un des quinze contrôles investigués (`PT-02`, `PT-03`, `PT-05`, `PT-06`, `PT-07`, `PT-08`, `PT-09`, `PT-10`, `PT-11`, `PT-13`). **Trois orphelins trouvés** : `PT-01` (rattachée à `A.8.32`, hors des quinze investigués), `PT-04` (`A.8.13`, `A.5.30`), `PT-12` (`A.5.37`) — leurs contrôles ne figurent pas encore à la déclaration d'applicabilité ; à investiguer en priorité si le temps de projet supervisé étend la SoA.

**Sens 3, ajouté par cette relecture — trois contrôles inclus sans mesure de traitement au registre.** `A.5.24`, `A.6.3` et `A.7.4` sont trois constats du jour, postérieurs à l'arrêt du registre de séance 7 : aucun n'a encore de mesure `PT-xx` qui le couvre. Ce n'est pas une incohérence de saisie — le registre a été clos avant que ces trois contrôles soient investigués — mais un chantier explicitement non budgété à porter au prochain cycle de traitement.

> **Réserve méthodologique, héritée de `fixes.md` F17** : les renvois ci-dessus vers `PT-02`, `PT-03` et `PT-06` retiennent la lecture de D7. Or trois mesures de D4 (`M1`→`A.8.22`, `M2`→`A.5.19`, `M4`→`A.5.15`/`A.5.16`/`A.5.19`/`A.8.2`) portent sur les **mêmes contrôles** avec des dates et parfois des porteurs différents — écart décrit par F17 et **délibérément laissé ouvert**, une décision d'auteur plutôt qu'une correction mécanique. `D8` cite `D7` parce que c'est la lecture la plus récente et la plus chiffrée, pas parce que l'écart serait refermé ; l'arbitrage `M1`/`PT-03`, `M2`/`PT-06`, `M4`/`PT-02` reste dû avant `D9`.

---

## 3. Registre des exclusions

*Reproduit tel que saisi dans `translog-b` le jour même — non réécrit.*

**A.8.28 — Codage sécurisé.** Seule exclusion de la déclaration d'applicabilité à ce jour.

> **Fait** : aucune activité de développement logiciel interne à MERIDIAN Logistique ; le WMS est un progiciel opéré par la tierce maintenance applicative (APPLICA Services, contrat `TMA-WMS-2021`), aucun développeur n'est nommé dans le pack de filiale.
> **Vérification** : confirmée par la DSI de la filiale (trois personnes, sans titre de RSSI) le 15/09/2026, sur la base de la cartographie de séance 2 (D2) et du pack de filiale.
> **Réexamen** : à toute prochaine revue de direction, ou dès qu'un projet de développement interne serait engagé — déclencheur porté par le processus projet, comme D6 le fait déjà pour les projets impliquant un tiers.

Aucune autre exclusion n'a été tentée : les quatorze autres contrôles applicables, y compris ceux où l'absence de preuve aurait pu tenter un « hors périmètre » de confort (`A.7.4` en particulier), sont restés notés et justifiés plutôt qu'exclus, conformément à la règle de l'énoncé — dans le doute entre non-conforme et non applicable, c'est le non-conforme qui l'emporte, sauf absence d'objet démontrée.

---

## 4. Synthèse pour la direction

1. L'évaluation initiale porte aujourd'hui sur les **30 exigences des clauses 4 à 10** et sur **15 contrôles d'annexe A** (16,1 % de couverture).
2. **Le plus solide du dossier** : la planification (clauses 6.1.2 et 6.1.3, seules notées pleinement conformes) — l'appréciation et le traitement des risques des séances 5 et 7 sont la pièce la plus fraîche et la plus aboutie.
3. **Les deux chantiers les plus nus, confirmés par la saisie** : le support documentaire (clause 7 — aucune politique de gestion documentaire, aucun dispositif de compétence ni de sensibilisation) et l'évaluation des performances (clause 9 — aucun indicateur mesuré, aucune revue de direction institutionnalisée).
4. Sur l'annexe A, la couverture concentre sans surprise les écarts déjà connus : **11 des 15 contrôles investigués sont non conformes**, dont les deux non-conformités majeures de l'audit de séance 4 (`C3`, `C4`).
5. **Une seule exclusion**, justifiée en trois lignes et vérifiée : le codage sécurisé, absent d'objet.
6. **Trois contrôles inclus n'ont pas encore de mesure de traitement** (`A.5.24`, `A.6.3`, `A.7.4`) : chantier à porter au prochain cycle, pas un oubli de saisie.
7. **Décision attendue** : le Comité Exécutif est invité à valider jeudi le lancement de l'effort de certification ISO/IEC 27001:2022 sur le périmètre décrit en §1, avec extension au reste du groupe à étudier ensuite (décision détaillée en `Session-8/1-CISO-desk/Seance-8-TD-S8-01-le-business-case-de-la-certification.md`, question 5).
8. Au client pharmaceutique, la filiale répond dès aujourd'hui au titre d'une démarche documentée équivalente, avec pour pièces à l'appui le référentiel adopté (D3), l'audit initial (D4) et le plan de traitement daté et chiffré (D7).
9. **Aucune date de certification n'est promise, aucun coût de certification n'est improvisé** — seul le coût déjà arrêté du plan de traitement (D7, ≈ 82 000 €/an) est cité, pour ce qu'il est : le coût de la trajectoire de risque, pas celui de l'audit de certification.
10. Le prochain jalon mesuré est la séance 9 : politique de sécurité consolidée, corpus documentaire, indicateurs — exactement les deux chantiers désignés au point 3.

---

> **Preuves à l'appui** : évaluation *« MERIDIAN - ISO/IEC 27001:2022 - initial assessment »* dans `translog-b`, `../3-Evidence/S8-05-*` (quatre captures), `../2-Labs/Seance-8-TP-S8-05-feuille-de-travail-evaluation-et-SoA.md` (feuille de travail du TP 1, écarts d'outil documentés). Périmètre proposé et décision de certification détaillés dans `../1-CISO-desk/Seance-8-TD-S8-01-le-business-case-de-la-certification.md`. Matière directe de la **sous-section 8** de la note de stratégie (`../../../Piece-1-Strategy-note/MERIDIAN-strategy-note.md`).
