# Séance 2 — TD (S2-01) : The CISO's briefing — The asset inventory
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN

---

## Rappel du cas

Mardi 9h05. En préparant la séance de cartographie, le RSSI Groupe a demandé son inventaire à chacune des 4 filiales. Trois réponses sont arrivées :

- **MERIDIAN Santé** envoie un export de son outil de gestion de parc, daté du mois dernier, **sans** les analyseurs de laboratoire ni les consoles d'imagerie.
- **MERIDIAN Logistique** répond : *« c'est dans la tête du Responsable Exploitation, il connaît ses six entrepôts par cœur »*.
- La **division Éducation & Territoires** (DSI mutualisée) envoie un tableur honnête, accompagné d'un e-mail gêné du DSI d'Éducation : en le compilant, son équipe a découvert **onze abonnements** à des services en ligne souscrits directement par les équipes pédagogiques, hors DSI — dont un outil d'IA générative utilisé par des enseignants pour faire relire des évaluations d'élèves.

**Question de gouvernance à trancher avant le comité de jeudi** : qui tient l'inventaire du groupe, sous quelles règles, et que fait-on des onze découvertes ?

Trois notions posées avant l'exercice : **inventaire d'actifs** (tenu à jour, décrit, avec un propriétaire), **actif critique** (dont l'atteinte empêcherait la mission), **Shadow IT / Shadow AI** (outils mis en service hors DSI/hors validation).

---

## Question 1 — Analyser les trois réponses reçues

*Pour chacune : ce qu'elle révèle sur la maturité de l'inventaire de la filiale, et le principal risque qu'elle laisse ouvert. Indice : les trois mots porteurs de la définition — tenu à jour, décrit, propriétaire.*

**MERIDIAN Santé — un outil, mais un périmètre tronqué.**
L'export existe, il est daté (récent, un mois), il provient d'un outil de gestion de parc : sur le papier, c'est la réponse la plus « outillée » des trois. Mais elle échoue sur le mot **« décrit »** : l'outil ne sait décrire que ce qu'il a été configuré pour voir, et les analyseurs de laboratoire et consoles d'imagerie — des équipements biomédicaux — lui échappent structurellement. Le risque ouvert n'est pas l'absence d'inventaire, c'est pire : c'est la **fausse confiance** dans un inventaire qui se croit complet alors qu'il ne l'est pas par construction. Un RSSI qui présenterait cet export en comité sans le signaler laisserait croire que le périmètre biomédical est couvert, alors qu'il ne l'a jamais été.

**MERIDIAN Logistique — pas d'inventaire, une mémoire.**
Ici c'est le mot **« tenu à jour »** qui échoue au sens le plus radical : il n'y a pas de support qui survivrait à une absence. Le Responsable Exploitation connaît réellement ses six entrepôts — ce n'est pas de l'incompétence, c'est un problème de **non-transmissibilité**. Le risque ouvert : le jour où cette personne est en congé, malade, ou quitte l'entreprise, la connaissance du système d'information part avec elle. C'est exactement ce qu'on a vu se matérialiser lors de l'arrêt du WMS en avril : personne n'a tenu de chronologie, chacun a appelé qui il pouvait, parce que la connaissance n'était nulle part ailleurs que dans une tête.

**Division Éducation & Territoires — la réponse la plus mature, malgré (ou grâce à) ses trous.**
C'est le résultat le plus contre-intuitif de l'exercice : cette réponse est **la meilleure des trois**. Elle est datée, honnête, et — point capital — elle a **découvert ses propres angles morts** en marge du travail de compilation. Un inventaire qui fait remonter onze inconnues fonctionne ; un inventaire qui n'en fait jamais remonter aucune est suspect (c'est probablement le cas de l'export de Santé). Le seul mot de la définition qui reste en jeu ici est **« propriétaire »** : rien ne dit encore qui doit porter chacun des onze services découverts — c'est tout l'enjeu des questions suivantes.

---

## Question 2 — Distinguer Shadow IT ordinaire et Shadow AI parmi les onze découvertes

*Et expliquer en quoi le second cas aggrave la question des données.*

Sur les onze services découverts, **dix relèvent du Shadow IT ordinaire** : des outils en ligne souscrits par les équipes pédagogiques hors DSI (abonnements SaaS classiques — planification, partage de fichiers, communication, etc.). Leur défaut structurel est d'être **invisibles à toute défense** : hors filtrage, hors sauvegarde, hors politique de mots de passe du groupe. Mais les données qui y transitent restent ce qu'on y a mis — le risque est un **angle mort d'infrastructure**.

**Le onzième service — l'outil d'IA générative — relève du Shadow AI**, et change de catégorie pour une raison précise et non négociable : des **évaluations d'élèves** y sont envoyées pour relecture. Ce sont des données personnelles par nature (mineurs, en plus, dans un contexte scolaire), transmises à un service tiers dont **personne n'a lu les conditions d'utilisation**, hors de tout registre de traitement RGPD.

Ce qui aggrave spécifiquement ce cas : le Shadow IT crée un trou dans l'infrastructure ; le **Shadow AI ajoute une fuite de données ORGANISÉE PAR L'USAGE LUI-MÊME**, sans qu'aucune compromission ne soit nécessaire. Chaque fois qu'un enseignant colle une copie d'élève dans l'outil, la donnée quitte le périmètre du groupe volontairement, légalement en apparence, et personne ne le sait. C'est exactement le mécanisme qu'IBM chiffre dans son rapport 2025 : une brèche sur cinq est due au Shadow AI, avec un surcoût moyen de 670 000 $ — la faille ne vient pas d'un attaquant sophistiqué, elle vient d'un outil que personne ne surveillait.

---

## Question 3 — Proposer le traitement des onze services

*Lequel documenter et régulariser, lequel superviser, lequel fermer — et selon quel critère générique (pas service par service : le critère).*

Le critère générique repose sur **deux questions posées à chaque service**, pas sur un jugement au cas par cas :

1. **Quelles données y transitent** (anodines / sensibles / personnelles ou stratégiques) ?
2. **Existe-t-il une alternative validée** répondant au même besoin métier ?

Trois issues possibles en découlent :

| Situation | Traitement |
|---|---|
| Données anodines + service utile sans équivalent interne | **Documenter et régulariser** : attacher un propriétaire, l'entrer dans l'inventaire |
| Données sensibles + besoin métier réel | **Superviser** : migrer vers un outil validé ou contractualiser avec le fournisseur, avec une échéance |
| Données personnelles ou stratégiques sur un service sans engagement contractuel possible (l'outil d'IA générative en premier) | **Fermer l'usage** — et surtout **OUVRIR une réponse au besoin**, car le besoin de relecture des enseignants, lui, ne se fermera pas |

Le point le plus important de la réponse : un traitement qui **interdirait les onze services d'un même geste** manquerait la moitié du métier — le Shadow IT renaît toujours d'une interdiction sèche qui ne répond pas au besoin métier réel. Pour Éducation, à moyens limités, cela signifie concrètement : proposer rapidement une alternative de relecture assistée validée par le groupe (ou à défaut une procédure d'anonymisation avant toute relecture externe), plutôt que de simplement couper l'accès.

---

## Question 4 — Mini-RACI de l'inventaire (3 niveaux de la séance 1)

*Qui est R, qui est A, qui est consulté, qui est informé — un seul A par ligne.*

| Niveau (séance 1) | Acteur | Rôle | Justification |
|---|---|---|---|
| **Opérationnel** | Chaque filiale (équipes IT / métier concernées) | **R** | Elle tient effectivement l'inventaire au quotidien dans l'outil commun, selon la nomenclature commune |
| **Tactique** | RSSI de filiale (ou DSI, pour la division mutualisée Éducation & Territoires) | **A** | Il/elle répond de l'exhaustivité et de la fraîcheur de l'inventaire de son périmètre — c'est la personne qui reporte |
| **Stratégique** | RSSI Groupe | **C / I** | Consulté sur les règles communes (nomenclature, outil, délais) ; informé des trous constatés ; ne redevient décideur que sur les **actifs inter-filiales** (ex. le fil rouge Logistique↔Santé), conformément à son mandat d'arbitrage posé en séance 1 |

**Erreur classique à éviter, explicitement signalée par la méthode** : faire du RSSI Groupe le **A universel** sur l'inventaire des quatre filiales. Avec des milliers d'actifs répartis sur 4 entités, un A unique au sommet n'est pas de la gouvernance, c'est un goulot d'étranglement — exactement le type de service qui a créé le blocage du dossier de gouvernance de la séance 1 (personne ne décidait, donc tout remontait, donc rien n'avançait).

---

## Question 5 — La règle de gouvernance à proposer jeudi

*Une seule phrase, applicable aux 4 filiales, couvrant à la fois la tenue de l'inventaire et le sort de ce qui n'y figure pas.*

> **« Chaque filiale tient son inventaire dans le référentiel commun du groupe, avec un propriétaire nommé pour chaque actif ; tout élément découvert en dehors de cet inventaire est rattaché à un propriétaire ou traité sous trente jours, et sa découverte est valorisée — jamais sanctionnée. »**

Cette formulation tient en trois pièces, toutes nécessaires :
1. **La règle de tenue** — un référentiel commun, un propriétaire par actif (répond au problème structurel de Logistique et de Santé).
2. **La règle du hors-liste, avec un délai** — sans délai chiffré, « traiter les découvertes » reste un vœu pieux, jamais vérifiable (test du sceptique de la séance 1 : *comment saurait-on que la règle n'est pas respectée ?* — ici, on le saurait au jour 31).
3. **L'incitation** — sans elle, la division Éducation & Territoires, qui vient d'être la plus honnête des trois filiales, deviendrait par punition la dernière à faire remonter ses trous à l'avenir. C'est la pièce la plus facilement oubliée, et la plus importante : elle transforme un aveu en donnée de gestion.

---

## Auto-évaluation (grille du TD)

| Critère | Notre niveau atteint |
|---|---|
| Lecture des trois réponses | Diagnostic distinct par filiale, ancré dans les 3 mots de la définition, **et** reconnaissance explicite qu'Éducation & Territoires est la réponse la plus mature malgré ses trous |
| Shadow IT / Shadow AI | Distinction faite, cas des données personnelles isolé, lien explicite « usage non gouverné → fuite sans attaquant » |
| Traitement proposé | Critère générique en deux questions, trois issues possibles, **et** réponse au besoin métier qui a créé l'usage caché |
| Mini-RACI | Trois niveaux distincts, un seul A par ligne, argument du goulot d'étranglement formulé explicitement |
| Règle de gouvernance | Une phrase couvrant tenue + hors-liste + délai, **et** mécanisme d'incitation à la découverte |

*Chaque case correspond à la colonne « Excellent » de la grille officielle — à confronter en séance avec le corrigé de référence du module.*
