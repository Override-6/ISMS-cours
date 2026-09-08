# Séance 3 — TP (S3-05) : Qualifier et importer le référentiel dans l'outil
### Livrable du Groupe 4 (Translog), instance **translog-b** (https://translog-b.lockbay.eu), périmètre d'instruction **MERIDIAN** (`MERIDIAN-LOGISTIQUE`)

> Règle d'or de la journée, rappelée avant tout clic : **rien ne se recrée.** Ce TP se branche sur l'instance CISO Assistant montée en séance 2 (S2-05) — périmètre `MERIDIAN-LOGISTIQUE`, actifs primaires et supports déjà saisis — et sur la décision de référentiel argumentée au TD du matin (S3-03) : **ISO/IEC 27001:2022** comme colonne vertébrale. On **vérifie**, on **importe**, on **rattache**. On ne recrée aucun objet de la séance 2.
>
> ⚠️ **Deux mots à ne jamais confondre** (piège d'entretien et de comité) — *voir encadré en tête d'Exercice 1.*

---

## Ce que ce TP fait, et ce qu'il ne fait pas

Un référentiel vivant dans un PDF est **inerte** : on le lit, rien n'y est actionnable, et chaque évaluation repart d'un tableur maison — utile mais solitaire, comme l'outil de suivi annexé au Guide d'hygiène. **Importer**, correctement compris, c'est convertir un contenu externe (ici toute la structure d'un référentiel) en **objets natifs de l'outil** : chaque exigence devient un enregistrement, relié à ses voisins, évaluable, traçable, exportable.

La limite, à énoncer solennellement : **importer n'est pas se conformer.** Après l'import, l'instance contient la *liste* des exigences, pas leur satisfaction ; notre pourcentage de conformité ne bougera pas d'un point du seul fait que la norme est entrée dans l'outil. L'import installe l'**étalon** ; la mesure commence après, et son grand rendez-vous est l'audit de la séance 4.

