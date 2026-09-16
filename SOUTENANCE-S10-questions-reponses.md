# Soutenance — banque de questions et réponses

**Séance 10 · 17 septembre 2026** · Groupe 4 « Translog » · MERIDIAN Logistique
**Les douze minutes de questions** · complément de [`SOUTENANCE-S10.md`](SOUTENANCE-S10.md) §6

> Ce document développe et étend la banque de treize questions de `SOUTENANCE-S10.md` §6.3. Les questions
> qui y figuraient déjà sont reprises ici, enrichies de leur preuve exacte, et signalées **★**.

---

## Mode d'emploi

### Les trois temps d'une réponse

> **1. La position** — une phrase, affirmative, sans « je pense que ».
> **2. Le chiffre** — celui du dossier, jamais un autre.
> **3. La pièce** — où le jury peut le vérifier, nommée.

**30 à 45 secondes. Jamais plus.** Une réponse d'une minute trente est une réponse qui doute.

### Ce que le jury va chercher

Le panel **a le dossier sous les yeux**. Il ne posera donc pas de question sur ce que nous exposons le
mieux. Trois familles de questions sont quasi certaines :

| Famille | Pourquoi | Où elles portent |
|---|---|---|
| **Les endroits où le dossier est faible** — et il les nomme lui-même | Un dossier qui déclare ses trous invite à les explorer ; c'est le prix de l'honnêteté, et il est payant | 16,1 % de couverture · l'auto-évaluation · le thème physique à zéro · les trois écarts sans mesure |
| **Les endroits où le dossier est surprenant** | Une décision inhabituelle appelle sa justification | Périmètre de certification étroit · zéro dérogation · aucun risque fermé · une personne dans le Top 5 |
| **Les endroits où deux pièces ne disent pas la même chose** | C'est ce que les 6 points de « dossier de preuve » sanctionnent | **`M1`/`M2`/`M4` de `D4` contre `PT-03`/`PT-06`/`PT-02` de `D7`** — voir §8, question 52 |

### Quatre réponses interdites

1. **« Je ne sais pas »**, seul. La forme qui rapporte : *« ce n'est pas tranché aujourd'hui, c'est le point
   ouvert n° 2, il se lève au test de restauration du 14 novembre. »* Un point ouvert daté vaut mieux qu'une
   réponse inventée.
2. **Improviser un chiffre.** Tout chiffre cité doit exister dans le dossier que le jury a en main. Voir
   l'aide-mémoire du §12.
3. **Laisser le binôme répondre à sa place** sur sa partie déclarée. C'est exactement ce que la question
   individuelle mesure — la moitié du coefficient individuel.
4. **Se justifier.** Une décision argumentée se **rappelle**, elle ne se défend pas. « Nous avons choisi X
   parce que Y » — pas « c'est vrai que peut-être on aurait pu… ».

### La formule de repli universelle

Quand la question sort du dossier :

> *« Cela n'est pas dans le dossier aujourd'hui. Ce que nous pouvons dire, c'est [le fait le plus proche que
> nous avons]. Et c'est exactement le type de donnée que nous demandons à [la Direction Financière / le
> prestataire / le fournisseur], plutôt que de l'estimer nous-mêmes. »*

---

# 1. Le message, le diagnostic, la première minute

**1. « Résumez-moi votre situation en une phrase. »**
Des fondations documentées, une application non prouvée, des angles morts nommés. Concrètement : nous savons
maintenant ce que nous devons protéger et ce qui nous menace, nous avons chiffré le traitement à 82 000 € par
an, et nous ne sommes pas encore protégés. *Pièce : sous-section 4 de la note de stratégie.*

**2. « Quel est votre risque numéro un ? »**
L'arrêt non planifié de l'expédition au-delà de six heures. Il bloque **40 % du volume expédié de tout le
groupe**, déclenche **12 000 € de pénalités par jour**, et il est crédible : système centralisé sur un seul
site sans secours, sauvegardes jamais restaurées depuis la mise en service, et **un arrêt de ce type a déjà
eu lieu en avril** — sans que personne ne puisse en tenir la chronologie. *Pièce : `D5`, événement redouté le
plus grave.*

**3. « Pourquoi devrais-je vous écouter plutôt que ma DSI ? »**
Nous ne disons pas autre chose que la DSI ; nous disons la même chose en euros de métier et avec une date.
La DSI décrit un réseau non cloisonné ; nous disons que ce réseau non cloisonné est le chemin qui fait passer
un scénario de rançongiciel du théorique au très probable, qu'il coûte 23 000 € par an à refermer, et qu'il
bloque la réponse au client pharmaceutique jusqu'au 14 juin 2027.

**4. « Vous êtes venus me demander de l'argent ? »**
Quatre choses, dont une seule est de l'argent : confirmer le seuil d'acceptation du risque, financer
82 000 € par an, autoriser deux avenants contractuels **avant novembre 2026**, et arrêter le périmètre de la
première certification. Les trois autres ne coûtent rien et deux d'entre elles ont une fenêtre qui se
referme. *Pièce : slide 14 et `SOUTENANCE-S10.md` §5.2.*

**5. « En quoi est-ce mon problème et pas celui de la filiale Logistique ? »**
Parce que l'atteinte déborde la filiale. Les 40 % de volume sont ceux du groupe, pas de la filiale ; le flux
vers MERIDIAN Santé est bloqué depuis trois mois ; et le client pharmaceutique interroge le groupe, pas
l'entrepôt. *Pièce : `D2` §5, dépendances inter-filiales.*

---

# 2. L'argent

**6. ★ « 82 000 €, c'est du build ou du run ? »**
Les deux, et le calcul est dans le dossier : environ **51 000 € d'investissement amorti** par an et
**31 400 € de fonctionnement** annuel. L'investissement initial cumulé est de l'ordre de **180 500 €**,
réparti sur trois ans, dont 123 000 € de coûts fixes. Le taux appliqué est de 500 € par jour-personne.
*Pièce : `D7` §1, colonne par colonne, et l'aperçu budgétaire de `translog-b`.*

