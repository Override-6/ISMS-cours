# PLAN D'ACTION — Séance 4, TP 1 : auto-évaluation de la filiale dans CISO Assistant

**Groupe 4 (Translog)** · instance `translog-b` (https://translog-b.lockbay.eu) · périmètre `MERIDIAN-LOGISTIQUE`
**Source du TP** : `../../../../S4 - Sources/TP 1/Subsidiary Self-Assessment in CISO Assistant _ Lockbay Academy.pdf`
**Ce fichier n'est pas un livrable** : c'est le mode opératoire. Le livrable de la séance 4 est **D4, le rapport d'audit initial**, écrit au **TP 2** ; ce TP-ci en fabrique la matière première.

> **Règle de la journée, avant tout clic** : *rien ne se recrée.* L'évaluation de conformité existe depuis la séance 3, vierge. On la **remplit**. Aucun objet des séances 2 et 3 n'est recréé ni renommé — c'est un critère de validation explicite du TP.

---

## 0. Ce qui bloque, et qu'il faut faire d'abord

Le TP 1 s'appuie sur **les constats gradués « à midi »** — c'est-à-dire le **TD 2 de la séance 4** (`S4 - Sources/TD 2/`), qui n'est pas encore fait au dossier. Sans ces gradations, les exercices 2, 3 et 5 n'ont pas leur matière.

**Étape 0 (20 min, hors ligne, à faire avant d'ouvrir l'instance)** — produire le tableau de gradation du TD 2, exercice 1 : les **huit constats C1 à C8**, gradés *conforme / non-conformité majeure / non-conformité mineure / observation*, chacun justifié en une phrase citant **l'exigence** et **l'étendue** de l'écart (jamais la gravité ressentie), plus les **deux gradations discutables** avec l'argument de chaque camp.
→ fichier : `../4-Working-notes/Seance-4-TD-S4-03-gradation-des-constats.md`

**Les trois constats qui concernent Logistique** (les seuls dont ce TP a besoin) :

| Réf. | Constat | Critère cité | Gradation proposée (à débattre au TD) |
|---|---|---|---|
| **C3** | Réseaux bureautique et industriel interconnectés, sans cloisonnement | A.8.22 | **Non-conformité majeure** — l'exigence est *absente* sur la totalité du périmètre, et l'écart expose directement les automates qui portent `PA-01` |
| **C4** | Compte de domaine partagé avec la tierce maintenance du WMS, porté par un nombre de personnes que personne ne peut établir | A.5.19, A.8.2 *(+ ACC-01, ACC-02)* | **Non-conformité majeure** — l'imputabilité est *inopérante*, pas dégradée : l'audit interne a demandé la liste nominative et a reçu un nom de compte |
| **C7** | Flux inter-filiales Logistique↔Santé : VLAN dédié et pare-feu d'inspection en place, **seul cloisonnement du groupe** ; flux suspendu depuis trois mois à la demande du RSSI de Santé | A.8.22 | **Conforme** *(sur ce seul flux)* — et c'est le piège : un point conforme sur un flux à l'arrêt ne couvre pas l'exigence sur le périmètre. À écrire tel quel, c'est la nuance qui fera la valeur du rapport |

Les cinq autres constats (C1, C2, C5, C6, C8) appartiennent aux autres filiales : ils sont gradés au TD parce que le cycle d'audit est celui du groupe, mais **ils n'entrent pas dans l'auto-évaluation**, qui porte sur `MERIDIAN-LOGISTIQUE`.

---

## 1. Vérifications d'instance avant de commencer (10 min, en ligne)

| # | À vérifier dans `translog-b` | Attendu | Si ce n'est pas le cas |
|---|---|---|---|
| 1 | **Connecté sous un compte nominatif**, pas sous `admin@lockbay.eu` | Compte personnel créé dans *Identity management*, droits sur le domaine de la filiale | **Le créer maintenant.** C'est `fixes.md` **F5**, et le coefficient individuel (0,85 → 1,15) s'appuie à parts égales sur la traçabilité nominative dans l'instance. Tous les objets créés aujourd'hui — quatre mesures appliquées, douze statuts — porteront un auteur : c'est le meilleur moment de la séance pour fermer F5 |
| 2 | Le **périmètre** `MERIDIAN-LOGISTIQUE` existe et porte les actifs de la séance 2 | 4 valeurs métier + 13 biens supports | Ne rien recréer : chercher, l'objet est là depuis S2-05 |
| 3 | L'**évaluation de conformité** existe, adossée à ISO/IEC 27001:2022, rattachée au périmètre | `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, **vierge**, 123 exigences dont 93 contrôles d'annexe A | Ne pas la renommer. ⚠️ Le PDF du TP l'appelle « MERIDIAN-SUBSIDIARY - … » : c'est un libellé générique de l'énoncé, pas une consigne de renommage. **Noter la correspondance dans l'encadré de cadrage de la feuille de travail** et passer |
| 4 | Les **libellés de statut de l'outil** dans cette version | à relever à l'écran | C'est l'objet du §2 : le TP dit explicitement que l'échelle du module doit être *mappée* sur les libellés de l'outil, et le mapping écrit sur la feuille |
| 5 | Où l'outil range les **mesures appliquées** (*applied controls*) et comment on en rattache une à une exigence évaluée | repéré, pas encore créé | Repérage seulement — l'exercice 3 en créera quatre |

**Deux gestes en attente qui se ferment bien aujourd'hui** (facultatifs, mais l'instance est ouverte) : le marquage du **Top 5** dans la liste des actifs (`fixes.md` **F3**) et la **capture de l'arbre déplié** montrant 93 contrôles en 37/8/14/34 (`fixes.md` **F6**).