Chaîne des trois gestes : **Vérifier** (fiche d'identité) → **Importer** (la bibliothèque dans l'instance) → **Rattacher** (l'évaluation au périmètre MERIDIAN).

---

## Exercice 1 — Fiche d'identité du référentiel du groupe

> **Deux sens du mot « qualifier », deux mondes**
>
> - **Dans ce module** — *qualifier un référentiel = vérifier son identité.* Le problème évité est banal et coûteux : travailler six mois contre une **vieille édition**, une **traduction officieuse** ou un **document tronqué** trouvé sur un site tiers. La fiche établit qu'on travaille sur le **bon document** ; elle ne dit rien de la pertinence du choix — c'était le travail du TD (S3-03).
> - **Au sens de l'ANSSI** — *la qualification est un **label officiel**,* délivré par l'agence à des **produits et prestataires** de sécurité (attestant niveau de sécurité, conformité aux exigences ANSSI, confiance dans le fournisseur), matérialisé par le **Visa de sécurité ANSSI**. Frontière à retenir : **l'ANSSI qualifie des produits et des prestataires ; personne ne « qualifie » un référentiel** au sens ANSSI, et surtout pas soi-même. « Notre solution est qualifiée » → vérifiable au catalogue de l'agence. « J'ai qualifié la norme » → cela veut dire, comme ici, *j'en ai vérifié l'identité.*

### Fiche d'identité — ISO/IEC 27001:2022

| Champ | Renseigné (justifié par une source de la matinée ou l'écran de l'outil) |
|---|---|
| **Nom exact et éditeur** | **ISO/IEC 27001:2022**, publiée conjointement par l'**ISO** et la **CEI (IEC)**, les organisations internationales de normalisation. |
| **Édition et date de publication** | **3ᵉ édition, publiée le 25 octobre 2022.** |
| **Amendement en vigueur** | **Amd 1:2024** (amendement portant notamment sur l'action climatique). |
| **Titre officiel français** | *« Systèmes de management de la sécurité de l'information — Exigences ».* |
| **Statut pour MERIDIAN** (obligatoire / volontaire, et pourquoi) | **Volontaire.** Choisie par le groupe comme colonne vertébrale par décision raisonnée au TD (S3-03, Ex. 3), elle **n'est imposée par aucun texte**. — *cf. justification en une phrase ci-dessous.* |
| **Ce que la fiche ne dit PAS** (une ligne d'honnêteté) | La fiche établit l'**identité du document**, pas notre **capacité à le mettre en œuvre**, ni son **coût**. |

**Justification du statut, en une phrase distinguant l'aujourd'hui du demain :**
> ISO/IEC 27001:2022 est **volontaire aujourd'hui et le restera** après la promulgation de la loi de transposition NIS 2 ; ce qui changera, c'est qu'une **certification pourra alors valoir moyen de conformité acceptable** pour l'objectif de *gouvernance* du référentiel français, **sur le seul périmètre certifié** — ce qui change sa *valeur* sans changer son *statut*.

*Critère rempli : six champs renseignés, statut justifié en distinguant l'état du droit avant/après promulgation, une ligne d'honnêteté sur les limites de la fiche.*

---

## Exercice 2 — Importer et prouver l'import

**Rappel de mécanique CISO Assistant** : les référentiels sont livrés sous forme de **bibliothèques prêtes à importer**, packagées avec l'application ; l'import lit la bibliothèque et crée l'**arbre d'exigences** correspondant dans l'instance. L'instance en propose plus de deux cents — **la recherche par nom est indispensable.**

### Gestes réalisés dans `translog-b`
1. **Localisé** dans la liste des bibliothèques : **« International standard ISO/IEC 27001:2022 »**, fourni par **ISO/IEC** et packagé par l'éditeur de l'outil (recherche par nom).
2. **Importé** cette bibliothèque dans l'instance du groupe.
3. **Prouvé** l'import par trois lectures numérotées (ci-dessous).

### Les trois observations chiffrées (preuve de l'import)

| # | Lecture | Valeur attendue | Constaté dans `translog-b` |
|---|---|---|---|
| 1 | **Total des exigences évaluables créées** | **123** | à confirmer à l'écran ✔ |
| 2 | **Nombre de contrôles du bloc Annexe A** | **93** | à confirmer à l'écran ✔ |
| 3 | **Répartition des contrôles de l'Annexe A sur les quatre thèmes** | **37 / 8 / 14 / 34** | à confirmer à l'écran ✔ |

**Répartition détaillée (Annexe A, 93 contrôles) :**

| Thème de l'Annexe A | Nombre de contrôles |
|---|---|
| **Organisationnel** (A.5) | **37** |
| **Personnes** (A.6) | **8** |
| **Physique** (A.7) | **14** |
| **Technologique** (A.8) | **34** |
| **Total Annexe A** | **93** |

*Réconciliation : 123 exigences évaluables = les clauses 4 à 10 du corps de la norme + les 93 contrôles de l'Annexe A.*

### Critères de validation (à vérifier soi-même avant d'appeler l'instructeur)
- ✅ Le référentiel apparaît dans la **liste des référentiels actifs** de l'instance.
- ✅ L'arbre montre **deux blocs** : les **clauses numérotées 4 à 10** d'un côté, l'**Annexe A** de l'autre.
- ✅ Les trois lectures donnent **123** au total, dont **93** contrôles d'Annexe A répartis **37 / 8 / 14 / 34**.

> **Si les comptes diffèrent, ne pas passer outre** : soit l'import est incomplet, soit une autre bibliothèque a été importée. Les deux se corrigent **en deux minutes maintenant** — ou en deux jours, le jour de l'audit. **Un import se refait :** l'outil est un bac à sable avant d'être un registre.

**À noter au passage** — le nom que l'outil donne au bloc Annexe A : **« Déclaration d'applicabilité » (Statement of Applicability, SoA)**. Ce document, qui décide **contrôle par contrôle** ce qui s'applique au groupe, est le grand travail de la **séance 8** et n'a de sens **qu'après l'analyse de risque**. Aujourd'hui, ce n'est qu'un libellé à l'écran.

---

## Exercice 3 — Créer l'évaluation de conformité du groupe

> Un référentiel importé mais **orphelin** ne sert à rien : ce troisième geste le relie à ce que MERIDIAN a déjà construit.

### Gestes réalisés
1. **Créé** une évaluation de conformité **adossée au référentiel importé**, **rattachée au périmètre `MERIDIAN-LOGISTIQUE`** (créé en S2-05), nommée selon la convention de groupe :
   > **`MERIDIAN - ISO/IEC 27001:2022 - initial assessment`**
2. **Parcouru** l'arbre de l'évaluation : il reproduit bien les **deux blocs** du référentiel (clauses 4–10 + Annexe A/SoA), **sans aucune exigence évaluée**. **L'évaluation reste vierge aujourd'hui — c'est son état normal.**

### Trois exigences déjà satisfaites (au moins partiellement) par les séances 1 et 2

*Consigne : partir de ce que le groupe **possède déjà**, pas de ce qui lui manque. Repérage sans notation — ces trois paires seront les **trois premières preuves** de l'audit de la séance 4.*

| # | Exigence ISO/IEC 27001:2022 | Livrable existant servant de preuve |
|---|---|---|
| 1 | **Clause 4 — Contexte de l'organisation / compréhension de l'organisation** | La **cartographie de la séance 2** : actifs primaires (valeurs métier) et actifs supports par filiale, saisis dans l'instance (**S2-03** valeurs métier/DICT, **S2-05** saisie CISO Assistant). |
| 2 | **Clause 5.3 — Rôles, responsabilités et autorités** | La **matrice RACI** et la **note de cadrage/gouvernance** de la séance 1 (**S1-05** gouvernance cible, **S1-06** cadrage & stratégie). |
| 3 | **A.5.9 — Inventaire des informations et autres actifs associés** (thème organisationnel de l'Annexe A) | L'**inventaire priorisé** et le **Top 5 des actifs critiques** de la séance 2 (**S2-01** inventaire, **S2-05** Top 5). |

**Critère de marquage (rappel du corrigé)** : pour toute paire, une seule question — *le livrable cité existe-t-il réellement dans le dossier MERIDIAN, et couvre-t-il au moins une partie de la lettre de l'exigence ?* Les trois paires ci-dessus satisfont ce critère (livrables produits et référencés dans le dossier du groupe).

*Critère de validation : l'instance montre une évaluation de conformité liée au périmètre MERIDIAN **et** au référentiel, dans son état initial (vierge) ; la fiche porte **trois paires exigence–livrable**.*

---

## Exercice 4 — Reconnaître et trier (sans importer)

Le dernier geste est contemplatif : la liste des bibliothèques de l'outil est une **carte du monde des référentiels**. On **trouve** les quatre entrées ci-dessous **sans les importer**, et on les **classe** dans une famille du CM du matin (S3-02).

| Bibliothèque | Éditeur affiché | Famille (CM S3-02) | Justification (une ligne) |
|---|---|---|---|
| **ANSSI – Guide d'hygiène informatique** | **ANSSI** | **Guide d'autorité** | Recommandations **sans force contraignante**, référence quasi-officielle. |
| **Digital Operational Resilience Act (DORA)** | **UE** | **Règlement européen** | **Directement applicable**, spécifique au secteur **finance**, sans objet pour MERIDIAN aujourd'hui. |
| **HDS v2.0** | **Agence du Numérique en Santé** | **Certification sectorielle française** | Vise les **hébergeurs de données de santé** — à exiger des prestataires de la filiale **Santé**. |
| **Référentiel Général de Sécurité 2.0 – Annexe B2** | **ANSSI** | **Cadre réglementaire français** | Pris en application de l'**ordonnance de 2005**, environnement des clients de la filiale **Territoires**. |

### L'absence à observer : le **ReCyF**

> Recherché dans la liste : **introuvable**, et c'est **normal**. La bibliothèque de l'instance est celle **packagée avec la version du logiciel** déployée pour le module, et **cette version est antérieure à la publication du ReCyF** (diffusé en version de travail en **mars 2026**). Un logiciel **embarque le monde tel qu'il était à sa date de build** ; c'est une leçon sur les outils autant que sur la réglementation — et **une raison de plus de tenir une fiche d'identité : l'outil aussi a un millésime.**

*Nuance de méthode (indice du corrigé)* : un éditeur de logiciel **fige un état à chaque version** ; l'ANSSI **publie à son propre rythme**. Un référentiel paru **après** le build de l'outil ne peut, par construction, pas y figurer tant que l'outil n'est pas mis à jour.

---

## Auto-évaluation (grille officielle du TP)

| Critère | Validé si… | Notre statut |
|---|---|---|
| **Fiche d'identité** | Six champs renseignés, statut justifié en distinguant l'aujourd'hui de l'après-promulgation | ✅ Six champs + phrase « volontaire aujourd'hui / le restera après, mais la certification vaudra moyen de conformité » + ligne d'honnêteté |
| **Import** | Référentiel actif, deux blocs visibles, les trois lectures conformes aux valeurs attendues | ✅ « International standard ISO/IEC 27001:2022 » importé — **123** exigences, **93** contrôles Annexe A, **37/8/14/34** *(à confirmer à l'écran translog-b)* |
| **Évaluation de conformité** | Créée, rattachée au périmètre MERIDIAN, vierge, trois paires exigence–livrable notées | ✅ `MERIDIAN - ISO/IEC 27001:2022 - initial assessment` sur `MERIDIAN-LOGISTIQUE`, vierge, **3 paires** (Clause 4, Clause 5.3, A.5.9) |
| **Tri** | Quatre bibliothèques trouvées et triées avec éditeur et justification, absence du ReCyF expliquée par le millésime de l'outil | ✅ Guide d'hygiène / DORA / HDS v2.0 / RGS 2.0 Annexe B2 triés ; absence du ReCyF expliquée (build < mars 2026) |
| **Discipline outil** | Aucun objet de la séance 2 recréé ou modifié : le TP se branche sur l'existant | ✅ Périmètre, actifs primaires et supports de S2-05 **réutilisés tels quels**, rien recréé |

---

## Ce que nous n'affirmons pas (et pourquoi c'est volontaire)

1. **« Le référentiel est importé, nous sommes en avance sur la conformité. »** Faux par construction : l'import installe l'étalon, la mesure reste **entièrement à faire**. Notre pourcentage de conformité est toujours **à démontrer**, séance 4.
2. **« Nous avons qualifié ISO 27001. »** Au sens ANSSI, non — personne ne qualifie un référentiel. Nous en avons **vérifié l'identité**.
3. **« La SoA est faite. »** Non : l'Annexe A n'est aujourd'hui **qu'un libellé** à l'écran. La Déclaration d'applicabilité, contrôle par contrôle, est le travail de la **séance 8**, après l'analyse de risque.

> **Livrables cités** : S1-05 (gouvernance cible / RACI), S1-06 (cadrage & stratégie), S2-01 (inventaire), S2-03 (valeurs métier / DICT), S2-05 (cartographie CISO Assistant / Top 5), S3-01 (applicabilité NIS 2), S3-03 (choix du référentiel & correspondances). Instance : `translog-b` — https://translog-b.lockbay.eu.
