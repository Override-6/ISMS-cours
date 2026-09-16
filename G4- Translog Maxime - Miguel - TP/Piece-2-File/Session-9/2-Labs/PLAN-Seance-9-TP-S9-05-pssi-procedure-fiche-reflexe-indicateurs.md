# PLAN — Séance 9, TP 1 (S9-05) : section PSSI, procédure, fiche réflexe, indicateurs et tableau de bord

**Mode opératoire écrit avant la saisie**, au format des plans des séances 4 à 8. Instance `translog-b`,
domaine `MERIDIAN-LOGISTIQUE`. Quatre exercices, tous dans le menu **Governance** (Documents, Metrics,
Dashboards). **Rien n'est recréé** : les quatre exercices s'appuient sur les objets déjà en place — la
déclaration d'applicabilité de la séance 8 (D8), le registre de risques et le plan de traitement de la
séance 7 (D7), les directives et règles d'arbitrage de la séance 1 (D1).

---

## 0. Discipline d'écriture à tenir (rappel du CM, cinq règles)

Une règle est une **obligation vérifiable** (sujet identifiable, verbe d'obligation, critère de
vérification) ; elle porte un **propriétaire et une preuve** ; **pas de verbe mou** (« veiller à »,
« s'efforcer de » sont interdits) ; **une phrase, une règle** ; **chaque document cite ce sur quoi il
repose** (la section PSSI cite le risque ou le contrôle qui la justifie, la procédure cite la règle qu'elle
déroule, la fiche réflexe cite la procédure qu'elle condense). Aucune règle n'est inventée : les trois
documents du jour **habillent** des obligations que le groupe porte déjà depuis D1/D4/D7/D8, ils n'en créent
pas de nouvelles hors de ce périmètre — sauf la fiche réflexe, qui peut nommer un point de contact resté
vide jusqu'ici (séance 3 : *« aucun point de contact unique n'existe »*), parce que c'est précisément
l'objet d'une fiche réflexe que de combler ce vide.

---

## 1. Exercice 1 — Section « gestion des vulnérabilités » de la PSSI-cadre (20 min, obligatoire)

**Ce qui l'ancre** : le risque **OS1** du registre (D7, `Very likely × Critical = High`, résiduel `Medium`
après `PT-01` à `PT-04`) ; le contrôle **A.8.8** retenu et **non conforme** dans la déclaration
d'applicabilité (D8 §2.2 : *« Directive `COR-01` de D1, non mesurée ; mises à jour du WMS non maîtrisées ;
scénario OS1 »*, traitement `PT-01`, 14/12/2026) ; le constat de l'audit initial (D4 : A.8.8 non couvert,
*« ni mesuré ni mesurable, mises à jour décidées par la TMA sans préavis »*).

**À créer** : document type **Policy**, référence `PSSI-VUL`, domaine `MERIDIAN-LOGISTIQUE`, source de
contenu *Authored*, lié en Relations au contrôle `A.8.8` de l'évaluation et/ou à la mesure `PT-01`.

