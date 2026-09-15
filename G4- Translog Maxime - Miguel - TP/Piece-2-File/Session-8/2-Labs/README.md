# Séance 8 — TP · livrable D8 (2 points)

**État : TP 1 et TP 2 entièrement faits.** Évaluation des 30 exigences de clauses 4-10 et déclaration
d'applicabilité sur 15 contrôles d'annexe A saisies dans `translog-b` ; livrable `D8` assemblé ; sous-section 8
de la note de stratégie rédigée.

| Fichier | Rôle | État |
|---|---|---|
| `PLAN-Seance-8-TP-S8-05-evaluation-clauses-et-SoA.md` | Le mode opératoire du TP 1, écrit **avant** la saisie : verdict décidé pour les 30 exigences de clauses et les 15 contrôles d'annexe A, sourcé sur D1-D7 et le pack de filiale | ✅ **écrit** — trace de méthode |
| `Seance-8-TP-S8-05-feuille-de-travail-evaluation-et-SoA.md` | La feuille de travail du TP 1 : compteurs lus dans l'outil, trois écarts d'outil trouvés et corrigés (le champ Observation n'enregistrait rien au premier passage ; les boutons de soumission ; deux observations de séance 3 restées en place sur `4.1` et `5.3`, §5 bis), captures listées | ✅ **remplie** — 30 clauses et 15 contrôles évalués, comptes vérifiés à l'écran |
| **`D8-declaration-d-applicabilite.md`** | **Le livrable D8** — deux périmètres distingués (SMSI de la filiale entière / certification visée sur le seul périmètre pharmaceutique) avec test du tiers dedans/dehors, déclaration d'applicabilité (16,1 % de couverture, cohérence croisée avec D4 et D7 vérifiée dans les deux sens), registre des exclusions (`A.8.28`), synthèse pour la direction en dix lignes | ✅ **rédigé** · ✅ **2 points** |

> **Note de rangement (15 sept.)** : deux versions du livrable ont été écrites en parallèle par les deux
> auteurs pendant la même fenêtre de travail ; `D8-declaration-d-applicabilite.md` (Miguel) a été retenue
> comme version canonique — plus complète (test du tiers §1.5, distinction périmètre SMSI / périmètre de
> certification en §1.6, cohérence croisée dans les deux sens en §2.4) — et la réserve F17 sur les dates
> `M1`/`M2`/`M4` de D4 y a été reportée depuis l'autre version, qui a été retirée pour ne garder qu'un seul
> livrable `D8`.

## TP 1 — Évaluation des clauses 4-10 et déclaration d'applicabilité

**Source** : `../../../../S8 - Sources/TP 1/ISO 27001 and SoA Assessment on CISO Assistant _ Lockbay Academy.pdf`

Travaille entièrement **dans** l'évaluation existante (« MERIDIAN - ISO/IEC 27001:2022 - initial assessment »,
créée en séance 3, complétée en séance 4 sur douze exigences d'annexe A) : rien n'est recréé.

1. **Vérifier l'état de départ** — 123 exigences évaluables, 93 contrôles d'annexe A ; clauses à *not
   assessed*/*to do*, annexe A porteuse des douze statuts de la séance 4.
2. **Évaluer les 30 exigences des clauses 4 à 10** — résultat et progression `Done` pour chacune, observation
   uniquement pour les résultats non conformes. Interdits : `Not applicable` sur une clause, `Compliant` de
   complaisance. Résultat : 2 conformes, 8 non conformes, 20 partiellement conformes.
3. **Marquer l'applicabilité sur les quinze contrôles déjà investigués** (douze de la séance 4, trois du CM,
   cinq communs) — statut, résultat, justification tracée à une pièce du dossier ; l'unique exclusion en
   trois lignes (fait, vérification, réexamen). Résultat : 11 non conformes, 3 partiellement conformes, 1
   non applicable (`A.8.28`).

## TP 2 — Déclaration d'applicabilité (D8) et note de stratégie

**Source** : `../../../../S8 - Sources/TP 2/Justification of Exclusions (D8) and Strategy Note _ Lockbay Academy.pdf`

Quatre sections attendues, toutes dans `D8-declaration-d-applicabilite.md` : le **périmètre du SMSI**
(activités, entités et systèmes, interfaces, exclusions assumées — avec, en plus, le test du tiers dedans/dehors
et la distinction entre le périmètre du SMSI et le périmètre visé pour la première certification) ; la
**déclaration d'applicabilité**, taux de couverture affiché en tête et comptes lus dans l'outil, jamais
recopiés à la main ; le **registre des exclusions**, repris tel que saisi le matin, non réécrit ; la
**synthèse pour la direction**, dix lignes — profil de l'évaluation, deux clauses les plus faibles, chantier
désigné, décision attendue.

**Cohérence croisée vérifiée dans les deux sens** (exigée par l'énoncé) : chaque écart majeur de D4 (`C3`,
`C4`) mène à un contrôle inclus et non conforme parmi les quinze — aucun orphelin ; côté D7, chaque risque
réduit du registre mène à au moins un contrôle retenu, sauf **ER7** (perte du savoir-faire), dont l'unique
ancrage `A.5.37` fait partie des 78 contrôles non investigués ; huit contrôles au total sont rapprochés d'une
mesure du plan sans être encore investigués, et trois contrôles inclus ce jour (`A.5.24`, `A.6.3`, `A.7.4`)
n'ont pas encore de mesure de traitement au registre — chantiers signalés, pas des oublis de saisie.
Le rapprochement se lit ligne à ligne sur le tableau mesure ↔ exigence de **D7 §6** : les deux seuls
rapprochements que D7 ne portait pas (`A.5.15` par `PT-02`, `A.8.8` par `PT-01`) sont signalés comme des
lectures de D8 et inscrits au tableau des orphelins, correction due dans D7 en séance 9.

**Sévérité assumée, pas subie.** Le CM présumait un état *partiel* sur cinq des huit contrôles calibrés
(`A.5.17`, `A.5.19`, `A.5.24`, `A.6.3`, `A.8.8`) ; ils sont notés **non conformes** ici. La règle de
notation — l'état constaté au 15 septembre 2026, jamais l'intention — est écrite dans `D8` §2.2 avec ses
trois conséquences, dont la cohérence avec `D4`, qui avait déjà noté trois de ces cinq contrôles non
conformes. L'écart avec le CM est donc défendu, pas ignoré.

> **Réserve héritée de `fixes.md` F17** : trois mesures de D4 (`M1`, `M2`, `M4`) portent sur les mêmes
> contrôles que trois mesures de D7 (`PT-03`, `PT-06`, `PT-02`) avec des dates différentes — écart décrit et
> délibérément laissé ouvert par F17, une décision d'auteur. `D8` cite `D7`, la lecture la plus récente et la
> plus chiffrée, sans que l'écart soit refermé pour autant.

### Sous-section 8 de la note de stratégie

Le périmètre du SMSI et le périmètre de certification visé, distingués en deux phrases et articulés à la
sous-section 2 (actifs critiques) ; la décision de certification recommandée le matin (TD 1) avec la réponse
au client dans l'intervalle ; le constat de l'évaluation initiale en une phrase, articulé à la sous-section 7
(le plan de traitement fonde la déclaration d'applicabilité). Rien n'est réécrit dans les sous-sections 1 à 7.

---

**Deux points de vigilance, constants depuis la séance 1.** Le livrable, c'est `D8-…` : autonome, nommé, au
format exigé, **un seul par séance**. Les feuilles de travail restent à côté comme trace de méthode. Chaque
objet modifié dans `translog-b` se capture dans `../3-Evidence/` — c'est la moitié du coefficient individuel.
