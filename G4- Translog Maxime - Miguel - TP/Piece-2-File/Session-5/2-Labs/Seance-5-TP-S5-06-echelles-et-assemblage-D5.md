# Feuille de travail — Séance 5, TP 2 : échelles de risque, assemblage de D5, note de stratégie

**Groupe 4 (Translog)** · instance `translog-b` (https://translog-b.lockbay.eu)
**Domaine** `MERIDIAN-LOGISTIQUE` · **étude** `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1`
**Date** : 9 septembre 2026 · **compte utilisé** : `maximebatista18@gmail.com` (compte nominatif, jamais `admin@lockbay.eu`)
**Matière** : TD 2 (`../4-Working-notes/Seance-5-TD-S5-03-ateliers-1-et-2-EBIOS-RM.md`), échelles de l'énoncé du TP 2, appétence du bureau du RSSI (`../1-CISO-desk/Seance-5-TD-S5-01-appetence-au-risque.md`)

> **Ce fichier n'est pas le livrable.** C'est la trace du TP 2 : les échelles décrites niveau par niveau, l'ajout d'ER7 dans l'outil et son arbitrage, les écarts outil/papier. Le livrable est **D5** (`D5-appreciation-initiale-des-risques.md`), et la note de stratégie gagne sa sous-section 5.

---

## 0. Répartition nominative

| Objet | Fait par |
|---|---|
| Ajout d'ER7 dans l'instance (atelier 1, activité 3) + liaison au couple SR/OV n°3 | Maxime Batista |
| Échelles de gravité et de vraisemblance, seuil d'acceptation | Maxime Batista |
| Assemblage de D5 | Maxime Batista |
| Sous-section 5 de la note de stratégie | Maxime Batista |

TP 1 (saisie des ateliers 1 et 2) : fait par Miguel Monereo le 9 septembre 2026 — voir `Seance-5-TP-S5-05-feuille-de-travail-saisie-EBIOS-RM.md`.

---

## 1. Exercice 1 — Les échelles du groupe

### 1.0 Ce que l'outil impose et ce qu'il ne porte pas

La matrice `4x4 risk matrix from EBIOS-RM` importée au TP 1 est un **objet de bibliothèque `intuitem`, publié, en lecture seule** (`urn:intuitem:risk:matrix:risk-matrix-4x4-ebios-rm`, aucun bouton *Edit* — vérifié à l'écran, capture `../3-Evidence/S5-06-matrice-4x4-niveaux-de-risque.jpg`). Elle porte :

- **Vraisemblance** (4 niveaux) : `Unlikely`, `Likely`, `Very likely`, `Certain`.
- **Impact** (4 niveaux — le mot de l'axe est « Impact », cf. écart n°3 du TP 1) : `Minor`, `Significant`, `Important`, `Critical`.
- **Niveaux de risque** (3), avec leur texte déjà écrit dans la matrice :
  - `Low` — *« Acceptable as is. »*
  - `Medium` — *« Tolerable under control. Risk management monitoring must be conducted, and actions should be implemented as part of continuous improvement in the medium and long term. »*
  - `High` — *« Unacceptable. Risk reduction measures must be implemented urgently in the short term. Otherwise, all or part of the activity will be denied. »*

**Conséquence méthodologique** : les descriptions niveau par niveau dans les termes du groupe (gravité G1–G4, phrases d'interprétation V1–V4, seuil) n'ont **aucun champ dans l'outil**. Comme la table du socle à quatre colonnes au TP 1, elles vivent dans **D5, section 1**. Ce qui est vérifiable à l'écran, c'est que ces descriptions **coïncident** avec la matrice importée — et le texte des trois niveaux de risque de la matrice dit déjà, mot pour mot, « acceptable / tolérable sous contrôle / inacceptable » : le seuil dérivé de l'appétence ne fait que s'y adosser.

### 1.1 Échelle de gravité G1–G4, dans les termes de MERIDIAN

*Trois questions par niveau : effet sur les missions, effet sur les personnes, le groupe se rétablit-il et en combien de temps. Gradation du modèle du guide EBIOS RM : de la simple consommation de marges d'exploitation jusqu'à la survie de l'organisation menacée.*

| Niveau (outil) | Missions | Personnes | Reprise |
|---|---|---|---|
| **G1 — `Minor`** (mineure) | Gêne opérationnelle absorbée sans dégradation visible du service ; consomme une marge d'exploitation (heures supplémentaires, report d'une tâche interne). | Aucun effet sur la sécurité des soins ; aucune donnée personnelle exposée. | Retour à la normale en quelques heures, par les équipes en place, sans décision d'un niveau supérieur. |
| **G2 — `Significant`** (significative) | Un service rendu est dégradé ou interrompu de façon perceptible par un client ou un usager sans le priver de l'essentiel ; un objectif de la période est manqué. | Aucune atteinte à la sécurité des soins ; au plus une donnée personnelle non sensible exposée à un cercle restreint. | Retour à la normale en un à quelques jours, cellule mobilisée, Comité sécurité groupe informé ; pas d'impact contractuel chiffré. |
| **G3 — `Important`** (grave) | Interruption ou défaillance d'un service **essentiel** du groupe : arrêt d'expédition au-delà des six heures qui bloque 40 % du volume du groupe, rupture de la chaîne du froid, indisponibilité d'une plateforme citoyenne, compromission de l'annuaire du pôle ; un engagement contractuel est rompu et se paie (pénalités de 12 000 €/jour, délai de notification manqué). | Retard de soins ou d'un réapprovisionnement d'urgence sans conséquence vitale établie ; exposition de données personnelles — mineurs ou patients inclus — à un tiers non autorisé. | Retour à la normale en une à plusieurs semaines, sur décision du Comité Exécutif, client et le cas échéant régulateur informés ; trace durable sur la relation client. |
| **G4 — `Critical`** (critique) | La capacité du groupe à tenir une de ses missions est remise en cause dans la durée : perte de confiance d'un client majeur ou d'un régulateur menant à la perte d'un contrat ou d'une délégation, incapacité prolongée à expédier ou à soigner ; l'existence d'une filiale est menacée. | Conséquence vitale ou sanitaire pour un patient ou un usager du fait de la défaillance ; fuite massive de données de santé ou de mineurs. | Incertaine ou supérieure à plusieurs mois, sur décision de la Direction Générale et saisine du Conseil d'Administration ; événement qui se communique publiquement. |

### 1.2 Vraisemblance V1–V4 — les libellés de l'outil ne sont pas réécrits, une phrase d'interprétation chacun

*Sur quels signaux on cote à ce niveau. Sans ces phrases, deux participants coteront la même situation V2 et V3.*

| Niveau (outil) | On cote à ce niveau quand… |
|---|---|
| **V1 — `Unlikely`** | Aucune faiblesse connue exploitable dans le périmètre, ou un mode opératoire qui suppose des moyens que les sources de risque identifiées n'ont pas ; rien d'observable ne soutient le scénario aujourd'hui. |
| **V2 — `Likely`** | Une faiblesse existe mais son exploitation demande un concours de circonstances ou un accès que la source n'a pas encore ; le scénario est plausible sans être soutenu par un fait précis (exemple : espionnage concurrentiel, aucun signal observé). |
| **V3 — `Very likely`** | Une faiblesse **connue et actuelle** rend le scénario réalisable avec les moyens courants de la source, et le secteur en donne des exemples récents ; un observable du dossier ouvre directement le chemin — secret de service en clair connu de toute l'Exploitation, box 4G hors supervision, aucun journal OT au SOC. |
| **V4 — `Certain`** | Le scénario s'est déjà réalisé dans le périmètre, ou sa réalisation ne dépend plus d'un attaquant : la dégradation est en cours (le flux vers Santé est bloqué depuis trois mois ; l'arrêt du WMS d'avril a eu lieu). Réservé aux événements **constatés**, pas anticipés. |

### 1.3 Le seuil d'acceptation, posé sur la grille

*Report de l'appétence du bureau du RSSI (matin) sur les trois niveaux de risque de la matrice. Une phrase de justification par niveau.*

| Niveau de risque (outil) | Statut au regard de l'appétence | Justification |
|---|---|---|
| **`Low` — Faible** | **Acceptable en l'état** | Le groupe porte ce risque sans mesure spécifique et le revoit à la cadence normale (revue trimestrielle du ComEx). L'appétence du matin accepte de dégrader ce qui reste sous ce niveau : une expédition retardée dans une fenêtre hors pointe publiée, un écart documenté de faible portée. |
| **`Medium` — Moyen** | **Tolérable sous conditions** | Acceptable **uniquement** formalisé en tolérance — datée, surveillée, avec un propriétaire nommé et une mesure compensatoire intérimaire ; à défaut, il rejoint `High`. C'est la machinerie de la question 3 du bureau du RSSI (interconnexion IT/OT, journaux locaux de Territoires) : un écart qu'on garde le temps de le fermer, pas un état stable. |
| **`High` — Élevé** | **Inacceptable en l'état** | Appelle une décision de traitement avant mise en production ou avant d'être porté plus longtemps ; l'activité concernée peut être suspendue si le traitement n'est pas engagé. L'appétence refuse, quel qu'en soit le coût, l'arrêt d'expédition non planifié au-delà de six heures, la rupture de la chaîne du froid et l'action à privilèges non imputable — tout risque coté Élevé touche l'un de ces refus. |

**Coïncidence avec la matrice, vérifiée à l'écran** : le texte des trois niveaux de la matrice importée (`Acceptable as is` / `Tolerable under control…` / `Unacceptable…`) dit déjà cela. Le seuil dérivé de l'appétence **ne réécrit rien**, il nomme la même ligne dans le vocabulaire du groupe. C'est le passage attendu par l'énoncé : « l'appétence cesse d'être un discours et devient une ligne sur une grille ».

> La cotation du registre complet — quel événement redouté et quel scénario tombent dans `Low`, `Medium` ou `High` — est le travail de la **séance 7** (atelier 5), avec ces échelles **inchangées**. Le TP 2 pose les échelles, il ne cote pas.

---

## 2. Ajout d'ER7 dans l'instance — trace

**Arbitrage rendu** : D5 **adopte** le septième événement redouté pour `LOG-PA-03` que le TD 2 recommandait et que le TP 1 avait laissé en suspens (feuille de travail S5-05, §4.3). Raison : le couple SR/OV n°3 (`Avenger` — initié de l'Exploitation) vise explicitement le savoir-faire non écrit ; sans ER7, ce couple retenu resterait **sans événement redouté associé** pour la moitié de son objectif. Le critère de validation « compteur = 6 » était celui du **TP 1** ; le TP 2 est le point d'arbitrage, et les critères d'acceptation de D5 ne fixent pas de nombre.

**Fiche saisie** (atelier 1, activité 3) :

| Champ | Valeur |
|---|---|
| ID | `ER7` |
| Name | *Le savoir-faire opérationnel des six entrepôts est perdu — départ ou absence du Responsable Exploitation, aucune trace écrite pour le remplacer* |
| Assets | `LOG-PA-03` — Savoir-faire operationnel des six entrepots *(actif primaire, relié — non recréé)* |
| Qualifications | `Proof` (traçabilité — dans D2, la traçabilité de `LOG-PA-03` est « très importante par absence ») |
| Severity | `Important` (grave) — dégradation durable de l'exploitation des six sites, reprise lente et coûteuse (reconstruction du savoir), sans échéance certaine ; pas d'atteinte directe aux personnes ni manquement réglementaire immédiat, d'où `Important` et non `Critical` |
| Description | note d'arbitrage : compteur 6 → 7, raison, renvoi à la feuille S5-05 §4.3 |
| Selected | coché |

**Liaison** : le couple SR/OV n°3 (`67958fec-…`) porte désormais **ER2 + ER7** dans son champ *Feared events* (auparavant ER2 seul).

**Compteurs de la carte *Summary* après TP 2** :

| Compteur | Avant TP 2 | Après TP 2 |
|---|---|---|
| `Assets` | 17 | **17** |
| `Feared events` | 6 | **7** ⚠️ *(écart assumé avec le TP 1 — raison ci-dessus)* |
| `Audits` | 1 | **1** |
| `RO/TO couples` | 5 | **5** |
| `Stakeholders` / `Strategic scenarios` / `Operational scenarios` | 0 / 0 / 0 | **0 / 0 / 0** |

**Piège de l'éditeur markdown rencontré** : les champs `Description` et `Justification` de la fiche « Add feared event » n'acceptent la saisie qu'après un **double-clic** sur la zone d'aperçu, qui fait apparaître le `textarea` ; le simple bouton « Edit » ne suffit pas. À signaler pour les saisies des séances 6 et 7.

**Captures** : `../3-Evidence/S5-06-ER7-ajoute-7-evenements-redoutes.jpg`, `S5-06-couple3-avenger-lie-ER2-ER7.jpg`, `S5-06-etude-summary-compteurs-7-ER.jpg`, `S5-06-matrice-4x4-niveaux-de-risque.jpg`, `S5-06-rapport-etude-EBIOS-RM-ateliers-1-2.jpg`.

---

## 3. Exercice 2 — Assemblage de D5 : d'où vient chaque section

| Section D5 | Source | Ce qui n'a pas de champ dans l'outil et vit dans D5 |
|---|---|---|
| 1. Cadrage de l'étude | Description de l'étude dans l'instance (TP 1, ex. 3) + exercice 1 du TD 2 | **Les échelles G1–G4, V1–V4 et le seuil** (section 1 ci-dessus) |
| 2. Socle de sécurité | Audit S4 rattaché à l'étude (TP 1) + exercice 3 du TD 2 | **La table à quatre colonnes** (PSSI-cadre, guide d'hygiène, ISO 27001, contrat client) **et la décision de poursuite en trois phrases** |
| 3. Sources de risque | 5 couples SR/OV dans l'instance (TP 1, ex. 5) + exercice 4 du TD 2 | La liste des **couples secondaires sous surveillance** (n°2 intégrateur, n°5 hacktiviste) et leur raison d'être écartés |
| 4. Événements redoutés | 7 événements redoutés dans l'instance (TP 1 ex. 4 + ER7 au TP 2) + exercice 2 du TD 2 | Rien — les 7 fiches portent actif primaire, qualification, gravité et justification |

**Critères d'acceptation de D5, relus avant remise** :

- [x] Valeurs métier et biens supports **identiques** à la cartographie de la séance 2 — 4 primaires `LOG-PA-01…04`, 13 supports `LOG-SA-01…13`, aucun recréé ni renommé (l'outil affiche « API » là où D2 dit « interface » pour `SA-13` : les deux libellés sont cités, rien n'a été renommé).
- [x] Chaque couple SR/OV motivé **en une phrase**.
- [x] Échelles réutilisables telles quelles en séance 7 : niveaux décrits dans les termes du groupe, seuil posé, aucune retouche à prévoir.

---

## 4. Entrées pour les séances suivantes

| Ce qui sort d'ici | Où ça va |
|---|---|
| Les échelles G1–G4 / V1–V4 et le seuil `Low`/`Medium`/`High` | D5 §1 ; utilisées **inchangées** pour coter le registre en séance 7 (atelier 5) |
| ER7 saisi, compteur *Feared events* = 7, couple n°3 relié à ER2 + ER7 | D5 §4 ; confrontation SR/OV ↔ ER désormais complète pour le couple n°3 |
| ER3 (chaîne du froid) et ER5 (réappro Santé) **toujours sans source de risque retenue** | D5 §4 + séance 6 : réintégrer un couple « fournisseur des sondes » et un couple « pivot Logistique → Santé » avant l'atelier 3 |
| Couple n°2 (intégrateur) — partie prenante critique de l'écosystème | Séance 6, atelier 3 |
| Le seuil `Medium` = tolérable **seulement formalisé** (daté, surveillé, propriétaire) | Séances 7 à 9 : registre des tolérances, indicateurs (S9) |
