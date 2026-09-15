# PLAN — Séance 8, TP 1 (S8-05) : évaluation des clauses 4-10 et déclaration d'applicabilité

**Mode opératoire écrit avant la saisie**, au format des plans des séances 4, 5, 6 et 7. Instance
`translog-b`, évaluation existante *« MERIDIAN - ISO/IEC 27001:2022 - initial assessment »* (créée en
séance 3, remplie en séance 4 sur douze exigences d'annexe A). **Rien n'est recréé** : ce TP travaille
entièrement dans l'objet existant.

---

## 1. État à vérifier avant toute saisie (Step 1 de l'énoncé)

- L'arbre de l'évaluation affiche deux blocs : `core - Clauses` (30 exigences) et `annex-a - Statement of
  Applicability` (93 contrôles).
- **123 exigences évaluables au total**, dont **93 contrôles d'annexe A** — si ce compte diffère, arrêter et
  corriger l'import avant d'évaluer quoi que ce soit (consigne de l'énoncé).
- Les clauses 4 à 10 doivent être à l'état initial : résultat *not assessed*, progression *to do*.
- L'annexe A doit déjà porter les douze statuts saisis en séance 4 (constats C3, C4, C7 de D4).

## 2. Vocabulaire de l'outil à ne pas confondre

| Champ | Ce qu'il dit | Valeurs |
|---|---|---|
| **Status** (progression) | Où en est l'évaluateur | To do · In progress · In review · **Done** |
| **Result** (résultat) | Ce que vaut l'exigence pour MERIDIAN | Not assessed · Non compliant · Partially compliant · Compliant · **Not applicable** |
| **Observation** | Justification tracée à une pièce du dossier | Obligatoire pour tout résultat *Non compliant* (clauses) et pour **tout** contrôle applicable ou non applicable d'annexe A (la Déclaration d'applicabilité exige une justification, y compris pour les contrôles retenus) |

`Not applicable` n'a de sens légitime que sur l'annexe A — jamais sur une clause, qui s'applique dans son
intégralité (règle rappelée par l'énoncé et par le CM).

## 3. Les 30 exigences des clauses 4 à 10 — verdict décidé avant saisie

Sourcé exclusivement sur D1 à D7 et le pack de filiale ; le détail de chaque décision est dans le TD 1 de
la séance 8 (`../1-CISO-desk/Seance-8-TD-S8-01-le-business-case-de-la-certification.md`) et dans la
correspondance clause ↔ dossier du CM.

| Clause | Résultat | Observation |
|---|---|---|
| 4.1, 4.2, 4.3, 4.4 | Partially compliant | — |
| 5.1, 5.2, 5.3 | Partially compliant | — |
| 6.1.1 | Partially compliant | — |
| 6.1.2, 6.1.3 | **Compliant** | — |
| 6.2, 6.3 | Partially compliant | — |
| 7.1 | Partially compliant | — |
| **7.2** | **Non compliant** | Aucun dispositif de compétence ou de formation à la sécurité établi pour les rôles qui en ont la charge |
| **7.3** | **Non compliant** | Aucun programme de sensibilisation documenté ni mesuré ; D4 l'avait laissé sans preuve, angle mort assumé |
| 7.4 | Partially compliant | — |
| **7.5.1** | **Non compliant** | Aucune politique de gestion documentaire établie |
| 7.5.2 | Partially compliant | — |
| **7.5.3** | **Non compliant** | Aucun contrôle formel de version, diffusion, conservation |
| 8.1, 8.2, 8.3 | Partially compliant | — |
| **9.1** | **Non compliant** | Aucun indicateur mesuré ni suivi — objet de la séance 9 |
| 9.2.1, 9.2.2 | Partially compliant | — |
| **9.3.1** | **Non compliant** | Aucune revue de direction du SMSI institutionnalisée |
| **9.3.2** | **Non compliant** | Aucun ensemble d'éléments d'entrée rassemblé |
| **9.3.3** | **Non compliant** | Aucune décision de revue tracée |
| 10.1, 10.2 | Partially compliant | — |

**Total attendu** : 2 *Compliant*, 8 *Non compliant*, 20 *Partially compliant*, 0 *Not assessed*.

## 4. Les 15 contrôles d'annexe A déjà investigués — verdict décidé avant saisie

Douze de la séance 4 (D4) + trois du CM (A.5.24, A.7.4, A.8.28), cinq communs aux deux listes (A.5.9,
A.5.17, A.5.19, A.6.3, A.8.8) → **15 contrôles uniques**.

| Contrôle | Résultat | Source de la justification |
|---|---|---|
| A.5.9 | Partially compliant | D2 (cartographie), lacunes assumées |
| A.5.15 | Non compliant | Constat C4 de D4, traitement PT-02 de D7 |
| A.5.16 | Non compliant | Constat C4 de D4, traitement PT-02 de D7 |
| A.5.17 | Non compliant | Constat D4 (secret partagé), traitement PT-09 de D7 |
| A.5.19 | Non compliant | Constat C4 de D4 + écosystème D6, traitements PT-02/PT-06/PT-08 |
| A.5.22 | Non compliant | Pack de filiale (mises à jour TMA non contrôlées), traitement PT-01 |
| A.5.24 | Non compliant | Directive INC-01 non tenue en avril, aucune procédure d'incident |
| A.6.3 | Non compliant | Angle mort de D4 tranché (aucune preuve de sensibilisation depuis) |
| A.7.4 | Partially compliant | Aucune surveillance physique nommée, à investiguer site par site |
| A.8.2 | Non compliant | Constat C4 de D4, traitement PT-02 |
| A.8.5 | Non compliant | Directive ACC-01 + secret en clair, traitements PT-02/PT-09 |
| A.8.8 | Non compliant | Directive COR-01 non mesurée, traitement PT-01 |
| A.8.15 | Partially compliant | SOC ne reçoit que le réseau bureautique, traitement PT-07 |
| A.8.22 | Non compliant | Constat C3 de D4, traitement PT-03 (mesure la plus coûteuse) |
| **A.8.28** | **Not applicable** | **Seule exclusion** — aucun développement logiciel interne (WMS en TMA, APPLICA) |

**Total attendu** : 11 *Non compliant*, 3 *Partially compliant*, 1 *Not applicable*, 78 *Not assessed*
(les 78 autres contrôles d'annexe A restent hors du périmètre de ce TP — matière du temps de projet
supervisé, si le groupe va plus loin).

## 5. Justification de l'exclusion A.8.28 — les trois lignes obligatoires

- **Fait** : aucune activité de développement logiciel interne à MERIDIAN Logistique ; le WMS est un
  progiciel opéré par la tierce maintenance applicative (APPLICA Services, contrat TMA-WMS-2021), aucun
  développeur n'est nommé dans le pack de filiale.
- **Vérification** : confirmée par la DSI de la filiale (trois personnes, sans titre de RSSI) le
  15/09/2026, sur la base de D2 et du pack de filiale.
- **Réexamen** : à toute prochaine revue de direction, ou dès qu'un projet de développement interne serait
  engagé.

Discipline de l'énoncé appliquée : pas d'exclusion de confort — dans le doute entre *Non compliant* et
*Not applicable*, c'est *Non compliant* qui l'emporte, sauf absence d'objet démontrée (ici : pas de
développement du tout dans le périmètre).

## 6. Captures attendues

Préfixe `S8-05-`, dans `../3-Evidence/` : état final des compteurs (donuts compliance/progression), le
bloc `core - Clauses` complété, le bloc `annex-a` avec les 15 contrôles investigués, le détail de
l'exclusion A.8.28.

## 7. Critères de validation

Aucune exigence de clause à *not assessed* ; chaque *Non compliant* porte son observation ; aucun
*Not applicable* dans le bloc clauses ; les quinze contrôles d'annexe A investigués portent un résultat et
une justification ; l'unique exclusion porte ses trois lignes obligatoires.
