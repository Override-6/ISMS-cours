# Bureau du RSSI — séance 7

**Question du jour** : *« Combien tout cela va nous coûter, et surtout, combien coûte le fait de ne rien
faire ? »* — le Directeur Financier du holding, en marge du Comité Exécutif, après le bilan de mi-parcours
transmis à la fin de la séance 6.

**Consigne** (format constant depuis la séance 4) : une page écrite, **individuelle**, par étudiant,
déposée dans le dossier de la séance, transposée à MERIDIAN Logistique et close par une recommandation à la
direction. Note individuelle — 10 points sur les neuf séances, coefficient 1.

| Étudiant | Fichier | État |
|---|---|---|
| Miguel Monereo | `S7-bureau-du-RSSI-Miguel-Monereo.md` | 🟢 **fait** — angle 1 (le chiffre qui manque est le constat ; financer d'abord le test de restauration) |
| Maxime | `S7-bureau-du-RSSI-Maxime.md` | 🟢 **fait** — angle 2 (l'asymétrie des deux nombres ; la sécurité entre dans le régime commun), clos sur l'angle 3 (ce que Mærsk ne prouve pas) |

`Seance-7-TD-S7-01-chiffrer-le-cout-de-l-inaction.md` — le **compte rendu collectif** du TD (les trois
questions guidées), conservé comme matière de travail. **Ce n'est pas le bureau du RSSI** : il est collectif
et bien plus long qu'une page. C'est la matière première des deux pages individuelles, exactement comme aux
séances 4, 5 et 6.

**Source** : `../../../../S7 - Sources/TD 1/The CISO's Desk_ Quantifying the Cost of Inaction _ Lockbay Academy.pdf`
(énoncé ; corrigé et barème repliés dans la page, « cliquer pour révéler »). Corpus mobilisé : pack de
filiale §2, §4, §5, §6 · reference pack §3, §5, §7 · D4 (constats C3, C4, recommandations), D5 (échelles,
couples SR/OV, événements redoutés), D6 (écosystème coté, scénarios stratégiques) · CM de la séance 7
(processus ISO/IEC 27005:2022).

## Les trois notions du matin

| Notion | En une phrase | Sa limite |
|---|---|---|
| **Coût de l'inaction** | L'ensemble des pertes plausibles que l'organisation supporterait si un risque identifié se réalisait sans que rien n'ait été investi pour le réduire | C'est une **estimation de plausibilité**, pas une prédiction ; un RSSI qui promet un chiffre exact perd sa crédibilité à la première contre-question |
| **Décomposition de l'impact financier** | Quatre composantes documentables : **interruption d'activité**, **remédiation**, **sanctions et règlements**, **atteinte à la confiance** | La quatrième ne se chiffre jamais complètement — les communications financières ne la détaillent pas |
| **Justification d'investissement** | Trois pièces : le scénario du registre · le coût plausible de l'inaction (documenté, daté, sourcé, en fourchette) · le coût du traitement, **build (CAPEX)** distingué du **run (OPEX)** | Elle **ne calcule pas un retour sur investissement** : la sécurité produit des incidents évités, qui ne se mesurent pas |

**Les références chiffrées de l'exposé**, et rien d'autre : Mærsk **250-300 M$** (Transport & Logistics,
T3 2017, NotPetya) · Norsk Hydro **~800 M NOK** (mars 2019) · Equifax **≥ 575 M$** (règlement 2019,
~147 millions de personnes) · France Travail **5 M€** (CNIL, janvier 2026, fuite de 2024 pouvant toucher
43 millions de personnes) · IBM *Cost of a Data Breach* — France **3,85 M€** (2024), monde **4,44 M$** et
cycle de vie moyen **241 jours** (2025).

**La fourchette, en quatre termes** : *perte par jour d'arrêt × durée + remédiation + sanction éventuelle.*
La perte par jour vient du pack ; la durée se prend **deux fois** (basse = la panne déjà vécue, haute = ce
que les cas documentés montrent) ; la remédiation se prend au dossier, sinon la moyenne IBM sert d'ordre de
grandeur **dit comme tel** ; la sanction ne s'ajoute que si des données personnelles sont en jeu. **Ce qui
manque au dossier se demande nommément au Directeur Financier** : une fourchette honnête dit ce qu'elle ne
sait pas.

**Réflexe de méthode** — chaque chiffre porté devant une direction répond à trois questions en une phrase :
*de qui vient-il · de quelle année date-t-il · à quoi de notre registre se rattache-t-il.* Un chiffre qui
échoue à l'une des trois n'entre pas dans le dossier.

## Les trois questions du cas

1. **Rattacher** les références de coût aux scénarios du registre : un tableau, une ligne par scénario
   (indisponibilité de l'actif critique · vol ou fuite de données personnelles · malveillance ou erreur
   interne), avec la référence documentée qui l'éclaire le mieux, la nature du coût, le montant, l'année, la
   source, et une phrase qui dit *pourquoi celle-là*. **Quand aucune référence ne colle, l'écrire dans la
   ligne : c'est une réponse.**
2. **Rédiger** l'argument d'investissement pour le scénario d'indisponibilité de l'actif critique : une
   phrase de réponse au Directeur Financier, puis trois pièces — le scénario et son chemin ; le coût
   plausible de l'inaction en fourchette basse et haute, aux quatre termes du cadrage, les termes non
   chiffrés nommés comme **données à demander** ; la nature du traitement de l'après-midi, build et run
   distingués, **sans le chiffrer encore**.
3. **Répondre** au contre-interrogatoire : les trois objections du Directeur Financier telles qu'il les
   dirait, et pour chacune une réponse en une phrase, appuyée sur une pièce du pack ou sur l'échelle de
   gravité du groupe, **jamais sur une promesse**.

**Minutage de l'énoncé** : 15 min pour Q1, 20 min pour Q2, 10 min pour Q3.

## Barème de la page, sur 10

*Grille reprise du format des séances précédentes — à confirmer avec le corrigé officiel replié dans
l'énoncé.*

| Bloc | Points | Détail |
|---|---|---|
| Exactitude et pertinence | **4** | chaque chiffre répond aux trois questions (source, année, scénario du registre) · aucun chiffre qui ne vienne de l'exposé ou du pack · les quatre composantes de l'impact distinguées · les absences documentées comme des absences |
| Posture de RSSI | **3** | une recommandation explicite à la direction · une fourchette honnête plutôt qu'une précision suspecte · aucun retour sur investissement promis · les données manquantes demandées **nommément** au Directeur Financier |
| Rédaction | **3** | une page, lisible par un dirigeant non technicien · sigles définis (WMS, TMA, SOC, CAPEX, OPEX, RTO) · des phrases prononçables en comité |

## Angles disponibles pour les deux pages

Les deux étudiants prennent des **angles distincts** — c'est la règle du dossier depuis la séance 1.

1. **Le chiffre qui manque est le constat.** La fourchette basse s'arrête à 12 000 €/jour parce que le
   groupe ne sait ni son chiffre d'affaires expédié par jour, ni son RTO (les sauvegardes n'ont jamais été
   restaurées), ni le coût d'un avoir sur erreur de préparation. Angle : *ne pas savoir chiffrer sa perte
   est déjà une défaillance de pilotage*, et la première mesure à financer est le test de restauration —
   parce qu'il est le seul qui transforme une borne inconnue en nombre.
2. **L'asymétrie des deux nombres.** Le Directeur Financier compare un coût certain et modeste à une perte
   incertaine et lourde ; c'est un arbitrage qu'il fait déjà sur tous ses autres risques (assurance,
   change, créances). Angle : *la sécurité ne demande pas un régime d'exception, elle demande d'entrer dans
   le régime commun* — et ce qu'elle apporte en échange, c'est une fourchette datée et sourcée, pas une
   alarme.
3. **Ce que Mærsk ne prouve pas.** Le facteur d'échelle entre un armateur mondial et six entrepôts en
   France est de plusieurs ordres de grandeur : le chiffre ne se transpose pas, seul le **mécanisme** se
   transpose. Angle : *la discipline de sourçage est ce qui protège le RSSI en comité* — un chiffre mal
   transposé se retourne contre celui qui l'a cité, et l'exagération coûte plus cher que la prudence.
4. **La quatrième composante, celle qu'on n'écrit pas.** Interruption, remédiation et sanctions se
   chiffrent ; la confiance, non — et c'est pourtant elle qui décide du renouvellement du contrat
   pharmaceutique, dont le questionnaire de sécurité est déjà annoncé (pack §2). Angle : *le coût de
   l'inaction le plus lourd pour Logistique n'est pas dans la fourchette*, et il se traite avant l'audit
   client, pas après.

Une page, sigles développés au premier emploi, recommandation explicite en clôture.

---

> **Suite de la journée** : CM *Le processus ISO/IEC 27005:2022 et ses étapes* → TD 2 (matrices de cotation
> et options de traitement, `../4-Working-notes/`) → TP 1 (atelier 4 détaillé et registre de risques dans
> `translog-b`) → TP 2 (plan de traitement, risque résiduel — livrable **D7**, 5 points — et sous-section 7
> de la note de stratégie).
