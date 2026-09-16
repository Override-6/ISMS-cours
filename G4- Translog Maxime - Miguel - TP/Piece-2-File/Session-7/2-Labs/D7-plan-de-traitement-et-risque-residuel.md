# D7 — PLAN DE TRAITEMENT ET RISQUE RÉSIDUEL

**Groupe 4 (Translog)** · Miguel Monereo, Maxime · filiale d'instruction **MERIDIAN Logistique** · instance `translog-b`, domaine `MERIDIAN-LOGISTIQUE`
**Registre source** : `Registre de risques MERIDIAN Logistique - cycle 1 - 1.0` (`translog-b`), assemblé au TP 1 — 8 lignes, chacune décidée et résiduel coté. Trace complète : `Seance-7-TP-S7-05-feuille-de-travail-atelier4-et-registre.md`.
**Échelle et appétence** : D5 (`../../Session-5/2-Labs/D5-appreciation-initiale-des-risques.md`), ligne d'acceptation confirmée au TD du matin (`Seance-7-TD-S7-03-matrices-de-cotation-et-options-de-traitement.md`).

> **État d'une donnée de ce fichier** : les coûts par mesure (colonne *Coût*) sont **calculés à la main** ci-dessous, à partir des estimations posées à la sous-section 1, avec le même taux journalier que l'instance (500 €/jour, laissé tel quel dans *Paramètres → Général → Paramètres financiers*). **La section *Coût* est saisie dans `translog-b` sur les 13 mesures** (captures `S7-06-mesures-appliquees-couts-build-run.jpg` et `S7-06-plan-d-action-apercu-budgetaire.jpg`) : l'aperçu budgétaire de l'onglet *Plan d'action* lit **82 K €/an** de coût total (123 K € de build fixe sur 115 jours-personnes, 16 K € de run annuel fixe sur 31 jours-personnes) — cohérent au millier d'euros près avec le calcul manuel ci-dessous. **`PT-13` existait dans `translog-b` sans être rattachée à un scénario de risque** (« orpheline », donc absente du plan d'action) ; elle a été rattachée à `AP.02` (OS2, son vecteur d'entrée) et compte désormais dans les 13/13 contrôles du registre. Les deux **`Risk acceptances`** formelles (ER3, ER6) ont également été créées dans l'outil (menu *Governance*, champs `Approver` + `Expiry date` — voir note d'écart de la feuille S7-05). Reste dû : l'export du rapport d'étude (`S7-06-rapport-etude-EBIOS-RM-ateliers-4-5`).

---

## 0. Les quatre exigences d'acceptation, vérifiées une par une

| # | Exigence | Vérifiée sur | Résultat |
|---|---|---|---|
| **1** | Aucun risque du registre sans décision | Les 8 lignes (§2) | ✅ — 8/8 portent une décision (`Mitigated` ×6, `Accepted` ×2). Le registre en comptait 6 après génération unique de l'atelier 5 ; ER2 et ER6 ont été créés à la main au TP 1 (note d'écart, feuille S7-05) précisément pour que cette exigence tienne. |
| **2** | Tout résiduel qui dépasse l'appétence porte une dérogation motivée | Les 8 résiduels (§2) | ✅ par le fait — **aucun résiduel ne dépasse `Medium`**, la ligne d'acceptation de D5. Zéro dérogation à demander ; §4 l'écrit et dit pourquoi. |
| **3** | Cotations cohérentes avec les échelles de D5, jamais recréées | Toutes les cotations, actuelles et résiduelles | ✅ — `Unlikely/Likely/Very likely/Certain` et `Minor/Significant/Important/Critical`, mot pour mot, aucune échelle réinventée (vérifié à la matrice `4x4 risk matrix from EBIOS-RM`, lecture seule). |
| **4** | Chaque risque porte option, mesures, responsable, échéance et résiduel coté | Les 8 lignes (§2) | ✅ pour l'option, la mesure et le résiduel, saisis dans `translog-b`. Le **responsable** est nommé en clair dans ce fichier (§2, §3) et dans la justification de chaque scénario, car le champ `Assigned to` de l'outil n'accepte que des comptes de l'instance, pas les rôles du pack §3 — écart déjà consigné au TP 1. |

---

## 1. Le plan de traitement, par décision

