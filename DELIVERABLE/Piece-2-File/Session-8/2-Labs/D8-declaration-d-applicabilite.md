# D8 — PÉRIMÈTRE DU SMSI ET DÉCLARATION D'APPLICABILITÉ

**Groupe 4 (Translog)** · Miguel Monereo, Maxime Batista · filiale sous revue **MERIDIAN Logistique** · instance `translog-b`, domaine `MERIDIAN-LOGISTIQUE`, périmètre `MERIDIAN-LOGISTIQUE-FINAL`
**Date d'établissement** : 15 septembre 2026 · **cycle 1** · **référentiel** : ISO/IEC 27001:2022, retenu par le Comité Exécutif en séance 3 (D3)
**Source d'état** : évaluation *« MERIDIAN - ISO/IEC 27001:2022 - initial assessment »* (`0f757e40-a51a-4563-9eb2-3ccd18c31d02`), renseignée au TP 1 de la séance 8 · captures `../3-Evidence/S8-05-*`

> **Document destiné à un lecteur extérieur** — auditeur de certification, client, successeur. Il ne suppose aucune connaissance de MERIDIAN : chaque sigle est développé à son premier emploi, chaque renvoi nomme sa pièce, chaque affirmation porte sa preuve.
>
> **Sigles** : **SMSI** système de management de la sécurité de l'information (*ISMS*) · **SoA** déclaration d'applicabilité (*Statement of Applicability*) · **WMS** logiciel de gestion d'entrepôt (*warehouse management system*) · **TMA** tierce maintenance applicative · **IT/OT** réseau bureautique / réseau industriel · **SOC** centre de supervision de la sécurité (*security operations center*) · **DSI** direction des systèmes d'information de la filiale · **MFA** authentification multifacteur · **RTO** durée maximale d'interruption admissible.

---

## 1. Périmètre du SMSI

**Les activités et les services couverts.** Le SMSI couvre l'ensemble des activités de MERIDIAN Logistique, filiale logistique du groupe MERIDIAN, 2 800 salariés : la réception, la préparation et l'expédition des flux du groupe depuis six entrepôts notés E1 à E6, et le transport et l'entreposage sous température dirigée. Quatre valeurs métier sont couvertes, telles que la cartographie de la séance 2 (D2 §2) les a arrêtées : l'exécution des flux logistiques (`LOG-PA-01`), le maintien de la chaîne du froid (`LOG-PA-02`), le savoir-faire opérationnel des six entrepôts (`LOG-PA-03`) et la conformité contractuelle avec le client pharmaceutique (`LOG-PA-04`). Deux entrepôts, E1 et E4, sont dédiés à ce client, dont le contrat prévoit des pénalités de 12 000 € par jour d'arrêt et un audit annuel de la chaîne du froid.

**Les entités, les sites et les systèmes.** Le périmètre porte les treize biens supports inventoriés en D2 §3, aucun de plus, aucun de moins : les six entrepôts E1 à E6 et le local serveur d'E1 ; le WMS, deux serveurs et une base hébergés à E1, qui pilote la préparation, l'expédition et les stocks des six sites ; environ trois cents scannettes d'entrepôt raccordées au WMS en Wi-Fi ; les automates de tri d'E2, E3 et E4 ; le compte de service reliant le WMS aux automates ; le logiciel de relevé des sondes de température, hébergé chez son fournisseur ; les chambres froides et les remorques réfrigérées ; le réseau local dédié et son pare-feu d'inspection ; l'interface d'approvisionnement d'urgence vers la filiale MERIDIAN Santé ; et trois biens supports de nature organisationnelle — le Responsable Exploitation, le Responsable Qualité et chaîne du froid, et le contrat de tierce maintenance du WMS (APPLICA Services, `TMA-WMS-2021`). Le tableau §1.5 tranche, système par système, ce qui est dedans et ce qui est dehors.