**7. ★ « Si je ne signe que la moitié, je prends quoi ? »**
Les deux mesures transversales d'abord, parce que chacune traite plusieurs scénarios à la fois :
**`PT-02`** — comptes nommés et authentification forte pour la tierce maintenance, 9 333 € par an, qui ferme
le compte partagé — et **`PT-03`** — la séparation des réseaux bureautique et industriel, 23 000 € par an.
Puis `PT-04`, le test de restauration à 9 833 €, parce que c'est lui qui borne le haut de notre fourchette.
Le reste glisse d'un exercice. *Pièce : `D7` §1.*

**8. ★ « Votre coût de l'inaction, c'est de la littérature. »**
La borne basse est contractuelle et vérifiable : **12 000 € par jour**, ce sont nos propres pénalités, dans
notre propre contrat. La borne haute est un ordre de grandeur, assumé comme tel, appuyé sur des cas publics.
Et c'est précisément pour la remplacer par un chiffre mesuré que nous demandons le test de restauration au
**14 novembre**. *Pièce : TD 1 de la séance 7, `D7` §1.*

**9. « 12 000 € par jour, ce n'est pas énorme face à 82 000 € par an. »**
C'est le tiers du coût annuel du plan pour **un seul jour** de l'incident que le plan traite. Et les 12 000 €
sont la borne la plus basse possible : pénalités du client pharmaceutique seules, hors perte d'exploitation,
hors remédiation, hors les 40 % de volume du groupe à l'arrêt.

**10. « Quelles références publiques avez-vous utilisées, et pourquoi celles-là ? »**
Chacune est rattachée à une famille de scénarios de notre registre, pas citée pour l'effet : Mærsk
250-300 M$ (2017) et Norsk Hydro ~800 M NOK (2019) pour l'indisponibilité ; France Travail 5 M€ (CNIL, 2026)
et Equifax ≥ 575 M$ pour la fuite de données ; IBM pour l'ordre de grandeur de la remédiation. Et une ligne
**« aucune référence ne colle »**, assumée, pour la malveillance interne. *Pièce : TD 1 de la séance 7.*

**11. « Vos jours-personnes, d'où sortent-ils ? »**
D'estimations, et le dossier le dit colonne par colonne. Là où le dossier de filiale ne donne aucun chiffre,
le coût fixe est posé à 0 € et les jours-personnes sont estimés, **explicitement**. Ce qui n'est pas estimé,
ce sont les pénalités contractuelles et le taux journalier. *Pièce : `D7` §1, note de méthode.*

**12. « Et le coût de la certification elle-même ? »**
Nous ne le proposons pas, délibérément. Nous demandons d'arrêter un **périmètre**, pas d'engager un budget de
certification : aucune date de certificat ni aucun coût de certification n'est promis. Le seul montant engagé
est celui du plan de traitement déjà arrêté. *Pièce : `D8` §4, point 10.*

**13. « Combien de temps-homme le référentiel vous coûte-t-il en interne ? »**
Environ **60 jours-homme la première année**, poste par poste, sur trois hypothèses de productivité écrites
pour être contestées — aucune donnée de ce type n'existe au dossier. *Pièce : `D3` §4.*

---

# 3. Le risque, les scénarios, la méthode

**14. « Pourquoi EBIOS RM et pas une autre méthode ? »**
Parce que c'est la méthode de l'ANSSI, qu'elle part des **valeurs métier** — ce que la filiale perd — et non
des vulnérabilités techniques, et qu'elle traite l'écosystème comme un objet d'analyse à part entière. C'est
ce dernier point qui nous a donné le scénario par le fournisseur, que n'importe quelle approche centrée sur
nos propres serveurs aurait manqué.

**15. « Trois scénarios, ce n'est pas un peu court ? »**
Cinq couples source de risque / objectif visé ont été instruits ; trois sont retenus, **et les raisons des
deux écartés sont écrites**. Sept événements redoutés sont cotés, huit lignes composent le registre. Le
critère n'est pas le nombre, c'est que chaque scénario vise un des cinq actifs critiques identifiés en
séance 2. *Pièce : `D5` §3 et §4.*

**16. « Pourquoi le prestataire des automates n'est-il pas dans vos trois scénarios majeurs ? »**
Il y est, une séance plus tard, et c'est écrit comme un choix de méthode et non comme un oubli : la
sous-section 5 le déclare « tenu en veille et traité en séance 6 avec le reste de l'écosystème ». En
séance 6, il ressort **partie prenante la plus critique de toutes**, cotée 12,0 — au-dessus du prestataire du
WMS à 8,0. *Pièce : note de stratégie §5 et §6, `D6` §4.*

**17. « Comment avez-vous coté la gravité ? Sur quelle base ? »**
Sur des échelles écrites **en termes du groupe**, pas en adjectifs génériques : un niveau de gravité se lit
en volume expédié bloqué, en pénalités contractuelles, en manquement d'audit client. Elles sont posées en
séance 5 et **jamais recréées ensuite** — la séance 7 a été vérifiée mot pour mot contre elles. *Pièce : `D5`,
échelles ; `D7` §0, exigence 3.*

**18. « Une personne dans votre top 5 des actifs critiques ? »**
Oui — le Responsable Exploitation, rang 3. C'est le **seul bien support d'une valeur métier entière**, le
savoir-faire des six entrepôts, qui n'est écrit nulle part. L'arrêt d'avril l'a démontré : personne n'a pu
tenir de chronologie. C'est aussi le seul actif de la liste qu'aucun budget ne remplace après coup — d'où la
mesure `PT-12`, formaliser par écrit l'organisation des six entrepôts. *Pièce : `D2` §6, `D7` `PT-12`.*

