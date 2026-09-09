# Séance 5 — TD (S5-01) : The CISO's briefing — Risk appetite
### Réponses du Groupe 4 (Translog), dans le rôle du RSSI Groupe de MERIDIAN

> Enchaînement de la journée : ce TD du matin **prépare** la proposition d'appétence que la Direction
> Générale fixera ; l'après-midi (TD 2, ateliers 1 et 2 d'EBIOS RM) transforme cette appétence en
> **seuil d'acceptation** matérialisé sur une grille, et alimente le livrable D5. Rien de ce qui est
> écrit ici n'est jetable : les deux énoncés d'appétence de la question 2 entrent tels quels dans D5
> et dans la sous-section 5 de la note de stratégie.

**Vocabulaire** : appétence au risque, tolérance au risque, seuil d'acceptation des risques — au sens
du CM de la séance 5. Filiale sous revue : **MERIDIAN Logistique** (instance `translog-b`).
Besoins de sécurité notés **DICT** (Disponibilité, Intégrité, Confidentialité, Traçabilité).

---

## Rappel du cas

**Mardi, 17h30.** À la sortie de la présentation du rapport d'audit (séance 4), la Directrice Générale
du groupe MERIDIAN retient le RSSI Groupe : *« Votre rapport dit que Logistique fait tourner ses
réseaux industriel et bureautique ensemble, et que Santé a des mots de passe sans vérification en deux
étapes. Le Directeur de Logistique me dit que personne ne touche aux automates en période de pointe, et
que la pointe dure dix mois sur douze. Le Directeur médical de Santé me dit qu'une étape
d'authentification de plus sur un poste de soin, c'est du temps pris au patient. L'Audit interne me dit
que Santé n'a toujours pas remis son registre des comptes d'administration, et qu'on joue avec des
données de patients. Ils ont tous raison, et je ne vais pas arbitrer trente fois par an. Donnez-moi de
quoi poser une règle une bonne fois pour toutes : ce que le groupe accepte, ce qu'il n'accepte pas. Je
veux votre proposition jeudi ; je la porte au Conseil d'Administration. »*

**En main** : le rapport d'audit de la séance 4 (D4) et ses déviations qualifiées par filiale — mots de
passe locaux sans MFA à MERIDIAN Santé, réseaux IT et OT interconnectés à MERIDIAN Logistique, comptes
d'administration partagés à MERIDIAN Éducation, journaux conservés localement à MERIDIAN Territoires ;
la cartographie et le Top 5 des actifs critiques de la séance 2 (D2) ; la gouvernance de la séance 1 (D1).

**Tâche du matin** : préparer la proposition d'appétence que la Direction Générale fixera, dans les
formes exigées par la gouvernance du groupe.

---

## Les trois notions, posées avant l'exercice

*Reprises du CM de la séance 5 — définitions du guide ANSSI / AMRAE 2019 « Maîtrise du risque numérique —
l'atout confiance » pour les deux premières, définition « pour le module » pour la tolérance (aucun
texte officiel du corpus ne la fixe).*

| Notion | Ce que c'est | Qui la porte | Sa signature |
|---|---|---|---|
| **Appétence au risque** | Le niveau de risque accepté pour soutenir l'activité | Direction Générale, approuvée par l'organe de gouvernance | Stratégique, stable, oriente **toutes** les décisions |
| **Seuil d'acceptation** | La ligne au-dessus de laquelle un risque appelle un traitement | Déduit de l'appétence, appliqué par la gestion des risques | Opérationnel, s'applique **risque par risque** (sur une grille) |
| **Tolérance au risque** | L'écart temporaire accepté entre l'appétence et la réalité | Décidée cas par cas, sous surveillance | **Datée, surveillée, se referme** |

**Réflexe de méthode** (CM) : une appétence se formule **toujours relativement à quelque chose qu'on
accepte de perdre ou de dégrader**, jamais dans l'absolu. « Nous sommes prudents » n'engage à rien.
« Nous acceptons de retarder une livraison, jamais d'exposer un dossier patient » engage à tout.

**Filet de sécurité de l'exercice** : quand une phrase entendue en comité mélange les trois notions,
elle fait presque toujours passer une **tolérance non datée** pour une appétence. C'est exactement le
glissement qu'un RSSI doit rattraper au vol.