| Rubrique | Contenu prévu |
|---|---|
| **Objet et fondement** | Gestion des vulnérabilités techniques du périmètre de MERIDIAN Logistique (WMS, base, scannettes, automates). Fondé sur le risque **OS1** (compromission du WMS via la TMA), le contrôle **A.8.8** retenu non conforme en D8, et le constat de D4 (correctifs non mesurés, TMA maîtresse du calendrier) |
| **Règles codifiées** (4 à 6, numérotées `PSSI-CADRE-VUL-01` et suivantes) | **VUL-01** — reprise littérale de `COR-01` : tout correctif qualifié critique est appliqué sous 14 jours calendaires. **VUL-02** — toute mise à jour du WMS fait l'objet d'une recette formalisée et d'un avenant au contrat `TMA-WMS-2021` avant déploiement (reprend `PT-01`). **VUL-03** — le périmètre couvert (WMS, base, scannettes, automates, réseau dédié) est inventorié et tenu à jour, chaque système portant un propriétaire nommé (reprend la règle de tenue de D2 §8). **VUL-04** — chaque vulnérabilité découverte est qualifiée en `Critique / Élevée / Moyenne / Faible` par le DSI de la filiale dans les 5 jours ouvrés suivant sa publication ou sa détection. **VUL-05** — un contrôle trimestriel de l'état des correctifs du périmètre est mené par le DSI de la filiale, daté et archivé |
| **Responsabilités** (alignées sur la matrice RACI de D1) | DSI de la filiale : R sur l'inventaire, la qualification et le contrôle trimestriel. Directeur de la filiale : A sur l'avenant contractuel de `PT-01`. RSSI Groupe : A sur le maintien en condition de sécurité (ligne RACI de D1), validateur des dérogations |
| **Dérogations** | Tout dépassement du délai de 14 jours est validé par le RSSI Groupe sous 48 heures (reprend `ARB-03` de D1) ; la dérogation est datée et motivée, jamais tacite |
| **Application et preuve** | Indicateur `IND-05` du tableau de bord (constats critiques sans plan daté) et un nouvel indicateur de correctifs à créer si le temps le permet ; preuve = l'avenant signé (`PT-01`), le registre trimestriel des vulnérabilités qualifiées |

**Test de l'auditeur, vérifié avant publication** : pour chaque règle, un tiers peut-il dire, sans
interroger l'auteur, qui est en défaut et sur quelle preuve ? VUL-01/02/05 le passent directement (délai et
propriétaire écrits) ; VUL-03/04 le passent via le renvoi à D2 §8 et à un délai chiffré (5 jours).

**Publication** : soumis à la revue d'un autre membre du groupe (Miguel) avant validation — **non
disponible aujourd'hui**, Miguel n'étant pas connecté à la séance ; publié sous compte Maxime avec cette
réserve tracée en §7 ci-dessous, à faire valider par Miguel dès son prochain passage dans l'instance.

---

## 2. Exercice 2 — Procédure de revue trimestrielle des comptes à privilèges (20 min, optionnel)

**Ce qui l'ancre** : la directive `PSSI-CADRE-ACC-02` (D1, revue trimestrielle des privilèges sur les bases
métier, propriétaire nommé « RSSI de filiale ») ; **la filiale n'a pas de RSSI** — écart déjà nommé à la
relecture de D8 (clause 5.3, partiellement conforme : *« la filiale n'a pas de RSSI »*) et par le TD 1 de la
séance 9 côté sensibilisation ; le compte de domaine partagé `svc-applica` (constat **C4** de D4, traitement
`PT-02`, 14/01/2027).

**À créer** : document type **Procedure**, référence `PRO-PRIV`, domaine `MERIDIAN-LOGISTIQUE`, liée en
Relations aux contrôles `A.5.15`/`A.5.16`/`A.8.2` (compromis, traitement `PT-02`).

| Rubrique | Contenu prévu |
|---|---|
| **Objet et document parent** | Déroule `PSSI-CADRE-ACC-02` : revue trimestrielle des comptes à privilèges du WMS et du domaine bureautique de Logistique |
| **Périmètre** | Comptes à privilèges des bases WMS, comptes administrateurs du domaine bureautique des six entrepôts. **Cas limite nommé** : le compte de service partagé `svc-applica` (`LOG-SA-04`) reste couvert par cette procédure **jusqu'à** sa fermeture par `PT-02` (comptes nommés + MFA, 14/01/2027) ; après cette date, la procédure ne revoit plus que des comptes nominatifs |
| **Déclencheur** | Échéance trimestrielle calendaire (dernier jour ouvré du trimestre) ; un trimestre manqué déclenche une alerte au RSSI Groupe sous 5 jours ouvrés |
| **Rôles** | **Prépare** : DSI de la filiale (liste extraite). **Exécute la revue** : DSI de la filiale. **Contrôle** : RSSI Groupe, faute de RSSI de filiale — **réserve écrite** : ce rôle revient nominalement au RSSI de filiale (D1), poste non pourvu à ce jour ; le RSSI Groupe l'exerce par défaut, à réattribuer dès la nomination. **Signe** : Directeur de la filiale |
| **Étapes** (numérotées) | 1) Extraire la liste des comptes à privilèges actifs (WMS + domaine). 2) La comparer à la liste signée du trimestre précédent. 3) Marquer les comptes inactifs depuis plus de 30 jours (cible du tableau de bord de séance 1 : 0 compte inactif non révoqué). 4) Faire valider chaque retrait par le propriétaire du système concerné. 5) Exécuter les révocations. 6) Signer et archiver la déclaration trimestrielle |
| **Preuve produite** | La déclaration signée du trimestre, archivée dans les dossiers de la filiale, datée et nominative |
| **Indicateur alimenté** | Part des comptes à privilèges revus dans le délai trimestriel (nouvel indicateur possible), ou, à défaut, le KPI de couverture MFA déjà posé en séance 1 |