**19. « Votre top 5, comment l'avez-vous construit ? »**
Sur un critère en quatre conditions, **écrit avant le classement** : l'actif porte un besoin de sécurité très
important, son atteinte déborde la filiale, une faiblesse connue et actuelle rend cette atteinte plausible
aujourd'hui, et il n'existe aucune substitution rapide. Écrire le critère après le classement, c'est
justifier un résultat déjà obtenu. *Pièce : `D2` §6.*

**20. « Et ce que vous avez écarté du top 5 ? »**
Le local serveur E1 et les entrepôts portent la même valeur que le WMS, mais leur atteinte est plus lente et
plus visible — on la voit venir. Les 300 scannettes sont redondantes. Le prestataire de maintenance est un
risque majeur, mais il se traite par le contrat et son vecteur technique est déjà classé au rang 2. *Pièce :
`D2` §6, dernier paragraphe.*

**21. ★ « Que se passe-t-il si votre analyse a manqué un risque ? »**
La règle de tenue de la cartographie s'applique : tout élément découvert hors inventaire est rattaché à un
propriétaire ou traité **sous trente jours**, et sa découverte est valorisée, jamais sanctionnée. Elle a déjà
servi — deux biens supports découverts en cours d'analyse de risque ont été inventoriés ainsi, c'est la
mesure `PT-13`, échéance 14/10/2026. *Pièce : `D2` §8, `D7` `PT-13`.*

**22. « Pourquoi votre matrice est-elle en 4×4 et pas en 5×5 ? »**
Parce qu'elle est importée telle quelle de la bibliothèque EBIOS RM de l'outil, pas fabriquée par nous. Une
échelle inventée est une échelle qu'on peut ajuster pour obtenir le résultat souhaité. *Pièce : capture de la
matrice, `Session-5/3-Evidence/`.*

---

# 4. Les décisions structurantes

**23. ★ « Pourquoi ISO 27001 et pas un autre référentiel ? »**
Une **règle de veto a été posée avant tout calcul** : est écarté, quelle que soit sa note, tout référentiel
ne couvrant pas simultanément les obligations de Santé, le périmètre industriel de Logistique et une filiale
hors du champ de la réglementation européenne. ISO est le seul à passer ce veto, et le seul à mener à une
preuve opposable au client qui l'exige déjà. *Pièce : `D3` §3.*

**24. « Le ReCyF n'est-il pas plus pertinent, puisque c'est devant lui qu'on vous contrôlera ? »**
C'est la meilleure objection, et elle est écrite dans le dossier comme telle. Notre réponse : le ReCyF est
une version de travail de mars 2026, il est **muet sur une filiale sur quatre**, et on n'érige pas un texte
de travail en colonne vertébrale d'un groupe de 7 700 personnes. L'écart se traite **par correspondance, pas
par un second chantier**, et le ReCyF reste en veille active. *Pièce : `D3` §3, « la meilleure objection et
notre réponse ».*

**25. « Votre classement donne 230 à ISO et 205 au ReCyF. 25 points, ce n'est pas grand-chose. »**
Exactement — et c'est pourquoi la décision ne repose pas dessus. Elle repose sur le veto. Nous l'avons
vérifié en pratique : une erreur de fait corrigée en cours de dossier a fait passer le ReCyF de 195 à 205 et
réduit l'écart de 35 à 25 points. **La recommandation n'a pas bougé.** Un classement qui se renverse à
dix points près n'est pas une décision, c'est un calcul.

**26. « Votre matrice de correspondance vous dispense-t-elle de refaire le travail ? »**
Non, et le dossier l'écrit : **il n'existe aucune présomption générale de conformité**, et notre matrice ne
comporte **aucune ligne « équivalence »**. Une matrice ne transfère rien ; elle impute chaque preuve à
l'obligation qu'elle sert, et montre surtout ce qui reste à produire. *Pièce : `D3` §3.*

**27. ★ « Pourquoi un périmètre de certification aussi étroit ? »**
Parce que le site E4 porte **à la fois** le service du client pharmaceutique **et** des automates de tri sur
un réseau non cloisonné. Certifier large aujourd'hui reviendrait à certifier ce défaut. L'exclusion de
l'automatisation d'E4 est écrite, **datée au 14 juin 2027** — échéance de la segmentation — et reprise dans
la réponse au client. *Pièce : `D8` §1.6 et §3.*

**28. « Vous certifiez donc le minimum pour rassurer un client. »**
Nous certifions ce que le client achète, et rien de plus, parce que nous pouvons le démontrer. L'inverse —
un périmètre large obtenu sur un réseau que nous n'avons pas cloisonné — serait exactement ce que les
certificats se font reprocher. L'extension au reste du groupe reste à étudier, sans date promise.

**29. « Que répondez-vous au client pharmaceutique dès aujourd'hui, avant tout certificat ? »**
Au titre d'une **démarche documentée équivalente** : le référentiel adopté, l'audit initial et le plan de
traitement chiffré. Ce sont les trois pièces, et elles existent. *Pièce : note de stratégie §8 ; TD 1 de la
séance 8.*

**30. « Et si le client exige le certificat, pas la démarche ? »**
Alors la question devient une question de délai et de périmètre, pas de principe : le périmètre proposé est
le sien, et la borne est le 14 juin 2027. C'est précisément pour cela que la demande n° 4 — arrêter le
périmètre — est demandée **immédiatement** et non à la prochaine revue.

---

# 5. Les tiers et le contrat

**31. « Pourquoi le risque tiers occupe-t-il autant de place chez vous ? »**
Parce que nos deux parties prenantes les plus dangereuses sont des tiers — l'intégrateur des automates coté
**12,0** et le prestataire de maintenance du WMS coté **8,0**, seuls au-dessus du seuil de criticité de 4,0
que nous avons posé **avant** de coter. Et parce que le scénario stratégique le plus grave passe par l'un
d'eux plutôt que par notre porte d'entrée. *Pièce : `D6` §4.*