---

## 2. Le mapping des statuts — à écrire avant d'évaluer

L'échelle du module, qui fait foi dans la feuille de travail :

| Statut du module | Sens | Ce qu'il exige |
|---|---|---|
| **Couvert** | Exigence satisfaite sur le périmètre évalué | Une **preuve vérifiable**, pas une déclaration |
| **Partiel** | Satisfaite sur une partie du périmètre, ou partiellement | La preuve de ce qui existe **ET** la description de ce qui manque |
| **Non couvert** | Non satisfaite | Le constat, tel que formulé le matin |
| **Non évalué** | Aucune preuve disponible, ni dans un sens ni dans l'autre | L'**aveu explicite**, qui vaut mieux qu'une estimation |
| **Non applicable** | Sans objet sur ce périmètre | Une justification écrite, jamais un confort |

**À faire à l'écran** : relever les libellés exacts de l'instance et remplir la colonne de droite. L'ossature attendue dans CISO Assistant est un couple *statut d'avancement* (à faire / en cours / …) et un **résultat** (non évalué / non conforme / partiellement conforme / conforme / non applicable) — **à confirmer**, la version fait foi, pas ce plan. La correspondance probable :

| Module | Résultat dans l'outil *(à confirmer à l'écran)* |
|---|---|
| Couvert | *Compliant* |
| Partiel | *Partially compliant* |
| Non couvert | *Non-compliant* |
| Non évalué | *Not assessed* — laisser le résultat non renseigné **ne suffit pas** : l'aveu doit être visible, donc l'avancement passe à « en cours/évalué » et la justification écrite |
| Non applicable | *Not applicable* |

> **Les statuts vont dans l'outil ; les justifications et les preuves vont sur la feuille de travail.** Si le champ de commentaire de l'exigence existe, y recopier la justification en une ligne : c'est ce que verra le correcteur dans l'export.

---

## 3. Exercice 1 — cadrer (10 min)

**Sortie attendue** : l'encadré de cadrage, en tête de la feuille de travail, trois lignes.

