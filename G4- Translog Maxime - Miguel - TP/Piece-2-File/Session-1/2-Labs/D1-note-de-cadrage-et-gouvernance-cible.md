# D1 — NOTE DE CADRAGE ET GOUVERNANCE CIBLE DU GROUPE MERIDIAN

**Émetteur** RSSI Groupe · **Destinataires** Direction Générale, Comité Exécutif, Conseil d'Administration
**Groupe 4 (Translog)** · filiale d'instruction MERIDIAN Logistique · **Séance 1** · deux pages

---

# Partie 1 — Cadrage

## Périmètre

Les **quatre filiales** du groupe — Santé (3 200 salariés, 4 établissements de soin), Logistique (2 800, 6 entrepôts), Éducation (900, 45 000 comptes), Territoires (650, ~30 collectivités clientes) —, la **division mutualisée Éducation & Territoires** et sa DSI commune, **l'ensemble des flux inter-filiales**, et la relation du RSSI Groupe avec les instances du groupe.

**Exclusions assumées**, parce qu'un périmètre qui ne dit pas ce qu'il exclut n'est pas un périmètre. Le RSSI Groupe **ne fixe pas** l'appétence au risque : il la propose et en informe les instances. Il **n'administre aucun système** : l'exploitation appartient aux filiales — le WMS de Logistique reste sous la responsabilité de son DSI et de sa TMA. Il **ne se substitue pas** aux RSSI de filiale dans l'adaptation de la PSSI-cadre : il la valide, il ne l'écrit pas à leur place.

## Enjeux

Ce que le groupe perd si la sécurité n'est pas gouvernée — exprimé en mission, pas en technique :

- **La continuité d'expédition du groupe.** Un arrêt du WMS de Logistique supérieur à six heures bloque **40 % du volume expédié de tout le groupe**. La continuité n'a jamais été testée : les sauvegardes quotidiennes n'ont pas été restaurées une seule fois depuis la mise en service.
- **La parole du groupe devant ses clients.** Le client pharmaceutique de Logistique impose des audits annuels de chaîne du froid et des pénalités de **12 000 €/jour d'arrêt** ; les ~30 collectivités clientes de Territoires conditionnent la relation à des garanties de sécurité.
- **La capacité des filiales à travailler ensemble.** Le flux d'approvisionnement d'urgence Logistique → Santé est **bloqué depuis trois mois**, faute d'arbitre désigné : deux filiales s'opposent, personne ne tranche.
- **L'exposition réglementaire.** Trois filiales sur quatre entreront dans le champ de la directive NIS 2 à la promulgation de la loi de transposition ; le RGPD s'applique déjà aux quatre.
- **La mission de soin.** Chez Santé, équipements biomédicaux et postes bureautiques partagent le même réseau, avec un compte administrateur commun.

## Parties prenantes

| Partie prenante | Ce qu'elle attend du RSSI Groupe | Ce qu'elle lui doit |
|---|---|---|
| Conseil d'Administration | Une vision d'exposition lisible, sans jargon | L'approbation formelle de l'appétence au risque |
| Direction Générale | Des propositions arbitrables et le signalement précoce | Le mandat, l'accès et l'engagement des ressources |
| Comité Exécutif | Un reporting régulier et des arbitrages instruits | La validation de la déclinaison et des budgets |
| RSSI et DSI de filiale | Un cadre commun, pas une tutelle | La tenue de l'inventaire et la remontée des incidents |
| Auditeur interne SSI | L'accès aux pièces | Une évaluation indépendante — jamais dirigée par le RSSI Groupe |
| Prestataires (TMA, intégrateur) | Des exigences écrites au contrat | Traçabilité nominative et réversibilité |

## Contraintes

Elles sont réelles et elles bornent ce qui est promettable : le poste de **RSSI Groupe a six semaines**, **sans prédécesseur**, **sans PSSI existante** et **sans budget consolidé** ; la Direction Générale exige de **n'engager aucun budget nouveau la première année** ; les quatre filiales ont des métiers disjoints et deux d'entre elles partagent une DSI ; la **maturité SSI est homogène et basse — niveau 2 sur 4 pour les quatre filiales** ; les moyens d'Éducation sont limités.

*Ces contraintes ne sont pas les exclusions ci-dessus : les exclusions disent ce que le RSSI Groupe n'a pas le droit de faire, les contraintes ce qu'il ne peut pas faire.*