**Les interfaces avec l'extérieur du périmètre.** Quatre franchissements de frontière sont déclarés, avec le mécanisme qui les maîtrise ou l'absence de ce mécanisme, tels que le pack de filiale §6 les décrit et que la cartographie les a repris. Vers **MERIDIAN Santé** : l'interface d'approvisionnement d'urgence, portée par un réseau local dédié et un pare-feu d'inspection — la seule segmentation réseau que le diagnostic initial ait trouvée dans le groupe, jugée conforme au titre du cloisonnement des réseaux sur ce flux précis (constat C7 de D4) ; le flux est suspendu depuis juin 2026 à la demande du responsable sécurité de MERIDIAN Santé, la livraison se faisant par bons papier dans l'intervalle. Vers le **SOC du groupe** : la filiale transmet les journaux de son réseau bureautique et rien d'autre — ni les automates, ni la liaison 4G de l'intégrateur, ni le WMS lui-même. Vers le **holding** : l'Audit Interne attend la liste nominative des porteurs du compte de la TMA du WMS, et le Directeur Financier du holding tient la paie et la comptabilité de la filiale sur une application en ligne partagée. Vers l'**extérieur** : six tiers accèdent au périmètre ou en reçoivent des données — la TMA du WMS, l'intégrateur des automates, le fournisseur des sondes de température et son logiciel hébergé, le fournisseur de télématique, l'opérateur des liaisons entre entrepôts, et le client pharmaceutique par son portail d'expédition.

**Les exclusions de périmètre, assumées et datées.** Le SMSI ne couvre pas, au cycle 1 : les trois autres filiales du groupe, qui relèvent chacune de leur propre système sous la gouvernance commune de D1 ; la paie et la comptabilité de la filiale, tenues par le Directeur Financier du holding sur une application que la filiale ne maîtrise pas ; la valeur métier « réapprovisionnement d'urgence », qui appartient à MERIDIAN Santé — nos biens supports qui l'alimentent restent, eux, dans le périmètre ; l'infrastructure d'hébergement du fournisseur des sondes de température, couverte par le contrat et non par nos contrôles, le logiciel lui-même restant un bien support du périmètre ; le SOC du groupe, service de groupe auquel la filiale s'interface ; et la flotte de véhicules et son logiciel de télématique, dont la preuve de température fournie au client pharmaceutique ne dépend pas — c'est le logiciel des sondes qui la produit. Chaque exclusion est datée du 15 septembre 2026 et réexaminée à la revue de direction du cycle 2.

### 1.5 Le test du tiers — ce qui est dedans, ce qui est dehors

*Un lecteur extérieur doit pouvoir dire, de tout système nommé au dossier, s'il est dans le périmètre ou hors de lui. Le tableau répond ; il ne compte pas au budget de pages.*

| Objet | Dans le périmètre ? | Fondement |
|---|---|---|
| Entrepôts E1 à E6, local serveur E1 | **Oui** | `LOG-SA-06`, `LOG-SA-07` (D2 §3) |
| WMS — deux serveurs et base, site E1 | **Oui** | `LOG-SA-01` |
| Scannettes d'entrepôt (~300, Wi-Fi) | **Oui** | `LOG-SA-02` |
| Automates de tri d'E2, E3 et E4 | **Oui** | `LOG-SA-03` — dans le SMSI, **hors du périmètre de certification visé** (§1.6) |
| Compte de service WMS ↔ automates | **Oui** | `LOG-SA-04` |
| Logiciel des sondes de température | **Oui** pour le logiciel et ses accès | `LOG-SA-05` — **hors périmètre** pour l'infrastructure d'hébergement du fournisseur |
| Chambres froides et remorques réfrigérées | **Oui** | `LOG-SA-08` |
| Réseau local dédié et pare-feu d'inspection | **Oui** | `LOG-SA-12` |
| Interface d'approvisionnement d'urgence | **Oui** | `LOG-SA-13` — l'interface, pas la valeur métier de Santé qu'elle alimente |
| Contrat de TMA du WMS (APPLICA, `TMA-WMS-2021`) | **Oui** | `LOG-SA-10` — le contrat et les accès qu'il ouvre ; l'organisation interne d'APPLICA est hors périmètre |
| Liaison 4G de l'intégrateur des automates | **Oui**, depuis septembre 2026 | Bien support découvert à l'atelier 4 (séance 7), inventaire dû au **14/10/2026** (`PT-13`) |
| Liaisons opérateur entre E1 et E2–E6 | **Oui**, depuis septembre 2026 | Même origine, même échéance |
| Paie et comptabilité de la filiale | **Non** | Application en ligne tenue par le Directeur Financier du holding |
| Système de gestion pharmaceutique de MERIDIAN Santé | **Non** | Périmètre de la filiale Santé |
| SOC du groupe | **Non** | Service de groupe ; interface déclarée |
| Flotte de véhicules et logiciel de télématique | **Non**, au cycle 1 | La preuve de température du client vient du logiciel des sondes |
| Filiales Santé, Éducation, Territoires | **Non** | Systèmes distincts sous gouvernance commune (D1) |

