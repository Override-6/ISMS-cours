# Séance 1 — Governing Security: Levels, Stakeholders, and Principles
### Study notes + TP (Groupe 4 — Translog), module M2-01-4-ISMS

---

## 0. Le cadre du module

- **Cas fil rouge** : groupe fictif **MERIDIAN**, ~7 700 salariés, holding de 150 personnes + 4 filiales :
  - **MERIDIAN Santé** — 3 200 salariés, 4 établissements de soin
  - **MERIDIAN Logistique** — 2 800 salariés, 6 entrepôts *(← notre filiale, Groupe 4 "Translog")*
  - **MERIDIAN Éducation** — 900 salariés, 45 000 comptes utilisateurs
  - **MERIDIAN Territoires** — 650 salariés, ~30 collectivités clientes
  - Éducation et Territoires partagent une DSI commune (« division Éducation & Territoires »)
- **Notre rôle pour les 10 séances** : RSSI Groupe de MERIDIAN, nommé il y a 6 semaines, rattaché à la Direction Générale, sans prédécesseur, sans PSSI, sans budget consolidé.
- **Rythme** : théorie le matin (CM), pratique outillée l'après-midi (TP), 15 min d'écriture stratégique en clôture (note de stratégie).
- **Livrables cumulatifs** : dossier MERIDIAN (note de cadrage, cartographie, rapport d'audit, D5–D9...) + note de stratégie (3 pages max, enrichie chaque séance, jamais réécrite — seulement amendée).
- **Barème** (100 pts) : 9 quiz (20), oral individuel gouvernance (15, séance 6), oral de groupe (10, séance 6), rapport de groupe (30), note de stratégie (10), soutenance finale (15).

---

## 1. CM — Decision levels and role allocation (synthèse)

**Gouvernance ≠ management.** Gouverner = décider ce qui doit fonctionner et vérifier que ça fonctionne. Manager = faire fonctionner. La **PSSI** (Politique de Sécurité des Systèmes d'Information) est le document par lequel le management fixe orientations, règles et responsabilités ; en groupe, une **PSSI-cadre** est déclinée par chaque filiale.

### Trois étages de décision (nature, pas prestige)
| Niveau | Horizon | Acteurs chez MERIDIAN | Nature des décisions |
|---|---|---|---|
| **Stratégique** | années | Conseil d'Administration, Direction Générale | Appétence au risque, arbitrages majeurs, budgets pluriannuels |
| **Tactique** | mois/trimestres | Comité Exécutif, RSSI Groupe, RSSI filiales, directeurs métier | Décliner la PSSI-cadre, piloter les projets, arbitrer les priorités |
| **Opérationnel** | jour le jour | Administrateurs, analystes SOC, CERT/CSIRT | Exploiter, superviser, détecter, corriger |

### Appétence au risque — qui fait quoi
| Instance | Rôle sur l'appétence |
|---|---|
| Conseil d'Administration | **Accountable** — approuve formellement |
| Direction Générale | **Responsible** — fixe et propose |
| Comité Exécutif | Valide la déclinaison opérationnelle/budgétaire |
| RSSI Groupe | **Consulted** — informe, ne fixe ni n'approuve |

### La matrice RACI
Outil pour rendre les responsabilités indiscutables : **R**esponsible (fait), **A**ccountable (répond du résultat, **un seul par ligne, non négociable**), **C**onsulted, **I**nformed.

Trois vérifications avant toute RACI : (1) un seul A par ligne ; (2) pas de A « contrôleur » sur un processus qu'il contrôle lui-même (ex. un auditeur A sur ce qu'il audite = on n'audite pas son propre travail) ; (3) pas de A sans autorité réelle.

**RACI standard MERIDIAN** (référence) :
| Processus | COMEX | RSSI Groupe | Équipes IT/métier | Auditeur SSI |
|---|---|---|---|---|
| Validation PSSI et adaptations | A | R | C | I |
| Arbitrage budgets/projets sécurité | A | C | R | I |
| Maintien en condition de sécurité | I | A | R | I |
| Évaluation de conformité / audits | I | C | I | R/A |

### Ce qu'une RACI ne fait PAS
Elle n'accorde aucune autorité (elle l'enregistre), ne règle aucun conflit (il faut une instance d'arbitrage), et elle vieillit (à revoir régulièrement).

### Cas d'arbitrage inter-filiales (fil rouge du module)
Flux entre les **scannettes d'entrepôt de Logistique** et le **système de gestion de stock pharmaceutique de Santé** : conflit disponibilité (Logistique) vs confidentialité/confiance (Santé). Décision du RSSI Groupe : flux **autorisé sous conditions** — VLAN dédié, pare-feu d'inspection, TLS 1.3 + MFA obligatoires sur l'API d'urgence, refus du protocole obsolète proposé par Logistique. **Personne ne « gagne »** : Logistique obtient son flux, Santé ses garanties, le groupe une jurisprudence réutilisable.

*(Note pour nous : ce flux Logistique↔Santé sera exactement le sujet central du dossier de filiale que nous instruirons en Séance 2 — le flux est aujourd'hui bloqué depuis 3 mois côté Santé.)*

---

## 2. TD — Structuring principles and anchoring activity (synthèse)

Trois principes structurants (outillage du niveau tactique) :

1. **Défense en profondeur** — plusieurs lignes de défense **indépendantes** ; deux barrières qui tombent pour la même cause = une seule ligne déguisée. Se dose selon la valeur protégée.
2. **Moindre privilège** — chaque compte/processus n'a que les droits strictement nécessaires à sa tâche ; exige de connaître les tâches (discipline de gouvernance, pas juste technique).
3. **Cloisonnement réseau** — regrouper ce qui est semblable (sensibilité, exposition, fonction), séparer le reste ; l'échec typique est le « réseau plat ». Cloisonner = choisir ses passages et les contrôler.

**Grille de maturité SSI** (4 niveaux, outil diplomatique de priorisation) :
1. Pratiques absentes
2. Pratiques informelles (portées par des individus)
3. Pratiques formalisées (écrites, applicables)
4. Pratiques managées (mesurées, revues)

### Notation de maturité de référence (donnée par le corrigé du TD)
| Filiale | Note | Justification |
|---|---|---|
| Santé | 2 | pratiques existent mais équipements biomédicaux/comptes trahissent l'absence de formalisation |
| **Logistique** | **2** | l'exploitation tient mais repose sur des individus et des comptes partagés |
| Éducation | 2 (tendance 1 sur les accès) | comptes admin partagés, moyens limités |
| Territoires | 2 | exigences réglementaires connues mais logs non centralisés |

### Exercice 2 (TD) — MERIDIAN Logistique, "le prestataire qui détient les clés du domaine" *(à retenir : c'est exactement notre terrain)*
Deux constats : (a) réseaux IT métier et OT (automates d'entrepôt) interconnectés sans cloisonnement ; (b) le Prestataire de Tierce Maintenance (TMA) des automates partage un **compte administrateur de domaine** avec l'administrateur système de la filiale.

- Le compte partagé rend impossible : l'imputabilité (traçabilité d'une action à une personne), la révocation du prestataire sans casser l'admin interne, la responsabilité contractuelle, la revue de moindre privilège.
- L'interconnexion IT/OT aggrave tout par la **portée** : sans cloisonnement, un droit volé côté bureautique arrive jusqu'aux automates d'entrepôt.
- Ordre de remédiation attendu : **1) les comptes d'abord** (séparer, tracer, révoquer — rapide et contractuel) **2) puis la segmentation IT/OT** (projet plus long) — l'ordre inverse laisserait un compte tout-puissant circuler pendant des mois sur un réseau déjà segmenté.

---

## 3. Le TP de Séance 1 — objectifs, questions, et travail attendu

Le TP comporte **deux documents/temps** : (A) *Framing the MERIDIAN case and target governance* (S1-05) et (B) *Drafting the scoping document and strategy note* (S1-06). À la fin, le dossier MERIDIAN doit contenir **5 livrables** :
1. Analyse d'écart du groupe (gap analysis)
2. Gouvernance cible écrite (2 pages, 4 sections)
3. Tableau de bord d'indicateurs du RSSI Groupe
4. Note de cadrage du RSSI Groupe (scoping note)
5. Feuille de route + budget pluriannuel + 1ʳᵉ sous-section de la note de stratégie

### Notions outillées avant d'écrire
- **Gap analysis** : comparaison méthodique état observé ↔ cible EXPLICITE (la cible doit exister avant l'analyse) → pour chaque écart : constat, principe/règle violé, priorité.
- **Charte de gouvernance** : document court, signé au bon niveau, qui fixe instances, RACI, règles d'arbitrage, directives — chaque règle doit être **vérifiable**, avec un propriétaire et une échéance.
- **KPI vs KRI** : un KPI mesure l'**efficacité** d'une mesure en cours (ex. % de comptes à privilèges protégés par MFA) ; un KRI **alerte sur une exposition** qui grossit toute seule si personne n'agit (ex. % d'OS obsolètes). Chaque indicateur a une cible ET un seuil d'alerte.
- **Test du sceptique** : pour toute règle/indicateur, « comment saurait-on qu'elle N'EST PAS respectée ? » — si la réponse n'est pas évidente, la formulation n'est pas vérifiable.

---

### A. Exercice 1 — Gap analysis du groupe (20 min)

**Consignes :**
1. Construire le tableau (Filiale | Écart observé | Principe/règle cible violé | Priorité 1–3 justifiée). Couvrir les 4 filiales avec tous les constats de la journée + 2 nouveaux signalements : Santé (mots de passe locaux sans MFA sur applis métier) et Territoires (logs conservés localement, non centralisés).
2. **Prioriser sans égalitarisme** : au maximum **2 écarts en priorité 1** pour tout le groupe ; la justification doit invoquer la **mission** de la filiale, pas seulement la sévérité technique.
3. Repérer l'écart qui n'appartient à aucune filiale mais au **groupe lui-même** (ligne « Groupe »).

**Corrigé de référence (à connaître, à adapter à notre analyse) :**
- **Logistique** — réseaux IT/OT interconnectés + compte de domaine partagé avec la TMA → violation cloisonnement + moindre privilège → **Priorité 1** (la continuité d'expédition du groupe en dépend).
- Santé — équipements biomédicaux sur le VLAN bureautique + compte admin commun → **Priorité 1** (mission de soin).
- Santé — mots de passe locaux sans MFA → Priorité 2.
- Éducation — comptes admin partagés → Priorité 2 (aggravé par les moyens limités).
- Territoires — logs non centralisés → Priorité 2 (ni détection, ni analyse post-incident possible ; collectivités clientes exigeantes).
- **Ligne « Groupe »** : absence de PSSI-cadre et de règles d'arbitrage — c'est LA racine de tous les autres écarts ; seul le groupe peut la traiter, aucune filiale seule.

---

### B. Exercice 2 — Rédaction de la gouvernance cible (25 min)

Document de **2 pages max**, titré *« Target governance of MERIDIAN group security »*, **4 sections** :

1. **Section 1** — instances + répartition des rôles sur l'appétence au risque (reprises du CM) ; **section 2** — grille RACI des processus clés. Chaque tableau doit être suivi d'une phrase disant ce qu'il **empêche** (étalon : les 3 dossiers du CISO du lundi matin doivent devenir impossibles).
2. **Section 3** — au moins **5 directives codifiées** `[PSSI-CADRE-XXX-nn]`, couvrant obligatoirement : authentification des accès distants/privilèges d'administration ; revue des privilèges sur bases métier ; notification des incidents majeurs au RSSI Groupe ; collecte des journaux ; traitement des correctifs critiques. Chaque directive doit passer le **test du sceptique** (vérifiable, propriétaire nommé, échéance/fréquence).
3. **Section 4** — 3 règles d'arbitrage inter-filiales : pouvoir du RSSI Groupe en cas de désaccord (véto suspensif) ; pouvoir d'urgence d'un RSSI de filiale en cas de compromission confirmée ; circuit de dérogation à la PSSI-cadre avec délai.

**Corrigé de référence :**
- `[PSSI-CADRE-ACC-01]` MFA obligatoire sur tout accès distant et tout privilège d'administration.
- `[PSSI-CADRE-ACC-02]` Revue trimestrielle des privilèges sur les bases métier.
- `[PSSI-CADRE-INC-01]` Notification de tout incident majeur au RSSI Groupe sous 2 heures.
- `[PSSI-CADRE-JRN-01]` Collecte des journaux vers le SOC centralisé du groupe (en montée en charge).
- `[PSSI-CADRE-COR-01]` Tout correctif critique appliqué sous 14 jours.
- `[ARB-01]` Véto suspensif du RSSI Groupe, arbitrage rendu sous 72h (suspend sans enterrer).
- `[ARB-02]` Droit d'isolement d'urgence de tout RSSI filiale sur un flux inter-filiales en cas de compromission confirmée (on coupe d'abord, on arbitre ensuite).
- `[ARB-03]` Toute dérogation à la PSSI-cadre validée par le RSSI Groupe sous 48h.
- Directive prioritaire par filiale : Santé → chiffrement AES-256 des données au repos ; **Logistique → cloisonnement strict IT/OT** ; Éducation → MFA généralisée ; Territoires → journalisation centralisée vers le SOC.

---

### C. Exercice 3 — Premier tableau de bord du RSSI Groupe (15 min)

1. **4 KRI max**, chacun avec cible + seuil d'alerte, couvrant 4 expositions différentes (indices : ce que le SOC ne voit pas, le vieillissement du parc, les comptes qui ne désignent personne, le facteur humain).
2. **3 à 5 KPI de mise en œuvre**, chacun rattaché à UNE directive de l'exercice 2, avec sa valeur cible.
3. **Vérifier la cohérence** : chaque priorité 1 de la gap analysis doit être surveillée par au moins un indicateur.

**Corrigé de référence (KRI) :**
| KRI | Cible | Seuil d'alerte |
|---|---|---|
| Part du périmètre non supervisé (logs non collectés) | < 5 % | > 20 % |
| Part d'OS obsolètes | < 5 % | > 15 % |
| Comptes à privilèges non nominatifs | 0 | > 5 |
| Taux de clic en campagne de phishing | < 5 % | > 15 % |

**Attention au piège** : couverture PSSI, délai moyen de détection, taux de sensibilisation sont des **KPI de pilotage**, pas des KRI (ils mesurent la progression d'un programme).

**KPI de mise en œuvre** (rattachés aux directives) : comptes à privilèges protégés par MFA (cible 100 %) ; comptes inactifs non révoqués à 30 jours (cible 0) ; vulnérabilités critiques non corrigées à 14 jours (cible 0) ; délai moyen de notification d'incident majeur (cible < 30 min, plus strict que l'obligation contractuelle de 2h) ; écarts critiques non résolus à 30 jours (cible 0).

**Couverture attendue** : le compte admin commun de Santé → KRI « comptes non nominatifs » + KPI MFA ; **l'interconnexion réseau de Logistique → KRI du périmètre non supervisé + KPI des écarts critiques non résolus** (mesure la progression de la directive de segmentation).

---

### D. TP suite (S1-06) — Note de cadrage, feuille de route, note de stratégie

**Trois documents, trois questions différentes** — ne pas les confondre :
- Note de cadrage → *« quelle est ma mission ? »*
- Feuille de route → *« quoi, et quand ? »*
- Note de stratégie → *« où va-t-on, et pourquoi ? »* (elle cite les deux autres, ne les recopie jamais)

#### Exercice 1 — Note de cadrage du RSSI Groupe (15 min)
Une page, 5 sections : **but** (2 phrases) ; **périmètre** (4 filiales + division Éducation&Territoires + flux inter-filiales) ; **prérogatives** (citer les 3 règles d'arbitrage, sans les réécrire) ; **contreparties** (les instances du matin, ce qui leur est dû : proposition, reporting, alerte) ; **limites** — **au moins 3 exclusions réalistes** (indice : la posture RSSI — ce que le RSSI Groupe n'a PAS le droit de faire à la place des autres).

**Corrigé de référence — les 3 limites attendues** : le RSSI Groupe ne fixe pas l'appétence au risque (il la propose/l'informe) ; n'administre aucun système (l'exploitation appartient aux filiales) ; ne se substitue pas aux RSSI de filiale dans l'adaptation de la PSSI, mais la valide.

#### Exercice 2 — Feuille de route et budget (15 min)
Trajectoire de 3 ans, 6 semestres, 3 axes stratégiques : **socle de confiance**, **résilience OT/IT**, **culture sécurité**.
1. Construire la feuille de route : objectif principal par semestre + 3 jalons vérifiables à 12/24/36 mois, cohérents avec les priorités 1 et 2.
2. Proposer une pondération budgétaire des 3 axes (%), justifiée, en **précisant la base** de chaque chiffre.
3. Trancher 2 arbitrages : enveloppe exceptionnelle Santé + Éducation (répartition à justifier) ; part des enveloppes existantes à réallouer vers la modernisation des infrastructures obsolètes.

**Corrigé de référence :**
- **12 mois** : écarts priorité 1 traités — **segmentation des automates biomédicaux de Santé** ET **séparation des comptes du prestataire de Logistique en cours** — + PSSI-cadre adaptée par les 4 filiales.
- **24 mois** : **segmentation IT/OT de Logistique opérationnelle**, journalisation de Territoires centralisée vers le SOC, tableau de bord alimenté sans collecte manuelle.
- **36 mois** : gouvernance cible pleinement appliquée et mesurée, sous réserve de révision de la trajectoire (elle-même un jalon).
- Pondération (base = budget sécurité pluriannuel du groupe) : Socle de confiance 40 % (identités/accès portent les 2 priorités 1), **Résilience OT/IT 35 % (cœur industriel de Logistique + équipements biomédicaux de Santé)**, Culture sécurité 25 %.
- Enveloppe exceptionnelle (base = les 2 filiales concernées) : 60 % Santé / 40 % Éducation (mission de soin + état du parc biomédical pèsent plus que l'exposition réelle mais moins vitale d'Éducation).
- Réallocation modernisation : 15 % des enveloppes existantes, adossée au KRI d'obsolescence du tableau de bord.

#### Note de stratégie — 1ʳᵉ sous-section : « Context and target governance » (15 min)
Demi-page max, 3 contenus seulement : le **contexte** (ce qu'est le groupe et pourquoi la sécurité y devient un sujet de gouvernance) ; la **gouvernance cible** (instances, RACI, règles d'arbitrage — citées par référence à la charte, jamais recopiées) ; l'**engagement de trajectoire** (adaptation de la PSSI-cadre par chaque filiale sous 6 mois — premier jalon opposable de la feuille de route).

**Règle d'or** : rien n'est jamais supprimé de la note de stratégie ; tout peut être amendé avec une phrase de justification.

---

## 4. Ce qui nous attend en Séance 2 (lien direct avec Translog)

Le CM annonce la suite : *« ce que la charte a décidé, c'est QUI arbitre et sous quelles règles ; il manque encore de savoir exactement SUR QUOI cela règne »* → Séance 2 = cartographie du SI du groupe.

Le dossier de filiale **MERIDIAN Logistique** (déjà reçu, à traiter en binôme avec le Groupe 3 « translog-a ») confirme et prolonge exactement les constats du TD/TP de Séance 1 :
- Réseaux bureautique/industriel interconnectés, sans cloisonnement (E2, E3, E4 avec automates).
- Compte de domaine partagé avec la TMA du WMS — nombre d'utilisateurs inconnu ; pas de journalisation nominative dans le contrat.
- Compte de service WMS↔automates : **même mot de passe sur les 6 entrepôts depuis 2019**, en clair dans un fichier de config.
- Sauvegardes quotidiennes du WMS **jamais restaurées** depuis la mise en service (continuité non testée).
- Un arrêt > 6h bloque **40 % du volume expédié du groupe** (dépendance critique au WMS centralisé sur E1).
- Aucune procédure d'incident (l'arrêt d'avril l'a démontré : chacun a appelé qui il pouvait, pas de chronologie tenue).
- Intégrateur des automates connecté par box 4G **hors réseau supervisé**, contrat sans clause de réversibilité ni exigence de sécurité.
- Flux vers Santé (scannettes → stock pharmaceutique) **bloqué depuis 3 mois** — c'est le fil rouge du CM de Séance 1, vu ici côté Logistique : la filiale veut la reprise du flux, Santé exige des garanties.
- Question posée par la DG après l'incident d'avril, à préparer : *« si ça s'arrête six heures, qui appelle qui, et qui décide de prévenir le client ? »*

**À faire avant/pendant la Séance 2** : appliquer la gap analysis, la RACI et les 3 principes structurants (défense en profondeur, moindre privilège, cloisonnement) directement sur ces constats Logistique, et proposer la RACI d'incident + la règle d'arbitrage manquante pour le flux Logistique↔Santé — en cohérence avec les règles `[ARB-01]` à `[ARB-03]` déjà écrites en Séance 1.