**32. « "Le pivot est signé, pas piraté" — expliquez. »**
C'est la position exacte d'un transporteur européen en 2017 : il n'a pas été piraté, il a installé de bonne
foi la mise à jour d'un fournisseur compromis. 250 à 300 millions de dollars en un trimestre. Notre
prestataire de maintenance a un accès permanent au WMS par un **compte de domaine partagé dont nous ne
connaissons pas le nombre de porteurs** : le même mécanisme est ouvert chez nous, et il est contractuel, pas
technique.

**33. ★ « Le prestataire refuse l'avenant. Vous faites quoi ? »**
Le contrat vient à renouvellement en **novembre 2026** : c'est notre fenêtre de levier, et c'est pourquoi la
demande porte une date antérieure. En cas de refus, l'exigence devient un critère de réversibilité et une
condition du prochain appel d'offres, et **le risque résiduel remonte formellement au comité** — il ne
s'absorbe pas en silence.

**34. « Vos trois exigences contractuelles, pourquoi celles-là ? »**
Journalisation par utilisateur nommé, notification sous 24 heures d'une compromission chez le prestataire, et
réversibilité. Chacune ferme un mécanisme que nous avons constaté : nous ne savons pas qui agit sous le
compte partagé, nous n'apprendrions rien d'une compromission chez lui, et nous ne pourrions pas sortir du
contrat. Elles sont **opposables par la Direction Juridique avant signature** — ce n'est pas un vœu, c'est
une condition de signature.

**35. « Ces exigences coûtent combien ? »**
Rien la première année, et c'est le point : **la règle des trois exigences est une condition de signature,
pas un achat**. Ce qui coûte, ce sont les mesures techniques du registre, et elles sont chiffrées à part.
*Pièce : note de stratégie §6, et l'amendement daté du 14 septembre qui précise cette portée.*

**36. « Comment saurez-vous que le prestataire tient ses engagements après signature ? »**
Par le dispositif de surveillance de `D6` : trois indicateurs, un comité de suivi, une preuve annuelle
demandée, et ce qui reste explicitement à la charge du client. Une exigence contractuelle sans dispositif de
surveillance meurt à la signature. *Pièce : `D6` §3.2.*

**37. « Et l'intégrateur des automates, qui est encore plus critique ? »**
Son contrat ne porte **aucune** exigence de sécurité aujourd'hui — c'est la mesure `PT-06`, avenant au
14/03/2027, plus `PT-05` : raccorder ou supprimer sa liaison 4G, qui est hors du réseau supervisé, échéance
14/12/2026. *Pièce : `D7` §1.*

---

# 6. La gouvernance

**38. « Qui décide quoi, chez vous ? »**
Trois niveaux, chacun avec sa fréquence : le Conseil d'Administration approuve l'appétence au risque
(annuel), la Direction Générale la fixe et la propose (mensuel), le Comité Exécutif arbitre budgets et
priorités (trimestriel), le comité sécurité groupe pilote (mensuel), l'opérationnel exploite (continu), la
cellule de crise décide de l'isolement (sur déclenchement, notification sous 2 h). *Pièce : `D1` partie 2.*

**39. « Votre gouvernance, c'est un organigramme de plus. »**
Chaque élément est écrit **contre un dysfonctionnement nommé du dossier**. Le comité sécurité et le veto
suspensif à 72 h existent parce qu'un flux entre deux filiales est bloqué depuis trois mois sans arbitre. La
règle d'un seul responsable par ligne de la matrice existe parce que l'auditeur interne proposait de gérer le
registre qu'il devait contrôler. Et chaque directive porte sa mesure de vérification, sous le test :
*comment saurait-on qu'elle n'est pas respectée ?* *Pièce : `D1`, colonnes « ce que ce tableau empêche ».*

**40. « Qui signe une acceptation de risque chez vous ? »**
La **Direction Générale du groupe**, au niveau où l'appétence a été fixée. Pas le RSSI. Le dossier écrit la
phrase à ne jamais écrire : *« Risque accepté par le RSSI »* — aucune de nos sept fiches ne porte cette
signature. Le RSSI prépare et propose. *Pièce : `D7` §3.*

**41. « Pourquoi zéro dérogation ? C'est suspect. »**
Parce qu'une dérogation se demande quand un résiduel dépasse l'appétence, et **aucun des huit résiduels ne
dépasse `Moyen`**, qui est notre ligne d'acceptation. Il n'y a donc rien à déroger. Ce n'est pas une absence
de rigueur, c'est une conséquence arithmétique — et nous l'écrivons plutôt que de laisser un auditeur nous
demander pourquoi la case est vide. *Pièce : `D7` §0 exigence 2, et §4.*

**42. « Que fait votre règle d'arbitrage si une filiale passe outre ? »**
`ARB-01` : veto **suspensif** du RSSI Groupe, arbitrage rendu sous 72 heures. Suspendre sans enterrer — c'est
ce qui le rend politiquement acceptable. Et `ARB-03` : toute dérogation validée sous 48 heures, parce
qu'*une dérogation sans circuit devient un droit acquis*. *Pièce : `D1` partie 2.*

---

# 7. Les indicateurs et le pilotage *(séance 9)*

**43. « Comment saurai-je, dans six mois, que tout cela a servi ? »**
Par sept indicateurs, dont **six sont calculables dès aujourd'hui**. Trois répondent directement à vos trois
signatures : la couverture de la déclaration d'applicabilité, les restaurations du WMS testées sur douze
mois, et l'avancement de la séparation des réseaux — celui-là même dont dépend la levée de l'exclusion d'E4.
*Pièce : `D9`.*