### 1.6 Le périmètre de certification visé, distinct du périmètre du SMSI

Le SMSI couvre la filiale entière ; le **périmètre de certification** proposé au Comité Exécutif est plus étroit et le reste tant qu'un chantier daté n'est pas achevé : les services que reçoit le client pharmaceutique — la chaîne du froid et le flux WMS des entrepôts E1 et E4 (`LOG-PA-02` et `LOG-PA-04`) — **à l'exclusion explicite de l'automatisation d'E4**. Le motif est écrit plutôt que laissé à découvrir : E4 est à la fois dédié au client pharmaceutique et équipé d'automates de tri depuis 2025, sur un réseau bureautique et industriel interconnecté sans cloisonnement (constat C3 de D4, non-conformité majeure). Aucun périmètre incluant l'industriel n'est honnêtement déclarable avant la segmentation IT/OT, mesure `PT-03` du plan de traitement de la séance 7, échéance **14/06/2027**. L'exclusion tombe à cette date, sur preuve de recette de la segmentation, et pas avant.

---

## 2. Déclaration d'applicabilité

### 2.1 Taux de couverture, affiché en tête

| Mesure | Valeur | Lecture |
|---|---|---|
| **Contrôles d'annexe A investigués** | **15 sur 93** — **16,1 %** | 78 contrôles restent **non investigués** ; ils sont listés comme tels et ne sont **comptés conformes nulle part** |
| Exigences traitées, clauses et annexe A | 45 sur 123 — 36,6 % | Progression *Done* lue dans l'outil |
| Clauses 4 à 10 | **30 sur 30 — 100 %** | Aucune clause laissée non évaluée, aucune déclarée non applicable |
| Résultats sur les 15 contrôles investigués | 0 conforme · 3 partiellement conformes · 11 non conformes · 1 non applicable | Aucun contrôle pleinement en place au cycle 1 |
| Résultats sur les 30 clauses | 2 conformes · 20 partiellement conformes · 8 non conformes | Les deux conformes sont l'appréciation (6.1.2) et le traitement (6.1.3) des risques |

*Comptes lus dans l'instance, non recopiés à la main : 1,63 % conforme, 15,45 % non conforme, 18,70 % partiellement conforme, 0,81 % non applicable, 63,41 % non évalué sur les 123 exigences. Capture `../3-Evidence/S8-05-etat-final-donuts-compliance-et-progression.jpg`.*

### 2.2 Les quinze contrôles investigués

*Chaque contrôle retenu est tracé soit à un risque du registre de la séance 7 (D7 §2), soit à une exigence légale ou contractuelle nommée. La ligne de traçabilité de chaque contrôle est son observation dans l'instance ; le tableau la cite, il ne la réécrit pas.*