**Organisation par décision, pas par scénario** — un comité arbitre des décisions. Les mesures qui traitent plusieurs risques à la fois (`PT-02`, `PT-03`) sont indiquées à chaque ligne qu'elles couvrent, comptées **une seule fois** au total budgétaire.

**Porteurs** — carte du pouvoir du pack §3 : le **Directeur de la filiale** décide budget et contrats ; le **Responsable Informatique** (DSI, trois personnes, sans titre de RSSI) décide réseau bureautique, postes et comptes de domaine, mais ni l'OT ni les contrats ; le **Responsable Exploitation** décide du réseau industriel des automates ; le **RSSI Groupe** décide de l'intégration au SOC ; la **Direction Générale du groupe** signe les acceptations, au niveau où l'appétence a été fixée (D1, D5 §1).

**Coût** — `build` = ce qui se paie une fois (CAPEX), `run` = ce qui se paie chaque année (OPEX), taux 500 €/jour, `annuel` = `(build_fixe + build_jp × 500) / amortissement + run_fixe + run_jp × 500`. Où le pack ne donne aucun chiffre, coût fixe posé à **0 €** et jours-personnes **estimés**, dit explicitement colonne par colonne.

### Décisions de direction — engagement de budget ou de contrat

| Décision et risque visé | Mesure | Porteur · Échéance | Coût (build · run · amortissement · annuel) | Effet sur la cotation |
|---|---|---|---|---|
| **Réduire** — OS1 : WMS chiffré via APPLICA (`Very likely × Critical` = `High`) | **`PT-01`** Validation préalable des mises à jour du WMS — recette formalisée et avenant au contrat TMA-WMS-2021 | Directeur de la filiale (avenant) · **14/12/2026** | Build 0 € + 5 jp · run 0 € + 3 jp/an · amort. 2 ans · **2 750 €/an** | Ferme le maillon « mise à jour déployée sans recette » — contribue à `Very likely → Likely` |
| **Réduire** — OS2 : automates via la liaison 4G de l'intégrateur (`Very likely × Critical` = `High`) | **`PT-06`** Inscrire des exigences de sécurité et une clause de réversibilité au contrat de l'intégrateur des automates | Directeur de la filiale (avenant) · **14/03/2027** | Build 0 € + 4 jp · run 0 € + 1 jp/an · amort. 2 ans · **1 500 €/an** | Le contrat de l'intégrateur ne porte aujourd'hui **aucune** exigence — contribue à `Very likely → Likely` |
| **Réduire** — OS3 : exfiltration par le concurrent, sous-traitance non déclarée d'APPLICA (`Likely × Important` = `Medium`) | **`PT-08`** Clause de maîtrise de la sous-traitance à l'avenant du contrat TMA-WMS-2021 | Directeur de la filiale (avenant) · **14/03/2027** | Build 0 € + 3 jp · run 0 € + 1 jp/an · amort. 2 ans · **1 250 €/an** | Ferme la voie du sous-traitant non déclaré — contribue à `Likely → Unlikely` |
| **Réduire** — ER5 : réapprovisionnement d'urgence Santé non assuré (`Certain × Critical` = `High`) | **`PT-11`** Projet de reprise sécurisée du flux (jalons M1 à M6 de **D6**, déjà engagé, propriétaire unique par jalon) | Propriétaires de jalon nommés en **D6** · **14/09/2027** (M6) | Build 20 000 € + 25 jp · run 1 000 € + 2 jp/an · amort. 3 ans · **12 833 €/an** | Le flux cesse d'être un état constaté — `Certain → Likely` |
| **Accepter, formellement** — ER3 : chaîne du froid rompue ou relevés faussés (`Likely × Critical` = `Medium`) | **`PT-10`** Tolérance datée : obtenir du fournisseur des sondes le journal des accès et sa réponse au questionnaire de sécurité, avant l'audit annuel du client | Responsable Qualité et chaîne du froid · signature **Direction Générale** · réexamen **avant l'audit client** | Build 0 € + 2 jp · run 0 € + 1 jp/an · amort. 1 an · **1 500 €/an** | Mesure **compensatoire** (surveillance) — le niveau **ne change pas**, `Medium` inchangé, conforme à la règle « pas de mesure structurelle ⇒ pas de baisse de niveau » |
| **Accepter** — ER6 : données de température et d'expédition du client divulguées (`Likely × Significant` = `Low`) | *Aucune mesure* — acceptable en l'état | **Direction Générale** · revue **trimestrielle du ComEx** | — | Inchangé, `Low` |

