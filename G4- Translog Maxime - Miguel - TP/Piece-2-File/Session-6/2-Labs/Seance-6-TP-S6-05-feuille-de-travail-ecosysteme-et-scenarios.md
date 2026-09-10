# Feuille de travail — Séance 6, TP 1 : écosystème et scénarios (atelier 3 + amorce de l'atelier 4)

**Rédigée pendant la saisie**, conformément à la règle du plan. Compte utilisé : **Miguel Monereo**
(`miguel.monereodelasota@...`), nominatif. Répartition non appliquée telle que proposée par le plan (un
seul compte disponible dans cette session) : Miguel a saisi l'intégralité — parties prenantes, cotation,
scénarios stratégiques et opérationnel — et le a relit en fin de séance.

---

## 1. Exercice 1 — Vérification de la reprise

| # | Vérifié à l'écran | Conforme |
|---|---|---|
| 1a | Domaine = `MERIDIAN-LOGISTIQUE` | ✅ |
| 1b | Matrice `4x4 risk matrix from EBIOS-RM`, méthode `Manual` (constatée dans la liste des études avant ouverture) | ✅ |
| 1d | `Assets` = 17 | ✅ |
| 1e | `Audits` = 1 | ✅ |
| 1f | `Feared events` = **7**, tous Selected | ✅ — écart avec l'énoncé (qui annonce six) **confirmé et non corrigé**, cf. §0 du plan : ER7 a été ajouté au TP 2 de la séance 5, D5 fait foi |
| 1g | `RO/TO couples` = 5, Selected sur n°1, 3, 4 | ✅ |
| 1h | Ateliers 3, 4, 5 vides avant saisie | ✅ |

**Capture** : `S6-05-ex1-etude-reprise-compteurs.jpg`.

---

## 2. Exercice 2 — Écosystème : le point de friction anticipé, confirmé

**La fiche *Add stakeholder* exige un champ `Entity`, désactivé quand aucune entité n'existe encore dans le
domaine.** Message affiché : *« This input is disabled »*. Geste appliqué, conforme à la contingence écrite
dans le plan : création de **5 objets `Entity`** dans `Third Parties → Entities`, domaine
`MERIDIAN-LOGISTIQUE`, chacun avec sa description collée depuis le pack et son `Relationship` (le même
référentiel de catégories que le champ `Category` du stakeholder). Une fois les 5 entités créées, le champ
`Entity` de la fiche stakeholder s'est rempli normalement (liste déroulante de recherche).

**Catégories réellement proposées par l'outil** (relevées à l'écran, aucune inventée) :
`Accreditation authority`, `Client`, `Contractor`, `Other`, `Partner`, `Regulatory authority`, `Supplier`.
Correspondance retenue : PP1 et PP2 → `Supplier` ; PP3 et PP5 → `Partner` ; PP4 → `Client`. Le plan proposait
« Prestataire / partenaire » pour PP3 : l'outil n'offre pas de catégorie composée, `Partner` a été retenu
(PP3 n'a aucun accès logique, la relation est celle d'un partenaire opérationnel plutôt que d'un prestataire
contractant).

**Aucun acteur interne saisi** (Responsable Exploitation, DSI, chefs d'entrepôt) : ce sont des biens supports
de D2, pas des parties prenantes de l'écosystème — règle du plan appliquée sans écart.

**Capture** : `S6-05-ex2-5-parties-prenantes-liste.jpg`.

---

## 3. Exercice 3 — Cotation : criticités lues, un écart d'arrondi relevé et conservé

Le formulaire de l'atelier 3 regroupe en une seule fiche l'exercice 2 (Entity, Category) **et** l'exercice 3
(les quatre notes, la case Selected, la Justification) : gain de temps non anticipé par le plan, noté ici.

| Partie prenante | D · P · M · T | Criticité lue | Attendue (plan) | Écart |
|---|:--:|:--:|:--:|---|
| PP2 · Intégrateur | 3 · 4 · 1 · 1 | **12** | 12,0 | aucun |
| PP1 · APPLICA | 4 · 4 · 1 · 2 | **8** | 8,0 | aucun |
| PP5 · MERIDIAN Santé | 2 · 3 · 2 · 3 | **1** | 1,0 | aucun |
| PP3 · Opérateur des liaisons | 3 · 1 · 2 · 3 | **0,5** | 0,5 | aucun |
| PP4 · Client pharmaceutique | 2 · 2 · 3 · 3 | **0,44** | 0,4 | **arrondi affiché à deux décimales** (4/9 = 0,444…), pas d'arrondi à une décimale comme supposé par le plan |

**L'écart PP4 est la première des trois causes anticipées par le plan** (§3, « l'échelle ou l'arrondi
d'affichage ») : l'outil affiche la valeur exacte du quotient, sans arrondi à une décimale. **Le
classement n'est pas affecté** : PP2 puis PP1, très loin devant PP5, PP3, PP4 — la conclusion du TD 2 tient.
Notes non modifiées pour faire coller l'affichage à 0,4.

**Seuil ≥ 4,0 appliqué** : `Selected` coché sur PP1 et PP2 uniquement, conforme au plan. Valeurs résiduelles
laissées identiques aux valeurs courantes (l'outil ne les distingue pas tant qu'elles ne sont pas
explicitement modifiées) — aucune mesure de traitement n'existe encore, rien n'a été saisi pour « faire
propre ».

**Captures** : `S6-05-ex3-PP1-applica-4-notes-criticite.jpg`, `S6-05-ex3-PP2-integrateur-4-notes-criticite.jpg`,
`S6-05-ex3-carte-dangerosite-classement.jpg`.

---

## 4. Exercice 4 — Scénarios stratégiques et chemins d'attaque

**SS1** (couple n°1, `Organized crime`) rattaché à **ER1** via le champ *Focused feared event* — gravité
**`Critical`** affichée automatiquement, jamais ressaisie. Deux chemins d'attaque créés et rattachés chacun à
une partie prenante critique : `AP.01` (APPLICA) et `AP.02` (l'intégrateur, résolution du couple n°2 mis en
réserve à la séance 5 — la phrase de traçabilité a été écrite dans la description du chemin, comme prévu).

**SS2** (couple n°4, `Competitor`) rattaché à **ER4** — gravité **`Important`**. **Point de friction
confirmé** : le champ *Focused feared event* n'accepte **qu'un seul** événement redouté (liste déroulante à
sélection unique, pas de multi-sélection). ER6 n'a donc **pas** pu être rattaché en objet : il reste écrit
dans la description du scénario et dans celle du chemin d'attaque, exactement comme le plan l'anticipait en
alternative. Un seul chemin créé (`AP.01`), rattaché à APPLICA — le seul chemin exigé par le critère de
l'énoncé (« au moins un chemin par scénario, relié à une partie prenante critique »).

Couple n°3 (`Avenger`) **non traité** : son chemin ne passe pas par l'écosystème (initié de l'Exploitation),
conforme à la règle de méthode écrite dans le plan — geste à documenter en séance 7.