| Contrôle | Intitulé | Applicable | Justification du maintien — risque du registre ou exigence nommée | État constaté | Contrôle en place ou mesure du plan |
|---|---|---|---|---|---|
| **A.5.9** | Inventaire des informations et des autres actifs associés | Oui | Exigence de connaître le système d'information, portée par la règle de tenue de D2 §8 ; scénario **OS2** (entrée par la liaison 4G de l'intégrateur, bien support absent de l'inventaire) | **Partiellement conforme** | Cartographie D2 : 17 actifs à propriétaire nommé dans l'instance ; deux biens supports découverts en séance 7 — `PT-13`, **14/10/2026** |
| **A.5.15** | Contrôle d'accès | Oui | Constat **C4** de D4 (non-conformité majeure) ; scénarios **OS1**, **OS3** ; directive `ACC-01` de D1 | **Non conforme** | `PT-02` — comptes nommés et MFA pour les accès de la TMA, **14/01/2027** |
| **A.5.16** | Gestion des identités | Oui | Constat **C4** ; demande de l'Audit Interne du holding, restée sans réponse nominative ; scénarios **OS1**, **OS3** | **Non conforme** | `PT-02`, **14/01/2027** |
| **A.5.17** | Informations d'authentification | Oui | Secret du compte de service `LOG-SA-04` identique sur les six entrepôts depuis 2019, en clair dans un fichier de configuration ; scénario **ER2** | **Non conforme** | `PT-09` — un secret par site, en coffre, **14/01/2027** |
| **A.5.19** | Sécurité de l'information dans les relations avec les fournisseurs | Oui | Constat **C4** ; contrat de l'intégrateur sans aucune exigence de sécurité ; scénarios **OS1**, **OS2**, **OS3** ; règle des trois exigences contractuelles de D6 | **Non conforme** | `PT-02`, `PT-06` (**14/03/2027**), `PT-08` (**14/03/2027**) |
| **A.5.22** | Surveillance, revue et gestion des changements des services fournisseurs | Oui | Mises à jour du WMS déployées de nuit par la TMA sans recette ni information préalable ; scénarios **OS1**, **ER3** ; contrat `TMA-WMS-2021` | **Non conforme** | `PT-01` (**14/12/2026**), `PT-08`, `PT-10` (journal des accès du fournisseur des sondes) |
| **A.5.24** | Planification et préparation de la gestion des incidents | Oui | Aucune procédure d'incident dans la filiale ; l'arrêt du WMS d'avril 2026 l'a démontré, sans chronologie tenue ; directive `INC-01` de D1 | **Non conforme** | **Aucune mesure du plan de traitement ne le porte** — orphelin identifié en §2.4, chantier de la séance 9 |
| **A.6.3** | Sensibilisation, apprentissage et formation à la sécurité | Oui | Angle mort assumé de D4, tranché ici faute de toute preuve de sensibilisation depuis ; scénario **ER2** (initié) | **Non conforme** | **Aucune mesure du plan** — orphelin identifié en §2.4 |
| **A.7.4** | Surveillance de la sécurité physique | Oui | Local serveur d'E1 situé au fond de l'atelier de maintenance ; scénario **OS1** (disponibilité du WMS) | **Partiellement conforme** | Aucune surveillance physique nommée ; investigation site par site à programmer — **aucune mesure du plan** |
| **A.8.2** | Droits d'accès privilégiés | Oui | Constat **C4** ; compte de domaine partagé avec la TMA, nombre de porteurs inconnu ; scénarios **OS1**, **OS3** | **Non conforme** | `PT-02`, **14/01/2027** |
| **A.8.5** | Authentification sécurisée | Oui | Directive `ACC-01` de D1 ; secret partagé en clair ; scénarios **OS1**, **ER2** | **Non conforme** | `PT-02`, `PT-09` |
| **A.8.8** | Gestion des vulnérabilités techniques | Oui | Directive `COR-01` de D1, non mesurée ; mises à jour du WMS non maîtrisées ; scénario **OS1** | **Non conforme** | `PT-01`, **14/12/2026** |
| **A.8.15** | Journalisation | Oui | Le SOC du groupe ne reçoit que le réseau bureautique — ni automates, ni liaison 4G, ni WMS ; scénario **OS2** ; directive `JRN-01` de D1 | **Partiellement conforme** | `PT-07` — raccordement des journaux OT et WMS au SOC, **14/03/2027** |
| **A.8.22** | Cloisonnement des réseaux | Oui | Constat **C3** de D4 (non-conformité majeure, réseaux bureautique et industriel interconnectés sur les six sites) ; scénarios **OS1**, **OS2** | **Non conforme** | `PT-03` — segmentation IT/OT des six entrepôts, **14/06/2027**. Point conforme sur le seul flux Logistique↔Santé (constat **C7**), aujourd'hui suspendu |
| **A.8.28** | Codage sécurisé | **Non** | **Exclusion unique** — absence d'objet démontrée, §3 | *Sans objet* | *Sans objet* |