### Mesures d'exécution — DSI, Responsable Exploitation, RSSI Groupe

| Décision et risque visé | Mesure | Porteur · Échéance | Coût (build · run · amortissement · annuel) | Effet sur la cotation |
|---|---|---|---|---|
| **Réduire** — OS1 **et** OS3 *(mesure transversale)* | **`PT-02`** Comptes nommés et MFA pour les accès de la TMA, avec journalisation nominative | DSI de la filiale · **14/01/2027** | Build 8 000 € + 10 jp · run 3 000 € + 4 jp/an · amort. 3 ans · **9 333 €/an** | Ferme le compte de domaine partagé `svc-applica` — contribue à `Very likely → Likely` (OS1) et `Likely → Unlikely` (OS3) |
| **Réduire** — OS1 **et** OS2 *(mesure transversale)* | **`PT-03`** Segmentation des réseaux bureautique et industriel (IT/OT) des six entrepôts | DSI de la filiale · **14/06/2027** | Build 60 000 € + 30 jp · run 5 000 € + 6 jp/an · amort. 5 ans · **23 000 €/an** | Empêche la propagation latérale (constat C3, majeure `A.8.22`) — mesure la plus coûteuse, la plus transversale |
| **Réduire** — OS1 | **`PT-04`** Test de restauration du WMS et de sa base, avec mesure du RTO réel | DSI de la filiale · **14/11/2026** | Build 15 000 € + 8 jp · run 2 000 € + 3 jp/an · amort. 3 ans · **9 833 €/an** | Transforme la borne haute indéterminée de la fourchette du TD 1 du matin en chiffre mesuré ; sans effet direct sur l'axe vraisemblance/gravité mais condition de la crédibilité du RTO |
| **Réduire** — OS2 | **`PT-05`** Raccorder ou supprimer la liaison 4G de l'intégrateur des automates, et l'inventorier | Responsable Exploitation · **14/12/2026** | Build 3 000 € + 4 jp · run 500 € + 1 jp/an · amort. 3 ans · **2 667 €/an** | Ferme le vecteur d'entrée du maillon 3 d'OS2 |
| **Réduire** — OS2 | **`PT-07`** Raccorder au SOC les journaux du réseau industriel, des automates et du WMS | RSSI Groupe · **14/03/2027** | Build 12 000 € + 6 jp · run 4 000 € + 5 jp/an · amort. 4 ans · **10 250 €/an** | Passe la détection OT de « rien » à « quelque chose » — réduit la durée d'arrêt, donc la gravité effective |
| **Réduire** — ER2 : données de préparation altérées (`Very likely × Important` = `High`) | **`PT-09`** Rotation du secret du compte de service `LOG-SA-04` : un secret par site, en coffre *(reprend et replanifie `M3` de D4, F15)* | DSI de la filiale · **14/01/2027** | Build 5 000 € + 5 jp · run 500 € + 2 jp/an · amort. 3 ans · **4 000 €/an** | Ferme l'accès par secret partagé de tout initié — `Very likely → Likely` |
| **Réduire** — ER7 : perte du savoir-faire opérationnel des six entrepôts (`Very likely × Important` = `High`) | **`PT-12`** Formaliser par écrit l'organisation et les procédures de préparation des six entrepôts | Direction de la filiale (propriétaire de `LOG-SA-09` en D2) · **14/09/2027** | Build 0 € + 12 jp · run 0 € + 2 jp/an · amort. 3 ans · **3 000 €/an** | Le savoir écrit survit au départ — **gravité** `Important → Significant` (seul cas du registre où la mesure agit sur cet axe, pas sur la vraisemblance) |
| *(note d'écart, TP 1)* — les deux trous de cartographie découverts à l'atelier 4 | **`PT-13`** Inventorier et rattacher à un propriétaire les deux biens supports découverts (liaison 4G de l'intégrateur ; liaisons opérateur E1↔E2-E6) | DSI de la filiale · **14/10/2026** *(règle D2 §8 : rattachement sous 30 jours)* | Build 0 € + 1 jp · run 0 € · amort. 1 an · **500 €/an** | Sans effet direct sur une cotation — condition de traçabilité pour que `PT-05` et les mesures réseau aient un propriétaire d'actif |

**Le test de la ligne lisible** (énoncé) : chaque ligne ci-dessus se lit sans son auteur — risque visé, mesure, porteur, échéance, effet — pris isolément.

### Total du plan

| Poste | Montant |
|---|---|
| **Coût annuel total** (13 mesures, mutualisations comptées une fois) | **≈ 82 400 €/an** |
| dont **CAPEX amorti / an** (part `build` des annuités) | ≈ 51 000 €/an |
| dont **OPEX** (part `run`) | ≈ 31 400 €/an |
| **Investissement `build` cumulé** (payé une fois, réparti années 1-3) | ≈ 180 500 € |

*Calcul détaillé, colonne par colonne, ci-dessus. Confirmé dans l'outil : l'aperçu budgétaire de l'onglet **Plan d'action** de `translog-b` lit **82 K €/an**, 123 K € de build (115 jp), 16 K € de run annuel (31 jp), sur les **13 mesures** (`PT-13` rattachée à `AP.02` — voir bandeau en tête de fichier). Capture `S7-06-plan-d-action-apercu-budgetaire.jpg`.*

**Mis en face de la fourchette du coût de l'inaction** (TD 1 du matin, `../1-CISO-desk/Seance-7-TD-S7-01-chiffrer-le-cout-de-l-inaction.md`) : le plan complet coûte de l'ordre de **82 000 €/an**, contre une fourchette documentable allant de **12 000 € minimum** (une seule journée d'arrêt, pénalités pharmaceutiques seules — **déjà** le tiers du coût annuel du plan pour **un seul jour** de l'incident qu'il traite) à un **ordre de grandeur de plusieurs millions d'euros** (remédiation IBM 2025 : 4,44 M$ ; pénalité CNIL France Travail : 5 M€ si des données personnelles sont en jeu). C'est l'arbitrage promis au Directeur Financier : **un coût certain, annuel, borné, contre une perte plausible, non bornée, qui se réalise en un jour de plus que le plan n'en coûte en un an.**

---

## 2. Le registre, vue synthétique par ligne (renvoi)

*Détail des cotations actuelles, résiduelles et de la mécanique de chaque baisse : `Seance-7-TP-S7-05-feuille-de-travail-atelier4-et-registre.md`, §3 et §4. Reproduit ici pour la lecture autonome du fichier D7.*

| Ligne | Décision | Actuel | Résiduel | Mesures | Porteur(s) |
|---|---|---|---|---|---|
| OS1 (`AP.01`/SS1) | Mitigated | `Very likely × Critical` = **High** | `Likely × Critical` = **Medium** | PT-01, PT-02, PT-03, PT-04 | Directeur de la filiale · DSI |
| OS2 (`AP.02`/SS1) | Mitigated | `Very likely × Critical` = **High** | `Likely × Critical` = **Medium** | PT-05, PT-06, PT-03, PT-07 | Responsable Exploitation · Directeur de la filiale · RSSI Groupe |
| OS3 (`AP.01`/SS2) | Mitigated | `Likely × Important` = **Medium** | `Unlikely × Important` = **Low** | PT-02, PT-08 | DSI · Directeur de la filiale |
| ER2 | Mitigated | `Very likely × Important` = **High** | `Likely × Important` = **Medium** | PT-09 | DSI |
| ER3 | Accepted (formalisé) | `Likely × Critical` = **Medium** | `Likely × Critical` = **Medium** *(inchangé)* | PT-10 | Responsable Qualité · signature Direction Générale |
| ER5 | Mitigated | `Certain × Critical` = **High** | `Likely × Critical` = **Medium** | PT-11 | Propriétaires de jalon (D6) |
| ER6 | Accepted | `Likely × Significant` = **Low** | `Likely × Significant` = **Low** *(inchangé)* | *(aucune)* | Direction Générale |
| ER7 | Mitigated | `Very likely × Important` = **High** | `Very likely × Significant` = **Medium** | PT-12 | Direction de la filiale |

**Aucun résiduel ne reste `High`.** Six lignes ressortent `Medium` (OS1, OS2, ER2, ER3, ER5, ER7), une `Low` inchangée (ER6, aucune mesure), une `Low` par réduction (OS3).

---

## 3. Formalisation des acceptations — les six tolérances `Medium`, et l'acceptation `Low`

**Pourquoi sept fiches et non une** : D5 pose que `Medium` n'est tolérable **que formalisé** — tolérance datée, surveillée, propriétaire nommé, mesure compensatoire — à défaut traité comme `High`. Les **six lignes résiduelles `Medium`** en appellent chacune une, y compris les cinq qui portent par ailleurs une décision **Réduire** : la mesure abaisse le niveau, elle ne le fait pas disparaître, et ce qui reste à `Medium` doit être formalisé au même titre que ce qui y était déjà. `ER6`, seule ligne `Low`, reçoit une acceptation simple, plus légère (D5 : `Low` acceptable en l'état).

> **La phrase à ne jamais écrire** : *« Risque accepté par le RSSI. »* Aucune des sept fiches ci-dessous n'est signée par un RSSI — la Direction Générale du groupe signe, au niveau où l'appétence a été fixée (D1, D5 §1) ; le RSSI Groupe prépare et propose.

> **Dans l'outil** : les deux acceptations formelles au sens de l'objet dédié de `translog-b` (`Risk acceptances`, menu *Governance*) sont créées — ER3 (échéance 14/03/2027) et ER6 (échéance 14/12/2026), chacune rattachée à son scénario de risque. Les cinq autres résiduels `Medium` (OS1, OS2, ER2, ER5, ER7) restent des acceptations documentées ici, dans D7, et non comme objets `Risk acceptances` séparés — l'outil réserve cet objet à la tolérance formelle au sens strict de D5 ; les mesures `Réduire` en cours n'en sont pas une.

### Fiche d'acceptation — OS1 (résiduel `Medium`)

| Élément | Contenu |
|---|---|
| **Risque tel que coté** | Résiduel `Likely × Critical` = `Medium`, après application de PT-01 à PT-04 |
| **Raison de l'accepter à ce niveau** | Les quatre mesures ferment les maillons connus du chemin APPLICA (recette, comptes nommés, segmentation, restauration testée) ; aller plus loin (ex. authentification renforcée sur l'ensemble du parc TMA) excède l'appétence de budget de l'année 1 pour un gain marginal non démontré tant que le RTO réel n'est pas mesuré (`PT-04`) |
| **Instance qui accepte** | Direction Générale du groupe |
| **Date** | 14/09/2026 |
| **Réexamen** | Au premier test de restauration (`PT-04`), et à défaut sous 12 mois |

### Fiche d'acceptation — OS2 (résiduel `Medium`)

| Élément | Contenu |
|---|---|
| **Risque tel que coté** | Résiduel `Likely × Critical` = `Medium`, après PT-03, PT-05, PT-06, PT-07 |
| **Raison de l'accepter à ce niveau** | La liaison 4G est traitée à la racine (raccordée ou supprimée) et le contrat de l'intégrateur porte désormais des exigences ; le résiduel `Medium` reflète que l'intégrateur reste, par nature, un accès externe au réseau industriel — un risque plancher pour ce type de tiers |
| **Instance qui accepte** | Direction Générale du groupe |
| **Date** | 14/09/2026 |
| **Réexamen** | À la prochaine revue de la carte de dangerosité de l'écosystème (atelier 3), au plus tard 12 mois |

### Fiche d'acceptation — ER2 (résiduel `Medium`)

| Élément | Contenu |
|---|---|
| **Risque tel que coté** | Résiduel `Likely × Important` = `Medium`, après PT-09 |
| **Raison de l'accepter à ce niveau** | La rotation du secret ferme l'accès trivial d'un initié ; le résiduel reflète que l'Exploitation garde, par construction, un accès légitime au compte de service — un contrôle de journalisation supplémentaire (hors périmètre décidé aujourd'hui) serait la prochaine étape si le niveau ne baisse pas au réexamen |
| **Instance qui accepte** | Direction Générale du groupe |
| **Date** | 14/09/2026 |
| **Réexamen** | 12 mois après la mise en service de la rotation |

### Fiche d'acceptation — ER3 (résiduel `Medium`, inchangé)

| Élément | Contenu |
|---|---|
| **Risque tel que coté** | `Likely × Critical` = `Medium`, inchangé (aucune mesure structurelle — `PT-10` est une mesure compensatoire de surveillance) |
| **Raison de l'accepter à ce niveau** | Le logiciel des sondes est hébergé chez un fournisseur hors de notre maîtrise directe ; la tolérance formalisée (journal des accès, réponse au questionnaire de sécurité avant l'audit annuel du client) est le contrôle disponible à ce niveau contractuel — c'est un risque d'origine essentiellement accidentelle (D5), mieux couvert par la conformité du tiers que par un scénario d'attaque |
| **Instance qui accepte** | Direction Générale du groupe |
| **Propriétaire de la mesure compensatoire** | Responsable Qualité et chaîne du froid |
| **Date** | 14/09/2026 |
| **Réexamen** | Avant l'audit annuel du client pharmaceutique, au plus tard le **14/03/2027** |

### Fiche d'acceptation — ER5 (résiduel `Medium`)

| Élément | Contenu |
|---|---|
| **Risque tel que coté** | Résiduel `Likely × Critical` = `Medium`, après PT-11 (jalons M1-M6 de D6) |
| **Raison de l'accepter à ce niveau** | Le flux cesse d'être un état constaté (le seul risque du registre déjà réalisé, coté `Certain` en actuel) une fois la reprise sécurisée en place ; le résiduel `Medium` reflète que le flux reste, par nature, un point de défaillance unique vers un tiers critique (MERIDIAN Santé) tant qu'aucun secours n'existe |
| **Instance qui accepte** | Direction Générale du groupe |
| **Date** | 14/09/2026 |
| **Réexamen** | Au jalon M6 de D6 (fin de projet), au plus tard le **14/09/2027** |

### Fiche d'acceptation — ER7 (résiduel `Medium`, via la gravité)

| Élément | Contenu |
|---|---|
| **Risque tel que coté** | Résiduel `Very likely × Significant` = `Medium` — seule ligne du registre où la mesure abaisse la **gravité** et non la vraisemblance |
| **Raison de l'accepter à ce niveau** | Un départ du Responsable Exploitation reste tout aussi probable après la mesure (`PT-12` ne change rien à ce fait) ; ce qui change est que le savoir survit désormais au départ — le résiduel `Medium` reflète le temps de transition qu'un remplacement demanderait malgré la procédure écrite |
| **Instance qui accepte** | Direction Générale du groupe |
| **Propriétaire de la mesure** | Direction de la filiale |
| **Date** | 14/09/2026 |
| **Réexamen** | 12 mois après la formalisation des procédures |

### Fiche d'acceptation simple — ER6 (résiduel `Low`)

| Élément | Contenu |
|---|---|
| **Risque tel que coté** | `Likely × Significant` = `Low`, inchangé, aucune mesure appliquée |
| **Raison de l'accepter** | `Low` est acceptable en l'état selon D5 ; un traitement technique (DLP, filtrage) serait disproportionné au regard d'un impact `Significant`, alors que trois scénarios `High` mobilisent déjà les ressources de l'année 1 — arbitrage explicite, pas confort |
| **Instance qui accepte** | Direction Générale du groupe |
| **Date** | 14/09/2026 |
| **Réexamen** | Revue trimestrielle du ComEx (cadence D5) |

---

## 4. Dérogations — aucune à demander, et pourquoi

**Aucun résiduel ne reste au-dessus de la ligne d'acceptation** (`High`) après traitement : le plus haut niveau résiduel du registre est `Medium` (six lignes), les deux autres sont `Low`. L'exigence 2 de D7 (*tout résiduel qui dépasse l'appétence porte une dérogation motivée*) est donc satisfaite par le fait — **zéro dérogation à demander**, et la raison tient en une phrase : les six réductions engagées abaissent chacune d'au moins un cran (`High → Medium` ou `Medium → Low`), et les deux acceptations (`ER3`, `ER6`) portaient déjà, avant traitement, un niveau à l'intérieur ou à la limite de la ligne d'acceptation.

Si un résiduel devait, au prochain cycle, rester `High` malgré le traitement engagé — par exemple si le test de restauration (`PT-04`) révélait un RTO incompatible avec l'appétence — la dérogation porterait alors les trois éléments supplémentaires exigés : pourquoi le traitement complémentaire n'est pas engagé, ce qu'il faudrait pour l'engager, et à quelle condition la dérogation tomberait. Ce cas ne se présente pas aujourd'hui.

---

## 5. Auto-évaluation — la grille de l'énoncé

| Exigence | Atteinte quand | Vérifié |
|---|---|---|
| **Aucun risque sans décision** | Chaque ligne du registre porte une option ou l'explication écrite de son report | ✅ 8/8, aucune ligne laissée ouverte |
| **Dérogations justifiées** | Chaque résiduel au-dessus de l'appétence porte sa justification et son instance | ✅ par le fait — zéro résiduel au-dessus (§4) |
| **Cotations cohérentes** | Les niveaux cités sont ceux de D5, sans exception | ✅ vérifié à la matrice de l'instance |
| **Traçabilité des mesures** | Risque visé, mesure, porteur, échéance, effet attendu | ✅ §1 |
| **Effort et coût annuel** | Chaque mesure porte ses jours-personnes et son coût annuel lu dans l'outil, build et run distingués ; le plan porte son total en face du coût de l'inaction | ✅ lu dans l'outil (82 K €/an, 123 K € build/115 jp, 16 K € run/31 jp) — 13/13 mesures |
| **Résiduels cohérents** | Coté après décision, jamais supérieur à l'actuel | ✅ vérifié ligne par ligne (§2) ; l'outil lui-même **n'impose pas** cette contrainte (constaté au TP 1, note d'écart) — c'est une discipline appliquée ici, pas un garde-fou technique |
| **Légitimité des signatures** | Acceptations et dérogations au niveau où l'appétence a été fixée | ✅ Direction Générale du groupe pour les sept fiches (§3), jamais un directeur de filiale sur un risque de groupe |
| **Lisibilité** | Chaque ligne se comprend sans son auteur | ✅ testé (§1) |

---

## 6. Ce qui s'emporte vers la séance 8 — déclaration d'applicabilité

Chaque mesure du plan est formulée en **objectif vérifiable**, pas en intention générale, pour pouvoir être rapprochée d'une exigence d'ISO/IEC 27001:2022 (référentiel retenu en séance 3) :

| Mesure | Formulation vérifiable | Exigence ISO/IEC 27001:2022 rapprochée |
|---|---|---|
| `PT-01` | Recette formalisée + avenant avant toute mise à jour du WMS | `A.8.32` (gestion du changement), `A.8.8` (gestion des vulnérabilités techniques — l'écart de A.8.8 *est* l'absence de maîtrise de ces mises à jour) |
| `PT-02` | Suppression des comptes de domaine partagés au profit de comptes nominatifs tracés, MFA | `A.5.16`, `A.8.2`, `A.8.5`, `A.5.15` (contrôle d'accès, fermé de fait par les mêmes comptes nominatifs tracés) |
| `PT-03` | Cloisonnement réseau IT/OT sur les six sites | `A.8.22` |
| `PT-04` | Test de restauration périodique avec RTO mesuré | `A.8.13`, `A.5.30` |
| `PT-05` | Inventaire et supervision de la liaison 4G de l'intégrateur | `A.5.9`, `A.8.20` |
| `PT-06` | Exigences de sécurité et réversibilité au contrat de l'intégrateur | `A.5.19`, `A.5.20` |
| `PT-07` | Journaux OT et WMS centralisés au SOC | `A.8.15`, `A.8.16` |
| `PT-08` | Clause de maîtrise de la sous-traitance | `A.5.19`, `A.5.22` |
| `PT-09` | Rotation du secret de service, un par site, en coffre | `A.5.17`, `A.8.24` |
| `PT-10` | Journal des accès et questionnaire de sécurité du fournisseur des sondes | `A.5.22` |
| `PT-11` | Reprise sécurisée du flux d'urgence (jalons M1-M6 de D6) | `A.5.30`, `A.5.22` |
| `PT-12` | Procédures écrites de préparation des six entrepôts | `A.5.37` |
| `PT-13` | Inventaire et propriétaire des biens supports découverts | `A.5.9` |

Aucune mesure formulée « renforcer la sécurité des accès » ou équivalent générique : chacune se vérifie.

**Correction de séance 9 (`fixes.md` F22 §3)** : `A.5.15` et `A.8.8` manquaient à ce tableau alors que D8 §2.4
les rapprochait déjà de `PT-02` et `PT-01` — un rapprochement juste sur le fond (mêmes comptes nominatifs
tracés pour `A.5.15` ; même absence de maîtrise des mises à jour du WMS pour `A.8.8`) mais qui étendait D7
en silence. Les deux lignes ci-dessus sont désormais complètes ; les deux contrôles ne sont plus orphelins
« de D7, pas de la déclaration ».

---

*Livrable D7 — 5 points. Matière directe de la **sous-section 7** de la note de stratégie (`../../../Piece-1-Strategy-note/MERIDIAN-strategy-note.md`).*