1. **Périmètre** : MERIDIAN Logistique — six entrepôts E1–E6, WMS, ~300 scannettes, automates de tri E2/E3/E4, chaîne du froid ; les actifs cartographiés en séance 2 (`LOG-PA-01` à `04`, `LOG-SA-01` à `13`). Dire aussi ce qui **n'est pas** évalué : les trois autres filiales, et les 111 exigences non retenues aujourd'hui.
2. **Critères** : les **douze exigences** du sous-ensemble ci-dessous, extraites d'ISO/IEC 27001:2022 importé en séance 3, **complétées des directives de la PSSI cadre** codifiées en séance 1 — `PSSI-CADRE-ACC-01` (MFA sur tout accès distant et tout privilège d'administration), `ACC-02` (revue trimestrielle des privilèges sur les bases métier), `INC-01` (notification d'incident majeur au RSSI Groupe sous 2 h), `JRN-01` (collecte des journaux vers le SOC centralisé), `COR-01` (correctif critique sous 14 jours).
3. **Règle de preuve** : aucune exigence déclarée *couverte* sans **preuve nommée** ; le doute se déclare *non évalué*.

**La question qui sauve l'auto-évaluation**, à se poser avant chaque « couvert » : *quelle preuve un auditeur indépendant accepterait-il demain matin ?* Si la réponse est « la parole de l'équipe », le statut honnête est **non évalué**.

---

## 4. Exercice 2 — évaluer douze exigences (35 min)

**Dans l'outil** : ouvrir l'évaluation, chercher chaque exigence par sa référence, poser le résultat. **Sur la feuille** : la justification, preuve nommée ou constat cité.

Pré-analyse du dossier, à **contester** exigence par exigence avant de la saisir — elle n'est là que pour éviter de repartir de zéro devant l'écran :

| Réf. | Exigence | Statut proposé | Justification / preuve nommée | Actif concerné |
|---|---|---|---|---|
| **A.5.9** | Inventaire des informations et actifs associés | **Partiel** | *Ce qui existe* : la cartographie D2 saisie dans `translog-b` — 4 valeurs métier, 13 biens supports, un propriétaire par actif, Top 5 justifié. *Ce qui manque* : la filiale n'a envoyé **aucun** inventaire (« tout est dans le WMS »), le nombre exact de scannettes est inconnu, aucun schéma réseau n'existe, les automates ne sont pas inventoriés par leur exploitant, et la règle de tenue à 30 jours est **écrite mais pas appliquée** | `SA-01`…`SA-13` |
| **A.5.15** | Contrôle d'accès | **Non couvert** | Constat **C4** + pack §5.2 : compte de domaine partagé avec la tierce maintenance, porteurs inconnus ; l'intégrateur accède par une **liaison 4G hors du réseau supervisé** ; aucune revue de privilèges (`ACC-02` non tenue) | `SA-01`, `SA-03`, `SA-10` |
| **A.5.16** | Gestion des identités | **Non couvert** | **C4** : l'identité n'est pas unique et attribuable — l'audit interne du holding a demandé la liste nominative des porteurs du compte de la TMA et a reçu **un nom de compte, aucun nom de personne** | `SA-10` |
| **A.5.17** | Informations d'authentification | **Non couvert** | Pack §5.3 : le compte de service WMS↔automates porte **le même mot de passe sur les six entrepôts depuis 2019**, en clair dans un fichier de configuration, connu de tous en Exploitation | `SA-04` *(rang 2 du Top 5)* |
| **A.5.19** | Sécurité dans les relations fournisseurs | **Non couvert** | **C4** + pack §2 : le contrat de l'intégrateur ne comporte **ni clause de réversibilité ni exigence de sécurité** ; le contrat de TMA prévoit une astreinte, **pas de journalisation nominative** | `SA-03`, `SA-10` |
| **A.5.22** | Surveillance, revue et gestion des changements des services fournisseurs | **Non couvert** | Pack §4 : « la TMA fait les mises à jour la nuit, quand elle veut, on l'apprend le matin » — aucun contrôle de changement, aucune revue de service ; l'intégrateur considère les réglages des automates comme sa **propriété industrielle** | `SA-01`, `SA-03` |
| **A.6.3** | Sensibilisation, formation à la sécurité | **NON ÉVALUÉ** ✅ | **Aucune preuve disponible dans un sens ni dans l'autre.** Le dossier de filiale ne mentionne ni sensibilisation, ni support, ni feuille d'émargement, et nous n'avons **pas posé la question**. L'aveu est le statut honnête — c'est le « non évalué » assumé qu'exige la règle d'or | — |
| **A.8.2** | Droits d'accès à privilèges | **Non couvert** | **C4** + pack §5.2/5.3 : compte de domaine partagé et compte de service partagé, aucun inventaire des comptes à privilèges, aucune revue trimestrielle (`ACC-02`) | `SA-04`, `SA-10` |
| **A.8.5** | Authentification sécurisée | **Non couvert** | `ACC-01` exige la MFA sur tout accès distant et tout privilège d'administration : la TMA intervient par un compte partagé, l'intégrateur par une 4G hors supervision, et le secret du compte de service est en clair. **À débattre** : on peut soutenir *non évalué* faute de preuve d'absence de MFA — mais un secret partagé en clair suffit à établir l'écart | `SA-01`, `SA-03`, `SA-04` |
| **A.8.8** | Gestion des vulnérabilités techniques | **Non couvert** | `COR-01` (correctif critique sous 14 jours) n'est **ni mesuré ni mesurable** : mises à jour du WMS décidées par la TMA sans information préalable, automates sous propriété industrielle de l'intégrateur, aucun suivi des vulnérabilités. **À débattre** : *non évalué* est défendable sur le délai lui-même ; *non couvert* l'est sur l'absence de processus | `SA-01`, `SA-03` |
| **A.8.15** | Journalisation | **Partiel** | *Ce qui existe* : le SOC du groupe reçoit les journaux du **réseau bureautique** de la filiale (`JRN-01` amorcée). *Ce qui manque* : rien des **automates**, rien de la **liaison 4G**, rien du **WMS** lui-même ; l'arrêt d'avril l'a prouvé — personne n'a pu tenir de chronologie | `SA-01`, `SA-03` |
| **A.8.22** | Cloisonnement des réseaux | **Non couvert** | Constat **C3** : réseaux bureautique et industriel interconnectés, sans segmentation, sur les six sites. Nuance à écrire : le **VLAN dédié + pare-feu d'inspection** du flux Santé (**C7**) est le seul cloisonnement du groupe, mais il porte sur **un flux suspendu depuis trois mois** — un point conforme hors périmètre utile ne couvre pas l'exigence | `SA-03`, `SA-12` |

**Contrôle avant de passer à la suite** : les trois constats Logistique du TD (**C3, C4, C7**) doivent être **retrouvables** dans ces douze lignes — C3 en A.8.22, C4 en A.5.15/A.5.16/A.5.19/A.8.2, C7 en nuance de A.8.22. Un constat gradué le matin qui ne réapparaît nulle part l'après-midi est un constat perdu.

**Ce que cette grille produit** : 0 couvert · 2 partiels · 9 non couverts · 1 non évalué. C'est sévère, et c'est le point : *toute la séance est un exercice de sévérité envers soi-même*. Si l'un de nous veut remonter une ligne à « couvert », il doit nommer la preuve qu'un auditeur accepterait demain matin.

---

## 5. Exercice 3 — quatre mesures appliquées dans l'outil (15 min)

**Sortie attendue** : **quatre mesures appliquées** (*applied controls*), deux par constat, chacune rattachée à l'exigence en écart évaluée à l'exercice 2, chacune avec **propriétaire** et **échéance**.

**Les deux constats retenus** :
- **du tableau du TD** : **C3**, réseaux bureautique et industriel interconnectés — le plus grave des trois, parce que l'écart porte sur *la totalité* du périmètre et qu'il transforme le compte partagé de C4 en chemin vers les automates. *(C4 est défendable comme « le plus grave » ; si le TD le grade au-dessus, permuter — mais l'écrire.)*
- **du pack de filiale §5, non repris par le TD** : **§5.3**, le compte de service WMS↔automates, même mot de passe sur six entrepôts depuis 2019, en clair. C'est le **rang 2 du Top 5** de la séance 2. *(Alternative défendable : §5.6, l'absence de procédure d'incident — elle rend `INC-01` intenable et répond à la question de la Direction Générale « si ça s'arrête six heures, qui appelle qui ? ». À garder sous la main pour le TP 2, section 4.)*

| # | Constat | Type | Mesure — formulée SMART | Rattachée à | Propriétaire | Échéance |
|---|---|---|---|---|---|---|
| **M1** | C3 | **Correction** | Placer les automates de E2/E3/E4 sur un VLAN dédié, filtrage en défaut-refus à la frontière IT/OT, matrice de flux documentée. *Mesurable* : 0 route entre VLAN bureautique et VLAN industriel hors matrice, vérifié sur extraction de configuration | A.8.22 | DSI filiale, avec le Responsable Exploitation | date fixe, **hors pic** — le pic est de 10 mois sur 12, donc la fenêtre se négocie, elle ne se souhaite pas |
| **M2** | C3 | **Action corrective** | Traiter la cause — aucun schéma réseau, aucune règle de raccordement : produire le schéma réseau des six sites et **soumettre tout raccordement d'équipement industriel à un avis d'architecture écrit de la DSI filiale avant mise en service**, clause portée au contrat de l'intégrateur à son échéance. *Mesurable* : schéma daté et versionné + 100 % des raccordements passés par l'avis, contrôlé en revue trimestrielle | A.8.22, A.5.19 | DSI filiale (schéma) · Direction de la filiale (contrat) | schéma à 3 mois · clause à l'échéance contractuelle |
| **M3** | Pack §5.3 | **Correction** | Remplacer le secret partagé par **six secrets distincts**, retirés des fichiers de configuration en clair et déposés dans un coffre à secrets ; rotation à la mise en œuvre. *Mesurable* : 6 secrets distincts, **0 occurrence en clair** trouvée par une recherche sur les fichiers de configuration des six sites | A.5.17, A.8.2 | DSI filiale | date fixe, coordonnée avec la TMA |
| **M4** | Pack §5.3 | **Action corrective** | Traiter la cause — aucun cycle de vie des comptes de service : tenir un **registre nominatif des comptes de service et à privilèges** (propriétaire, usage, date de dernière rotation), rotation annuelle, revue trimestrielle des privilèges alignée sur `ACC-02` ; exiger contractuellement de la TMA une **journalisation par utilisateur nommé**. *Mesurable* : registre à jour à chaque revue trimestrielle, écart au calendrier mesuré | A.8.2, A.5.19, A.5.15 | RSSI de filiale (registre) · DSI filiale (TMA) | registre à 2 mois · première revue au trimestre suivant |

**Test SMART, à passer ligne par ligne avant de valider** : spécifique, **mesurable**, atteignable et réaliste, **défini dans le temps**. L'indice du TP : « sensibiliser les équipes » échoue sur **M** et sur **T** — aucune des quatre lignes ci-dessus ne doit pouvoir se reformuler ainsi.

**Distinction à ne jamais perdre** (elle est notée) : la **correction** fait disparaître l'écart constaté ; l'**action corrective** fait disparaître sa **cause**. Corriger sans traiter la cause, c'est éponger sous une fuite.

---

## 6. Exercice 4 — synthèse et lecture de maturité (15 min)

**Sortie attendue** : la synthèse en bas de la feuille de travail.

**a) Comptage par thème** — squelette à remplir avec les statuts réellement saisis :