---

## Question 1 — Classer trois phrases entendues au dernier Comité Exécutif

*Pour chacune : appétence, tolérance ou seuil d'acceptation, avec une phrase de justification.*

### Phrase A — « Aucun projet ne sera bloqué plus de 48 heures pour une revue de sécurité »

**→ Appétence au risque.** Elle énonce ce que le groupe accepte de dégrader — la complétude d'une revue
de sécurité avant mise en production — au nom d'un bénéfice métier durable, la vitesse de livraison ;
c'est une orientation stable qui vaut pour **tous** les projets, pas une règle appliquée risque par
risque (ce serait un seuil) ni un écart daté qui se referme (ce serait une tolérance).

### Phrase B — « On garde l'interconnexion IT/OT jusqu'à la prochaine fenêtre hors pic, avec surveillance renforcée, et on réexamine au trimestre prochain »

**→ Tolérance au risque.** Les trois signatures y sont : un **écart** assumé entre l'appétence (faible
appétence pour un réseau industriel non cloisonné) et la réalité, une **surveillance** explicite
(« renforcée »), et une **échéance qui referme** (« prochaine fenêtre hors pic », « réexamine au
trimestre prochain »).

### Phrase C — « Tout risque coté au-dessus du niveau élevé sur notre future grille devra être traité avant mise en production »

**→ Seuil d'acceptation des risques.** C'est la traduction opérationnelle de l'appétence : une **ligne
sur une grille de cotation** (« au-dessus du niveau élevé »), au-delà de laquelle un risque identifié
**appelle une décision de traitement** (« traité avant mise en production »), examinée risque par
risque — c'est précisément la grille que le groupe construit cet après-midi (TD 2 / D5).

**Le piège de la question** : les phrases A et C se ressemblent (toutes deux parlent de « mise en
production »), mais A fixe une **orientation** — combien d'assurance on accepte de sacrifier pour aller
vite — et C fixe une **règle de tri** appliquée à chaque risque coté. L'une se décide en Conseil, l'autre
se lit sur une grille.

---

## Question 2 — Deux énoncés d'appétence

*Contrainte : chaque énoncé doit permettre de trancher **au moins une décision concrète que le groupe a
réellement devant lui**, en la nommant. Test appliqué (CM) : un énoncé qui ne fait ni gagner ni perdre
une décision réelle est à réécrire.*

### Énoncé 1 — sur le bien à protéger de MERIDIAN Logistique (l'exécution des flux logistiques, §2 du pack de filiale)

> **MERIDIAN accepte qu'une expédition depuis un entrepôt Logistique soit délibérément interrompue
> jusqu'à quelques heures, dans une fenêtre hors pointe annoncée à l'avance, pour une opération de
> sécurité ou de maintenance planifiée et supervisée. MERIDIAN n'accepte pas une interruption non
> planifiée du flux d'expédition du groupe au-delà de six heures, ni aucune rupture de la chaîne du
> froid du client pharmaceutique, quel que soit le coût de l'éviter.**

- **Ce qu'on accepte de dégrader** : le débit d'un entrepôt pris isolément, pendant une fenêtre publiée.
- **Ce qu'on refuse de perdre** : la continuité d'expédition du groupe au-delà du seuil des six heures
  (un arrêt > 6 h bloque 40 % du volume expédié du groupe — pack §2, §5.5) et la chaîne du froid
  (manquement contractuel direct + risque sanitaire — pénalités de 12 000 €/jour, pack §2).
- **Décision concrète qu'il tranche** : **le calendrier de la mesure M1 du plan d'action correctif de D4**
  — création du VLAN dédié pour les automates de tri d'E2/E3/E4, filtrage en défaut-refus. L'énoncé
  autorise à programmer cette bascule dans la fenêtre hors pic malgré la position du **Directeur de la
  filiale** (« ne veut aucune intervention sur les automates en période de pointe, soit dix mois sur
  douze », pack §3) — celui-là même qui décide des budgets et des contrats, donc la seule position que
  l'énoncé doit pouvoir surmonter ; symétriquement, il interdit de repousser M1 indéfiniment au motif
  qu'elle porte un risque d'arrêt —
  l'arrêt planifié, borné et supervisé est explicitement dans l'appétence.

