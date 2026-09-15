# Feuille de travail — Séance 8, TP 1 (S8-05) : évaluation des clauses 4-10 et déclaration d'applicabilité

**Remplie à l'observé**, après saisie réelle dans `translog-b` (évaluation *« MERIDIAN - ISO/IEC 27001:2022
- initial assessment »*, `0f757e40-a51a-4563-9eb2-3ccd18c31d02`). Mode opératoire :
`PLAN-Seance-8-TP-S8-05-evaluation-clauses-et-SoA.md`.

---

## 1. État initial vérifié (Step 1)

Compteurs conformes à l'attendu : **123 exigences évaluables**, **93 contrôles d'annexe A**. Le bloc
`core - Clauses` était à 0 % partout (résultat non évalué, progression à faire) sur ses 30 exigences.
Le bloc `annex-a` portait déjà les statuts de la séance 4 : 9 non conformes, 2 partiellement conformes,
82 non évalués (dont A.6.3, laissé sans preuve dans un sens ou dans l'autre par D4).

> **Réserve de méthode** : cet état initial a été vérifié à l'écran (tree du composant, compteurs lus)
> mais **pas capturé en image avant le début de la saisie** — la séance a enchaîné directement sur
> l'évaluation des clauses. Ce n'est pas la pratique des séances précédentes (qui capturent l'« avant »
> avant de saisir) ; assumé ici, sans conséquence sur le fond puisque les comptes de départ sont vérifiés
> et cités ci-dessus.

## 2. Les 30 exigences des clauses 4 à 10 — saisies conformes au plan

Toutes réglées à **Status = Done**. Résultats obtenus, comptés dans l'outil (badge de synthèse du bloc
`core - Clauses` : `2` compliant, `8` non compliant, `20` partiellement compliant, `0` non évalué) :

- **Compliant (2)** : 6.1.2, 6.1.3 — l'appréciation et le traitement des risques sont la pièce la plus
  fraîche et la plus complète du dossier (D5, D7).
- **Non compliant (8), chacune avec son observation** : 7.2 (compétence), 7.3 (sensibilisation), 7.5.1
  (information documentée, général), 7.5.3 (maîtrise de l'information documentée), 9.1 (mesure et
  surveillance), 9.3.1/9.3.2/9.3.3 (revue de direction, ses trois sous-clauses). Cinq des huit portent sur
  les deux clauses que le CM annonçait comme les plus faibles — support (7) et évaluation des performances
  (9) — confirmé par la saisie, pas supposé.
- **Partially compliant (20)** : le reste — 4.1-4.4, 5.1-5.3, 6.1.1, 6.2, 6.3, 7.1, 7.4, 7.5.2, 8.1-8.3,
  9.2.1, 9.2.2, 10.1, 10.2.

Aucune clause laissée à *not assessed*, aucun *not applicable* saisi sur une clause — les deux interdits de
l'énoncé sont tenus.

## 3. Les 15 contrôles d'annexe A investigués — saisis conformes au plan

