# D4 — RAPPORT D'AUDIT INITIAL : MERIDIAN LOGISTIQUE

**Émetteur** RSSI Groupe (auto-évaluation outillée, premier cycle du programme d'audit interne)
**Destinataires** Direction Générale de MERIDIAN Logistique (décide), Comité Exécutif Groupe (informé), DSI et Exploitation de la filiale (agissent)
**Groupe 4 (Translog)** · instance `translog-b` · **Séance 4** · trois pages

---

## 1. Cadrage

**Périmètre** : MERIDIAN Logistique — six entrepôts (E1 à E6), le WMS et ses ~300 scannettes, les automates de tri d'E2/E3/E4, la chaîne du froid ; actifs cartographiés en séance 2 (`LOG-PA-01` à `04`, `LOG-SA-01` à `13`). **N'est pas audité** : les trois autres filiales du groupe, et les 111 exigences ISO/IEC 27001:2022 hors du sous-ensemble de douze retenu ce jour.

**Critères** : ISO/IEC 27001:2022 (les douze exigences évaluées, Annexe A), les directives PSSI-cadre codifiées en séance 1 (`ACC-01`, `ACC-02`, `INC-01`, `JRN-01`, `COR-01`), et les fondations réglementaires et contractuelles de la filiale posées en séance 3 (contrat du client pharmaceutique — pénalités et audits chaîne du froid).

**Méthode et limite assumée** : ce rapport s'appuie sur une **auto-évaluation outillée** de la filiale sous revue, conduite par le RSSI Groupe lui-même dans l'instance de gouvernance — elle n'a donc **pas** l'indépendance qu'exige la définition normative de l'audit (ISO/IEC 27000:2018 ; CM méthodologie, S4). Elle est complétée par les constats du cycle d'audit interne des quatre filiales, gradés le matin même (TD 2) selon la même discipline — l'exigence citée et l'étendue mesurée de l'écart, jamais la gravité ressentie. Cette limite est reprise en section 6 : une vérification indépendante reste à programmer avant toute décision engageant durablement le groupe.

---

## 2. Synthèse pour décision

Sur les douze exigences ISO évaluées, **aucune n'est pleinement couverte** ; deux sont partielles et neuf ne le sont pas, concentrées sur le cloisonnement réseau, les accès à privilèges et la gouvernance des comptes tiers. Le point le plus solide du jour est aussi le plus étroit : le seul cloisonnement réseau du groupe existe bel et bien entre Logistique et Santé, mais sur un flux suspendu depuis trois mois — un point conforme qui ne protège rien tant qu'il reste à l'arrêt. Ce qui reste inconnu est nommé, pas deviné : la sensibilisation à la sécurité (A.6.3) n'a fait l'objet d'aucune preuve, ni pour ni contre, faute d'avoir posé la question à la filiale. Le point urgent est celui qui relie deux non-conformités majeures au même système : le réseau bureautique, non cloisonné du réseau industriel, et le compte de domaine partagé avec la TMA du WMS exposent directement le système dont l'arrêt bloque 40 % du volume expédié du groupe et déclenche des pénalités de 12 000 €/jour. Quatre mesures correctives sont déjà assignées à un propriétaire nommé et à une échéance ; ce qui reste à faire est nommé en section 6, notamment l'approche d'homologation du WMS, cadrée mais incomplète.

---

## 3. Constats gradués

### 3.1 Constats du cycle d'audit groupe (TD 2, gradés le matin même)

| Réf. | Constat | Critère cité | Preuve | Gradation |
|---|---|---|---|---|
| **C3** | Réseaux bureautique et industriel interconnectés, sans cloisonnement, sur les six sites | A.8.22 | Pack de filiale §3, §5(1) ; auto-évaluation A.8.22 = *Non compliant* | **Non-conformité majeure** — exigence absente sur la totalité du périmètre |
| **C4** | Compte de domaine partagé entre l'administrateur système et la TMA du WMS, porteurs inconnus | A.5.19, A.8.2 | Pack de filiale §3, §5(2) ; audit interne du holding sans réponse nominative ; auto-évaluation A.5.15/A.5.16/A.5.19/A.8.2 = *Non compliant* | **Non-conformité majeure** — imputabilité inopérante, pas seulement dégradée |
| **C7** | VLAN dédié + pare-feu d'inspection sur l'interconnexion de réapprovisionnement d'urgence Logistique↔Santé | A.8.22 | Pack de filiale §6 ; auto-évaluation A.8.22 (nuance) | **Conforme**, sur ce flux uniquement — flux suspendu depuis trois mois, un point conforme hors périmètre utile ne couvre pas le reste (cf. C3) |

### 3.2 Écarts complémentaires identifiés par l'auto-évaluation (statuts saisis, non gradés par le TD 2)

*Le TD 2 a gradé huit constats pour le groupe avant l'ouverture de l'instance ; l'auto-évaluation exigence par exigence, l'après-midi, en a mis au jour d'autres, sourcés directement au pack de filiale. Ils n'ont pas de lettre « C » — ce n'est pas un oubli, c'est que la gradation matinale portait sur un ensemble plus restreint que la maille de l'auto-évaluation.*

| Exigence | Statut | Preuve | Actifs |
|---|---|---|---|
| A.5.9 | Partiellement couvert | Cartographie S2 (Top 5), règle de tenue à 30 jours écrite mais non appliquée | SA-01…SA-13 |
| A.5.17 | Non couvert | Pack §4 : secret du compte de service WMS↔automates identique sur les six entrepôts depuis 2019, en clair dans un fichier de configuration | SA-04 |
| A.5.22 | Non couvert | Pack §4 : « la TMA fait les mises à jour la nuit, quand elle veut » — aucun contrôle de changement | SA-01, SA-03 |
| A.8.5 | Non couvert | `ACC-01` (MFA obligatoire) + pack §5.3 : secret de compte de service en clair | SA-01, SA-03, SA-04 |
| A.8.8 | Non couvert | `COR-01` (correctif sous 14 jours) : ni mesuré ni mesurable, mises à jour décidées par la TMA sans préavis | SA-01, SA-03 |
| A.8.15 | Partiellement couvert | Le SOC groupe reçoit les journaux du réseau bureautique ; rien des automates, de la liaison 4G ni du WMS lui-même | SA-01, SA-03 |

**Angle mort assumé** : A.6.3 (sensibilisation) reste **non évalué** — aucune preuve dans un sens ni dans l'autre. Traité en section 6, pas ici : ce n'est ni une conformité, ni un écart, c'est une question qui n'a pas été posée.

---

## 4. Recommandations

*Priorisées par gradation — majeure avant partiel — jamais par une pondération de risque, qui n'existe pas encore (elle ouvre en séance 5).*

1. **MERIDIAN Logistique isole le réseau des automates de tri (E2/E3/E4) sur un VLAN dédié, filtrage en défaut-refus vis-à-vis du réseau bureautique, matrice de flux documentée.** *(C3)*
2. **MERIDIAN Logistique soumet tout raccordement futur d'équipement industriel à un avis d'architecture écrit de la DSI filiale avant mise en service, et porte cette exigence au contrat de l'intégrateur.** *(C3)*
3. **MERIDIAN Logistique exige contractuellement de la TMA du WMS une journalisation par utilisateur nommé et tient un registre nominatif des comptes de service et à privilèges, revu trimestriellement.** *(C4)*
4. **MERIDIAN Logistique remplace le secret partagé du compte de service WMS↔automates par un secret distinct par entrepôt, retiré des fichiers de configuration en clair, déposé dans un coffre à secrets.** *(A.5.17)*
5. **MERIDIAN Logistique étend la collecte de journaux vers le SOC centralisé aux automates, à la liaison 4G de l'intégrateur et au WMS lui-même.** *(A.8.15)*

**Aucune recommandation sur C7** : le point est conforme sur son flux ; la reprise du flux Logistique↔Santé relève de l'arbitrage inter-filiales `ARB-01` (D1), hors du présent audit.

---

## 5. Plan d'action correctif

*Les quatre mesures saisies dans l'instance en TP 1, propriétaire nominatif et échéance à l'appui — correction et action corrective jamais confondues.*

| # | Rattachée à | Type | Ce qu'elle fait | Propriétaire | Échéance |
|---|---|---|---|---|---|
| **M1** | A.8.22 *(C3)* | **Correction** | VLAN dédié automates E2/E3/E4, filtrage en défaut-refus | Miguel (DSI filiale + Resp. Exploitation) | 12/7/2027 — hors pic |
| **M2** | A.8.22, A.5.19 *(C3)* | **Action corrective** | Schéma réseau des six sites, avis d'architecture obligatoire, clause au contrat de l'intégrateur | Maxime + Miguel | 8/12/2026 |
| **M3** | A.5.17, A.8.2 | **Correction** | Six secrets distincts, coffre à secrets, rotation | Miguel (DSI filiale) | 8/11/2026 |
| **M4** | A.8.2, A.5.19, A.5.15 *(C4)* | **Action corrective** | Registre nominatif des comptes de service, journalisation nominative exigée de la TMA | Maxime + Miguel | 8/11/2026 |

**Test SMART vérifié pour les quatre** : chacune mesurable, datée, non reformulable en objectif de sensibilisation. Détail complet : `Seance-4-TP-S4-05-feuille-de-travail-auto-evaluation.md`, section 4.

---

## 6. Angles morts et suite

**Ce qui reste explicitement non évalué** : A.6.3 (sensibilisation) — à poser à la filiale avant le prochain cycle, pas à estimer.

**L'audit indépendant à programmer** : ce rapport est une auto-évaluation, pas un audit au sens normatif — il lui manque l'indépendance. L'Audit Interne du holding, qui a déjà demandé la liste nominative des porteurs du compte de la TMA sans l'obtenir (pack de filiale §3), est le candidat naturel pour la vérification indépendante du prochain cycle.

**La suite immédiate** : l'analyse de risque de la séance 5 pondérera ces écarts par conséquence et vraisemblance — ce rapport ne priorise que par gradation, il ne préjuge d'aucun poids de risque. L'approche d'homologation du système le plus exposé de la filiale (le WMS et ses échanges avec le portail d'expédition du client pharmaceutique) est cadrée en exercice complémentaire — voir `Seance-4-TP-S4-06-exercice1-cadrage-homologation-WMS-et-exercice3-recommandations.md` — mais reste incomplète : il y manque ce soir un schéma réseau daté des six sites (exigé par M2, inexistant à ce jour).

---

> **Pièces à l'appui** : feuille de travail de l'auto-évaluation `../2-Labs/Seance-4-TP-S4-05-feuille-de-travail-auto-evaluation.md` · gradation TD 2 `../4-Working-notes/Seance-4-TD-S4-03-gradation-des-constats.md` · suivi outillé des constats et des mesures dans `translog-b` (Follow-ups → *MERIDIAN Logistique - Internal audit - Initial audit report (S4)*) · captures `../3-Evidence/`.
