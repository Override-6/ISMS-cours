# D2 — CARTOGRAPHIE DE MERIDIAN LOGISTIQUE

**Groupe 4 (Translog)** · instance `translog-b` · périmètre `MERIDIAN-LOGISTIQUE` · **Séance 2**
**Vocabulaire** : EBIOS Risk Manager (ANSSI, v1.5, sept. 2024). Besoins de sécurité notés **DICT** — Disponibilité, Intégrité, Confidentialité, Traçabilité.

---

## 1. Périmètre cartographié

Filiale logistique du groupe MERIDIAN — **six entrepôts E1 à E6**, dont deux dédiés à un client pharmaceutique sous exigence de chaîne du froid — assurant la réception, la préparation et l'expédition des flux du groupe. 2 800 salariés. E1 porte la salle serveurs du logiciel de gestion d'entrepôt (WMS) ; E2, E3 et E4 sont équipés d'automates de tri ; E5 et E6 sont manuels.

---

## 2. Valeurs métier

*Quatre valeurs métier, décrites par la **perte** et non par le fonctionnement. Le test appliqué : « la filiale pleurerait-elle sa disparition, ou seulement la DSI ? »*

| Réf. | Valeur métier | Ce qui est perdu si elle est atteinte |
|---|---|---|
| `LOG-PA-01` | **Exécution des flux logistiques** | L'entrepôt ne réceptionne, ne prépare ni n'expédie plus rien. Un arrêt de plus de six heures bloque **40 % du volume expédié de tout le groupe**. |
| `LOG-PA-02` | **Maintien de la chaîne du froid** | Le client pharmaceutique perd la garantie de température dirigée exigée par ses audits annuels — un manquement contractuel direct, pas seulement une panne. |
| `LOG-PA-03` | **Savoir-faire opérationnel des six entrepôts** | La connaissance fine de l'organisation de chaque site disparaît d'un coup, sans aucune trace écrite pour la remplacer. |
| `LOG-PA-04` | **Conformité contractuelle avec le client pharmaceutique** | La filiale échoue à son prochain audit ou questionnaire de sécurité — pénalités contractuelles de **12 000 €/jour d'arrêt**. |

*Le WMS, les scannettes et les automates ne figurent volontairement pas ici : ce sont des biens supports, pas des valeurs métier.*

---

## 3. Biens supports

*Treize biens supports, **les trois natures couvertes**, chacun rattaché à la valeur métier qu'il porte, chacun avec un propriétaire. Aucun actif sans propriétaire.*

| Réf. | Bien support | Nature | Porte | Propriétaire |
|---|---|---|---|---|
| `LOG-SA-01` | WMS — 2 serveurs + base, site E1 | Numérique | `PA-01` | DSI filiale (3 pers.) |
| `LOG-SA-02` | Scannettes d'entrepôt (~300, Wi-Fi) | Numérique | `PA-01` *(+ flux Santé)* | DSI filiale |
| `LOG-SA-03` | Automates de tri (E2/E3/E4) | Numérique | `PA-01` | Intégrateur des automates |
| `LOG-SA-04` | Compte de service WMS ↔ automates | Numérique | `PA-01` | DSI filiale *(à réaffecter)* |
| `LOG-SA-05` | Logiciel des sondes de température | Numérique *(hébergé fournisseur)* | `PA-02`, `PA-04` | Responsable Qualité |
| `LOG-SA-06` | Local serveur E1 | Physique | `PA-01` | DSI filiale |
| `LOG-SA-07` | Entrepôts E1–E6 | Physique | `PA-01` | 6 chefs d'entrepôt |
| `LOG-SA-08` | Chambres froides et remorques réfrigérées | Physique | `PA-02` | Responsable Qualité |
| `LOG-SA-09` | **Responsable Exploitation** | **Organisationnel** | `PA-03` | Direction de la filiale |
| `LOG-SA-10` | Prestataire de tierce maintenance du WMS | Organisationnel | `PA-01` | DSI filiale (contrat) |
| `LOG-SA-11` | Responsable Qualité (répond aux audits) | Organisationnel | `PA-04` | Direction de la filiale |
| `LOG-SA-12` | VLAN dédié + pare-feu d'inspection | Numérique | `PA-01` | DSI filiale |
| `LOG-SA-13` | Interface d'approvisionnement d'urgence | Numérique | `PA-01` *(+ flux Santé)* | DSI filiale |