---

# Partie 2 — Gouvernance cible

## Schéma de gouvernance à trois niveaux

| Niveau | Instance | Fréquence | Nature des décisions |
|---|---|---|---|
| **Stratégique** | Conseil d'Administration | **Annuelle**, + saisine exceptionnelle sur incident majeur | Approuve l'appétence au risque et les orientations pluriannuelles |
| **Stratégique** | Direction Générale | **Mensuelle** | Fixe et propose l'appétence, porte la stratégie, engage les ressources |
| **Tactique** | Comité Exécutif | **Trimestrielle** — la revue déjà engagée au titre du reporting du RSSI Groupe | Valide la déclinaison de la PSSI-cadre, arbitre budgets et priorités |
| **Tactique** | Comité sécurité groupe (RSSI Groupe + RSSI de filiale) | **Mensuelle** | Pilote les projets, prépare les arbitrages inter-filiales |
| **Opérationnel** | Équipes IT et métier des filiales, SOC | **Continue** | Exploite, supervise, détecte, corrige |
| **Opérationnel** | Cellule de crise | **Sur déclenchement** — notification d'incident majeur sous 2 h | Décide de l'isolement, de la reprise et de l'information client |

**Ce que ce tableau empêche** : le blocage de trois mois du flux Logistique ↔ Santé. Un conflit inter-filiales a désormais un arbitre identifié et une instance d'approbation, au lieu de deux filiales qui s'opposent sans que personne ne tranche.

## Matrice RACI des processus clés

| Processus | Comité Exécutif | RSSI Groupe | Équipes IT / métier | Auditeur SSI |
|---|---|---|---|---|
| Validation de la PSSI et de ses adaptations | **A** | R | C | I |
| Arbitrage des budgets et projets sécurité | **A** | C | R | I |
| Maintien en condition de sécurité | I | **A** | R | I |
| Évaluation de conformité et audits | I | C | I | **R/A** |

*Un seul A par ligne. **Ce que cette matrice empêche** : que l'auditeur interne reprenne la gestion du registre des comptes à privilèges de Santé — il est A sur son seul processus d'évaluation, jamais sur un processus qu'il doit contrôler. On n'audite pas son propre travail.*

## Directives codifiées de la PSSI-cadre

Chacune passe le test du sceptique — *comment saurait-on qu'elle n'est pas respectée ?* — donc chacune porte une mesure, un propriétaire et une échéance.

| Code | Directive | Propriétaire | Vérifiable par |
|---|---|---|---|
| `PSSI-CADRE-ACC-01` | Authentification multi-facteurs obligatoire sur tout accès distant et tout privilège d'administration | DSI de filiale | Taux de comptes à privilèges couverts |
| `PSSI-CADRE-ACC-02` | Revue trimestrielle des privilèges sur les bases de données métier | RSSI de filiale | Date de la dernière revue, écart au calendrier |
| `PSSI-CADRE-INC-01` | Notification de tout incident majeur au RSSI Groupe **sous 2 heures** | Chaque filiale | Délai mesuré entre détection et notification |
| `PSSI-CADRE-JRN-01` | Collecte des journaux vers le SOC centralisé, en montée en charge | RSSI Groupe (SOC), DSI de filiale (source) | % du périmètre dont les journaux remontent |
| `PSSI-CADRE-COR-01` | Application de tout correctif critique **sous 14 jours** | DSI de filiale | Délai entre publication et application |

## Règles d'arbitrage inter-filiales

| Code | Règle | Équilibre recherché |
|---|---|---|
| `ARB-01` | Véto suspensif du RSSI Groupe sur toute décision de filiale engageant la sécurité du groupe ; arbitrage rendu **sous 72 h** | Suspendre sans enterrer — c'est ce qui le rend politiquement acceptable |
| `ARB-02` | Droit d'isolement d'urgence de tout RSSI de filiale sur un flux inter-filiales en cas de compromission confirmée | En crise, on coupe d'abord, on arbitre ensuite |
| `ARB-03` | Toute dérogation à la PSSI-cadre validée par le RSSI Groupe **sous 48 h** | Une dérogation sans circuit devient un droit acquis |

---

> **Engagement de trajectoire** : chaque filiale adapte la PSSI-cadre **sous six mois**. C'est le premier jalon opposable, et la première chose que ce document rend vérifiable.