### Énoncé 2 — transverse au groupe, valable pour les quatre filiales

> **Pour maintenir ses quatre filiales en production sans budget nouveau la première année, MERIDIAN
> accepte de porter un écart de sécurité documenté pendant une durée limitée et surveillée. MERIDIAN
> n'accepte pas qu'une action d'administration ou d'un prestataire sur un système portant un actif
> critique reste non imputable à une personne nommée, ni qu'un contrat de prestation nouveau ou
> renouvelé omette la journalisation par utilisateur nommé et une clause de réversibilité.**

- **Ce qu'on accepte de dégrader / porter** : un écart connu, pendant une durée bornée ; l'absence de
  budget dédié la première année (contrainte posée par la DG — reference pack §7, D1).
- **Ce qu'on refuse de perdre** : l'**imputabilité** des actions à privilèges, et la **maîtrise
  contractuelle** des tiers (réversibilité + traçabilité nominative — parties prenantes de D1).
- **Décision concrète qu'il tranche** : **les conditions de renouvellement du contrat de l'intégrateur
  des automates de Logistique** (aujourd'hui sans clause de réversibilité ni exigence de sécurité, accès
  par box 4G hors réseau supervisé — pack §3, §4, §5). L'énoncé conclut : ce contrat n'est pas reconduit
  en l'état. Par la même règle, l'accès de maintenance distant permanent de l'éditeur du SIH de Santé
  (un identifiant unique partagé entre neuf personnes — reference pack §3) passe à des comptes nommés
  comme condition de sa poursuite.

### Forme exigée par la gouvernance

Les deux énoncés sont **datés** (adoptés et datés par la Direction Générale), **approuvés** par le
Conseil d'Administration, **revus au moins une fois par an** (cadence du CA dans D1) et **amendés,
jamais effacés**, lorsqu'une décision ultérieure les contredit (règle du fil rouge du module). Ils sont
**testables** : on peut vérifier qu'une fenêtre a été publiée, qu'un contrat porte les deux clauses,
qu'un compte est nominatif.

---

## Question 3 — Confronter les quatre déviations d'audit aux énoncés et à l'esprit de l'appétence

*Pour chacune : nettement au-dessus de la ligne (à traiter, pas de tolérance possible), ou relevant
d'une tolérance à formaliser ? Et que manque-t-il encore à cette tolérance pour en être une ?*

| Déviation | Verdict | Lecture au regard des énoncés / de l'esprit |
|---|---|---|
| **Santé — mots de passe sans MFA** | **Mixte** : au-dessus de la ligne pour l'accès distant partagé (9 personnes, 1 identifiant) et le registre des comptes non remis ; **tolérance formalisable** pour la généralisation de la MFA aux postes de soin | Énoncé 2 : un accès de maintenance non imputable à des données de santé = imputabilité inopérante → refus. La directive `PSSI-CADRE-ACC-01` (MFA sur tout accès distant et privilège) est déjà codifiée : sur ce périmètre, il n'y a rien à tolérer. En revanche, la MFA sur chaque ouverture de session applicative d'un poste de soin a un coût opérationnel réel (l'objection du Directeur médical) : déploiement priorisé acceptable. |
| **Logistique — réseaux IT et OT interconnectés** | **Tolérance à formaliser** | Énoncé 1 : l'interconnexion est le chemin par lequel une compromission bureautique atteint les automates et le WMS — donc le chemin vers l'arrêt d'expédition non planifié > 6 h que l'appétence refuse. Mais le cloisonnement lui-même exige une fenêtre planifiée : on ne coupe pas ce soir. C'est mot pour mot la phrase B de la question 1. D4 a déjà nommé M1 (12/7/2027, hors pic) et M2 (schéma réseau + avis d'architecture, 8/12/2026). |
| **Éducation — comptes d'administration partagés** | **Au-dessus de la ligne** | Énoncé 2 : « personne ne peut dire qui a fait quoi » entre deux filiales partageant un annuaire = imputabilité inopérante, et une compromission d'un côté se propage à l'autre (dépendance inter-filiales n°2 du reference pack). Le correctif (comptes nommés dans un annuaire qui existe déjà) est un travail de procédure, à coût quasi nul : la contrainte « sans budget nouveau » ne le couvre pas. |
| **Territoires — journaux conservés localement** | **Mixte** : **tolérance formalisable** pour la centralisation vers le SOC ; **au-dessus de la ligne** pour l'absence de procédure de notification sous 24 h | Énoncé 2 : aucune détection ni analyse post-incident sur un système à données citoyennes → refus sur le principe. Mais le SOC du groupe est « en montée en charge » (2 filiales sur 4 y envoient leurs journaux) : l'embarquement de Territoires est un vrai projet. Les journaux **existent** localement six mois (atténuation partielle). La procédure de notification sous 24 h à la collectivité, elle, ne coûte rien et relève de la parole donnée au client : à traiter maintenant. |

