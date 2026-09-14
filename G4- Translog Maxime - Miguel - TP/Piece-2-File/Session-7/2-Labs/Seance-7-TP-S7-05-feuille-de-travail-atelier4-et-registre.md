# FEUILLE DE TRAVAIL — Séance 7, TP 1 : atelier 4 détaillé et registre de risques dans CISO Assistant

**Ce fichier n'est pas le mode opératoire** (`PLAN-Seance-7-TP-S7-05-atelier4-et-registre.md`) : il enregistre **ce que la saisie a réellement produit** dans `translog-b`, écart par écart avec ce qui était prévu.

**Instance** `https://translog-b.lockbay.eu` · **Domaine** `MERIDIAN-LOGISTIQUE` · **Registre** `Registre de risques MERIDIAN Logistique - cycle 1 - 1.0`
**Étude** `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1`

---

## 0. Compteurs avant saisie

Vérifiés à l'écran avant tout clic (capture `S7-05-ex0-etude-compteurs-avant-saisie.jpg`) — conformes à l'attendu du plan : rien n'a été recréé, l'étude ouverte en séance 5 et enrichie en séance 6 sert de support.

---

## 1. Scénarios opérationnels — ce qui a été saisi

Les deux scénarios opérationnels manquants ont été créés depuis leurs chemins d'attaque respectifs, exactement comme prévu :

| Scénario opérationnel | ID dans l'outil | Chemin | Partie prenante | Événement redouté |
|---|---|---|---|---|
| **OS1** *(existait déjà, séance 6)* | `AP.01` de SS1 | Chemin 1 — APPLICA | APPLICA Services (8,0) | ER1 (`Critical`) |
| **OS2** | `AP.02` de SS1 | Chemin 2 — intégrateur des automates | Intégrateur des automates (12,0) | ER1 (`Critical`) |
| **OS3** | `AP.01` de SS2 | Chemin unique — APPLICA | APPLICA Services (8,0) | ER4 (`Important`) |

Kill chains saisies en sept maillons chacune, chaque étape nommant un bien support de l'inventaire (ou signalant son absence — voir §5), conformément au format du mode opératoire. Captures : `S7-05-ex1-scenarios-operationnels-liste.jpg`, `S7-05-ex1-OS2-detail-kill-chain.jpg`.

---

## 2. Vraisemblances saisies

| Scénario | Vraisemblance saisie | Niveau affiché | Conforme au plan ? |
|---|---|---|---|
| OS1 | `Very likely` | `High` | ✅ (vérifié, non ressaisi) |
| OS2 | `Very likely` | `High` | ✅ |
| OS3 | `Likely` | `Medium` | ✅ |