---

## 4. Besoins de sécurité (DICT)

*Échelle relative à trois niveaux — négligeable / notable / très important. Aucun niveau intermédiaire inventé.*

| Valeur métier | D | I | C | T | Justification de la note dominante |
|---|---|---|---|---|---|
| `PA-01` Exécution des flux | **TI** | **TI** | Notable | Notable ⚠️ | Un arrêt > 6 h bloque 40 % du volume expédié du groupe |
| `PA-02` Chaîne du froid | **TI** | **TI** | Notable | **TI** | Rupture = manquement contractuel direct et risque sanitaire pour le client |
| `PA-03` Savoir-faire | Notable | Notable | Notable | **TI** | *Par absence* : la traçabilité de cet actif est aujourd'hui nulle |
| `PA-04` Conformité contractuelle | Notable | **TI** | Notable | **TI** | C'est l'intégrité des preuves fournies à l'audit qui est vérifiée |

⚠️ **Arbitrage demandé** : la traçabilité de `PA-01` est notée *notable* et mériterait **très important**. Le SOC du groupe ne reçoit aujourd'hui **aucun journal** des automates, de la liaison 4G de l'intégrateur ni du WMS lui-même ; l'arrêt d'avril l'a démontré, personne n'a pu tenir de chronologie. La révision est proposée au Directeur Logistique, elle n'est pas décidée ici.

---

## 5. Dépendances inter-filiales

La valeur métier **« réapprovisionnement d'urgence »** appartient à **MERIDIAN Santé**, mais la plupart de ses biens supports vivent chez nous : scannettes (`SA-02`), interface d'approvisionnement d'urgence (`SA-13`), VLAN dédié et pare-feu d'inspection (`SA-12`), équipes d'exploitation des entrepôts. **Le flux est bloqué depuis trois mois** à la demande de Santé.

> **Limite structurelle assumée** : une instance de l'outil correspond à une filiale. L'actif primaire « réapprovisionnement d'urgence » n'existe que côté Santé (`medsecure`) ; notre instance ne peut pas le porter, seulement documenter dans la description de nos propres biens supports qu'ils l'alimentent. Une cartographie de groupe supposerait un objet de niveau supérieur aux instances.

**Ce que ce cas démontre** : une cartographie par filiale montrerait, côté Santé, une valeur métier sans ses biens supports, et côté Logistique, des biens supports sans la valeur qu'ils portent. Seule une carte de **groupe** rend la dépendance visible.

---

## 6. Top 5 des actifs critiques — justifié

**Critère de classement, posé avant le classement.** Un actif est d'autant plus critique que : **(a)** il porte une valeur métier dont un besoin DICT est *très important* ; **(b)** son atteinte déborde la filiale et touche le groupe ou un client ; **(c)** une faiblesse **connue et actuelle** rend cette atteinte plausible aujourd'hui, pas en théorie ; **(d)** il n'existe **aucune substitution** rapide.

*Le classement porte sur les **biens supports** : les quatre valeurs métier sont critiques par construction — un « top 5 » de quatre éléments ne classerait rien. Ce sont les supports qui se protègent, se remplacent et se budgètent.*