**Les 78 contrôles non investigués.** Ils ne sont ni applicables ni exclus à ce jour : ils sont **non évalués**, et le tableau ci-dessus ne les couvre pas. Les déclarer conformes serait la faute que la déclaration d'applicabilité sert précisément à empêcher. Leur investigation est un chantier ouvert ; §2.4 désigne les huit par lesquels commencer.

### 2.3 Profil des clauses 4 à 10

| Clause | Résultat dominant | Ce qui le porte |
|---|---|---|
| **4** Contexte de l'organisme | Partiellement conforme (4/4) | Contexte, parties intéressées et périmètre écrits en D1 et dans le présent document |
| **5** Leadership | Partiellement conforme (3/3) | Gouvernance à trois niveaux, matrice de responsabilité et charte adoptées en D1 ; l'engagement de direction n'est pas encore tracé par des revues |
| **6** Planification | **2 conformes**, 3 partiellement | L'appréciation (6.1.2) et le traitement des risques (6.1.3) sont la pièce la plus complète du dossier : D5, D7, registre à 8 lignes, zéro résiduel au-dessus de `Medium` |
| **7** Support | **4 non conformes** sur 6 | Compétence (7.2), sensibilisation (7.3), information documentée générale (7.5.1) et sa maîtrise (7.5.3) : aucune politique documentaire, aucun programme de sensibilisation |
| **8** Fonctionnement | Partiellement conforme (3/3) | Les processus existent et produisent des sorties datées, sans planification ni maîtrise formalisées |
| **9** Évaluation des performances | **4 non conformes** sur 6 | Aucun indicateur mesuré (9.1), aucune revue de direction institutionnalisée (9.3.1 à 9.3.3) |
| **10** Amélioration | Partiellement conforme (2/2) | Les actions correctives de D4 existent et sont suivies dans l'instance, sans processus écrit |

**Ce que ce profil dit.** Les clauses qui tiennent sont celles que les huit dernières semaines ont construites — contexte, planification, appréciation et traitement du risque. Les deux qui restent nues sont le **support** (clause 7) et l'**évaluation des performances** (clause 9), c'est-à-dire exactement ce qu'un système de management ajoute à une analyse de risque : un corpus documentaire maîtrisé et une mesure. Ce n'est pas une surprise, c'est l'ordre dans lequel le travail a été mené.

### 2.4 Contrôle de cohérence croisée, dans les deux sens

*Vérification conduite dans l'instance, plan d'action et registre en vis-à-vis. L'outil montre les liens ; il ne fait pas le contrôle.*

