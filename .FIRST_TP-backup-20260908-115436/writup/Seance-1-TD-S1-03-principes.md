# Séance 1 — TD (S1-03) : Structuring principles and anchoring activity
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN

---

## Rappel des 3 principes et du réflexe des 3 questions

- **Défense en profondeur** : plusieurs lignes de défense **indépendantes** — deux barrières qui tombent pour la même cause ne forment qu'une seule ligne déguisée.
- **Moindre privilège** : chaque compte/processus n'a que les droits strictement nécessaires à sa tâche.
- **Cloisonnement réseau** : regrouper ce qui est semblable en sensibilité/exposition/fonction, séparer le reste ; le cloisonnement, c'est choisir ses passages et les contrôler.

**Le réflexe en trois questions** (à appliquer à toute architecture) : *Si cette barrière tombe, qu'y a-t-il derrière ? Ce compte a-t-il plus de droits que sa tâche ? Si cette machine est compromise, jusqu'où voit-elle ?*

**Constats de base par filiale** (rappel) : Santé — analyseurs/consoles sur l'IP range bureautique + compte admin commun + mots de passe locaux sans MFA. **Logistique — réseaux IT/OT interconnectés + compte de domaine partagé avec le prestataire de maintenance tierce.** Éducation — comptes admin partagés entre les équipes de la division mutualisée, moyens limités. Territoires — logs conservés localement, non centralisés, malgré des exigences réglementaires connues et inscrites dans les contrats de délégation.

---

## Exercice 1 — MERIDIAN Santé : l'imagerie sur le réseau de tout le monde

*Deux constats : les analyseurs de laboratoire et consoles d'imagerie sont sur la même plage IP que la bureautique ; un compte administrateur local identique est déployé sur tout le parc.*

### Q1. Identifier le(s) principe(s) violé(s) par chaque constat

**Premier constat (équipement biomédical sur l'IP range bureautique)** : violation frontale du **cloisonnement réseau**. Des équipements sensibles et difficiles à mettre à jour partagent le segment de la population la plus exposée au phishing (les postes de bureau) — c'est exactement le regroupement de sensibilités et d'expositions hétérogènes que le principe proscrit.

**Second constat (compte administrateur identique sur tout le parc)** : il viole **deux principes à la fois**, comme l'indice le suggère. D'abord le **moindre privilège**, de façon évidente : un compte administrateur unique sur l'ensemble du parc donne à quiconque l'obtient des droits sans commune mesure avec la tâche de gérer une seule machine. Ensuite, plus subtilement, la **défense en profondeur** : ce compte unique transforme TOUTES les barrières du parc en **une seule ligne déguisée** — celle qui tombe le jour où le compte fuite. Deux défenses qui cèdent pour la même cause n'en sont qu'une.

### Q2. Décrire le scénario en 3 étapes maximum

1. Un poste de bureau est compromis par **phishing** (la population la plus exposée, sur le même réseau que les équipements critiques).
2. L'attaquant y récupère le **compte administrateur local**, identique partout sur le parc.
3. L'attaquant se déplace latéralement vers les analyseurs et consoles, **sur le même réseau**, avec des **droits d'administrateur** — aucune barrière supplémentaire à franchir.

### Q3. Formuler la recommandation en langage de gouvernance

**Décision tactique** de la filiale Santé : segmenter les équipements biomédicaux et déployer des comptes administrateur uniques par machine — mais **adossée à une directive de niveau groupe**, car le constat concerne la sécurité maximale de la filiale la plus critique du groupe. Dans la RACI : **le RSSI Groupe est A** (répond du maintien en condition de sécurité devant la Direction Générale), **le DSI de la filiale Santé est R** (exécute la segmentation), conformément à la grille RACI standard posée dans le CM de la matinée.

---

## Exercice 2 — MERIDIAN Logistique : le prestataire qui détient les clés du domaine

*C'est notre terrain : réseaux IT métier et OT (automates d'entrepôt) interconnectés sans cloisonnement ; le prestataire de Tierce Maintenance (TMA) des automates partage un compte administrateur de domaine avec l'administrateur système de la filiale.*

### Q1. Ce que le partage de compte rend impossible, au regard du moindre privilège

Un compte partagé détruit, d'un seul coup, quatre garanties fondamentales — pas seulement le risque d'intrusion pointé spontanément :

- **La traçabilité** : impossible d'attribuer une action précise à une personne précise ; le journal du compte ne dit jamais « qui » a agi, seulement « le compte ».
- **La révocation** : on ne peut pas retirer l'accès au prestataire sans casser en même temps l'administration interne de la filiale — le compte étant le même pour les deux usages.
- **La responsabilité contractuelle** : en cas d'incident, il devient impossible de démontrer contractuellement qui a fait quoi, donc d'engager la responsabilité du prestataire ou de l'exonérer.
- **La revue de moindre privilège elle-même** : un compte partagé est par construction surdimensionné pour chacun de ses usages pris séparément — on ne peut réduire ses droits sans casser l'un des deux usages qu'il porte.

*Contexte du dossier de filiale qui aggrave encore ce point : le contrat de la TMA prévoit une astreinte, mais **pas de journalisation nominative** — la faiblesse n'est donc pas seulement technique, elle est aussi contractuelle, dès l'origine.*

### Q2. Pourquoi l'interconnexion IT/OT aggrave spécifiquement ce constat, via le cloisonnement