Justifications saisies dans le champ *Justification* de chaque scénario, citant les signaux vérifiables prévus (constat d'audit séance 4, cotation atelier 3 de la partie prenante traversée). Captures : `S7-05-ex2-OS2-vraisemblance-justifiee.jpg`, `S7-05-ex2-OS3-vraisemblance-justifiee.jpg`.

---

## 3. Le registre — écart n°1, majeur

**L'activité 1 de l'atelier 5, lancée une seule fois, n'a produit que 6 lignes, pas 8.**

Le générateur a ajouté ER3, ER5 et ER7 (événements redoutés sans scénario stratégique), mais **pas ER2 ni ER6**. Cause identifiée : ER2 et ER6 figurent tous deux dans la liste *Feared events* d'un scénario stratégique (ER2 dans celle de SS1, ER6 dans celle de SS2), sans en être le *Focused feared event* — l'outil les considère donc déjà couverts par la ligne du scénario opérationnel correspondant. Ils ne le sont pas **au sens de la décision** : la gravité portée par les lignes `AP.01`/`AP.02` est celle de l'événement focalisé (ER1 `Critical`, ER4 `Important`), et ni ER2 (`Important`, Integrity) ni ER6 (`Significant`, Confidentiality) n'auraient alors porté d'option, de porteur ni d'échéance propres.

**Décision prise** : conformément à l'exigence 1 de D7 (*aucun risque du registre sans décision*), ER2 et ER6 ont été **créés explicitement** comme scénarios de risque dans le registre, avec leurs biens supports repris de la fiche de l'événement redouté correspondant (ER2 → `Exécution des flux logistiques` + biens supports du compte de service ; ER6 → `Maintien de la chaîne du froid`) et une origine de risque cohérente (ER2 : `Avenger`, couple SR/OV n°3, sans scénario stratégique mais dont le risque est porté ici et dans ER7 ; ER6 : `Competitor`, cohérent avec SS2). **8 lignes au total**, conforme au chiffre attendu par le plan une fois la correction appliquée.

Capture : `S7-05-ex3-registre-genere.jpg`.

### Les 8 lignes, options, mesures, porteurs

| Ligne | Décision | Actuel | Mesures appliquées |
|---|---|---|---|
| OS1 (`AP.01`/SS1) | Mitigated | `Very likely × Critical` = `High` | PT-01 (validation préalable des MAJ), PT-02 (comptes nommés + MFA TMA), PT-03 (segmentation IT/OT), PT-04 (test de restauration + RTO) |
| OS3 (`AP.01`/SS2) | Mitigated | `Likely × Important` = `Medium` | PT-08 (clause de maîtrise de la sous-traitance), PT-02 *(commune à OS1)* |
| OS2 (`AP.02`/SS1) | Mitigated | `Very likely × Critical` = `High` | PT-05 (liaison 4G raccordée/supprimée), PT-06 (exigences contractuelles intégrateur), PT-03 *(commune à OS1)*, PT-07 (raccordement SOC) |
| ER2 | Mitigated | `Very likely × Important` = `High` | PT-09 (rotation du secret `LOG-SA-04`) |
| ER3 | Accepted (formalisé) | `Likely × Critical` = `Medium` | PT-10 (tolérance : journal des accès + réponse questionnaire fournisseur) |
| ER5 | Mitigated | `Certain × Critical` = `High` | PT-11 (projet de reprise sécurisée, jalons M1-M6 de D6) |
| ER6 | Accepted (formalisé) | `Likely × Significant` = `Low` | *(aucune, acceptable en l'état)* |
| ER7 | Mitigated | `Very likely × Important` = `High` | PT-12 (formaliser par écrit l'organisation des six entrepôts) |

**Porteurs et échéances** : voir §5 (écart — champ `Assigned to` inutilisable pour les rôles du pack §3). Toutes les mesures portent une échéance (`ETA`) déjà saisie lors de leur création. Capture : `S7-05-ex3-registre-options-porteurs-echeances.jpg`.

### Contrôle qualité de l'outil

Fonction retrouvée sous **`X-rays` → onglet `Risk assessments`** (pas sous un bouton « Quality check » du registre lui-même — écart de libellé, voir §5).

**Avant les résiduels** : 1 type de problème au rouge, 8 constats — *« Residual risk level has not been assessed »*, un par ligne.
**Après la saisie des résiduels (§4)** : le bucket rouge a **disparu**. Restent deux types de problèmes non bloquants, sans lien avec les exigences de ce TP :
- jaune (14 constats) — *« Does not have an estimated effort »* sur les mesures appliquées (matière du TP 2, section *Coût*) ;
- bleu/info (15 constats) — *« Applied control does not have an external link attached »*.

Le contrôle qualité est donc **passé au vert** au sens de l'exigence 1 de D7 (aucun scénario sans décision, aucun résiduel non coté) ; les deux buckets restants relèvent de l'enrichissement TP 2, pas de ce TP. Capture : `S7-05-ex3-controle-qualite-au-vert.jpg`.

---

## 4. Risques résiduels

Cotés **après** la décision, jamais avant, conformément à la règle. Résultat conforme, ligne pour ligne, à ce que le mode opératoire visait :

| Ligne | Actuel | Résiduel | Mécanisme |
|---|---|---|---|
| OS1 | `High` (V3×G4) | **`Medium`** (V2×G4) | Vraisemblance abaissée (résistance ajoutée sur le chemin) |
| OS2 | `High` (V3×G4) | **`Medium`** (V2×G4) | Vraisemblance abaissée |
| OS3 | `Medium` (V2×G3) | **`Low`** (V1×G3) | Vraisemblance abaissée (MFA ferme l'accès partagé) |
| ER2 | `High` (V3×G3) | **`Medium`** (V2×G3) | Vraisemblance abaissée (rotation du secret) |
| ER3 | `Medium` (V2×G4) | **`Medium`** (V2×G4, inchangé) | Mesure compensatoire (surveillance), pas structurelle — niveau inchangé, conforme à la règle D7 |
| ER5 | `High` (V4×G4) | **`Medium`** (V2×G4) | Vraisemblance abaissée (projet en cours, jalons M1-M6) |
| ER6 | `Low` (V2×G2) | **`Low`** (V2×G2, inchangé) | Aucune mesure — acceptation, niveau inchangé |
| ER7 | `High` (V3×G3) | **`Medium`** (V3×G2) | **Gravité** abaissée, pas la vraisemblance — seul cas du registre où la mesure agit sur l'autre axe (le savoir écrit survit au départ de la personne) |

**Confrontation à la ligne d'acceptation** : aucun résiduel ne reste `High`. **Six lignes ressortent `Medium`** (OS1, OS2, ER2, ER3, ER5, ER7) — exactement le nombre anticipé par le plan — et appellent chacune une fiche d'acceptation formalisée en D7 (D5 : `Medium` tolérable uniquement formalisé, sinon traité comme `High`). **Aucune dérogation à demander** : toutes les réductions engagées abaissent d'au moins un cran, aucune ligne ne reste au-dessus de la ligne d'acceptation. Capture : `S7-05-ex4-residuels-cotes.jpg`.

### Le test du refus — écart n°2, majeur

Le mode opératoire, reprenant l'énoncé, annonçait : *« l'outil refuse un résiduel supérieur au niveau actuel »*. **Ce n'est pas ce qui a été observé.**

Test effectué sur ER3 : résiduel actuel `Medium` (V2×G4) remplacé délibérément par `Certain × Critical` = `High` (supérieur au niveau actuel), puis **Save**. Résultat : **« The risk scenario object has been successfully updated »** — aucun blocage, aucun avertissement, l'enregistrement a réussi. La valeur a ensuite été corrigée à sa valeur correcte (`Medium`, inchangé) et resauvegardée.

**Conclusion à retenir** : dans cette instance, la cohérence *résiduel ≤ actuel* et *pas de mesure ⇒ pas de baisse de niveau* est une **discipline de méthode à appliquer par la personne qui saisit**, pas une contrainte technique imposée par l'outil. C'est un écart entre ce que décrit l'énoncé du TP et le comportement observé de la version déployée — et c'est exactement le genre de découverte que la note d'écart doit porter. Capture : `S7-05-ex4-refus-outil-residuel-superieur.jpg`.

---

## 5. Note d'écart complète

### Trous de cartographie (biens supports absents de l'inventaire — non créés dans `Assets`)

| Bien support traversé | Où il apparaît | Traitement |
|---|---|---|
| **Liaison 4G de l'intégrateur des automates** | Maillon 3 d'OS2 — vecteur d'entrée du scénario | Absente de l'inventaire de la séance 2 ; couverte au registre par la mesure **PT-05** (raccorder/supprimer la liaison) et par **PT-13** (inventorier et rattacher à un propriétaire les deux biens supports découverts à l'atelier 4) |
| **Liaisons opérateur E1 ↔ E2-E6** | Maillon 5 d'OS2, propagation d'OS1 | Idem — couverte par **PT-13** |

### Libellés d'écran divergents

- Le **contrôle qualité** de l'outil n'est pas un bouton du registre ni de l'étude EBIOS RM : c'est la page **`X-rays`**, menu `Operations`, onglet `Risk assessments`.
- Les **statuts de traitement** réels de l'outil sont `Open / Mitigated / Accepted / Avoided / Transfered / Cancelled` — à comparer aux quatre familles du TD 2 (réduire / accepter / éviter / transférer). Correspondance retenue : réduire → `Mitigated`, accepter → `Accepted`, éviter → `Avoided`, transférer → `Transfered`. **`Transfered` est une faute d'orthographe de l'outil** (un seul « r »), pas une saisie de notre part.
- Le champ *Current impact* / *Residual impact* du formulaire de scénario s'affiche bien en anglais (`Minor / Significant / Important / Critical`), identique aux niveaux de D5 — aucun écart de fond ici, mais la page confirme que les échelles sont reprises mot pour mot, pas réinventées.

### Champs sans équivalent dans l'outil

- **`Assigned to`** (porteur) n'accepte que des **comptes de l'instance** — les rôles du pack §3 (Directeur de la filiale, Responsable Informatique/DSI, Responsable Exploitation, RSSI Groupe, Responsable Qualité, Direction Générale) n'y sont pas nommables directement. Ils ont donc été **nommés en texte libre dans le champ Justification** de chaque scénario, avec leur périmètre de décision — la correspondance porteur ↔ scénario vivra formellement dans **D7**.
- Aucun champ pour l'**instance signataire** d'une acceptation, ni pour sa **date de réexamen** — ces deux éléments, prévus par le TD 2 pour chaque acceptation formelle, vivent également dans **D7**, comme les descriptions d'échelles vivent dans D5. Ils ont néanmoins été consignés en texte dans la Justification d'ER3 et ER6 (signataire Direction Générale du groupe, D1/D5 §1 ; échéance de réexamen précisée).
- Le champ **`Risk tolerance`** de l'étude ne porte qu'un **niveau** (`Low` acceptable en l'état, `Medium` tolérable) et ne sait pas exprimer la **condition de formalisation** que D5 attache à `Medium` (tolérance datée, surveillée, propriétaire nommé, mesure compensatoire). Cette condition est donc reportée dans la description du registre et dans D7, pas dans un champ dédié.

### Nombre de lignes du registre

**6 générées, 8 attendues, 8 obtenues après création manuelle d'ER2 et ER6** — voir §3.

### Le refus de l'outil sur un résiduel supérieur

**Ne se produit pas** dans cette instance — voir §4, « Le test du refus ». Écart avec l'énoncé du TP.

---

## 6. Ce qui n'a pas été fait ici, et pourquoi

Conforme au mode opératoire :
- Le plan de traitement organisé **par décision** et les fiches d'acceptation formelles (ER3, ER6, et les six lignes `Medium`) : **TP 2, livrable D7**.
- La saisie des coûts *build*/*run* sur les mesures appliquées : **TP 2**, section *Coût* de chaque mesure.
- Le couple SR/OV n°3 (`Avenger`) reste sans scénario stratégique (choix de méthode de la séance 6, reconduit) ; ses deux événements redoutés ER2 et ER7 sont bien au registre.

---

## 7. Répartition et relecture croisée

Saisie effectuée avec le compte nominatif de l'instance (`miguel.monereodelasota@ynov.com`), conformément à la consigne — jamais `admin@lockbay.eu`.

---

## 8. Ce qui sort de ce TP

Vers **TP 2 / D7** : le registre à 8 lignes complet (décision, mesures, porteur en texte, échéance, résiduel coté), les six fiches d'acceptation à rédiger pour les lignes `Medium`, la phrase qui explique l'absence de dérogation, et la mesure `PT-13` (inventaire des deux biens supports découverts). Vers la sous-section 7 de la note de stratégie : le constat qu'aucun traitement ne referme un risque — tous passent de `High`/`Medium` à `Medium`/`Low`, jamais à zéro — et le cas ER5 (le risque le plus certain du portefeuille est celui que personne n'attaque, traité par un projet et non par une mesure technique).