**44. « Pourquoi ces sept-là, et pas d'autres ? »**
Parce que **chacun surveille un objectif nommé de la note de stratégie** : la couverture surveille le
périmètre du SMSI, les résiduels au-dessus du seuil surveillent l'appétence, les accès nominatifs de la
maintenance surveillent la règle contractuelle. Un indicateur qui ne surveille aucun objectif est un chiffre
orphelin, si bien construit soit-il.

**45. « KPI ou KRI ? »**
Les deux, et un troisième registre : le jeu mêle délibérément **conformité** (`IND-01`, `IND-02`), **risque**
(`IND-04`, `IND-05`, `IND-06`) et **opérations** (`IND-03`, `IND-07`). Un tableau de bord qui ne contient que
des indicateurs de conformité ne dit rien de ce qui est en train de se dégrader.

**46. « Pourquoi un de vos indicateurs est-il inactif ? »**
`IND-07`, le respect du délai de notification d'incident, est saisi en **brouillon** parce qu'il n'est pas
mesurable aujourd'hui : aucune chronologie d'incident n'existe dans la filiale. Le déclarer non mesurable est
plus utile au comité que de lui donner une valeur plausible — **une case vide se lit trop facilement comme
une case verte**.

**47. « Un indicateur à zéro, c'est bon ou mauvais ? »**
Cela dépend de ce que zéro mesure, et c'est pour cela que chaque fiche porte son **seuil et ce que son
franchissement déclenche**. Zéro restauration du WMS testée sur douze mois est notre pire chiffre ; zéro
risque résiduel au-dessus du seuil est notre meilleur.

**48. « À quelle fréquence comptez-vous me présenter cela ? »**
Au rythme du Comité Exécutif, trimestriel, tel que `D1` l'a fixé. Le relevé, lui, peut être plus fréquent que
la présentation — chaque fiche distingue les deux.

---

# 8. Les questions d'auditeur — la solidité du dossier

**49. ★ « Votre audit, c'est vous qui l'avez fait. »**
Oui, et le rapport le dit en **première section**, pas en note de bas de page : il lui manque l'indépendance.
C'est une auto-évaluation outillée — le premier jeu de faits que la filiale se donne sur elle-même — pas un
audit de certification. Une vérification indépendante est à programmer avant tout engagement de
certification, et `D8` §5 l'inscrit comme tel.

**50. ★ « 15 contrôles sur 93, c'est peu. »**
C'est ce que nous savons mesurer aujourd'hui, et nous affichons **16,1 % en tête de la déclaration** plutôt
que de l'arrondir. Les quinze sont ceux que l'audit initial et le cours désignent comme les plus exposés. Un
taux confortable obtenu sur un périmètre choisi serait moins utile au comité que 16 % assumés. Et les
78 autres ne sont comptés conformes nulle part.

**51. ★ « Zéro exigence évaluée sur le thème physique, alors que vous exploitez six entrepôts et des chambres froides. »**
C'est notre angle mort principal, et il **n'apparaît que parce que nous avons ventilé par thème** — un taux
global de 9 % l'aurait masqué. Il est nommé comme tel dans `D4` §2.1, avec la ventilation à l'appui :
8 % organisationnel, 10 % technologique, **zéro sur quatorze exigences physiques**.

