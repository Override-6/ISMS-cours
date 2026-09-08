# Séance 1 — TP (S1-06) : Drafting the scoping document and strategy note
### Livrables du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN

> Rappel du test qui sépare les 3 documents : la note de cadrage répond à *« quelle est ma mission ? »*, la feuille de route à *« quoi, et quand ? »*, la note de stratégie à *« où va-t-on, et pourquoi ? »* — celle-ci cite les deux autres, ne les recopie jamais.

---

## Exercice 1 — Note de cadrage du RSSI Groupe (15 min)

*Une page, 5 sections. C'est le document qui aurait dû exister avant le lundi matin du RSSI Groupe.*

**But** : Le groupe MERIDIAN a créé le poste de RSSI Groupe pour doter quatre filiales aux métiers disjoints d'une gouvernance de sécurité commune, après avoir constaté que les décisions de sécurité se prenaient sans niveau ni règle identifiés.

**Périmètre** : Les quatre filiales (Santé, Logistique, Éducation, Territoires) et la division Éducation & Territoires avec sa DSI mutualisée ; l'ensemble des flux inter-filiales ; la relation avec les instances du groupe.

**Prérogatives** *(en citant les 3 règles d'arbitrage de la gouvernance cible, sans les réécrire)* : celles de la charte de gouvernance — véto suspensif `[ARB-01]` avec arbitrage rendu sous 72h, validation des dérogations `[ARB-03]` sous 48h, et le droit d'isolement d'urgence des RSSI de filiale `[ARB-02]`, que le RSSI Groupe outille et supervise sans l'exercer lui-même.

**Contreparties** : Direction Générale, à qui le RSSI Groupe propose ; Comité Exécutif, à qui il reporte, notamment via la revue trimestrielle ; Conseil d'Administration, informé via la Direction Générale ; Auditeur Interne, informé et jamais dirigé par le RSSI Groupe.

**Limites** *(au moins 3 exclusions réalistes, ancrées dans la posture CISO de la séance du matin)* :
1. Le RSSI Groupe **ne fixe pas** l'appétence au risque du groupe — il la propose et en informe les instances, conformément au tableau du CM (Responsible = Direction Générale, Accountable = Conseil d'Administration).
2. Le RSSI Groupe **n'administre aucun système** — l'exploitation appartient aux filiales (ex. le WMS de Logistique reste sous la responsabilité de son DSI et de sa TMA).
3. Le RSSI Groupe **ne se substitue pas** aux RSSI de filiale dans l'adaptation de la PSSI-cadre — il la valide, il ne la rédige pas à leur place.

*Vérification de la contrainte « une page » : la note tient effectivement sur une page une fois les 5 sections condensées comme ci-dessus — une note de cadrage longue est une note de cadrage qui n'a pas choisi.*

---

## Exercice 2 — La feuille de route et son budget (15 min)

*Trajectoire de 3 ans, 6 semestres, 3 axes : socle de confiance, résilience OT/IT, culture sécurité.*

### La feuille de route (jalons cohérents avec les priorités 1 et 2 de la gap analysis)

| Échéance | Jalons vérifiables |
|---|---|
| **12 mois** | Les écarts priorité 1 traités : segmentation des équipements biomédicaux de Santé engagée **et** séparation des comptes du prestataire TMA de Logistique achevée ; PSSI-cadre adaptée par les 4 filiales (engagement à 6 mois, avec 6 mois de marge de vérification) |
| **24 mois** | Cloisonnement IT/OT de Logistique opérationnel ; journalisation de Territoires centralisée vers le SOC ; tableau de bord alimenté sans collecte manuelle |
| **36 mois** | Gouvernance cible pleinement appliquée et mesurée, sous réserve de révision de la trajectoire (elle-même un jalon) |

*Cohérence de la logique : ce qui est vrai à 12 mois (comptes traités, PSSI adaptée) conditionne le jalon à 24 mois (cloisonnement IT/OT, qui suppose que les comptes ne circulent plus librement) — exactement l'ordre de remédiation établi dans le TD sur Logistique.*