**Publication** : même réserve qu'à l'exercice 1 — soumis à Maxime, validation croisée par Miguel à faire.

---

## 3. Exercice 3 — Fiche réflexe « suspicion de rançongiciel », site E1 (15 min, obligatoire)

**Site choisi** : **E1**, pour trois raisons tirées de la carte du pouvoir et de la cartographie : c'est le
site qui héberge le WMS et son **local serveur unique** (D4 §2.1 : angle mort du thème physique, point de
défaillance unique) ; c'est l'un des deux entrepôts dédiés au client pharmaceutique (`LOG-PA-02`,
`LOG-PA-04`) ; et il ne porte **pas** d'automates de tri (contrairement à E2/E3/E4), ce qui isole l'exercice
sur le risque WMS pur, sans mélanger IT et OT.

**À créer** : document type **Other** (aucun type « fiche réflexe » n'existe dans l'outil), référence
`FR-RANCON`, domaine `MERIDIAN-LOGISTIQUE`, liée en Relations au contrôle de sauvegarde/réponse à incident
le plus proche (`A.5.24`, gestion des incidents — orphelin sans mesure en D8 §2.4 — et/ou `PT-04`, test de
restauration).

| Bloc | Contenu prévu, une liste numérotée par bloc |
|---|---|
| **Actions immédiates** | 1) Déconnecter du réseau les serveurs WMS et le poste du local serveur d'E1 — **débrancher, ne jamais éteindre** (préserve la mémoire volatile). 2) Le droit d'isolement d'urgence (`ARB-02` de D1) est exercé, **à défaut de RSSI de filiale**, par le DSI de la filiale jusqu'à nomination — réserve à écrire noir sur blanc, pas à cacher. 3) L'interface d'urgence Logistique↔Santé (`ARB-02`) est déjà suspendue depuis juin 2026 (D8 §1) : rien à couper de ce côté, le vérifier plutôt que le supposer. 4) **Nommer ici, maintenant, le point de contact unique** de la crise (le DSI de la filiale) — comble le vide documenté depuis la séance 3 (*« trois chefs d'entrepôt ont appelé la TMA, deux l'intégrateur, un le Responsable SI en congé »*) |
| **Alertes à faire remonter** | 1) RSSI Groupe sous 2 heures (`PSSI-CADRE-INC-01`), chronologie tenue dès la première minute — l'absence de chronologie est le constat même de `A.5.24` en D8. 2) SOC du groupe, pour surveiller une éventuelle propagation vers E2/E3/E4 par le réseau bureautique/industriel **non cloisonné** (constat **C3**, majeur) — l'alerte ne s'arrête pas à E1. 3) Direction de la filiale, au titre du contrat client pharmaceutique (pénalités 12 000 €/jour d'arrêt). 4) APPLICA (TMA du WMS) est informée **après** la mise en sécurité, jamais avant : le contrat actuel ne prévoit qu'une astreinte pour panne (art. 2), pas une obligation de notification d'incident — cette obligation est en cours de négociation (`PT-06`/`PT-08`, D7, 14/03/2027) et **n'est pas acquise aujourd'hui** |
| **Interdits** | 1) Ne jamais éteindre les machines touchées — seule la déconnexion réseau est autorisée. 2) Ne jamais payer ou négocier avec l'attaquant sans autorisation explicite de la Direction Générale. 3) Ne jamais restaurer depuis une sauvegarde avant capture forensique — et savoir que le délai de restauration réel est **inconnu** : aucun test de restauration n'a jamais été mené (D1 ; `PT-04`, échéance 14/11/2026, encore ouverte). 4) Ne jamais laisser un chef d'entrepôt appeler directement un technicien de l'intégrateur ou de la TMA sur un contact personnel — pratique déjà identifiée comme un risque (D6, T4 : *« aucune vérification d'identité »*) — tout contact technique passe par le point de contact nommé ci-dessus. 5) Ne jamais communiquer vers le client pharmaceutique ou l'extérieur sans validation de la Direction de la filiale |

**Test à blanc** (Step 5 de l'énoncé) : lu en binôme si Miguel est disponible ; à défaut, relu par Maxime
seul en chronométrant une minute de lecture puis en récitant les quatre premières actions sans relire — fait
et documenté en feuille de travail.

**Publication** : après le test à blanc, export PDF pour affichage physique — non réalisable dans cette
séance (pas d'imprimante ni de mur à documenter), noté comme reste à faire matériellement.

---

## 4. Exercice 4 — Indicateurs et tableau de bord (25 min, obligatoire)

**Matière de composition** (énoncé : dashboard de séance 1, indicateurs promis par les trois documents du
jour, le trou du filet nommé en cours — *l'avancement de la segmentation à Logistique, qu'aucun chiffre ne
suit* —, les réserves de D7/D8).

### 4.1 Sélection retenue — six indicateurs, trois familles, deux calculables aujourd'hui

| Réf. | Indicateur | Famille (compliance / risk / operations) | Objectif de la note de stratégie | Calculable aujourd'hui avec le fichier ? |
|---|---|---|---|---|
| `IND-01` | Couverture de la PSSI-cadre | Compliance | Sous-section 1 (gouvernance cible) | Non — donnée groupe, hors instance `translog-b` |
| `IND-02` | Obsolescence du parc technique | Risk | Sous-section 5 (risques majeurs, OS1) | Non — pas encore instrumenté dans l'outil |
| `IND-03` | Délai moyen de détection des incidents | Operations | Sous-section 7 (traitement, `PT-07`) | Non — aucun incident réel enregistré dans l'instance |
| `IND-04` | Respect du délai de notification à 2 h (`INC-01`) | Compliance | Sous-section 1 (directive `INC-01`) | Non — même raison |
| `IND-05` | Constats d'audit critiques sans plan daté après 30 jours | Risk | Sous-section 4 (état des lieux, C3/C4) | **Oui** — `C3`→`PT-03` (14/06/2027), `C4`→`PT-02` (14/01/2027) : 2/2 majeurs déjà datés, valeur du jour = **0 %** |
| `IND-06` | Avancement de la segmentation réseau IT/OT (`PT-03`) | Operations | Sous-section 7 (traitement du risque) | **Oui** — `PT-03` non démarré à ce jour (build non engagé), valeur du jour = **0 %**, cible 100 % au 14/06/2027 |

Six indicateurs, les trois familles couvertes, deux valeurs lisibles aujourd'hui dans le registre de D7 et
la déclaration de D8 (`IND-05`, `IND-06`) — preuve que le jeu n'est pas un vœu pour un outillage futur.
`IND-01` à `IND-04` reprennent, complétés, les cinq indicateurs retenus au TD 1 de ce matin (candidats 10, 4,
5, 12 du cas), à l'exception du candidat 9 (constats non résolus à 30 jours) qui devient ici `IND-05`,
reformulé identique.

### 4.2 Fiches complètes (cible, seuil, phrase de la règle d'or — reprises du TD 1 quand elles existent)

| Réf. | Cible | Seuil d'alerte | Fréquence | Destinataire |
|---|---|---|---|---|
| `IND-01` | 100 % des quatre filiales | < 75 % | Trimestrielle | Comité Exécutif |
| `IND-02` | < 5 % | > 15 % | Trimestrielle | Comité Exécutif |
| `IND-03` | < 2 h | > 4 h | Mensuelle | RSSI Groupe, remonté trimestriellement au Comité |
| `IND-04` | 100 % | < 100 % | À chaque incident majeur | RSSI Groupe, Comité Exécutif |
| `IND-05` | 0 % | > 0 % | Mensuelle | Comité sécurité groupe |
| `IND-06` | 100 % au 14/06/2027 | Aucun jalon intermédiaire atteint à échéance -6 mois | Mensuelle | Comité Exécutif, Directeur de la filiale |

### 4.3 Étapes dans l'outil

1. **Définir** chaque métrique (Metrics → Metric definitions → Add) : référence `IND-01` et suivantes, nom
   sans jargon, description au format « KPI/KRI, ce que le chiffre mesure », domaine du groupe, catégorie
   Quantitative, unité Percentage (sauf `IND-03` en Duration/heures si le champ l'autorise, sinon Count),
   cible par défaut, case « plus haut = mieux » décochée pour tout ce qui doit baisser (`IND-02`, `IND-03`,
   `IND-05`).
2. **Instancier** chaque métrique (Metric instances → Add) : référence identique, domaine `translog-b`,
   description reprenant formule + source + seuil d'alerte, fréquence de collecte, destinataire et
   objectif de la note de stratégie visés, valeur cible, propriétaire en `Assigned to`. Statut **Active**
   pour `IND-05` et `IND-06` (lisibles aujourd'hui), **Draft** pour les quatre autres (source encore à
   ouvrir : groupe, incidents réels, obsolescence instrumentée).
3. **Lire** la valeur du jour pour `IND-05` et `IND-06` : ajouter un échantillon daté du 16/09/2026, valeur
   0 %, observation citant `C3`/`C4`/`PT-02`/`PT-03` pour `IND-05` et `PT-03` seul pour `IND-06`.
4. **Construire le tableau de bord** (Dashboards → Add) : référence `TDB-COMEX`, une tuile texte en tête
   (période couverte : T3 2026), une carte par indicateur (valeur + cible), ordonnées par poids de décision
   — `IND-05` et `IND-06` en tête puisqu'ils sont les seuls à porter une valeur réelle aujourd'hui —, une
   tuile texte en pied pour les messages et décisions demandées.

### 4.4 Captures attendues

Préfixe `S9-05-`, dans `../3-Evidence/` : les trois documents publiés (ou en revue), la liste des six
métriques définies, le détail des instances `IND-05`/`IND-06` avec leur échantillon du jour, le tableau de
bord assemblé.

---

## 5. Ordre d'exécution retenu

CM déjà lu (matière du TD 1 de ce matin) → Exercice 1 (PSSI-VUL) → Exercice 3 (FR-RANCON, avant l'exercice 2
optionnel, pour ne pas risquer de manquer un exercice obligatoire si le temps presse) → Exercice 4
(indicateurs, qui a besoin des deux documents précédents pour ses renvois) → Exercice 2 (PRO-PRIV,
optionnel, si le temps le permet).

## 6. Critères de validation

Les trois documents obligatoires (`PSSI-VUL`, `FR-RANCON`, et `PRO-PRIV` si le temps le permet) créés,
chacun citant sa source amont ; aucune règle au verbe mou ; le tableau de bord porte au moins un indicateur
avec une valeur du jour lisible dans le fichier ; les six familles/objectifs sont couverts sans indicateur
orphelin d'objectif de note.

## 7. Réserve connue avant de commencer

**Validation croisée non disponible aujourd'hui.** L'énoncé demande que chaque document soit soumis à la
revue d'un autre membre du groupe avant publication (règle déjà appliquée aux exigences de conformité
depuis la séance 3 : *« l'outil interdit à un auteur de valider son propre texte »*). Miguel n'étant pas
connecté à cette séance, les trois documents sont rédigés et **publiés sous le compte de Maxime avec cette
réserve tracée dans la feuille de travail** ; la revue croisée de Miguel reste due avant la remise du 17
septembre.
