# Séance 2 — TD (S2-03) : Business assets, supporting assets and DICT needs
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN — appliquées à **MERIDIAN Logistique**

> Note de méthode : le TD officiel illustre l'Exercice 1 avec la filiale Santé. Notre filiale d'instruction étant **MERIDIAN Logistique**, nous rejouons l'Exercice 1 sur notre propre dossier de filiale (au lieu de Santé) — c'est plus utile pour notre livrable réel, et l'Exercice 2 du TD porte de toute façon déjà sur Logistique par construction.

---

## Rappel du vocabulaire (EBIOS Risk Manager, ANSSI v1.5, sept. 2024)

- **Valeur métier** : « composante importante pour l'organisation dans l'accomplissement de sa mission » — service, fonction support, information, savoir-faire. **Zéro mot technique.**
- **Bien support** : « composante du SI sur laquelle repose une ou plusieurs valeurs métier » — nature **numérique, physique ou organisationnelle**.
- **Besoin de sécurité (DICT)** : Disponibilité, Intégrité, Confidentialité, Traçabilité — propriété à garantir pour une **valeur métier**, jamais une propriété de la machine qui la porte.
- **Notation** : échelle **relative** (3-4 niveaux), pas de fausse précision.
- **Test rapide** : *« la filiale pleurerait-elle sa disparition, ou seulement la DSI ? »* → valeur métier vs bien support.

---

## Exercice 1 — Les valeurs métier de MERIDIAN Logistique (adapté à notre filiale)

*Contexte tiré du dossier de filiale : 6 entrepôts (E1–E6), 2 dédiés au client pharmaceutique (pénalités 12 000 €/jour, audits annuels de la chaîne du froid), WMS maintenu par une TMA, automates de tri maintenus par un intégrateur via box 4G hors réseau supervisé, flotte télématique.*

### Q1. Entre 3 et 5 valeurs métier, en langage métier

1. **L'exécution des flux logistiques** (réception, préparation, expédition sur les 6 entrepôts — le service rendu, celui dont dépend 40 % du volume expédié du groupe)
2. **Le maintien de la chaîne du froid** pour le client pharmaceutique (température dirigée en entrepôt et en transport)
3. **Le savoir-faire opérationnel des six entrepôts** — l'information/le savoir-faire au sens du glossaire EBIOS RM : la connaissance fine de l'organisation de chaque site, aujourd'hui **non écrite**, portée par une seule personne
4. **La conformité contractuelle avec le client pharmaceutique** (réponse aux audits annuels, respect des engagements de pénalité, futur questionnaire de sécurité)

*Le WMS, les scannettes et les automates n'apparaissent **volontairement pas** dans cette liste : ce sont des biens supports (cf. Q2), pas des valeurs métier.*

### Q2. Biens supports rattachés, couvrant les 3 natures

