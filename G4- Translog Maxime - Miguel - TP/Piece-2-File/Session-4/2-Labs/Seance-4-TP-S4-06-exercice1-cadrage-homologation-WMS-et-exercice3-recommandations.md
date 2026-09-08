# Séance 4, TP 2 — Exercice 1 : fiche de cadrage de l'homologation du WMS · Exercice 3 : recommandations réparées

**Groupe 4 (Translog)** · filiale d'instruction MERIDIAN Logistique
**Source** : `../../../../S4 - Sources/TP 2/Initial Audit Report and Strategy Note _ Lockbay Academy.pdf`

---

## Exercice 1 — Fiche de cadrage de l'approche d'homologation

**Système concerné** : le WMS de MERIDIAN Logistique et ses échanges avec le portail d'expédition du client pharmaceutique (un compte par entrepôt). C'est le système le plus exposé aux utilisateurs externes de la filiale — les analogues des trois autres filiales (portail de rendez-vous et SIH hébergé pour Santé, portail pédagogique pour Éducation, plateforme citoyenne pour Territoires) ne sont pas dans notre périmètre de revue.

**Déclencheur** : pour Territoires, le RGS imposerait l'homologation via le client collectivité. Pour Logistique, le déclencheur est la question que la Direction Générale du groupe a posée après l'arrêt d'avril, à la fin du pack de filiale (§7) : *« si ça s'arrête six heures, qui appelle qui, et qui décide de prévenir le client ? »* — une question qui ne trouve pas de réponse sans une décision formelle d'exploiter.

### 1. Niveau de l'approche

**Criticité** — *élevée*. Un arrêt du WMS de plus de six heures bloque **40 %** du volume expédié de tout le groupe et déclenche des pénalités de **12 000 €/jour** auprès du client pharmaceutique, dont deux entrepôts (E1 et E4) lui sont dédiés sous audit annuel de chaîne du froid.

**Exposition aux sources de risque** — *élevée*. Le WMS est atteignable depuis un réseau bureautique non cloisonné du réseau industriel (C3), administré via un compte de domaine partagé avec la TMA dont le nombre de porteurs n'est établi par personne (C4), relié aux automates par un secret unique en clair depuis 2019 (A.5.17), et il échange avec un portail externe du client sans qu'aucune exigence de sécurité contractuelle connue n'encadre cet échange.

**Croisement** — *grille de travail du groupe*, construite sur le principe enseigné (croiser criticité et exposition, quatre niveaux) plutôt qu'une reproduction du guide ANSSI/DINUM, dont le texte est payant et n'est pas cité ligne à ligne (CM méthodologie, S4) :

| | Exposition faible | Exposition moyenne | Exposition élevée |
|---|---|---|---|
| **Criticité faible** | Niveau 1 | Niveau 1 | Niveau 2 |
| **Criticité moyenne** | Niveau 1 | Niveau 2 | Niveau 3 |
| **Criticité élevée** | Niveau 2 | Niveau 3 | **Niveau 4 → WMS** |

Criticité élevée × exposition élevée = **niveau 4 sur 4 (renforcé)** : le dossier doit être instruit au niveau le plus exigeant que porte cette grille de travail — pas parce que le WMS serait un système d'importance vitale au sens réglementaire (il ne l'est pas, aucun PASSI n'est requis ici), mais parce qu'aucune décision d'exploiter n'a jamais été formalisée pour un système dont l'arrêt a un effet de groupe mesuré.

### 2. Comité d'homologation

| Rôle | Qui | Pourquoi |
|---|---|---|
| **Préside** | Directrice Générale de MERIDIAN Logistique | Elle porte déjà budget et contrats du WMS, de la TMA, de l'intégrateur et du client pharmaceutique (pack §3) — c'est elle qu'Executive Management interroge en §7 |
| **Membre** | RSSI Groupe | Instruit le dossier, présente les constats gradués et le plan d'action — **ne décide pas** |
| **Membre** | DSI de la filiale | Faisabilité technique, propriétaire de M1 et M3 |
| **Membre** | Responsable Exploitation | Propriétaire opérationnel de M2, seul détenteur du savoir-faire non écrit (D3, sous-section 2) |
| **Membre** | Responsable Qualité et Chaîne du Froid | Interface contractuelle avec les audits du client pharmaceutique |
| **Ne décide pas** | RSSI Groupe, auditeur (nous-mêmes) | Même principe que la matrice RACI de D1 : *on n'audite pas son propre travail* — celui qui a produit l'auto-évaluation ne peut pas être A sur la décision qui en découle |
| **Ne décide pas** | TMA du WMS, intégrateur | Prestataires : « décident de leurs interventions, pas de la sécurité du système d'information » (pack, carte des pouvoirs) |

### 3. Autorité d'homologation