L'interconnexion agit comme un **multiplicateur de portée**. Sans cloisonnement, un droit volé côté informatique de gestion (bureautique) atteint directement les automates industriels des entrepôts — l'absence d'isolation convertit un problème de compte en un **problème d'usine**. Autrement dit : le compte partagé définit *qui* peut faire des dégâts ; l'interconnexion IT/OT définit *jusqu'où* ces dégâts peuvent se propager. Les deux constats s'aggravent mutuellement, ce qui est précisément ce que demande la question 3.

### Q3. Ordre de remédiation, et pourquoi cet ordre

**Ordre attendu : (1) les comptes d'abord, (2) la segmentation IT/OT ensuite.**

- **Étape 1 — séparer, tracer, révoquer les comptes** : c'est rapide, essentiellement contractuel (renégocier l'accès du prestataire, imposer une journalisation nominative), et cela réduit **immédiatement** la surface d'attaque, sans attendre un projet d'infrastructure.
- **Étape 2 — segmenter IT/OT** : projet plus long, budgété, techniquement plus lourd.

**Pourquoi cet ordre et pas l'inverse** : segmenter le réseau *avant* de traiter les comptes laisserait un compte tout-puissant continuer de circuler pendant des mois — sur un réseau désormais mieux découpé, certes, mais toujours ouvert par la même clé partagée. C'est l'image donnée en cours : *une clé maîtresse qui continue de circuler dans un bâtiment aux portes neuves*. Traiter les comptes en premier retire l'usage abusif de la clé pendant que le chantier de cloisonnement, plus long, se déroule en arrière-plan.

---

## Exercice 3 — La division Éducation & Territoires : arbitrer un projet avec les principes

*Le projet de plateforme pédagogique d'Éducation doit se connecter aux bases administratives de Territoires (données citoyennes réglementées de ~30 collectivités clientes). Le responsable SI de Territoires s'y oppose ; l'arbitrage remonte au RSSI Groupe.*

### Q1. Examiner le projet avec les trois principes

- **Moindre privilège** : la plateforme ne doit accéder qu'aux données strictement nécessaires des bases de Territoires — jamais à leur intégralité.
- **Cloisonnement** : une connexion directe entre un service exposé au public étudiant et des bases citoyennes réglementées est interdite par principe — les sensibilités et expositions sont trop hétérogènes pour cohabiter sans séparation.
- **Défense en profondeur** : plusieurs barrières indépendantes doivent exister entre les deux systèmes — une seule protection ne suffit pas pour un flux entre deux mondes aussi différents.

### Q2. Arbitrage, sur le modèle du fil rouge de la matinée (autoriser SOUS CONDITIONS)

> *« Le projet est autorisé, PARCE QUE l'accès passera par une zone démilitarisée (DMZ) et des API sécurisées n'exposant que les données strictement nécessaires, avec les garanties d'authentification et de journalisation exigées par le groupe. Le responsable SI de Territoires obtient ses protections, Éducation obtient son projet, et le groupe gagne une nouvelle jurisprudence d'arbitrage inter-filiales. »*

C'est la même structure que l'arbitrage Logistique↔Santé du matin : **personne ne « gagne » au sens d'imposer sa position brute** — chacun obtient satisfaction sous condition, et la décision devient réutilisable pour le prochain conflit similaire.

### Q3. Grille de maturité des 4 filiales (activité d'ancrage — sert de point de départ à tout le module)

| Filiale | Note | Justification en une phrase |
|---|---|---|
| Santé | **2** | Des pratiques existent, mais le parc biomédical et le compte administrateur commun trahissent l'absence de toute formalisation |
| **Logistique** | **2** | L'exploitation fonctionne au quotidien, mais elle repose sur des individus (mémoire du Responsable Exploitation) et des comptes partagés avec un prestataire externe |
| Éducation | **2, tendant vers 1** sur la gestion des accès | Comptes administrateur partagés entre équipes, dans un contexte de moyens limités qui empêche toute formalisation |
| Territoires | **2** | Les exigences réglementaires sont connues et écrites dans les contrats de délégation, mais les journaux restent locaux, non centralisés — la connaissance existe, la pratique organisée non |

**Ce qui compte dans cette notation** : ce n'est pas le chiffre exact, c'est qu'**aucune filiale n'est notée sans justification**, et que la grille produit une base de discussion en comité — pas un classement qui humilie personne. C'est l'usage diplomatique de l'outil rappelé en cours : dire « vous êtes au niveau 2, les pratiques reposent sur des individus » ouvre une discussion de progrès ; dire « c'est amateur » ouvre une guerre.

---

## Auto-évaluation (grille du TD)

| Critère | Notre niveau atteint |
|---|---|
| Principes identifiés | Chaque constat rattaché aux bons principes, justifié — **et** la double violation du compte administrateur commun de Santé (moindre privilège + défense en profondeur / effet « ligne unique ») explicitée |
| Scénario d'attaque | Trois étapes plausibles, du poste de bureau à l'équipement de soin |
| Langage de gouvernance | Décision, niveau, et A nommé dans la RACI, avec la directive groupe distinguée de son application filiale |
| Arbitrage (ex. 3) | Autorisation sous conditions, garanties précisées, structurée comme le fil rouge : personne ne perd, le groupe gagne une règle |
| Grille de maturité | Quatre notes, chacune justifiée en une phrase — **et** l'usage diplomatique de la grille assumé |

*Points forts à faire valoir pour notre filiale (Exercice 2) : la distinction entre ce que le compte partagé rend impossible (traçabilité, révocation, responsabilité, revue) au-delà du seul risque d'intrusion, et l'argument d'ordre de remédiation (comptes avant segmentation) correctement justifié par l'effet multiplicateur de l'interconnexion IT/OT.*
