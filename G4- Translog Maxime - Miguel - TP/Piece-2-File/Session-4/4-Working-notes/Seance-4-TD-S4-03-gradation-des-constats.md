# TD 2 — Exercice 1 : gradation des constats du cycle d'audit groupe

**Source** : `../../../../S4 - Sources/TD 2/Qualification of Findings and Security Authorization Process _ Lockbay Academy.pdf`
**Critères en vigueur** : ISO/IEC 27001:2022 (Annexe A) + directives PSSI cadre codifiées en séance 1 (`ACC-01` à `COR-01`), qui font foi quel que soit le libellé adopté par la filiale.
**Règle de gradation** : la gravité **ressentie** n'entre jamais dans la justification — seuls comptent **l'exigence citée** et **l'étendue mesurée** de l'écart.

---

## Tableau de gradation — les huit constats

| Réf. | Filiale | Constat (résumé) | Exigence(s) | Gradation | Justification (exigence + étendue, jamais la gravité) |
|---|---|---|---|---|---|
| **C1** | Santé | Applications métier sur mots de passe locaux, sans MFA ; accès de maintenance distant permanent de l'éditeur du SIH via **un identifiant unique partagé entre neuf personnes** | `ACC-01`, A.8.5 | **Non-conformité majeure** | La MFA est **absente sur la totalité** du canal de maintenance distant, et l'identifiant unique partagé entre neuf personnes rend l'imputabilité **inopérante**, pas dégradée, sur un accès permanent à des applications métier |
| **C2** | Santé | Machines d'analyse et consoles d'imagerie sur la **même plage IP** que la bureautique, compte d'administration locale **identique sur tout le parc** | A.8.22, A.8.2 | **Non-conformité majeure** | Le cloisonnement est **absent**, pas dégradé (même plage IP) ; le compte d'administration identique sur l'ensemble du parc rend le contrôle d'accès à privilèges inopérant sur toute l'étendue du parc d'imagerie |
| **C3** | Logistique | Réseaux bureautique et industriel interconnectés, sans cloisonnement | A.8.22 | **Non-conformité majeure** | L'exigence est absente sur la **totalité** du périmètre (six sites), et l'écart expose directement les automates industriels |
| **C4** | Logistique | Compte de domaine partagé avec la TMA du WMS, porté par un nombre de personnes que personne ne peut établir | A.5.19, A.8.2 | **Non-conformité majeure** | L'imputabilité est **inopérante**, pas dégradée : l'audit interne a demandé la liste nominative des porteurs et a reçu un nom de compte, aucun nom de personne |
| **C5** | Éducation | Comptes d'administration partagés entre les équipes des deux filiales du cluster (DSI mutualisée), personne ne pouvant dire qui a fait quoi | A.5.16, A.8.2 | **Non-conformité majeure** | L'imputabilité est inopérante **entre deux filiales**, pas sur un cas isolé — c'est le fonctionnement courant de la DSI mutualisée, pas un incident ponctuel |
| **C6** | Territoires | Journaux conservés localement six mois, **jamais transmis** au SOC centralisé du groupe, consultés sur demande seulement ; demande de contact du SOC restée sans réponse | `JRN-01`, A.8.15 | **Non-conformité majeure** *(débattue — voir ci-dessous)* | La collecte centralisée exigée par `JRN-01` est **totalement absente** pour cette filiale, qui relève en outre du RGS — un cadre où la traçabilité outillée n'est pas un confort |
| **C7** | Logistique↔Santé | VLAN dédié et pare-feu d'inspection en place sur l'API de réapprovisionnement d'urgence, **seul cloisonnement du groupe** ; flux suspendu depuis trois mois à la demande du RSSI Santé | A.8.22 | **Conforme** *(sur ce flux)* | Le cloisonnement exigé par A.8.22 est en place et documenté sur l'interconnexion concernée ; la nuance à écrire ailleurs (TP 1, TP 2) est que ce point conforme porte sur un flux **à l'arrêt** — un conforme hors périmètre utile ne couvre rien d'autre |
| **C8** | Éducation | Onze abonnements à des services en ligne souscrits par les équipes pédagogiques hors DSI, sans contrat ni analyse d'impact (shadow IT vu en séance 2) | *aucune exigence précise directement violée* | **Observation** *(débattue — voir ci-dessous)* | L'énoncé le dit lui-même : aucune exigence précise du périmètre d'audit n'est directement violée — c'est la définition même de l'observation, un signal que l'auditeur ne peut pas accrocher à une exigence, consigné parce que le taire serait malhonnête |

---

## Les deux gradations discutables

### C6 — Territoires, journaux non centralisés

- **Argument pour « majeure »** *(gradation retenue ci-dessus)* : `JRN-01` exige la collecte vers le SOC centralisé, sans exception ; ici elle est absente à 100 %, depuis une durée non bornée, et la filiale relève du RGS, qui suppose une capacité de traçabilité mobilisable rapidement — pas seulement archivée localement.
- **Argument pour « mineure »** : les journaux **existent** et sont conservés six mois localement, ce qui limite (sans l'annuler) la perte d'information en cas d'investigation ; on pourrait lire cette rétention locale comme un contrôle compensatoire partiel qui évite le pire cas (aucune trace nulle part), ramenant l'écart à une défaillance d'acheminement plutôt qu'à une absence totale de traçabilité.

### C8 — Éducation, shadow IT

- **Argument pour « observation »** *(gradation retenue ci-dessus)* : l'énoncé exclut lui-même une exigence précisément violée ; on est dans le signal qu'il serait malhonnête de taire, pas dans l'écart mesurable contre un critère.
- **Argument pour « non-conformité mineure »** : onze abonnements sans contrat ni analyse d'impact touchent concrètement A.5.19 (relations fournisseurs — aucune clause de sécurité sur ces services) et, en creux, l'inventaire des actifs informationnels (A.5.9) puisque personne ne sait ce qui y transite ; sous cet angle l'écart est réel, seulement circonscrit et pas encore relié à un incident.

---

## Constats concernant Logistique — récapitulatif pour le TP 1

Seuls **C3, C4 et C7** entrent dans l'auto-évaluation `MERIDIAN-LOGISTIQUE` du TP 1. C1, C2, C5, C6, C8 sont gradés ici parce que le cycle d'audit est celui du groupe, mais ils appartiennent aux autres filiales et ne sont pas repris.

| Réf. | Gradation retenue |
|---|---|
| C3 | Non-conformité majeure |
| C4 | Non-conformité majeure |
| C7 | Conforme *(sur ce flux, avec sa limite)* |

---

*TD 2, exercice 1 — fait le 8 septembre 2026, avant ouverture de l'instance pour le TP 1.*