### Ce qui manque à chaque tolérance pour en être une

Aucune des quatre déviations n'est aujourd'hui **exprimée** comme une tolérance : ce sont des **écarts
non datés**. Une tolérance, au sens du CM, a trois signatures — **datée / surveillée / propriétaire
nommé** — plus une **mesure compensatoire intérimaire**. Application :

- **Santé (MFA généralisée)** : il manque *tout* — une échéance, un propriétaire nommé, un indicateur
  suivi (le % de comptes à privilèges couverts par la MFA, qui est exactement la métrique de
  vérification de `ACC-01` dans D1), et une mesure compensatoire le temps du déploiement (isoler du
  réseau bureautique les machines d'analyse et consoles d'imagerie, aujourd'hui sur la plage IP
  bureautique).

- **Logistique (IT/OT)** : c'est la seule partiellement formalisée par D4, et il lui manque encore :
  1. **la surveillance pendant l'écart** — le SOC ne reçoit rien des automates, de la box 4G ni du WMS
     lui-même : on tolérerait un écart qu'on ne surveille pas (recommandation 5 de D4). Une tolérance
     sans surveillance n'est pas une tolérance.
  2. **une échéance qui referme vraiment** — « 12/7/2027, hors pic » est une cible adossée à une
     fenêtre, pas un engagement ferme avec escalade si la date est manquée ; et des mesures
     compensatoires d'ici là (durcir le point d'interconnexion unique, restreindre et journaliser la
     box 4G).
  3. **un propriétaire qui engage les deux côtés** — la box 4G a été installée par l'Exploitation
     précisément pour ne plus dépendre de la DSI (pack §3) ; le porteur de la tolérance doit avoir
     autorité sur le réseau de l'Exploitation.
  4. **ne pas laisser la tolérance réseau couvrir le secret du compte de service** WMS↔automates
     (même mot de passe sur six entrepôts depuis 2019, en clair — pack §5.3, `LOG-SA-04`, écart A.5.17
     de D4) : celui-là est au-dessus de la ligne, il est traité par M3 (8/11/2026).

- **Éducation (comptes partagés)** : si quelqu'un tentait d'en faire une tolérance, il lui manquerait
  là aussi tout — aucune échéance, aucun propriétaire disposant d'un mandat inter-filiales (le DSI
  mutualisé « parle pour les deux sans mandat écrit »), aucune mesure compensatoire. C'est pourquoi ce
  n'est pas une tolérance : c'est un écart à fermer, comptes nommés et compte partagé désactivé à date
  proche.

- **Territoires (journaux)** : pour la centralisation, il manque une échéance adossée au plan de montée
  en charge du SOC, un propriétaire des deux côtés (RSSI Groupe pour le SOC, DSI de Territoires pour la
  source — `PSSI-CADRE-JRN-01`), une mesure intérimaire (vérifier l'intégrité et la durée de rétention
  locale ; **et** la procédure de notification sous 24 h en place dès maintenant), et un indicateur
  suivi (% du périmètre Territoires dont les journaux remontent au SOC).

---

## Question 4 — Attribuer les rôles pour jeudi, et repérer le piège de posture

