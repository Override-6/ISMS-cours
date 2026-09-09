# D5 — APPRÉCIATION INITIALE DES RISQUES : MERIDIAN LOGISTIQUE ET SON FLUX D'APPROVISIONNEMENT D'URGENCE VERS MERIDIAN SANTÉ

**Émetteur** RSSI Groupe · **Destinataires** Direction Générale du groupe (accepte le risque résiduel), Comité Exécutif (valide la déclinaison et les budgets), Direction et DSI de MERIDIAN Logistique (agissent)
**Groupe 4 (Translog)** · instance `translog-b` · étude `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1` · **Séance 5**

> Dossier documentaire prouvant que les **ateliers 1 et 2 d'EBIOS Risk Manager** ont été conduits avec méthode. Assemblé à partir des productions de la journée : appétence du bureau du RSSI, cadrage et événements redoutés du TD 2, socle tiré de l'audit de la séance 4, couples source de risque / objectif visé du TD 2, saisie dans l'outil aux TP 1 et TP 2. Les valeurs métier et les biens supports sont **repris à l'identique** de la cartographie de la séance 2 (D2). Les ateliers 3 à 5 sont vides : ils relèvent des séances 6 et 7.

---

## 1. Cadrage de l'étude

**Objectif** — Apprécier et traiter les risques numériques pesant sur MERIDIAN Logistique et sur son flux d'approvisionnement d'urgence vers MERIDIAN Santé, premier cycle d'une démarche de groupe, pour éclairer les décisions de traitement de la Direction Générale et matérialiser sur la grille le seuil d'acceptation dérivé de l'appétence.