| Valeur métier | Biens supports numériques | Biens supports physiques | Biens supports organisationnels |
|---|---|---|---|
| Exécution des flux logistiques | WMS (2 serveurs + BDD à E1), scannettes (~300, Wi-Fi), automates de tri (E2/E3/E4), compte de service WMS↔automates (mot de passe unique depuis 2019), liaisons opérateur inter-entrepôts | Entrepôts E1–E6, local serveur à E1 (climatisation défaillante) | Responsable Exploitation, 6 chefs d'entrepôt, Responsable SI filiale (3 pers.), Prestataire TMA du WMS, Intégrateur des automates |
| Maintien de la chaîne du froid | Logiciel des sondes de température (hébergé chez le fournisseur), télématique des remorques | Chambres froides, remorques réfrigérées, sondes physiques | Responsable Qualité et chaîne du froid |
| Savoir-faire opérationnel des entrepôts | *(aucun — c'est précisément le problème)* | — | **Responsable Exploitation, seul détenteur** |
| Conformité contractuelle client pharma | Portail d'expéditions du client (un compte par entrepôt) | — | Responsable Qualité (répond aux audits), Directeur de la filiale (porte le contrat) |

*La valeur métier n°3 est volontairement isolée pour montrer un cas limite du glossaire : un savoir-faire qui ne repose que sur **un seul bien support organisationnel**, sans aucun support numérique ou physique — ce qui en fait, par construction, la valeur métier la plus fragile de la filiale.*

### Q3. Le bien support le plus préoccupant, avec le vocabulaire du TD (pas celui de l'audit du dossier)

**Le compte de service WMS↔automates, au mot de passe identique sur les six entrepôts depuis 2019, en clair dans un fichier de configuration.** Dans le vocabulaire de ce TD : c'est un bien support qui porte une valeur métier — l'exécution des flux logistiques — dont les besoins de disponibilité **et** d'intégrité sont les plus élevés de la filiale, tout en étant, de l'aveu même de l'exploitation, connu de « tout le monde » sur le site. C'est donc un bien support dont la faiblesse expose **directement et largement** les besoins de sécurité de la valeur métier la plus critique de la filiale — exactement la définition que ce TD demande, à distinguer d'un simple « constat d'audit technique ».

*Mention à part pour la valeur métier n°3 : le Responsable Exploitation, en tant que bien support organisationnel **unique**, est structurellement le point de défaillance le plus fragile de tout le dossier — mais il porte une valeur métier de nature différente (un savoir-faire, pas un flux technique), ce qui justifie de garder le compte de service comme réponse principale à cette question.*

---

## Exercice 2 — Notation des besoins DICT, calibrage par les faits (déjà sur Logistique dans le TD officiel)

*4 faits réels servant d'étalon : CH Simone Veil de Cannes 2024 (ransomware, 15 % des postes chiffrés → disponibilité) ; amende CNIL Free/Free Mobile 2026, 42 M€ (confidentialité) ; France Travail 2024, 43 millions de personnes (l'échelle que peut prendre l'atteinte à une seule valeur métier) ; ENISA 2024, 32 % des opérateurs énergie européens sans supervision SOC de leurs processus OT critiques (traçabilité absente en monde industriel).*

### Q1. Deux valeurs métier de la filiale (imposées par l'énoncé du TD)

1. **La traçabilité du fret** (l'information qui rend le service valorisable pour les clients, notamment le client pharmaceutique)
2. **L'exécution des flux logistiques** (déjà identifiée en Exercice 1 — le TD réutilise volontairement la même valeur métier pour la noter)

### Q2. Notation DICT (échelle à 3 niveaux : négligeable / notable / très important), justification métier

| Besoin | Exécution des flux logistiques | Traçabilité du fret |
|---|---|---|
| **Disponibilité** | **Très important** — une panne du WMS arrête les camions ; un arrêt > 6h bloque 40 % du volume expédié du groupe (constat posé dès la séance 1) | Notable — une traçabilité momentanément indisponible ne stoppe pas l'expédition elle-même |
| **Intégrité** | **Très important** — des stocks faussés expédient le mauvais produit au mauvais endroit, et ce flux alimente directement la filiale Santé (fil rouge inter-filiales) | **Très important** — une fausse traçabilité est pire qu'aucune traçabilité : elle produit une **confiance mal placée** |
| **Confidentialité** | Notable — volumes et clients intéressent un concurrent, mais rien de comparable à une donnée de santé | Notable — même logique |
| **Traçabilité** | Notable à **très important** *(voir Q3)* | Très important — l'information est elle-même la traçabilité, son propre besoin en dépend directement |

### Q3. Comparaison et rating à réviser devant le Directeur Logistique

Le rating qui mériterait le plus clairement une **révision à la hausse** est la **traçabilité de l'exécution des flux logistiques**, en s'appuyant sur le fait ENISA : dans un environnement industriel **sans supervision** de ses processus critiques (rappel du dossier : le SOC du groupe ne reçoit **aucun** journal des automates, de la box 4G ni du WMS lui-même), on ne peut ni détecter ni comprendre un incident après coup — exactement la situation vécue lors de l'arrêt du WMS en avril, où *« personne n'a tenu de chronologie »*. Un candidat sérieux à passer de « notable » à « très important » avant d'être présenté en comité.

**Ce que cette comparaison prouve** : les deux valeurs métier ne sont **pas notées identiquement** partout — sinon la « position relative » n'aurait rien classé.

---

## Exercice 3 — La chaîne complète sur le fil rouge inter-filiales

*Le flux le plus intéressant du groupe traverse deux filiales : les scannettes d'entrepôt de Logistique alimentent le système de gestion des stocks de Santé, sur un réseau segmenté en séance 1 (VLAN dédié, pare-feu d'inspection, API d'urgence exigeant TLS 1.3 + MFA).*

### Q1. La chaîne complète du vocabulaire

**Valeur métier concernée** : le **réapprovisionnement d'urgence** des établissements de soin. La question de propriété n'était pas rhétorique : cette valeur métier **appartient à Santé** — c'est sa mission de soin qui exige d'être approvisionnée — alors que **la plupart des biens supports appartiennent à Logistique** :

| Bien support | Nature | Propriétaire opérationnel |
|---|---|---|
| Scannettes d'entrepôt | Numérique | Logistique |
| Système de gestion des stocks (côté Santé) | Numérique | Santé |
| API d'approvisionnement d'urgence | Numérique | Logistique/Santé (interface partagée) |
| VLAN dédié + pare-feu d'inspection | Numérique/infrastructure | Logistique (le seul cloisonnement réseau trouvé dans le groupe) |
| Équipes d'exploitation des entrepôts | **Organisationnel** — celui qu'on oublie | Logistique |

**Besoins DICT** de cette valeur métier : Disponibilité très importante (l'approvisionnement ne peut s'arrêter — rappel dossier : le flux est bloqué depuis 3 mois et « ça ne tiendra pas l'hiver » selon le Pharmacien chef de Santé), **Intégrité très importante** (cf. Q2 ci-dessous), Confidentialité notable, Traçabilité très importante (savoir ce qui a été commandé et livré à chaque établissement, exigence d'audit).

### Q2. Ce qui se passerait si l'intégrité des données de stock transmises était altérée — sans le terme technique de la séance 5

Des données de stock modifiées conduiraient à commander **trop, trop peu, ou au mauvais endroit** — jusqu'à priver un établissement de soin d'un approvisionnement urgent sur la foi d'un **stock fantôme**. C'est une atteinte à l'intégrité d'une valeur métier, avec des conséquences en cascade sur la mission de soin elle-même.

### Q3. Pourquoi ce cas justifie une cartographie de GROUPE, et non 4 cartographies de filiale

En deux phrases : une cartographie propre à chaque filiale montrerait, côté Santé, **une valeur métier sans ses biens supports**, et côté Logistique, **des biens supports sans la valeur métier qu'ils portent** — la dépendance elle-même resterait invisible dans les deux cas pris séparément. Seule la carte du **groupe** révèle cette dépendance croisée, et c'est très exactement le rôle d'arbitre inter-filiales confié au RSSI Groupe dès la séance 1.

---

## Auto-évaluation

| Critère | Notre niveau atteint |
|---|---|
| Valeurs métier (ex. 1, sur Logistique) | 4 actifs en langage métier, ancrés dans notre propre dossier de filiale, incluant un savoir-faire non écrit (pas seulement des services techniques) |
| Biens supports (ex. 1) | Les 3 natures représentées, rattachements explicites, **et** un cas limite exposé (le savoir-faire opérationnel porté par un seul bien support organisationnel) |
| Notation DICT (ex. 2) | Position relative assumée, une justification métier par note, **et** un arbitrage explicite revisité à la lumière d'un fait de calibrage (ENISA) |
| Chaîne complète (ex. 3) | Chaîne parcourue sur le fil rouge, propriété de la valeur métier établie, **et** l'argument de la carte de groupe formulé en termes de dépendance inter-filiales |
| Vocabulaire | Termes exacts utilisés, DICT présenté comme un alias de travail et non une norme officielle en tant que telle |