**La Directrice Générale de MERIDIAN Logistique.** Le guide cité en CM est explicite : *« l'audit doit être cadré et autorisé par le responsable du système d'information et par sa hiérarchie »* — transposé à une décision d'exploiter, l'autorité revient à qui répond du système devant le client et devant le groupe, pas à qui le mesure.

- **Le RSSI Groupe ne peut pas** : il propose et arbitre les conflits inter-filiales, il n'administre aucun système et ne se substitue à aucune direction de filiale (D1, exclusions du périmètre).
- **L'auditeur ne peut pas** : mesurer et décider dans le même geste effacerait la seule chose qu'un audit garantit — que la mesure n'a rien à gagner à son propre verdict (CM, § indépendance).

### 4. Inventaire des pièces du dossier

| Déjà possédées (séances 1 à 3) | Produites aujourd'hui | Manquante ce soir |
|---|---|---|
| Gouvernance et RACI (D1) | Auto-évaluation outillée des douze exigences (TP 1) | **Schéma réseau daté des six sites** — exigé par M2, jamais produit ; sans lui, aucun périmètre incluant l'industriel n'est honnêtement déclarable (déjà noté comme angle mort en D3) |
| Cartographie et Top 5 (D2) | Rapport d'audit initial (D4), constats gradués et plan d'action | Vérification indépendante de l'auto-évaluation (Audit Interne du holding, non encore programmée) |
| Choix du référentiel, évaluation ISO ouverte (D3) | Suivi outillé des constats dans `translog-b` (Follow-ups) | Exécution mesurée des quatre mesures correctives (échéances Nov. 2026 → juil. 2027, aucune close à ce jour) |

### 5. Avis anticipé

**Avis visé à court terme : autorisation conditionnelle, courte (6 mois).** Deux non-conformités majeures touchent directement le système à homologuer, et l'auto-évaluation qui les révèle n'a pas encore été vérifiée par un tiers — un avis favorable sans réserve serait une promesse que le dossier ne tient pas. Une autorisation courte, subordonnée à l'exécution de **M1 et M3** (les deux corrections, qui font disparaître l'écart plutôt que d'en traiter la cause) et à la production du **schéma réseau** (M2), avec réexamen au terme sur les mêmes pièces mises à jour, est l'avis le plus honnête que le comité puisse tenir sans bluffer ni bloquer une exploitation qui, dans les faits, n'a jamais cessé.

---

## Exercice 3 — Réparer trois recommandations

*Chaque recommandation reçue viole une des trois disciplines : rattachée à un constat, exprimée en résultat vérifiable, priorisée. Rattachées ici à des constats gradés le 8 septembre 2026 (TD 2), pas nécessairement ceux de Logistique — l'exercice porte sur la discipline d'écriture, pas sur le périmètre de notre filiale.*

| # | Recommandation reçue | Discipline violée | Version réparée |
|---|---|---|---|
| **R1** | « Great care must be taken with password management in all subsidiaries. » | **Résultat vérifiable** (aucun état mesurable — « great care » ne se contrôle pas) et **rattachement** (aucun constat cité) | *« MERIDIAN Santé déploie l'authentification multi-facteurs sur l'intégralité du canal de maintenance distant du SIH, aujourd'hui protégé par un identifiant unique partagé entre neuf personnes. »* (C1) |
| **R2** | « Deploy a latest-generation SIEM to solve the logs problem. » | **Rattachement** (« the logs problem » n'existe pas comme constat — c'est un symptôme, pas une cause citée) et **priorisation** (aucune indication de ce qui presse) | *« MERIDIAN Territoires met en place la collecte automatisée de ses journaux vers le SOC centralisé du groupe, aujourd'hui conservés localement six mois et jamais transmis malgré une demande de contact du SOC restée sans réponse. »* (C6) |
| **R3** | « Supplier security must become an absolute priority for the group. » | **Résultat vérifiable** (« absolute priority » n'est pas un état à observer) et **priorisation** (« absolute » n'est pas une position dans une hiérarchie de gradation, c'est une déclaration d'intention) | *« MERIDIAN Logistique exige contractuellement de la TMA du WMS une journalisation par utilisateur nommé, aujourd'hui absente d'un contrat qui ne prévoit qu'une astreinte. »* (C4) |

**Vérification** : les trois versions réparées citent leur constat entre parenthèses, décrivent un état observable et non un vœu, et n'affirment aucune priorité qui ne soit pas déjà celle de la gradation du constat cité (deux majeures, une majeure).

---

*TP 2, exercices 1 et 3 — faits le 8 septembre 2026. Alimentent la section 6 de D4 (approche d'homologation) et illustrent, hors périmètre Logistique pour R1/R2, la discipline de rédaction exigée en section 4 de D4.*
