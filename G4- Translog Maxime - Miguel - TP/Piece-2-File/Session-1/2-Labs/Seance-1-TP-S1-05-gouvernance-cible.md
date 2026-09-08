# Séance 1 — TP (S1-05) : Framing the MERIDIAN case and target governance
### Livrables du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN

> Objectif de l'heure : à la fin, la gouvernance du groupe existe **sur papier**. Trois documents produits : l'analyse d'écart, la gouvernance cible (2 pages, 4 sections), le premier tableau de bord d'indicateurs.

---

## Exercice 1 — L'analyse d'écart du groupe (20 min)

*Cible = les principes du TD + l'architecture de gouvernance du CM. État observé = les constats de la journée + 2 signalements reçus en direct : Santé (mots de passe locaux sans MFA sur applis métier) et Territoires (logs conservés localement, non centralisés).*

### Le tableau

| Filiale | Écart observé | Principe / règle cible violé(e) | Priorité (1–3) et justification |
|---|---|---|---|
| Santé | Analyseurs de labo et consoles d'imagerie sur l'IP range bureautique, avec un compte administrateur commun | Cloisonnement réseau + moindre privilège | **1** — la mission de soin repose directement dessus ; un poste de bureau compromis atteint l'équipement de soin en une étape |
| Santé | Mots de passe locaux sans MFA sur les applications métier | Moindre privilège (authentification faible = privilège d'accès mal gardé) | **2** — sérieux, mais sans chemin d'attaque aussi direct que le constat précédent |
| **Logistique** | **Réseaux IT et OT interconnectés, sans cloisonnement** | **Cloisonnement réseau** | **1** — la continuité d'expédition de TOUT LE GROUPE en dépend (un arrêt bloque l'acheminement, pas seulement la filiale) |
| **Logistique** | **Compte de domaine partagé avec le prestataire de Tierce Maintenance (TMA), utilisateurs non identifiables** | **Moindre privilège** | **2** — grave (traçabilité et révocation impossibles) mais sans exposition directe au public comme chez Santé |
| Éducation | Comptes administrateur partagés entre équipes de la division mutualisée | Moindre privilège | **2** — aggravé par les moyens limités, mais périmètre pédagogique moins vital que soin ou expédition |
| Territoires | Logs conservés localement, non centralisés | Absence de traçabilité groupée (aucun principe du TD directement, mais viole l'esprit de la défense en profondeur : pas de détection possible) | **2** — ni détection ni analyse post-incident possibles, et une clientèle de ~30 collectivités qui exigera des comptes |
| **Groupe** | **Absence de PSSI-cadre et de règles d'arbitrage écrites** | — (c'est la racine, pas une déclinaison) | Non noté en 1-3 : c'est l'écart **structurel** dont tous les autres découlent |

**Respect de la contrainte « au plus 2 priorités 1 pour tout le groupe »** : nous retenons **Santé (équipement biomédical)** et **Logistique (interconnexion IT/OT)** — les deux seuls écarts dont l'atteinte toucherait la **mission** du groupe de façon immédiate et non substituable (soigner, expédier), plutôt que des écarts sévères mais absorbables (mots de passe, comptes partagés localement).

### Réponse à « repérer l'écart qui n'appartient à aucune filiale »

**La ligne « Groupe »** : l'absence de PSSI-cadre et de règles d'arbitrage écrites. Ce n'est un écart d'aucune des quatre filiales prise isolément — c'est précisément ce qui explique pourquoi les quatre écarts ci-dessus n'ont jamais été traités : sans cadre commun, chaque filiale a géré sa sécurité « comme elle l'entendait » (dixit le dossier d'ouverture). Aucune filiale ne peut combler seule cet écart ; seul le groupe le peut. C'est l'écart que l'Exercice 2 ci-dessous adresse directement.

---

## Exercice 2 — Rédaction de la gouvernance cible (25 min)

*Document : « Target governance of MERIDIAN group security », 2 pages max, 4 sections.*

### Section 1 — Instances et appétence au risque (reprise du CM)

| Instance | Rôle en gouvernance | Rôle sur l'appétence au risque |
|---|---|---|
| Conseil d'Administration | Approuve les orientations sécurité du groupe | **Accountable** — approuve formellement |
| Direction Générale | Porte la stratégie sécurité, engage les ressources | **Responsible** — fixe et propose |
| Comité Exécutif | Fixe les priorités budgétaires, valide la stratégie | Valide la déclinaison opérationnelle et budgétaire |
| RSSI Groupe | Rédige la PSSI, propose le cadre, arbitre les conflits inter-filiales | **Consulted** — informe, ne fixe ni n'approuve |

**Ce que cette section empêche** : elle rend impossible le **Dossier 1 du lundi matin** (le blocage de trois mois entre Logistique et Santé) — désormais, un conflit inter-filiales a un arbitre identifié (le RSSI Groupe) et une instance d'approbation finale (le Comité Exécutif), au lieu de deux filiales qui s'opposent indéfiniment faute d'arbitre désigné.

### Section 2 — RACI des processus clés

| Processus | COMEX | RSSI Groupe | Équipes IT/métier | Auditeur SSI |
|---|---|---|---|---|
| Validation de la PSSI et de ses adaptations | A | R | C | I |
| Arbitrage des budgets/projets sécurité | A | C | R | I |
| Maintien en condition de sécurité | I | A | R | I |
| Évaluation de conformité / audits de sécurité | I | C | I | R/A |

