# Preuves d'instance — séance 7 : à produire

**État : vide, parce que le TP 1 n'a pas encore eu lieu.** Les deux TD de la séance sont rendus (matière
écrite) ; aucun objet n'a encore été créé ni modifié dans `translog-b` au titre de la séance 7. Ce dossier se
remplira pendant les TP.

## Les captures attendues

Nommage repris des séances 4 à 6 : `S7-05-…` pour le TP 1, `S7-06-…` pour le TP 2.

| Capture attendue | Ce qu'elle doit montrer | Pièce qu'elle appuie |
|---|---|---|
| `S7-05-ex1-scenarios-operationnels-liste.*` | Les scénarios opérationnels de l'atelier 4, **au moins deux**, chacun rattaché à son chemin d'attaque de la séance 6 | TP 1 étape 1 |
| `S7-05-ex1-scenario-operationnel-SS2-detail.*` | Le détail d'un scénario : l'enchaînement d'actions élémentaires, chaque étape nommant un bien support de l'inventaire de la séance 2 | TP 1 étape 1 |
| `S7-05-ex2-vraisemblances-justifiees.*` | La vraisemblance saisie par scénario opérationnel, **V1-V4 de D5**, avec sa justification | TP 1 étape 2 |
| `S7-05-ex3-registre-de-risques-genere.*` | Le registre généré depuis l'étude (atelier 5, activité 1), avec les événements redoutés sans scénario ajoutés par l'outil (ER3, ER5) | TP 1 étape 3 |
| `S7-05-ex3-registre-options-porteurs-echeances.*` | Chaque scénario avec son option de traitement, son porteur et son échéance — **aucune ligne sans décision** | TP 1 étape 3 · exigence 1 de D7 |
| `S7-05-ex3-controle-qualite-au-vert.*` | Le contrôle qualité de l'outil **passé au vert** — l'énoncé en fait une pièce du livrable | TP 1 étape 3 |
| `S7-05-ex4-residuels-cotes.*` | Le résiduel coté par scénario traité, cohérent avec le niveau actuel | TP 1 étape 4 · exigence 4 de D7 |
| `S7-05-ex4-refus-outil-residuel-superieur.*` | Le refus de l'outil sur un résiduel supérieur au niveau actuel, s'il se produit — c'est la méthode rendue visible | note d'écart |
| `S7-06-mesures-appliquees-couts-build-run.*` | La section *Coût* d'une mesure appliquée : coût fixe, jours-personnes, durée d'amortissement, build et run | TP 2 étape 1 |
| `S7-06-plan-d-action-apercu-budgetaire.*` | L'onglet *Plan d'action* et son **aperçu budgétaire** — le total annuel du plan, mis en face de la fourchette du coût de l'inaction | TP 2 étape 1 |
| `S7-06-rapport-etude-EBIOS-RM-ateliers-4-5.*` | Le rapport de l'étude exporté, ateliers 4 et 5 compris | D7 |

## La règle qui vaut depuis la séance 2

Une capture prouve **l'état d'un objet dans l'outil à une date**. Elle ne remplace pas le livrable et le
livrable ne la remplace pas : *la sous-section n de la note affirme ; la séance n du dossier prouve ; l'export
montre que l'objet existe dans l'outil.*

**Avant de capturer** : vérifier que l'objet porte un **auteur nommé**. Le coefficient individuel en dépend
pour moitié (`../../../fixes.md` F5).

**Contrôle à faire à la fin de la séance** : les captures du TP 1 de la séance 6 comportaient **deux paires
de fichiers identiques au bit près**, découvertes par un contrôle d'empreintes. Refaire ce contrôle ici :

```sh
shasum -a 256 *.jpg *.png 2>/dev/null | sort | awk '{print $1}' | uniq -d
```

Une empreinte qui sort de cette commande est un doublon à reprendre.