**52. ⚠️ « J'ouvre `D4` et `D7` sur le même sujet et je trouve deux dates différentes. »**
*(La question la plus probable d'un auditeur attentif. À ne pas subir.)*
Exact, sur trois mesures : le cloisonnement des automates (`M1`, 12/07/2027 contre `PT-03`, 14/06/2027),
l'avenant à l'intégrateur (`M2` contre `PT-06`) et le registre nominatif de la maintenance (`M4` contre
`PT-02`). **C'est décrit dans notre journal de corrections, et délibérément laissé ouvert** : `PT-03` est la
mesure large qui contient `M1`, et décréter l'une supersédée effacerait peut-être une distinction réelle
entre le cloisonnement d'un périmètre et la segmentation d'ensemble. **La date qui fait foi est celle de
`D7`**, parce que c'est la lecture la plus récente et la seule chiffrée. `D8` le dit en réserve
méthodologique explicite.
> **Pourquoi cette réponse rapporte** : elle montre que nous avions trouvé l'écart avant le jury, que nous
> savons lequel fait foi, et que la non-correction est une décision et non un oubli.

**53. « Trois de vos contrôles n'ont aucune mesure en face. »**
`A.5.24` gestion des incidents, `A.6.3` sensibilisation, `A.7.4` surveillance physique. C'est écrit dans
`D8` §2.4, dans un tableau intitulé « orphelins », parce que notre plan de traitement traite **les risques du
registre, pas les écarts de conformité**. Les deux premiers entrent au chantier documentaire de la séance 9 ;
le troisième appelle d'abord une investigation site par site.

**54. « Un de vos risques n'est couvert par aucun contrôle retenu. »**
`ER7`, la perte du savoir-faire opérationnel. Son unique ancrage, `A.5.37` — procédures d'exploitation
documentées —, fait partie des 78 contrôles non investigués. C'est **le seul trou de couverture** du contrôle
croisé, il est nommé comme tel, et `A.5.37` est en tête des huit contrôles prioritaires à investiguer.

**55. « Vous avez ajouté des rapprochements que votre propre plan ne contenait pas. »**
Deux, et ils sont **déclarés comme des ajouts** : `A.5.15` par `PT-02` et `A.8.8` par `PT-01`. La
justification est écrite. Tant que la correction n'est pas portée dans `D7` §6, les deux contrôles sont
traités *de fait* et orphelins *au registre* — nous préférons le dire ainsi plutôt que de faire disparaître
la couture.

**56. ★ « Vous n'avez pas de schéma réseau ? »**
Non, et c'est la première des six lacunes assumées de notre cartographie. C'est elle qui **borne ce que nous
pouvons honnêtement déclarer à un tiers** — et c'est elle, trois séances plus tard, qui produit l'exclusion
datée d'E4 du périmètre de certification. Elle se lève en deux temps : `PT-13` l'inventaire au 14/10/2026,
puis `PT-03` la segmentation au 14/06/2027.

**57. « Pourquoi une seule exclusion dans votre déclaration d'applicabilité ? »**
Parce que dans le doute entre *non conforme* et *non applicable*, c'est **non conforme** qui l'emporte, sauf
absence d'objet démontrée. `A.8.28`, codage sécurisé : la filiale ne développe aucun logiciel, fait confirmé
par la DSI le 15 septembre. `A.7.4` et `A.6.3` auraient pu recevoir un « ce n'est pas notre périmètre » — ils
restent retenus et non conformes. *La discipline se mesure aussi à ce qui n'a pas été exclu.*

**58. « Votre déclaration d'applicabilité est plus sévère que la moyenne. »**
Oui, et c'est assumé par écrit. Notre règle de notation est dans `D8` §2.2 : **on note l'état constaté,
jamais l'intention**. Adoucir une note aurait contredit notre propre rapport d'audit sans fait nouveau.

**59. « Comment savez-vous que ce que vous avez saisi dans l'outil correspond à ce que vous écrivez ? »**
Parce que nous l'avons relu exigence par exigence dans l'instance, et non sur nos captures : 123 exigences
évaluables, 30 clauses sur 30 traitées sans aucune non évaluée, et les bons quinze contrôles. Quatre
corrections en sont sorties, dont deux portées **dans l'outil**. *Pièce : `fixes.md` F22.*

**60. « Vos captures d'écran prouvent-elles quelque chose ? »**
Elles montrent qu'un objet existe et dans quel état, à une date. Elles ne remplacent pas l'export daté de
l'instance, qui est la pièce 3 et qui s'ouvre hors de l'outil. Les captures sont le journal ; l'export est la
preuve.

---

# 9. Les questions hostiles

**61. ★ « Vous n'avez fermé aucun risque. »**
Exact, et nous le disons ainsi plutôt que de l'habiller : aucune ligne du registre ne reste au-dessus du
seuil, mais aucune ne disparaît. Six passent à moyen, deux à faible, **chacune avec un propriétaire, une date
et une fiche d'acceptation** — sept fiches, zéro dérogation. Faire passer un risque d'inacceptable à
tolérable-formalisé n'est pas le faire disparaître, et c'est écrit dans la note.

**62. « Tout cela est très joli, mais rien n'est fait. »**
C'est exactement notre dernière phrase, et nous la disons avant vous : **un dossier prouve une méthode,
jamais la sécurité elle-même**. Ce qui transforme la méthode en preuve, ce sont trois dates : le test de
restauration au 14 novembre, les comptes nommés du prestataire au 14 janvier, la séparation des réseaux au
14 juin. Ce sont les trois premières échéances du plan, et les trois premiers indicateurs.

**63. « Vous décrivez un désastre. Comment se fait-il que rien ne soit encore arrivé ? »**
Quelque chose est arrivé : un arrêt d'expédition en avril, dont **personne n'a pu tenir la chronologie**,
faute de journalisation. L'absence d'incident connu, quand on n'a aucune détection sur le WMS, les automates
et la liaison 4G, n'est pas une preuve de sécurité — c'est une absence de mesure. C'est précisément ce que
`PT-07` corrige.

**64. « Vous êtes des étudiants, pas des RSSI. »**
Le dossier ne demande pas qu'on nous croie sur parole : chaque affirmation renvoie à une pièce, chaque
chiffre à un objet de l'instance. C'est la règle que nous avons appliquée de bout en bout — la note affirme,
le dossier prouve, l'export montre. Tout ce que nous avançons est vérifiable sans nous.

**65. « Pourquoi devrais-je croire vos chiffres de risque plutôt que mon intuition ? »**
Parce qu'ils sont reproductibles : les échelles sont écrites, le seuil est posé avant la cotation, le critère
du top 5 avant le classement, la règle de veto avant le calcul des référentiels. Vous pouvez contester chacune
de ces règles — c'est le but. Ce que vous ne pouvez pas faire, c'est obtenir un autre résultat en appliquant
les mêmes.

**66. « Et si je ne signe rien ? »**
Trois choses se produisent, dans cet ordre. La fenêtre contractuelle de novembre 2026 se referme et les mêmes
exigences se paient ou ne s'obtiennent pas. La réponse au client pharmaceutique se décale de neuf mois, ou se
fait sur un périmètre que nous ne pouvons pas démontrer. Et les treize mesures perdent leur critère de
priorité, faute de seuil confirmé.

---

# 10. Les questions individuelles

> **Une question individuelle par étudiant est certaine**, portant *« sur une partie du travail que
> l'étudiant a déclarée comme sienne »*. Elle pèse **la moitié du coefficient individuel**. La déclaration se
> fait deux fois : sur la slide d'annexe « qui a porté quoi », et oralement au passage de parole.
>
> **Chacun doit pouvoir résumer en une phrase la partie de l'autre** — c'est explicitement noté dans les
> 10 points de « maîtrise du fond ».

## Pour Miguel — gouvernance, cartographie, état des lieux, seuil, chiffrage

**67. « Votre centre de supervision ne reçoit rien de vos systèmes critiques. Développez. »**
Le SOC du groupe ne reçoit aucun journal du WMS, des automates, ni de la liaison 4G de l'intégrateur. La
conséquence n'est pas théorique : lors de l'arrêt d'avril, personne n'a pu établir de chronologie. C'est ce
qui m'a conduit à proposer de relever le besoin de traçabilité de l'exécution des flux de *notable* à *très
important* — arbitrage proposé au Directeur Logistique, **pas décidé dans le document**. Le traitement est
`PT-07`, raccordement au SOC, 14/03/2027.

**68. « Appétence, tolérance, seuil : ce sont trois mots pour la même chose ? »**
Non, et le glissement est précisément le problème. L'appétence est ce que la Direction Générale accepte de
risquer ; la tolérance est l'écart admis autour de cette ligne ; le seuil est la règle opérationnelle qui en
découle et qui tranche un cas concret. Chez nous, la Direction Générale fixe et propose, le Conseil approuve.
Ce qui manque encore, ce sont les **signatures** sur la tolérance appliquée à l'industriel — c'est la
demande n° 1.

**69. « Quelle est la première mesure que vous prendriez, vous, personnellement ? »**
Le test de restauration du WMS, `PT-04`, 14 novembre. Pas parce que c'est la plus urgente au sens du risque —
la segmentation l'est davantage — mais parce que **le chiffre qui nous manque est un constat** : nous ne
savons pas combien de temps il nous faut pour redémarrer. Tant que ce chiffre n'existe pas, la borne haute de
notre coût de l'inaction reste un ordre de grandeur, et je préfère la mesurer que l'argumenter.

**70. « Pourquoi répondre au client avant qu'il ne pose la question ? »**
Parce que le questionnaire de sécurité du client arrive de toute façon, et que la réponse qu'on improvise à
sa réception n'est pas la même que celle qu'on a préparée. Répondre d'abord, c'est choisir le périmètre sur
lequel on répond — le nôtre, écrit, avec son exclusion datée — au lieu de subir le sien.

**71. « Expliquez-moi votre indicateur de notification d'incident. »**
`IND-07`, le respect du délai de notification sous deux heures de la directive `INC-01`. Il est en brouillon
parce qu'il ne peut passer **ni au rouge ni au vert** : aucune chronologie d'incident n'existe dans la
filiale, donc aucun délai n'est mesurable. Le laisser vide dans le tableau de bord serait pire que de
l'exclure — **une case vide se lit trop facilement comme une case verte**.

**72. « Situez-moi la partie de votre binôme. »** *(à savoir dire en une phrase)*
Maxime a porté l'analyse de l'écosystème et du risque tiers — la cotation des cinq parties prenantes et le
scénario qui passe par le prestataire —, le périmètre du SMSI et son exclusion datée d'E4, et le jeu
d'indicateurs.

## Pour Maxime — risques et acteurs, écosystème et tiers, périmètre, indicateurs

**73. « "Le pivot est signé, pas piraté." Qu'est-ce que cela change pour moi ? »**
Cela change l'endroit où se prend la décision. Si le chemin d'entrée est technique, la réponse est un budget
DSI. S'il est contractuel — un accès permanent accordé par contrat à un prestataire dont nous ne contrôlons
ni les porteurs ni la sous-traitance —, la réponse est un avenant, et elle se signe au niveau du Directeur de
la filiale avec la Direction Juridique. C'est pourquoi la demande n° 3 n'est pas une demande de budget.

**74. « Pourquoi avoir exclu E4, alors que c'est un site du client ? »**
Parce qu'E4 est le seul site qui cumule les deux : il est dédié au client pharmaceutique **et** équipé
d'automates de tri sur un réseau non cloisonné, qui est le constat `C3` de notre audit. L'inclure
reviendrait à certifier ce défaut. L'exclusion porte sur l'**automatisation** d'E4, pas sur le site, elle est
datée au 14 juin 2027, et elle est reprise dans la réponse écrite au client.

**75. « Comment avez-vous coté vos parties prenantes ? »**
Sur deux axes — dépendance × pénétration pour l'exposition, maturité × confiance pour la fiabilité —, avec
un **seuil de criticité écrit avant la cotation** : dangerosité ≥ 4,0. Deux ressortent au-dessus :
l'intégrateur des automates à 12,0 et le prestataire du WMS à 8,0. Les trois autres sont à 1,0 et en dessous
— l'écart n'est pas discutable à la marge.

**76. « "Ce que Mærsk ne prouve pas" — que vouliez-vous dire ? »**
Qu'une référence publique donne un ordre de grandeur, pas une probabilité. Mærsk prouve qu'un arrêt
d'expédition mondial peut coûter des centaines de millions ; il ne prouve pas que cela nous arrivera, ni à
quelle fréquence. Utiliser un cas public comme argument d'autorité serait exactement le genre de raccourci
que le comité a raison de contester — c'est pourquoi nous avons aussi écrit, pour la malveillance interne,
la ligne « aucune référence ne colle ».

**77. « Votre indicateur de sensibilisation affiche un bon chiffre de groupe. Pourquoi le contestez-vous ? »**
Parce que les 64 % de sensibilisation du groupe agrègent une filiale qui n'a **jamais produit la mesure**.
Un indicateur moyen n'est prudent que si chacune de ses composantes existe ; sinon c'est une moyenne sur un
dénominateur faux, et elle rassure exactement là où il ne faudrait pas.

**78. « Situez-moi la partie de votre binôme. »** *(à savoir dire en une phrase)*
Miguel a porté la gouvernance et la cartographie, l'audit initial et sa ventilation par thème, le seuil
d'acceptation du risque, et le chiffrage du plan de traitement contre le coût de l'inaction.

---

# 11. Les questions de comparaison et de méta-niveau

**79. ★ « L'autre groupe Logistique a tranché autrement sur le même dossier. »**
Le fil rouge du module le pose : *il n'y a pas une bonne réponse, seulement des décisions argumentées et
traçables, ou non.* Nous répondons donc sur **la règle de décision**, pas sur le résultat : le critère du
top 5 écrit avant le classement, le veto posé avant le calcul des référentiels, le seuil de criticité posé
avant la cotation de l'écosystème, la règle de notation posée avant la déclaration d'applicabilité. Si une
autre règle mène ailleurs, la discussion porte sur la règle — et c'est la bonne discussion.

**80. « Qu'est-ce que vous referiez autrement ? »**
Trois choses. Nous daterions les six jalons du projet de reprise du flux dès `D6`, au lieu de laisser la date
de fin vivre dans `D7`. Nous refermerions l'écart de dates entre `D4` et `D7` au lieu de le décrire. Et nous
aurions investigué le thème physique plus tôt : l'angle mort n'est apparu qu'à la ventilation par thème,
c'est-à-dire tard.

**81. « Si vous n'aviez qu'une chose à retenir de ces dix séances ? »**
Que la règle s'écrit avant le résultat. Chaque fois que nous avons posé un critère avant de l'appliquer, la
décision a tenu — y compris quand un chiffre a changé en cours de route. Chaque fois que nous avons écrit
après coup, il a fallu corriger.

**82. « Combien de temps ce dossier tient-il sans vous ? »**
C'est le test du successeur, et c'est pour cela que le dossier est organisé en neuf séances séparées avec un
journal de corrections qui **ne supprime rien** : une correction close garde sa fiche. On peut reconstituer
non seulement l'état du dossier, mais l'histoire des décisions — y compris celles que nous avons
délibérément laissées ouvertes, avec leur raison.

---

# 12. Aide-mémoire — les chiffres autorisés

> **Règle absolue : aucun chiffre en soutenance qui ne figure pas dans cette table.**

| Sujet | Chiffre | Pièce |
|---|---|---|
| Volume du groupe bloqué par un arrêt WMS > 6 h | **40 %** | `D2` §2 |
| Pénalités contractuelles client pharmaceutique | **12 000 €/jour** | `D2` §2 |
| Valeurs métier · biens supports · actifs dans l'outil | **4 · 13 · 17** | `D2` |
| Lacunes assumées de la cartographie | **6** | `D2` §7 |
| Notes des référentiels (sur 300) | ISO **230** · ReCyF **205** · ANSSI **135** | `D3` §2 |
| Exigences importées · contrôles d'annexe A | **123** · **93** (37/8/14/34) | `D3`, `Session-3/3-Evidence/` |
| Charge estimée, 1re année | **≈ 60 jours-homme** | `D3` §4 |
| Taux de conformité par thème | org. **8 %** · techno **10 %** · physique **0 sur 14** · ensemble **9 %** sur 13 % de l'annexe A | `D4` §2.1 |
| Événements redoutés · couples SR/OV instruits · retenus | **7 · 5 · 3** | `D5` |
| Parties prenantes cotées · critiques · seuil | **5 · 2** (intégrateur **12,0**, APPLICA **8,0**) · seuil **4,0** | `D6` §4 |
| Jalons de sécurité projet · familles d'exigences contractuelles | **6 · 5** | `D6` |
| Lignes du registre · décisions | **8** (6 `Mitigated`, 2 `Accepted`) | `D7` §2 |
| Résiduels | **6 `Moyen` · 2 `Faible` · 0 `Élevé`** | `D7` §2 |
| Mesures · fiches d'acceptation · dérogations | **13 · 7 · 0** | `D7` |
| Coût du plan | **≈ 82 400 €/an** — dont **≈ 51 000 €** CAPEX amorti et **≈ 31 400 €** OPEX · build cumulé **≈ 180 500 €** | `D7` §1 |
| Mesure la plus coûteuse | `PT-03` segmentation IT/OT, **23 000 €/an** | `D7` §1 |
| Clauses 4 à 10 évaluées | **30** — 2 conformes, 20 partielles, 8 non conformes | `D8` §2.3 |
| Déclaration d'applicabilité | **15 contrôles sur 93 = 16,1 %** — 11 non conformes, 3 partiels, **1 exclu** (`A.8.28`) | `D8` §2 |
| Écarts sans mesure · contrôles prioritaires à investiguer | **3** (`A.5.24`, `A.6.3`, `A.7.4`) · **8** | `D8` §2.4 |
| Indicateurs · calculables aujourd'hui | **7 · 6** (`IND-07` en brouillon) | `D9` |
| Effectifs du groupe | **7 700** — Santé 3 200, Logistique 2 800, Éducation 900, Territoires 650, holding 150 | pack de référence |

## Les dates à connaître par cœur

| Date | Ce qui tombe |
|---|---|
| **novembre 2026** | Renouvellement du contrat de maintenance du WMS — **la fenêtre de levier** |
| **14/10/2026** | `PT-13` — inventaire des deux biens supports découverts |
| **14/11/2026** | `PT-04` — **test de restauration du WMS**, lève le point ouvert n° 1 |
| **14/12/2026** | `PT-01` recette des mises à jour · `PT-05` liaison 4G de l'intégrateur |
| **14/01/2027** | `PT-02` — **comptes nommés et authentification forte** pour la maintenance · `PT-09` rotation du secret |
| **14/03/2027** | `PT-06` avenant intégrateur · `PT-07` raccordement au SOC · `PT-08` clause de sous-traitance |
| **14/06/2027** | `PT-03` — **segmentation IT/OT**, lève l'exclusion d'E4 du périmètre de certification |
| **14/09/2027** | `PT-11` fin du projet de reprise du flux Santé (jalon 6) · `PT-12` formalisation du savoir-faire |

---

# 13. Les trois phrases à ne pas rater

Si la pression fait tout oublier, ces trois-là suffisent à tenir une réponse :

> **Sur l'argent** — *« Un coût certain et borné contre une perte plausible et non bornée, qui excéderait le
> budget annuel du plan en une seule journée d'incident. »*

> **Sur le risque** — *« Nous ne fermons aucun risque. Nous les faisons passer d'inacceptable à
> tolérable-formalisé : propriétaire nommé, date, fiche signée. Ce n'est pas la même chose, et nous ne le
> maquillons pas. »*

> **Sur la limite** — *« Un dossier prouve une méthode, jamais la sécurité elle-même. Ce que nous avons
> établi, c'est où nous en sommes, ce qui nous menace et ce que coûte le traitement. Pas que nous sommes
> protégés. »*