| Thème | Exigences | Couvert | Partiel | Non couvert | Non évalué |
|---|---|---|---|---|---|
| **Organisationnel (A.5)** | A.5.9 · 5.15 · 5.16 · 5.17 · 5.19 · 5.22 | 0 | 1 | 5 | 0 |
| **Personnes (A.6)** | A.6.3 | 0 | 0 | 0 | 1 |
| **Technologique (A.8)** | A.8.2 · 8.5 · 8.8 · 8.15 · 8.22 | 0 | 1 | 4 | 0 |
| **Total** | 12 | **0** | **2** | **9** | **1** |

**b) Lecture de maturité en deux phrases**, au sens de la grille de la séance 1 — la trame :
> *Là où la filiale est outillée* : sur ce que le RSSI Groupe a lui-même construit — la cartographie et le référentiel — pas sur ce qu'elle exploite. *Là où elle vit de déclarations* : la relation fournisseur, les sauvegardes « confirmées par la TMA » et jamais restaurées, l'inventaire « dans la tête du Responsable Exploitation ». *Là où elle est aveugle* : le périmètre industriel — automates, liaison 4G, WMS — dont **aucun journal** ne remonte au SOC, et la sensibilisation, dont nous ne savons rien.

**c) Le biais de notre propre évaluation** — la ligne la moins certaine et pourquoi. Le candidat : **A.5.9 en « partiel »**. La preuve invoquée est en partie **notre propre cartographie**, produite par nous et non vérifiée par un tiers, et la règle de tenue à 30 jours qui la maintient est une **directive écrite en séance 2, jamais appliquée** — une intention, pas un fait observable. Un auditeur indépendant pourrait la rétrograder. L'écrire nous-mêmes coûte moins cher que de se le faire dire.