### Pondération budgétaire des 3 axes (base = budget sécurité pluriannuel du groupe)

| Axe | Poids | Justification |
|---|---|---|
| Socle de confiance (identités, accès, authentification) | **40 %** | Porte les deux priorités 1 de la gap analysis (comptes Santé et Logistique) |
| Résilience OT/IT | **35 %** | Cœur industriel de Logistique (automates, WMS) + équipements biomédicaux de Santé |
| Culture sécurité | **25 %** | Investissement le plus lent et le plus durable |

### Les 2 arbitrages soumis par la Direction

**Enveloppe exceptionnelle (base = les deux filiales concernées uniquement)** : **60 % Santé / 40 % Éducation**. Justification : la mission de soin et l'état du parc biomédical (priorité 1 de notre gap analysis) pèsent davantage que l'exposition réelle mais moins vitale du parc d'Éducation, même si le secteur éducation/recherche reste, selon le panorama ANSSI, l'un des plus ciblés.

**Réallocation vers la modernisation des infrastructures obsolètes (base = les enveloppes existantes)** : **15 %**. Justification : ce chiffre s'adosse directement au **KRI d'obsolescence du parc** défini au tableau de bord (cible < 5 %, seuil d'alerte > 15 %) — c'est précisément ce seuil qui justifie de désinvestir ailleurs pour financer la modernisation.

*Règle commune aux deux arbitrages : chaque pourcentage porte sa base et sa justification — un pourcentage nu n'est pas un arbitrage, c'est une opinion habillée.*

---

## Note de stratégie — sous-section « Context and target governance » (15 min)

*Demi-page max, 3 contenus seulement : contexte, gouvernance cible citée par référence (jamais recopiée), engagement de trajectoire.*

> « Le groupe MERIDIAN, quatre filiales aux métiers et obligations disjoints, s'est doté d'une gouvernance de sécurité commune : des instances dont les rôles sur l'appétence au risque sont désormais codifiés, une matrice de responsabilité à propriétaire unique par ligne, des directives de groupe et des règles d'arbitrage écrites, réunies dans la charte de gouvernance à laquelle cette note renvoie. Cette gouvernance répond aux constats de l'analyse d'écart annexée au dossier : des décisions de sécurité jusqu'ici prises sans niveau ni règle identifiés — notamment le blocage de trois mois du flux Logistique-Santé et l'absence de propriétaire du registre des comptes administrateur de Santé. Chaque filiale adapte la PSSI-cadre sous six mois ; cette adaptation constitue le premier jalon de la feuille de route triennale approuvée en principe par le Comité Exécutif. »

**Vérification des deux disciplines imposées** : (1) la note **cite** le dossier (analyse d'écart, charte) sans jamais recopier son contenu — c'est ce qui lui permettra de tenir en 3 pages neuf séances plus tard ; (2) chaque affirmation reste vraie dans le temps ou pourra être amendée d'une phrase — rien n'y est daté de façon à devenir faux (« sera adaptée sous six mois » reste vrai même après l'échéance, il suffira d'amender avec le constat de réalisation).

---

## Auto-évaluation

| Critère | Notre niveau atteint |
|---|---|
| Note de cadrage | 5 sections, prérogatives citées par référence, **et** les 3 limites protègent réellement la posture (ne fixe pas, n'administre pas, ne se substitue pas) |
| Feuille de route | 3 jalons vérifiables à 12/24/36 mois, **et** la dépendance entre le jalon à 12 mois (comptes) et celui à 24 mois (segmentation) rendue explicite |
| Budget | Pondérations justifiées, bases précisées partout, **et** les deux arbitrages adossés à des éléments concrets du dossier (mission, KRI) |
| Note de stratégie | Demi-page, 3 contenus, référence au lieu de duplication, **et** chaque affirmation durable ou amendable d'une phrase |
| Transmission | Le lien vers la séance 2 (cartographie) est déjà préparé par la mention explicite de « ce sur quoi la gouvernance règne » restant à établir |
