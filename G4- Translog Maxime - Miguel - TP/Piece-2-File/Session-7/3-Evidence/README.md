# Preuves d'instance — séance 7

**État : TP 1 fait, dix captures produites.** Le TP 2 (D7, coûts, plan d'action) reste à faire.

## Les captures

Nommage repris des séances 4 à 6 : `S7-05-…` pour le TP 1, `S7-06-…` pour le TP 2 (à venir).

| Capture | Ce qu'elle montre | Pièce qu'elle appuie | État |
|---|---|---|---|
| `S7-05-ex0-etude-compteurs-avant-saisie.jpg` | Les compteurs du *Summary* avant saisie — rien n'a été recréé | TP 1 prérequis | ✅ |
| `S7-05-ex1-scenarios-operationnels-liste.jpg` | Les trois scénarios opérationnels (OS1 existant, OS2 et OS3 créés), chacun rattaché à son chemin d'attaque | TP 1 étape 1 | ✅ |
| `S7-05-ex1-OS2-detail-kill-chain.jpg` | Le détail d'OS2 : l'enchaînement d'actions élémentaires, chaque étape nommant un bien support ou signalant son absence | TP 1 étape 1 | ✅ |
| `S7-05-ex2-OS2-vraisemblance-justifiee.jpg` | La vraisemblance d'OS2 (`Very likely`) avec sa justification | TP 1 étape 2 | ✅ |
| `S7-05-ex2-OS3-vraisemblance-justifiee.jpg` | La vraisemblance d'OS3 (`Likely`) avec sa justification | TP 1 étape 2 | ✅ |
| `S7-05-ex3-registre-genere.jpg` | Le registre à 8 lignes (6 générées par l'outil + ER2 et ER6 créés à la main — voir note d'écart) | TP 1 étape 3 | ✅ |
| `S7-05-ex3-registre-options-porteurs-echeances.jpg` | Chaque ligne avec son option de traitement et ses mesures appliquées — aucune ligne sans décision | TP 1 étape 3 · exigence 1 de D7 | ✅ |
| `S7-05-ex3-controle-qualite-au-vert.jpg` | Le contrôle qualité (page `X-rays`) : le bucket rouge (résiduel non coté) a disparu | TP 1 étape 3 | ✅ |
| `S7-05-ex4-residuels-cotes.jpg` | Le résiduel coté pour les 8 lignes, cohérent avec le niveau actuel | TP 1 étape 4 · exigence 4 de D7 | ✅ |
| `S7-05-ex4-refus-outil-residuel-superieur.jpg` | Tentative d'un résiduel supérieur à l'actuel sur ER3 : **acceptée sans blocage** par l'outil (`successfully updated`) — écart avec l'énoncé, voir la note d'écart | note d'écart | ✅ |
| `S7-06-mesures-appliquees-couts-build-run.*` | La section *Coût* d'une mesure appliquée : coût fixe, jours-personnes, durée d'amortissement, build et run | TP 2 étape 1 | 🔴 à faire |
| `S7-06-plan-d-action-apercu-budgetaire.*` | L'onglet *Plan d'action* et son **aperçu budgétaire** — le total annuel du plan, mis en face de la fourchette du coût de l'inaction | TP 2 étape 1 | 🔴 à faire |
| `S7-06-rapport-etude-EBIOS-RM-ateliers-4-5.*` | Le rapport de l'étude exporté, ateliers 4 et 5 compris | D7 | 🔴 à faire |

Détail de ce que chaque capture appuie : `../2-Labs/Seance-7-TP-S7-05-feuille-de-travail-atelier4-et-registre.md`.

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

**Exécuté pour le TP 1** : aucune empreinte dupliquée sur les 10 captures `S7-05-…`.