| Rang | Actif | Valeur portée | Pourquoi ce rang |
|---|---|---|---|
| **1** | `LOG-SA-01` **WMS** (2 serveurs + base, E1) | `PA-01` (D et I très importants) | Les quatre critères sont réunis. Un arrêt > 6 h bloque **40 % du volume expédié du groupe** (b) ; la reprise n'est **pas démontrée** — les sauvegardes quotidiennes n'ont **jamais** été restaurées depuis la mise en service (c) ; le système est centralisé sur un site unique, sans secours (d). |
| **2** | `LOG-SA-04` **Compte de service WMS ↔ automates** | `PA-01` (D et I très importants) | **Même mot de passe sur les six entrepôts depuis 2019**, en clair dans un fichier de configuration, connu de « tout le monde » sur site (c). Il ouvre l'intégrité des flux **et**, les réseaux bureautique et industriel n'étant pas cloisonnés, le chemin vers les automates (b). Aucune substitution : il est câblé dans l'exploitation (d). |
| **3** | `LOG-SA-09` **Responsable Exploitation** | `PA-03` (traçabilité très importante *par absence*) | **Seul bien support d'une valeur métier entière**, sans aucun support numérique ni physique (d). Le savoir n'est écrit nulle part (c) — l'arrêt d'avril l'a prouvé, personne n'a pu tenir de chronologie. Le seul actif de cette liste qu'aucun budget ne remplace. |
| **4** | `LOG-SA-05` **Logiciel des sondes de température** | `PA-02` **et** `PA-04` (D, I, T très importants) | Le seul actif qui porte **deux** valeurs métier : la chaîne du froid et la preuve qui sera produite à l'audit annuel (a). Son atteinte se paie contractuellement, **12 000 €/jour** (b). Hébergé chez le fournisseur, donc hors de notre maîtrise directe (d). |
| **5** | `LOG-SA-03` **Automates de tri** (E2/E3/E4) | `PA-01` (D et I très importants) | Réseaux industriel et bureautique **interconnectés sans cloisonnement**, intégrateur raccordé par une liaison 4G **hors du réseau supervisé**, **aucun journal** transmis au SOC du groupe (c). C'est l'écart de priorité 1 de l'analyse d'écart du groupe, et le chantier inscrit à 24 mois de la trajectoire. |

**Ce que ce classement écarte, et pourquoi.** Le **local serveur E1** (climatisation défaillante) et les **entrepôts E1–E6** portent la même valeur que le WMS mais leur atteinte est plus lente et plus visible : on la voit venir. Les **scannettes** (~300) sont nombreuses donc redondantes — la perte de quelques-unes ne stoppe rien. Le **prestataire de tierce maintenance** est un risque de gouvernance majeur (compte de domaine partagé, nombre de porteurs inconnu) mais il se traite par le contrat, et son vecteur technique est déjà classé au rang 2.

---

## 7. Lacunes assumées

1. **Aucun schéma réseau de la filiale n'existe.** C'est la lacune la plus embarrassante : elle empêche de déclarer honnêtement un périmètre incluant l'industriel.
2. **Les plages d'adresses IP ne sont pas connues** — réseaux IT et OT interconnectés, liaison 4G de l'intégrateur hors supervision, ~300 scannettes en Wi-Fi, logiciels hébergés chez deux fournisseurs distincts.
3. **Le nombre de porteurs du compte de domaine partagé avec la tierce maintenance est inconnu**, et le contrat ne prévoit pas de journalisation nominative.
4. **Aucune procédure d'incident n'existe** dans la filiale — donc aucun point de contact unique nommé.
5. **Les objectifs de reprise (RTO/RPO) ne sont pas contractualisés** : le RPO de 24 h est un état de fait issu des sauvegardes quotidiennes, non un engagement, et il n'est pas démontré.
6. **La dépendance inter-filiales n'est pas représentable** dans l'outil ; elle est portée par les descriptions.

---

## 8. Processus de mise à jour

**La règle de tenue, applicable aux quatre filiales du groupe :**

> « Chaque filiale tient son inventaire dans le référentiel commun du groupe, avec un **propriétaire nommé pour chaque actif** ; tout élément découvert **en dehors** de cet inventaire est rattaché à un propriétaire ou traité **sous trente jours**, et sa découverte est **valorisée — jamais sanctionnée**. »

Trois pièces, toutes nécessaires : le **référentiel commun et le propriétaire** répondent au défaut structurel de Logistique, dont l'inventaire vivait dans une mémoire ; le **délai de trente jours** rend la règle vérifiable — on saurait au jour 31 qu'elle n'est pas tenue ; l'**incitation** évite que la filiale la plus honnête devienne, par punition, la dernière à signaler ses trous.

**Responsabilités** : la filiale tient l'inventaire au quotidien (R) ; le RSSI de filiale répond de son exhaustivité et de sa fraîcheur (A) ; le RSSI Groupe est consulté sur les règles communes et informé des trous, et ne redevient décideur que sur les **actifs inter-filiales**.

**Rythme de revue** : à chaque entrée ou sortie d'actif, et au minimum à la revue trimestrielle du Comité Exécutif.

---

> **Preuve d'état** : captures de l'instance dans `../3-Evidence/` — liste des actifs du périmètre `MERIDIAN-LOGISTIQUE` (2 pages) et vue d'analyse d'impact.