*Qui fixe l'appétence, qui l'approuve, qui valide sa déclinaison budgétaire, et que reste-t-il
exactement entre les mains du RSSI Groupe ? La gouvernance de la séance 1 (D1, reference pack §« ce qui
existe / n'existe pas ») donne la réponse.*

| Acte | Instance | Cadence | Justification (gouvernance S1) |
|---|---|---|---|
| **Fixe** l'appétence | **Direction Générale** | Mensuelle | « La Direction Générale fixe et propose l'appétence » (D1). C'est sa proposition, jeudi. |
| **Approuve** l'appétence | **Conseil d'Administration** | Annuelle (+ saisine sur incident majeur) | « Le CA approuve l'appétence au risque et les orientations pluriannuelles » (D1). La DG l'a dit : « je la porte au Conseil ». |
| **Valide** la déclinaison opérationnelle et budgétaire | **Comité Exécutif** | Trimestrielle | « Le ComEx valide la déclinaison de la PSSI-cadre, arbitre budgets et priorités » (D1) ; il est **A** sur l'arbitrage des budgets et projets sécurité (matrice RACI de D1). |

### Ce qui reste entre les mains du RSSI Groupe

1. **Rédiger la proposition** (les deux énoncés et leur justification) — le travail de ce matin.
2. **Déduire le seuil d'acceptation** de l'appétence et lui donner une grille — le travail de cet
   après-midi (TD 2, échelles de D5).
3. **Décliner l'appétence en directives** `PSSI-CADRE` (`ACC`, `INC`, `JRN`, `COR`) et les garder
   testables.
4. **Tenir le registre des tolérances** : chacune datée, surveillée, avec un propriétaire nommé ;
   signaler les dérives au ComEx (trimestre) et à la DG (mois).
5. **Arbitrer les conflits réellement inter-filiales** *à l'intérieur* de la règle — véto suspensif
   `ARB-01` sous 72 h (D1), par exemple sur la reprise du flux Logistique↔Santé. Pas les arbitrages
   internes à une filiale : ceux-là, le seuil les tranche sans réunion.

**Ce qui n'est pas entre ses mains** : fixer l'appétence ; **accepter le risque résiduel** (c'est la
Direction Générale — le guide EBIOS RM le rappelle via le TD 2 : « il est indispensable d'identifier la
personne responsable d'accepter les risques résiduels ») ; administrer un système ; décider de ce qui
est traité.

### Le piège de posture dans la phrase de la DG

*« Donnez-moi de quoi poser une règle une bonne fois pour toutes […] je ne vais pas arbitrer trente
fois par an. »*

La DG propose au RSSI de lui tendre **à la fois le stylo et la signature** — de devenir *lui-même* la
règle. S'il l'accepte :

- il **excède son mandat** : le RSSI Groupe *propose et informe*, il ne *fixe* pas (exclusion explicite
  de D1) ;
- il devient de fait **celui qui accepte le risque** : chaque incident futur se lira « la règle du RSSI
  a échoué », et les dirigeants seront spectateurs de leur propre risque ;
- il détruit la seule propriété qui fait tenir une appétence sous le feu — **l'appropriation visible par
  la direction** (c'est toute la leçon Norsk Hydro, question 5).

Deux pièges secondaires dans la même phrase : **« une bonne fois pour toutes »** — une appétence est
stable, pas figée : elle est revue chaque année et amendée (avec une phrase de justification) quand une
décision la contredit ; **« trente fois par an »** — l'appétence ne supprime pas l'arbitrage, elle en
convertit l'essentiel en simple application du seuil (aucun arbitrage), et ne laisse que le résidu
inter-filiales, que le RSSI prépare et que le ComEx ou la DG tranchent.

**La posture du RSSI jeudi** : « J'apporte la proposition ; vous la fixez, le Conseil la signe ; ensuite
je tiens le seuil et l'arbitrage *à l'intérieur* de la ligne que vous avez tracée. »

---

## Question 5 — Analyser la décision de Norsk Hydro (2019) avec le vocabulaire du matin

*Rappel du cas (CM S5) : producteur d'aluminium norvégien frappé par un rançongiciel en 2019 ; la
direction refuse de payer, bascule la production en mode manuel, communique publiquement jour après
jour ; impact financier estimé entre 250 et 300 millions de couronnes norvégiennes pour le 2ᵉ trimestre
2019.*

### (a) L'appétence implicite révélée par le refus de payer, en deux phrases

> La direction de Norsk Hydro avait une appétence **nulle** pour deux issues qu'elle jugeait créer un
> précédent inacceptable — financer une organisation criminelle, et abandonner à un tiers le contrôle
> de ses données et du calendrier de sa propre reprise —, quel qu'en soit le prix.
>
> Elle avait, en échange, une appétence **délibérée et assumée** pour un coût opérationnel et financier
> très lourd mais **borné et mesurable** — production en mode manuel, 250 à 300 millions de couronnes
> sur un seul trimestre — et pour une **transparence publique totale** sur l'incident, parce que ce coût
> était fini et n'hypothéquait pas l'avenir.

### (b) À quoi cette décision aurait ressemblé, improvisée sans appétence préalable

- **Décidée en quelques heures, sous la contrainte**, par les personnes présentes dans la salle, avec la
  **demande de rançon comme seul chiffre** sur la table et le coût du mode manuel encore inconnu : le
  biais naturel est de **payer**, parce que payer paraît moins cher, plus rapide et plus discret qu'un
  repli manuel dont personne n'a borné le coût.
- **Communication défensive et intermittente**, et non quotidienne et ouverte, parce que personne
  n'aurait convenu à l'avance que la transparence était acceptable.
- **Chaque étape suivante rejouée en interne** (« aurait-on dû payer ? »), faute de ligne directrice
  antérieure à laquelle rapporter la décision : lent, incohérent, difficile à défendre après coup.

**Ce que la leçon dit** : l'appétence de Norsk Hydro « était connue avant la crise, et elle a rendu
possibles des décisions rapides pendant la crise ».

**Report sur MERIDIAN Logistique** : c'est exactement pourquoi la DG doit fixer et le Conseil approuver
l'appétence **maintenant**, avant le prochain arrêt du WMS. Celui d'avril s'est passé sans règle —
« chacun a appelé qui il pouvait, personne n'a tenu de chronologie » (pack §2, §5.6) — et la question
que la Direction Générale a posée après cet arrêt, « si ça s'arrête pendant six heures, qui appelle qui,
et qui décide de prévenir le client ? » (pack §7), est mot pour mot une question d'appétence convenue à
l'avance.

---

## Auto-évaluation (grille officielle du TD)

| Critère | Niveau atteint |
|---|---|
| **Q1 — définitions** | Trois classements justifiés en une phrase chacun, avec le piège A/C explicité (orientation vs règle de tri) et le renvoi de C à la grille de l'après-midi |
| **Q2 — deux énoncés** | Un énoncé sur le bien de §2 (exécution des flux) et un énoncé transverse aux quatre filiales, chacun formulé **relativement à ce qu'on accepte de dégrader**, chacun nommant **une décision concrète du groupe** qu'il tranche (calendrier M1 ; renouvellement du contrat intégrateur), et la forme de gouvernance (daté, approuvé CA, revu annuellement, amendé jamais effacé) |
| **Q3 — confrontation** | Les quatre déviations qualifiées (au-dessus de la ligne / tolérance à formaliser, dont deux verdicts mixtes assumés), chacune lue au regard d'un énoncé nommé, et le manque de chaque tolérance décliné sur les trois signatures du CM (datée / surveillée / propriétaire) + mesure compensatoire |
| **Q4 — rôles + piège** | Trois actes attribués à trois instances avec la cadence et la justification D1 ; cinq prérogatives conservées par le RSSI Groupe et trois qui lui échappent (dont l'acceptation du risque résiduel) ; piège de posture nommé (stylo + signature) avec ses deux pièges secondaires |
| **Q5 — Norsk Hydro** | Appétence implicite en deux phrases (refus / contrepartie assumée), scénario de l'improvisation en trois effets, report explicite sur l'arrêt WMS d'avril et la question §7 du pack |

*Chaque case vise la colonne « Excellent » de la grille officielle — à confronter en séance avec le
corrigé de référence du module (replié dans l'énoncé, « cliquer pour révéler »).*

---

> **Suite immédiate (après-midi)** : les deux énoncés de la question 2 entrent dans le livrable D5
> (atelier 1, socle de sécurité et événements redoutés) ; le seuil d'acceptation de la question 1.C
> prend forme sur les échelles de vraisemblance et de gravité construites au TD 2 ; la confrontation de
> la question 3 alimente la sous-section 5 de la note de stratégie (« les événements redoutés qui
> justifient l'effort »).