---

## 7. Exercice 5 — extraire la matière du rapport (10 min)

**Sortie attendue** : deux listes séparées, en bas de la feuille — c'est *exactement* ce que consommera le TP 2, sections 3, 4, 5 et 6.

1. **Liste des écarts** — tous les statuts *non couvert* et *partiel*, avec pour chacun : l'exigence, le constat associé s'il existe (C3, C4, pack §5.x), et **la gradation retenue à midi**.
2. **Liste « angles morts »** — les *non évalué*, à part. A.6.3 aujourd'hui. Un rapport honnête distingue **ce qui est en écart** de **ce qui est inconnu**.
3. **Contrôle de complétude** : la liste contient-elle tout ce que le TD a gradué pour Logistique — **C3, C4 et C7** ? Un rapport qui perd des constats en route fabrique de la fausse assurance.

---

## 8. Preuves d'état à capturer (à faire pendant, pas après)

Dans `../3-Evidence/`, convention de nommage du dossier :

| Fichier | Ce qu'il doit montrer |
|---|---|
| `S4-05-evaluation-12-exigences-statuts.jpg` | L'arbre ou la table de l'évaluation, filtré sur les douze exigences, **statuts visibles** |
| `S4-05-detail-exigence-A822-non-couvert.jpg` | Une exigence en détail, statut + justification saisie, **et le nom de l'auteur** |
| `S4-05-mesures-appliquees-4-controles.jpg` | La liste des quatre mesures appliquées, avec **propriétaire et échéance** |
| `S4-05-taux-de-conformite-apres-saisie.jpg` | Le taux de conformité / le tableau de bord de l'évaluation **après** saisie — la contre-preuve du « l'import n'est pas la conformité » écrit en séance 3 |
| *(bonus F6)* `S4-05-annexeA-arbre-deplie-37-8-14-34.jpg` | Les 93 contrôles répartis 37/8/14/34 |
| *(bonus F3)* `S4-05-actifs-top5-marques.jpg` | Le Top 5 repérable dans la liste des actifs sans lire le dossier |