**Finalité retenue** parmi celles de la méthode : une **étude complète des scénarios de risque** (les cinq ateliers, sur les deux cycles), en vue du traitement et du pilotage — ni un socle seul, ni une homologation (le cadrage d'homologation du WMS de la séance 4 en est un sous-ensemble).

**Périmètre** — Métier et technique repris de D2 : quatre valeurs métier `LOG-PA-01` à `04`, treize biens supports `LOG-SA-01` à `13` ; plus, en quatrième ligne, la dépendance inter-filiales du §6 du pack de filiale — le flux d'approvisionnement d'urgence des scannettes de Logistique vers le système de gestion des stocks de Santé. **Hors périmètre** : les trois autres filiales, les ateliers 3 à 5.

**Participants et rôles** (atelier 1) — Responsable Exploitation de Logistique, en appui du Responsable Qualité et chaîne du froid (métier : ce que valent les flux et la chaîne du froid) ; DSI de la filiale, trois personnes sans titre de RSSI (SI : ce que le SI permet — **angle mort acté** : ni l'OT, ni la télématique, ni la box 4G de l'intégrateur) ; RSSI Groupe (cyber : état de la menace, couverture partielle du SOC, constats gradés de l'audit) ; Direction Générale du groupe, représentée en séance par le Directeur de la filiale pour ce qui engage la filiale (décision).

**Responsable de l'acceptation des risques résiduels** — la **Direction Générale du groupe**. La gouvernance de la séance 1 en fait la seule instance qui fixe l'appétence (le Conseil d'Administration l'approuve, le RSSI Groupe la propose sans la fixer) ; accepter le risque résiduel en est la face opérationnelle.

**Cycles** — cycle stratégique **3 ans** (l'étude entière et les scénarios stratégiques), cycle opérationnel **1 an** (les scénarios opérationnels, revus à la lumière des incidents, des vulnérabilités nouvelles et de l'évolution des modes opératoires). Référence : recommandation du guide EBIOS RM pour l'homologation de sécurité.

**Échelles justifiées** — L'outil impose la matrice `4x4 risk matrix from EBIOS-RM` (bibliothèque `intuitem`, lecture seule). Vraisemblance `Unlikely / Likely / Very likely / Certain`, gravité `Minor / Significant / Important / Critical`, niveaux de risque `Low / Medium / High`. Les descriptions dans les termes du groupe :

*Gravité :*

| Niveau | Missions | Personnes | Reprise |
|---|---|---|---|
| **G1 `Minor`** | Gêne absorbée sans dégradation visible du service ; consomme une marge d'exploitation. | Aucun effet sur la sécurité des soins ; aucune donnée personnelle exposée. | Quelques heures, équipes en place, sans décision supérieure. |
| **G2 `Significant`** | Service dégradé ou interrompu de façon perceptible sans priver de l'essentiel ; un objectif de période manqué. | Aucune atteinte aux soins ; au plus une donnée non sensible exposée à un cercle restreint. | Un à quelques jours, cellule mobilisée, Comité sécurité groupe informé ; pas d'impact contractuel chiffré. |
| **G3 `Important`** | Interruption d'un service **essentiel** : expédition arrêtée > 6 h (40 % du volume groupe), rupture de la chaîne du froid, plateforme citoyenne indisponible, annuaire du pôle compromis ; un engagement contractuel rompu et payé (12 000 €/jour, délai de notification manqué). | Retard de soins ou de réapprovisionnement d'urgence sans conséquence vitale établie ; données personnelles — mineurs, patients — exposées à un tiers non autorisé. | Une à plusieurs semaines, décision du Comité Exécutif, client et régulateur informés ; trace durable sur la relation client. |
| **G4 `Critical`** | Capacité du groupe à tenir une mission remise en cause dans la durée : perte d'un contrat ou d'une délégation, incapacité prolongée à expédier ou à soigner ; l'existence d'une filiale menacée. | Conséquence vitale ou sanitaire pour un patient ou un usager ; fuite massive de données de santé ou de mineurs. | Incertaine ou > plusieurs mois, décision de la Direction Générale et saisine du Conseil d'Administration ; événement qui se communique publiquement. |

*Vraisemblance — libellés de l'outil conservés, une phrase d'interprétation :* `Unlikely` : rien d'observable ne soutient le scénario, ou la source n'a pas les moyens du mode opératoire. `Likely` : une faiblesse existe mais son exploitation demande un concours de circonstances ou un accès que la source n'a pas encore. `Very likely` : une faiblesse **connue et actuelle** rend le scénario réalisable avec les moyens courants de la source, exemples récents dans le secteur (secret de service en clair, box 4G hors supervision, aucun journal OT au SOC). `Certain` : le scénario s'est déjà réalisé dans le périmètre ou sa réalisation ne dépend plus d'un attaquant (flux vers Santé bloqué depuis trois mois, arrêt WMS d'avril).

*Seuil d'acceptation, dérivé de l'appétence :* **`Low`** = acceptable en l'état, porté sans mesure spécifique, revu à la cadence trimestrielle du ComEx. **`Medium`** = tolérable **uniquement** formalisé en tolérance datée, surveillée, avec un propriétaire nommé et une mesure compensatoire ; à défaut, traité comme `High`. **`High`** = inacceptable en l'état, décision de traitement avant mise en production ou avant de le porter plus longtemps, activité suspendue si le traitement n'est pas engagé. Ce seuil ne réécrit pas la matrice : son texte dit déjà « acceptable / tolérable sous contrôle / inacceptable ». Il sera appliqué **inchangé** au registre complet en séance 7.

---

## 2. Socle de sécurité

*Le choix de référentiel de la séance 3 et le rapport d'audit de la séance 4 **sont** l'état d'application que demande la méthode. Les directives PSSI-cadre codifiées en séance 1 (`ACC-01` à `COR-01`) font foi quel que soit le libellé.*

| Référentiel | État d'application | Écarts | Justification |
|---|---|---|---|
| **PSSI-cadre du groupe** (S1) | Établie récemment, déclinaison filiale à six mois, appliquée à la marge sur Logistique | `ACC-01` MFA/privilèges : non appliqué (secret de service en clair, pas de MFA WMS/automates). `ACC-02` revue trimestrielle des privilèges : non appliqué (porteurs du compte TMA inconnus). `INC-01` notification < 2 h : non appliqué (arrêt d'avril, « chacun a appelé qui il pouvait »). `JRN-01` journaux → SOC : partiel (bureautique oui, OT/4G/WMS non). `COR-01` correctif < 14 j : ni mesuré ni mesurable (la TMA met à jour « quand elle veut »). | Les directives existent ; l'outillage et les preuves de mise en œuvre n'existent pas encore côté Logistique. |
| **Guide d'hygiène informatique de l'ANSSI** (v2, 42 mesures — S3, outil d'application immédiate) | Non déroulé formellement ; quelques mesures satisfaites de fait | Mesure 4 (actifs sensibles + **schéma réseau**) : aucun schéma réseau de la filiale n'existe. Cloisonnement : réseaux IT et OT interconnectés sur les six sites. Comptes d'administration : compte de domaine partagé avec la TMA. Sauvegarde : sauvegardes quotidiennes **jamais restaurées**. | Retenu en S3 comme mesure d'urgence, pas comme référentiel de conformité ; chantier « schéma réseau » inscrit à la trajectoire (M2 de D4, 8/12/2026). |
| **ISO/IEC 27001:2022** (référentiel colonne vertébrale du groupe, S3) | Auto-évaluation S4 sur 12 exigences : aucune pleinement couverte, 2 partielles, 9 non couvertes ; pas de SMSI | **C3 — `A.8.22`** cloisonnement : non-conformité **majeure** (IT/OT interconnectés sur tout le périmètre). **C4 — `A.5.19` / `A.8.2`** fournisseurs / droits d'accès : non-conformité **majeure** (compte de domaine partagé avec la TMA, porteurs inconnus, imputabilité inopérante). `A.5.17` secrets : non couvert (secret de service identique depuis 2019, en clair). `A.5.22`, `A.8.5`, `A.8.8`, `A.8.15` : non ou partiellement couverts. `A.8.13` / `A.5.30` sauvegarde / continuité : jamais restaurées, RTO/RPO non contractualisés. **C7 — `A.8.22`** sur le flux Logistique↔Santé : **conforme** (seul cloisonnement du groupe), mais flux suspendu depuis trois mois. | Référentiel choisi en S3, auto-évaluation en S4 ; écarts majeurs concentrés sur le cloisonnement et la gouvernance des comptes tiers, héritage de onze ans d'acquisitions sans intégration des SI. |
| **Obligations propres de la filiale** — exigences contractuelles du client pharmaceutique (§2 du pack : pénalités 12 000 €/j, audits annuels de chaîne du froid, questionnaire de sécurité annoncé) | Partiellement tenu : la chaîne du froid est opérée ; la maîtrise des accès et la preuve associée manquent | La filiale ne peut pas répondre au questionnaire de sécurité annoncé (« qui a accès aux relevés de température ? ») ; un compte par entrepôt sur le portail client, sans gestion nominative ; aucun journal. | Exigence contractuelle connue, jamais traduite en mesures internes ni en preuves ; le client a annoncé qu'il la contrôlerait au prochain audit. |

**Décision sur la suite** — Le guide ouvre deux voies : suspendre l'appréciation pour renforcer le socle d'abord, ou poursuivre en intégrant la non-conformité. **Le groupe poursuit l'appréciation en intégrant la non-conformité** : les écarts deviennent des données d'entrée de l'étude, pas un motif de suspension. C'est la seule voie raisonnable — l'appétence du matin traite déjà ces écarts comme des tolérances à formaliser avec une remédiation datée (M1 à M4 de D4), et suspendre priverait la Direction Générale de la priorisation par le risque qu'elle a demandée. **Conséquence** : les scénarios stratégiques et opérationnels de la séance 6 seront construits **sur ces fragilités** (interconnexion IT/OT, compte TMA partagé, secret de service en clair, absence de journalisation OT), et les niveaux de risque calculés en séance 7 refléteront l'état actuel du socle, non un état cible.

---

## 3. Sources de risque et objectifs visés (atelier 2)

*Contexte de menace : 128 compromissions par rançongiciel portées à la connaissance de l'ANSSI en 2025 ; le secteur santé reste une cible régulière (Centre Hospitalier Sud Francilien, 2022, LockBit). Objectifs formulés en résultats, jamais en motivations.*

**Trois couples retenus** — distincts et sur des valeurs métier différentes :

| # | Source de risque (catégorie outil) | Objectif visé — une phrase | Valeur métier | Pertinence (outil) |
|---|---|---|---|---|
| **1** | Cybercriminel (`Organized crime`) | Chiffrer le WMS et sa base pour arrêter le flux d'expédition du groupe et obtenir une rançon sous menace d'arrêt prolongé. | `LOG-PA-01` | Highly relevant |
| **3** | Initié de l'Exploitation, mécontent ou partant (`Avenger`) | Altérer les données de préparation et de stock via le compte de service en clair connu de toute l'Exploitation, et emporter le savoir-faire opérationnel non écrit des six entrepôts. | `LOG-PA-01` (intégrité) **et** `LOG-PA-03` | Fairly relevant |
| **4** | Concurrent (`Competitor`) | Obtenir les données d'exploitation et les données du client pharmaceutique (volumes, tournées, relevés de température) pour capter le marché. | `LOG-PA-04` et `LOG-PA-02` (confidentialité) | Partially relevant |

Le couple n°4 est retenu **malgré une pertinence modérée** : il est le seul à atteindre `LOG-PA-04` et la confidentialité — sans lui, toute la moitié « confiance / conformité contractuelle » du métier resterait sans adversaire dans l'étude. La colonne *Pertinence* de l'outil (motivation × ressources, l'activité n'y entre pas) n'a **pas** commandé la sélection : la justification écrite prévaut.

**Couples secondaires sous surveillance** — n°2, **attaquant passant par l'intégrateur des automates** (compromission de la chaîne d'approvisionnement, via la box 4G non supervisée) : redouble `LOG-PA-01` déjà porté par le couple n°1, et relève d'abord d'un risque de dépendance qui se traite au contrat et qui sera repris comme **partie prenante critique de l'écosystème en séance 6 (atelier 3)** — sa juste place méthodologique. n°5, **hacktiviste** visant l'image de la chaîne du froid : le plus bas sur les trois critères, aucune activité observable ; conservé en veille pour la cible symbolique (client pharmaceutique).

---

## 4. Événements redoutés

*Sept événements redoutés adossés aux valeurs métier de D2, cotés sur l'échelle générique (mineure / significative / grave / critique). Tous `Selected` dans l'instance.*

| Réf. | Événement redouté (valeur métier + besoin touché) | Gravité | Justification (nature des impacts) |
|---|---|---|---|
| **ER1** | `LOG-PA-01` — le flux d'expédition du groupe est interrompu, les six entrepôts ne préparent plus (**Disponibilité**) | Critique | Missions : arrêt > 6 h = 40 % du volume expédié du groupe ; contrat : pénalités 12 000 €/j ; reprise non démontrée (sauvegardes jamais restaurées). |
| **ER2** | `LOG-PA-01` — les données de préparation et de stock du WMS sont altérées, expéditions fausses non détectées (**Intégrité**) | Grave | Missions + client : erreurs en cascade, y compris vers Santé ; partiellement détectable ; pas de risque vital direct. |
| **ER3** | `LOG-PA-02` — la chaîne du froid est rompue ou ses relevés faussés sur un entrepôt pharma E1/E4 (**Disponibilité + Intégrité**) | Critique | Contrat : manquement direct + audit annuel ; personnes : risque sanitaire pour le patient final ; image. |
| **ER4** | `LOG-PA-04` — la filiale ne peut pas produire la preuve de qui accède aux relevés et aux systèmes, à l'audit ou au questionnaire client (**Traçabilité**) | Grave | Contrat : échec probable de l'audit → risque de perte du contrat ; image ; compte TMA partagé, aucun journal nominatif. |
| **ER5** | `§6` — le réapprovisionnement d'urgence de la pharmacie hospitalière de Santé n'est plus assuré (flux scannettes → interface → VLAN indisponible) (**Disponibilité**) | Critique | Personnes : réapprovisionnement d'urgence des établissements de soin ; missions inter-filiales ; « ça ne tiendra pas l'hiver ». *Valeur métier propriété de Santé, non modélisée comme actif primaire dans notre domaine — rattaché à `LOG-PA-01`, limite à lever à l'atelier 3.* |
| **ER6** | `LOG-PA-02` — les données de température et d'expédition du client pharmaceutique sont divulguées (fournisseur hors supervision) (**Confidentialité**) | Significative | Contrat : violation d'une clause de confidentialité ; image ; pas de donnée de santé nominative directe. |
| **ER7** | `LOG-PA-03` — le savoir-faire opérationnel des six entrepôts est perdu (départ ou absence du Responsable Exploitation, aucune trace écrite) (**Traçabilité**) | Grave | Missions : dégradation durable de l'exploitation des six sites, reprise lente et coûteuse (reconstruction du savoir), sans échéance certaine ; pas d'atteinte directe aux personnes ni manquement réglementaire immédiat. *Ajouté au TP 2 (compteur 6 → 7) : le couple SR/OV n°3 le vise ; sans lui, ce couple retenu resterait sans événement redouté.* |

**Événement redouté dont une durée change la cotation** — **ER1** : niveau **Critique** à partir de **six heures** d'interruption non planifiée du flux d'expédition (cas quantifié du pack : > 6 h = 40 % du volume du groupe) ; en deçà — incident résolu sous six heures ou arrêt planifié en fenêtre hors pointe — il reste **Grave**. C'est la borne de l'énoncé d'appétence n°1 du matin.

**Confrontation sources de risque ↔ événements redoutés** — couple 1 → ER1, ER2 ; couple 3 → ER2, **ER7** ; couple 4 → ER4, ER6. **Deux événements Critique restent sans source de risque retenue** : ER3 (chaîne du froid) et ER5 (réapprovisionnement Santé). Ce n'est pas un oubli : ce sont d'abord des risques d'origine **accidentelle** (défaillance du fournisseur des sondes, panne d'une liaison opérateur, blocage inter-filiales non résolu), que l'approche par conformité couvre mieux que les scénarios. **Recommandation portée en séance 6** : réintégrer un couple « fournisseur des sondes compromis » pour ER3 et un couple « attaquant pivotant Logistique → Santé » pour ER5, avant l'atelier 3.

---

> **Preuves à l'appui** : description de l'étude, 17 actifs liés, audit rattaché, 7 événements redoutés, 5 couples SR/OV dans `translog-b` — feuilles de travail `Seance-5-TP-S5-05-feuille-de-travail-saisie-EBIOS-RM.md` (TP 1) et `Seance-5-TP-S5-06-echelles-et-assemblage-D5.md` (TP 2) ; captures `../3-Evidence/S5-05-*` et `S5-06-*` ; rapport d'étude EBIOS RM généré par l'outil (`S5-06-rapport-etude-EBIOS-RM-ateliers-1-2.jpg`).