**Captures** : `S6-05-ex4-SS1-detail-chemins.jpg`, `S6-05-ex4-SS2-detail-chemin.jpg`,
`S6-05-ex4-scenarios-strategiques-liste-gravite.jpg`.

---

## 5. Exercice 5 — Scénario opérationnel : deux champs de vraisemblance, tous deux à régler

**Structure de l'atelier 4, non anticipée dans le détail par le plan** : un *Operational scenario* se crée
d'abord au niveau du chemin d'attaque (`Add operational scenario`, atelier 4 étape 1), avec un résumé des
modes opératoires (*Operating modes summary*) et une justification. **La vraisemblance ne s'y règle pas
directement** : il faut ensuite ouvrir la fiche créée et ajouter au moins un **`Operating mode`**
(sous-objet, atelier 4 également), qui porte son propre champ `Likelihood`. Constat supplémentaire : la
fiche du scénario opérationnel porte **elle aussi** un champ `Likelihood` séparé (accessible par `Edit`,
« Step 2 »), non déduit automatiquement de l'`Operating mode` — l'outil ne les synchronise pas. **Les deux
ont été réglés manuellement à `Very likely`** pour que le triptyque `Likelihood × Severity = Risk level`
s'affiche correctement (`Very likely × Critical = High`).

Échelle de l'outil relevée : `Unlikely`, `Likely`, `Very likely`, `Certain` — correspondance directe avec
V1-V4 de D5, aucune conversion nécessaire.

Rattaché au chemin `AP.01` de SS1 (le plus préoccupant), avec la kill chain en sept actions élémentaires sur
les biens supports nommés, et la justification V3 reprise du TD 2 (le socle et ses limites, le *pourquoi pas
V4* sur l'arrêt du WMS d'avril).

**Méthode `Manual` confirmée en usage** : aucune valeur n'a été recalculée ou écrasée par l'outil après
saisie.

**Captures** : `S6-05-ex5-scenario-operationnel-detail.jpg`, `S6-05-ex5-atelier4-liste-vraisemblance.jpg`.

---

## 6. Ce qui reste volontairement vide

- **Atelier 5** : aucun objet, aucune mesure de traitement. Capture `S6-05-atelier5-vide-et-compteurs.jpg`.
- **Couple SR/OV n°3** : sans scénario stratégique (méthode, cf. §4).
- **Valeurs résiduelles des parties prenantes** : identiques aux valeurs courantes, aucun traitement engagé.
- **Deuxième scénario opérationnel** (chemin `AP.02` de SS1, chemin de SS2) : la règle « un scénario
  opérationnel par chemin retenu » sera honorée en séance 7 ; un seul amorce l'atelier 4 aujourd'hui,
  conformément à l'énoncé.

---

## 7. Compteurs finaux de l'étude (Summary, après saisie)

| Compteur | Valeur |
|---|---|
| Assets | 17 |
| Feared events | 7 |
| Audits | 1 |
| RO/TO couples | 5 |
| **Stakeholders** | **5** créés, **2 `Selected`** (compteur du Summary = parties prenantes retenues) |
| **Strategic scenarios** | **2** |
| **Operational scenarios** | **1** |
| Applied controls (compliance) | 4 (hérités de l'audit — non touchés aujourd'hui) |

---

## 8. Geste en attente, non traité aujourd'hui

`S5-06-rapport-etude-EBIOS-RM-ateliers-1-2.jpg`, cité par D5, reste absent de `Session-5/3-Evidence/`. Non
régénéré pendant cette séance faute de temps ; à trancher (produire la capture ou corriger la mention dans
D5) avant l'export de séance 10.