---

## 9. Fichiers à produire, et où ils atterrissent

| Fichier | Rôle | Statut |
|---|---|---|
| `../4-Working-notes/Seance-4-TD-S4-03-gradation-des-constats.md` | TD 2 — les 8 constats gradués, 2 gradations discutées | ☐ **préalable, à faire en premier** |
| `Seance-4-TP-S4-05-feuille-de-travail-auto-evaluation.md` | **La feuille de travail** : cadrage · mapping des statuts · 12 lignes justifiées · 4 mesures SMART · synthèse par thème · maturité · biais · écarts · angles morts | ☐ à écrire pendant le TP |
| `../3-Evidence/S4-05-*.jpg` | Les captures ci-dessus | ☐ pendant, pas après |
| `D4-rapport-d-audit-initial.md` | **Le livrable D4 (4 pts)** — écrit au **TP 2**, six sections imposées | ☐ séance suivante |
| `../../../Piece-1-Strategy-note/MERIDIAN-strategy-note.md` | 4ᵉ sous-section « État des lieux », ½ page, qui **ne recopie rien** du rapport | ☐ séance suivante |
| `README.md` de `2-Labs/` | Dire lequel des fichiers est le livrable noté | ☐ à créer quand D4 existe |

---

## 10. Les pièges de ce TP