Comptes finaux lus sur le badge de synthèse du bloc `annex-a` : **11** non compliant, **3** partiellement
compliant, **1** non applicable, **78** non évalués (93 − 15 = 78, les contrôles non investigués
aujourd'hui). Détail vérifié contrôle par contrôle contre le plan — aucun écart.

- **Non compliant (11)** : A.5.15, A.5.16, A.5.17, A.5.19, A.5.22, A.5.24, A.6.3, A.8.2, A.8.5, A.8.8,
  A.8.22 — chacun avec sa justification tracée à un constat de D4 (C3, C4) ou à une pièce du pack, et le
  traitement prévu de D7 (`PT-xx`) nommé avec son échéance quand elle existe.
- **Partially compliant (3)** : A.5.9 (cartographie D2, lacunes ouvertes), A.7.4 (aucune surveillance
  physique nommée, à investiguer), A.8.15 (le SOC ne reçoit que le réseau bureautique).
- **Not applicable (1)** : **A.8.28** (Secure coding) — la seule exclusion de la séance, justifiée en trois
  lignes (§4).

## 4. L'exclusion A.8.28 — justification en trois lignes, saisie et vérifiée à l'écran

> **Fait** : aucune activité de développement logiciel interne à MERIDIAN Logistique ; le WMS est un
> progiciel opéré par la tierce maintenance applicative (APPLICA Services, contrat TMA-WMS-2021), aucun
> développeur n'est nommé dans le pack de filiale.
> **Vérification** : confirmée par la DSI de la filiale (trois personnes, sans titre de RSSI) le
> 15/09/2026, sur la base de la cartographie de séance 2 (D2) et du pack de filiale.
> **Réexamen** : à toute prochaine revue de direction, ou dès qu'un projet de développement interne serait
> engagé — déclencheur porté par le processus projet, comme D6 le fait déjà pour les projets impliquant un
> tiers.

Discipline tenue : aucune autre exclusion de confort tentée ; les quatorze autres contrôles applicables,
même ceux qui auraient pu tenter un « pas notre périmètre » (A.7.4 en particulier), sont restés notés et
justifiés plutôt qu'exclus.

## 5. Écart d'outil, le plus net de la séance — observation non persistée au premier passage

**Constat** : la zone *Observation* du formulaire d'édition d'une exigence affiche, par défaut, un
**aperçu rendu** (mode *Preview*) porté par un `<input type="hidden" name="observation">`. Écrire dans ce
champ caché via script, puis soumettre, **ne modifie rien côté serveur** : le POST part bien (200), mais le
champ cache est resynchronisé sur son état d'origine par le composant avant l'envoi effectif — vérifié en
rechargeant la page : le résultat et la progression étaient bien enregistrés, l'observation restait vide.

**Correction** : basculer explicitement en mode **Edit** (bouton dédié) fait apparaître le vrai
`<textarea name="observation">` ; écrire dedans (et déclencher l'événement `input`) persiste correctement,
vérifié à chaque fois par rechargement. **Les 23 observations concernées (8 clauses non compliant + 15
contrôles d'annexe A) ont été reprises une par une avec la bonne méthode** — aucune n'est restée sur le
premier essai raté. Écart documenté ici pour que la séance 9 ne le reproduise pas : **toujours passer par
le bouton *Edit* de l'Observation avant d'y écrire, jamais par le champ cache visible en mode Preview.**

**Second écart, mineur** : le bouton *« Save and next »* et le bouton *« Save and stay »* ne déclenchaient
pas la soumission par un clic Playwright standard (`click()`), sans erreur visible ni requête réseau —
contournement trouvé via `form.requestSubmit(bouton)`, qui a fonctionné à chaque fois et a même déclenché,
la plupart du temps, l'avance automatique vers l'exigence suivante de l'arbre (pratique pour les 30
exigences de clauses, saisies dans l'ordre).

## 5 bis. Troisième écart, trouvé à la relecture — deux observations de séance 3 restées en place

**Constat.** Les exigences **4.1** et **5.3** portaient encore leur observation de la séance 3, celle du
repérage sans notation (« *Repérage sans notation (S3-05 Ex.3)… Statut inchangé (évaluation initiale
vierge) ; 1ere preuve prévue pour l'audit S4* »). Les deux exigences sont désormais à `Done` et
*Partially compliant* sur des pièces de séances 1 à 8 : l'observation affirmait donc, dans l'outil, que
l'évaluation était vierge, à côté d'un résultat qui prouve le contraire. Un auditeur qui ouvre l'instance
lit l'observation avant le badge. Les dix-huit autres exigences partiellement conformes ne portaient,
elles, aucune observation — l'incohérence ne touchait que ces deux-là, héritées et non réécrites.

**Correction.** Les deux observations ont été reprises sur les pièces réellement disponibles, et la
persistance vérifiée par rechargement (méthode du §5 : bouton *Edit* d'abord, jamais le champ de
prévisualisation) :

- **4.1** — contexte décrit par D1, D2 et D3 ; partiellement conforme parce que le contexte n'est pas tenu
  comme un processus (aucune revue périodique) et que le périmètre qui en découle n'a été formalisé
  qu'aujourd'hui, en D8.
- **5.3** — rôles et autorités portés par la matrice RACI de D1 et les propriétaires nommés de D2 ;
  partiellement conforme parce que la filiale n'a pas de RSSI et que trois zones du pack §3 (WMS, réseau
  industriel, télématique) restent non arbitrées.

**Aucun compte ne bouge** : ni résultat ni progression n'ont été touchés, les compteurs du §6 sont
inchangés après correction (revérifiés à l'écran). Captures
`../3-Evidence/S8-05-clause-4-1-observation-reprise-seance-8.jpg` et
`../3-Evidence/S8-05-clause-5-3-observation-reprise-seance-8.jpg`.

> **Règle à tenir en séance 9** : une exigence dont le résultat change doit voir son observation relue.
> Une observation héritée d'une séance antérieure n'est pas neutre — elle date le jugement, et un
> jugement daté d'avant le résultat qu'il accompagne est un écart de traçabilité.

## 6. Comptes finaux vérifiés à l'écran (donuts de synthèse de l'évaluation)

- **Compliance** : 1,63 % compliant (2/123) · 15,45 % non compliant (19/123) · 18,70 % partiellement
  compliant (23/123) · 0,81 % non applicable (1/123) · 63,41 % non évalué (78/123).
- **Progress** : 36,59 % *Done* (45/123 — les 30 clauses + les 15 contrôles investigués) · 63,41 % *To do*.

Chiffres cohérents avec les comptes ligne à ligne des §2 et §3 (30 + 15 = 45 exigences touchées).

## 7. Captures produites

Dans `../3-Evidence/`, préfixe `S8-05-` :

- `S8-05-etat-final-donuts-compliance-et-progression.jpg` — vue de synthèse de l'évaluation, donuts
  compliance/résultat étendu/progression.
- `S8-05-clauses-4-a-10-completees-30-exigences.jpg` — détail des clauses 4 et 5, résultats et
  progression *Done* visibles.
- `S8-05-annexe-A-declaration-applicabilite-15-controles.jpg` — bloc `annex-a` et sous-groupe `A.5`,
  compteurs par résultat visibles sur les badges de synthèse.
- `S8-05-A8-28-exclusion-secure-coding-justification-3-lignes.jpg` — détail du contrôle A.8.28, résultat
  *Not applicable* et justification en trois lignes.
- `S8-05-clause-4-1-observation-reprise-seance-8.jpg` et `S8-05-clause-5-3-observation-reprise-seance-8.jpg`
  — les deux observations de séance 3 reprises (§5 bis), résultat et progression inchangés à l'écran.

## 8. Ce qui reste dû

Les 78 contrôles d'annexe A non investigués aujourd'hui — temps de projet supervisé, si le groupe va
jusqu'au bout de la déclaration d'applicabilité. **Priorité d'investigation arrêtée en TP 2** : les huit
contrôles que le plan de traitement de D7 rapproche déjà d'une mesure sans qu'ils soient évalués (A.5.20,
A.5.30, A.5.37, A.8.13, A.8.16, A.8.20, A.8.24, A.8.32), A.5.37 en tête — seul ancrage du traitement d'ER7.

> **Fait depuis** : le TP 2 de l'après-midi (Step 4 de l'énoncé — lecture du profil, message pour la
> direction, livrable **D8** et sous-section 8 de la note de stratégie) est **rédigé**, voir
> `D8-declaration-d-applicabilite.md` et `../../../Piece-1-Strategy-note/MERIDIAN-strategy-note.md`.