**Sens 1 — chaque risque traité par une réduction conduit-il à au moins un contrôle retenu ?** Les six lignes du registre décidées `Mitigated` sont couvertes : OS1 par A.5.15, A.5.16, A.5.19, A.8.2, A.8.5, A.8.8 et A.8.22 ; OS2 par A.8.22, A.8.15, A.5.19 et A.5.9 ; OS3 par A.5.19, A.5.22, A.8.2 et A.5.15 ; ER2 par A.5.17 et A.8.5 ; ER5 par A.5.22 ; ER7 par **aucun contrôle investigué** — son unique ancrage, A.5.37 (procédures d'exploitation documentées), fait partie des 78. Le risque accepté ER3 est couvert par A.5.22 ; ER6, accepté sans mesure, n'en appelle aucun.

**Sens 2 — chaque non-conformité majeure de l'audit initial conduit-elle à un contrôle retenu, non conforme ou partiel ?** C3 conduit à A.8.22, non conforme ; C4 conduit à A.5.15, A.5.16, A.5.19 et A.8.2, toutes non conformes. C7 est un point conforme, pas un écart. Aucune non-conformité majeure sans contrôle porteur.

**Orphelins relevés, et ce qui en est fait.**

| Orphelin | Nature | Traitement décidé |
|---|---|---|
| **A.5.24**, **A.6.3**, **A.7.4** | Contrôles retenus, non conformes ou partiels, **qu'aucune mesure du plan de traitement de la séance 7 ne porte** | Le plan de traitement traite les risques du registre, pas les écarts de conformité : trois écarts restent donc sans mesure. A.5.24 (gestion des incidents) et A.6.3 (sensibilisation) entrent au chantier documentaire de la séance 9 ; A.7.4 appelle d'abord une investigation site par site, avant toute mesure |
| **A.5.20**, **A.5.30**, **A.5.37**, **A.8.13**, **A.8.16**, **A.8.20**, **A.8.24**, **A.8.32** | Huit contrôles rapprochés d'une mesure du plan (D7 §6) mais **non encore investigués** : le plan les traite, la déclaration ne les couvre pas | Ce sont les huit premiers à investiguer lors de l'extension de la déclaration aux 78 restants. A.5.37 est prioritaire : il est le seul ancrage du traitement d'ER7 |

---

## 3. Registre des exclusions

Une seule exclusion est déclarée au cycle 1. Les exclusions de **périmètre** de la section 1 sont d'une autre nature : elles disent ce que le système ne couvre pas, non ce qui, dans le périmètre couvert, serait sans objet.

### A.8.28 — Codage sécurisé · **non applicable**

| Élément | Contenu |
|---|---|
| **Fait qui fonde l'exclusion** | MERIDIAN Logistique n'exerce **aucune activité de développement logiciel**, ni interne ni sous-traitée en son nom. Le WMS est un progiciel, exploité et mis à jour par la tierce maintenance applicative APPLICA Services au titre du contrat `TMA-WMS-2021` ; le logiciel des sondes de température est un service hébergé chez son fournisseur ; les paramètres des automates de tri sont la propriété industrielle de l'intégrateur. Aucun développeur n'est nommé ni dans l'inventaire de la filiale (D2 §3), ni dans la carte du pouvoir du pack de filiale (§3), qui recense sept fonctions décisionnaires et trois personnes à la DSI. |
| **Nature de la justification** | **Absence d'objet vérifiable** — le contrôle n'a pas de matière à s'appliquer. Ni un coût, ni une préférence, ni un report : le codage sécurisé n'est pas jugé trop cher, il n'a rien à régir ici. |
| **Qui a confirmé le fait, et quand** | Le responsable informatique de la filiale (DSI, trois personnes, sans titre de RSSI), le **15 septembre 2026**, sur la base de la cartographie de la séance 2 et du pack de filiale. |
| **Ce qui ferait tomber l'exclusion** | L'engagement de tout projet de développement interne ou de toute commande de développement spécifique — déclencheur porté par le processus projet à six jalons de D6, qui soumet déjà à la même grille tout projet impliquant un tiers. À défaut de déclencheur, réexamen à la prochaine revue de direction du SMSI. |
| **Effet sur les contrôles voisins** | Aucun report : la maîtrise des mises à jour du WMS, qui aurait pu servir de prétexte à exclure davantage, reste **retenue et non conforme** sous A.5.22 et A.8.8, avec la mesure `PT-01` et son échéance. |

**Les exclusions que nous n'avons pas prononcées.** La discipline se mesure aussi à ce qui n'a pas été exclu. A.7.4 (surveillance de la sécurité physique) aurait pu recevoir un « ce n'est pas notre périmètre » : il reste retenu, partiellement conforme, avec une investigation à mener. A.6.3 (sensibilisation) aurait pu être reporté au groupe : il reste retenu et non conforme. Dans le doute entre *non conforme* et *non applicable*, c'est *non conforme* qui l'emporte, sauf absence d'objet démontrée.

---

## 4. Synthèse pour la direction

1. Le SMSI de MERIDIAN Logistique dispose désormais d'un **périmètre écrit et daté** : les six entrepôts, les quatre valeurs métier et les treize biens supports de la cartographie, avec six exclusions de périmètre nommées et quatre interfaces déclarées.
2. La **déclaration d'applicabilité porte sur 15 contrôles d'annexe A sur 93, soit 16,1 %** ; les 78 autres sont non évalués et ne sont comptés conformes nulle part.
3. Sur ces quinze, **aucun n'est pleinement en place** : onze sont non conformes, trois partiels, un exclu. C'est un point de départ mesuré, pas un résultat.
4. Les **clauses 4 à 10 sont, elles, évaluées en totalité** : 2 conformes, 20 partiellement conformes, 8 non conformes.
5. Les deux clauses les plus faibles sont le **support (clause 7)** et l'**évaluation des performances (clause 9)** — pas de corpus documentaire maîtrisé, pas d'indicateur mesuré, pas de revue de direction.
6. Les deux clauses conformes sont l'**appréciation et le traitement des risques**, adossées au registre de la séance 7 : 8 scénarios, 13 mesures, ≈ 82 000 €/an, aucun risque résiduel au-dessus de `Moyen`.
7. **Une seule exclusion** est prononcée, A.8.28, fondée sur une absence d'objet confirmée par la DSI le 15 septembre 2026 : la filiale ne développe aucun logiciel.
8. Le contrôle de cohérence croisée relève **trois écarts sans mesure** (gestion des incidents, sensibilisation, surveillance physique) et **huit contrôles à investiguer en priorité**, dont A.5.37, seul ancrage du traitement de la perte du savoir-faire opérationnel.
9. **Deux chantiers sont désignés** : le corpus documentaire et la mesure — politique, procédures et indicateurs, objet de la prochaine séance de travail.
10. **Décision demandée au Comité Exécutif** : valider ce périmètre du SMSI et le périmètre de certification visé — chaîne du froid et flux WMS des entrepôts E1 et E4, **hors automatisation d'E4 jusqu'au 14/06/2027**, échéance de la segmentation IT/OT — et ouvrir les deux chantiers désignés. Aucune date de certificat n'est proposée ; le seul montant engagé reste celui du plan de traitement déjà arrêté.

---

## 5. Écarts restants, dits avant qu'un tiers ne les trouve

| Écart | Portée | Ce qui le lèvera |
|---|---|---|
| **84 % de l'annexe A non investiguée** | La déclaration est partielle et se présente comme telle | Extension aux 78 contrôles, en commençant par les huit de §2.4 |
| **Aucun contrôle pleinement en place** sur les quinze investigués | Une certification ne serait pas envisageable aujourd'hui sur ce constat | Les mesures `PT-01` à `PT-13`, échéances du 14/10/2026 au 14/09/2027 |
| **Aucun schéma réseau de la filiale n'existe** (lacune 1 de D2) | C'est elle qui borne ce qui est honnêtement déclarable sur l'industriel | `PT-13` (inventaire, 14/10/2026), puis `PT-03` (segmentation, 14/06/2027) |
| **Trois écarts sans mesure** — A.5.24, A.6.3, A.7.4 | Un auditeur les trouverait ; ils sont écrits ici | Chantier documentaire de la séance 9 pour les deux premiers ; investigation physique pour le troisième |
| **L'évaluation est une auto-évaluation** | Elle n'a pas l'indépendance qu'exige la définition normative de l'audit (D4 §1) | Une vérification indépendante, à programmer avant tout engagement de certification |

---

*Livrable D8. Matière directe de la **sous-section 8** de la note de stratégie (`../../../Piece-1-Strategy-note/MERIDIAN-strategy-note.md`). Pièces à l'appui : feuille de travail du TP 1 `Seance-8-TP-S8-05-feuille-de-travail-evaluation-et-SoA.md`, captures `../3-Evidence/S8-05-*`, note collective du TD 1 `../1-CISO-desk/Seance-8-TD-S8-01-le-business-case-de-la-certification.md`.*