1. **Recréer au lieu de remplir.** Critère de validation explicite : aucun objet des séances 2 et 3 recréé ou renommé. Y compris le nom de l'évaluation, même s'il diffère du libellé de l'énoncé.
2. **Douze « couvert » déclaratifs.** *Au moins un « non évalué » assumé vaut mieux que douze « couvert » déclaratifs.* Si la grille n'en contient aucun, elle est relue avec la question de l'encadré.
3. **Confondre statut et gravité.** Aujourd'hui on évalue **contre le critère**. Le poids en risque — gravité, vraisemblance — est le travail de la **séance 5**. Aucun chiffre de risque ne doit apparaître, ni ici ni dans D4.
4. **Confondre correction et action corrective.** Deux mesures par constat, jamais deux fois la même.
5. **Perdre C7.** Le seul point conforme du groupe est chez nous, sur un flux à l'arrêt. Il se dit — et il se dit avec sa limite.
6. **Regrader au moment d'écrire.** Le TP 2 l'interdit : aucune gradation ne change entre le TD et le rapport **sans justification écrite**. Donc le TD 2 se fait sérieusement, une fois.
7. **Oublier le compte nominatif.** Douze statuts et quatre mesures saisis sous `admin@lockbay.eu` ne prouvent la contribution de personne.

---

## 11. Minutage (85 min de TP)

| | Exercice | Durée | Où |
|---|---|---|---|
| **0** | Gradation TD 2 *(préalable)* | 20 min | hors ligne |
| 1 | Cadrage | 10 min | feuille |
| 2 | Douze exigences | **35 min** | **outil** + feuille |
| 3 | Quatre mesures appliquées | 15 min | **outil** |
| 4 | Synthèse et maturité | 15 min | feuille |
| 5 | Extraction pour le rapport | 10 min | feuille |

---

## 12. Auto-contrôle avant d'appeler l'instructeur

- ☐ Les **douze** exigences portent un statut **dans l'outil**
- ☐ **Chaque ligne** de la feuille porte une justification — preuve nommée, constat cité, ou aveu
- ☐ Les constats Logistique gradués à midi (**C3, C4, C7**) apparaissent dans les statuts
- ☐ **Au moins un « non évalué »** assumé
- ☐ **Quatre** mesures appliquées, deux par constat, rattachées à leur exigence, avec propriétaire **et** échéance, toutes passant le test SMART
- ☐ La synthèse par thème est comptée, la maturité tient en deux phrases, le biais est nommé
- ☐ Les deux listes de l'exercice 5 sont écrites et complètes
- ☐ **Aucun objet des séances 2 et 3 recréé ou renommé**
- ☐ Tout a été saisi sous un **compte nominatif**
- ☐ Les captures sont dans `../3-Evidence/`

---

*Plan établi le 8 septembre 2026 · remise du dossier : 17 septembre 2026 · barème D4 : 4 points sur 40.*