**Ce que cette section empêche** : elle rend impossible le **Dossier 3 du lundi matin** (l'Auditeur Interne proposant de reprendre lui-même la gestion du registre des comptes administrateur de Santé) — la ligne « audit » place l'auditeur R **et** A **uniquement sur son propre processus** (l'évaluation de conformité), jamais sur un processus qu'il est censé contrôler. Un auditeur A sur le maintien en condition de sécurité ne pourrait plus auditer son propre travail.

### Section 3 — Directives codifiées (au moins 5, thèmes imposés)

- `[PSSI-CADRE-ACC-01]` **Authentification multi-facteurs (MFA)** obligatoire sur tout accès distant et tout privilège d'administration. *Propriétaire : DSI de chaque filiale. Vérifiable : taux de comptes à privilèges couverts par MFA, mesurable dans l'outil de gouvernance.*
- `[PSSI-CADRE-ACC-02]` **Revue trimestrielle** des privilèges d'accès sur les bases de données métier. *Propriétaire : RSSI de filiale. Vérifiable : date de la dernière revue, écart au calendrier trimestriel.*
- `[PSSI-CADRE-INC-01]` **Notification de tout incident majeur au RSSI Groupe sous 2 heures.** *Propriétaire : chaque filiale. Vérifiable : délai réellement mesuré entre détection et notification, comme cela aurait dû arriver lors de l'arrêt du WMS de Logistique en avril.*
- `[PSSI-CADRE-JRN-01]` **Collecte des journaux** vers le SOC centralisé du groupe, en montée en charge. *Propriétaire : RSSI Groupe (SOC), DSI de filiale (source). Vérifiable : % du périmètre dont les logs remontent effectivement.*
- `[PSSI-CADRE-COR-01]` **Application de tout correctif critique sous 14 jours.** *Propriétaire : DSI de filiale. Vérifiable : délai entre publication du correctif et application effective.*

**Test du sceptique appliqué** : pour chacune, *« comment saurait-on qu'elle N'EST PAS respectée ? »* — chaque directive porte une mesure explicite (taux, délai, date), donc une réponse immédiate. Une directive du type « renforcer la sécurité des accès » aurait échoué à ce test.

### Section 4 — Règles d'arbitrage inter-filiales (3 règles)

- `[ARB-01]` Le **RSSI Groupe** détient un **véto suspensif** sur toute décision d'une filiale engageant la sécurité du groupe ; arbitrage rendu **sous 72 heures**. *Un véto qui suspend sans enterrer — c'est ce qui le rend acceptable politiquement.*
- `[ARB-02]` Chaque **RSSI de filiale** détient un **droit d'isolement d'urgence** sur tout flux inter-filiales en cas de compromission confirmée. *En crise, on coupe d'abord, on arbitre ensuite.*
- `[ARB-03]` Toute **dérogation** à la PSSI-cadre est validée par le RSSI Groupe **sous 48 heures**. *Une dérogation sans circuit devient un droit acquis.*

---

## Exercice 3 — Premier tableau de bord du RSSI Groupe (15 min)

### KRI (4 max, expositions qui grandissent seules si personne n'agit)

| KRI | Cible | Seuil d'alerte | Exposition surveillée |
|---|---|---|---|
| Part du périmètre non supervisé par le SOC (logs non collectés) | < 5 % | > 20 % | Ce que le SOC ne voit pas |
| Part d'OS/firmwares obsolètes sur le parc | < 5 % | > 15 % | Vieillissement du parc |
| Comptes à privilèges **non nominatifs** (ex. le compte partagé TMA de Logistique) | 0 | > 5 | Comptes qui ne désignent personne |
| Taux de clic en campagne de phishing simulée | < 5 % | > 15 % | Le facteur humain |

### KPI de mise en œuvre (3 à 5, chacun rattaché à UNE directive de l'exercice 2)

| KPI | Cible | Directive rattachée |
|---|---|---|
| Comptes à privilèges protégés par MFA | 100 % | `[PSSI-CADRE-ACC-01]` |
| Comptes inactifs non révoqués à 30 jours | 0 | `[PSSI-CADRE-ACC-02]` |
| Vulnérabilités critiques non corrigées à 14 jours | 0 | `[PSSI-CADRE-COR-01]` |
| Délai moyen de notification d'un incident majeur | < 30 min *(plus strict que l'obligation contractuelle de 2h — c'est le sens d'une cible interne)* | `[PSSI-CADRE-INC-01]` |

### Vérification de cohérence avec les priorités 1

- **Santé** (équipement biomédical + compte admin commun) → couvert par le **KRI comptes non nominatifs** + le **KPI de couverture MFA**.
- **Logistique** (interconnexion IT/OT) → couvert par le **KRI du périmètre non supervisé** (le SOC ne reçoit aujourd'hui aucun log des automates ni de la box 4G de l'intégrateur) — cet écart précis est donc bien visible dans le tableau de bord, pas seulement dans le texte de la gap analysis.

*Un tableau de bord qui ne montrerait pas ce rattachement serait décoratif — c'est la règle rappelée par le TP.*

---

## Auto-évaluation

| Critère | Notre niveau atteint |
|---|---|
| Gap analysis | Tableau complet, priorités justifiées par la mission (pas la sévérité seule), ligne « Groupe » identifiée comme écart racine |
| Directives | 5 thèmes imposés couverts, codifiés, chacune passe le test du sceptique (mesure explicite) |
| Règles d'arbitrage | Les 3 circuits écrits, avec la justification de chaque équilibre (suspendre sans enterrer, couper puis arbitrer) |
| Indicateurs | 4 KRI avec cible/seuil, KPI rattachés aux directives, cohérence explicitement vérifiée contre les 2 priorités 1 |
| Dossiers du lundi | Chaque section de la gouvernance rattachée explicitement au dossier qu'elle rend impossible (1 → RACI/arbitrage, 3 → RACI audit) |
