# Bureau du RSSI — séance 8

**Question du jour** : *« Jeudi, au Comité Exécutif, je veux votre recommandation : lançons-nous un effort
de certification, sur quel périmètre, et que répondons-nous à ce tiers en attendant. Pas de lyrisme, des
faits. »* — la Directrice Générale du groupe, après que la Directrice Générale de MERIDIAN Logistique lui a
transmis l'exigence du client pharmaceutique (questionnaire de sécurité annoncé pour le prochain audit,
pack §3).

**Consigne** (format constant depuis la séance 4) : une page écrite, **individuelle**, par étudiant,
déposée dans le dossier de la séance, transposée à MERIDIAN Logistique et close par une recommandation à la
direction. Note individuelle — 10 points sur les neuf séances, coefficient 1.

| Étudiant | Fichier | État |
|---|---|---|
| Miguel Monereo | `S8-bureau-du-RSSI-Miguel-Monereo.md` | 🟢 **fait** — angle 1 (le silence coûte plus cher que l'anticipation : répondre au client avant son questionnaire) |
| Maxime | `S8-bureau-du-RSSI-Maxime.md` | 🟢 **fait** — angle : la tension E4 (dédié au client pharmaceutique **et** équipé d'automates sur un réseau non cloisonné, constat C3) |

`Seance-8-TD-S8-01-le-business-case-de-la-certification.md` — le **compte rendu collectif** du TD (les cinq
questions guidées), conservé comme matière de travail. **Ce n'est pas le bureau du RSSI** : il est collectif
et bien plus long qu'une page. C'est la matière première des deux pages individuelles, exactement comme aux
séances 5 à 7 — la séance 4, elle, n'a pas de compte rendu collectif : ses deux pages individuelles
partent directement de l'énoncé.

**Source** : `../../../../S8 - Sources/TD 1/The CISO's Desk_ The Certification Business Case _ Lockbay Academy.pdf`
(énoncé ; corrigé et grille d'évaluation repliés dans la page, « cliquer pour révéler »). Corpus mobilisé :
pack de filiale §2, §3, §4, §6 · D1 (gouvernance, rôles de décision) · D2 (cartographie, valeurs métier `PA-02`
et `PA-04`) · D3 (référentiel adopté, angles morts déjà posés) · D4 (audit initial, écarts C3/C4) · D7
(plan de traitement daté et chiffré).

## Les deux notions du matin

| Notion | En une phrase | Sa limite |
|---|---|---|
| **Business case de certification** | Le document court qui organise la décision — ce que le certificat prouverait et à qui, ce qu'il ne prouverait pas, l'effort et la trajectoire, la décision demandée | Il ne décide pas, il rend la décision possible ; jugé à ses phrases négatives, pas à ses promesses |
| **Valeur métier du SMSI** | Confiance démontrable, constance des contrôles, arbitrages informés sur des risques cotés, réutilisation d'un même système pour plusieurs obligations | Elle ne se matérialise que si le système **vit** — un SMSI papier a un coût certain et une valeur nulle |

**Le repère chiffré de l'exposé, et rien d'autre** : un peu plus de mille organisations certifiées
ISO/IEC 27001 en France fin 2023 selon l'AFNOR (*ISO Survey*), trois fois plus qu'en 2019 ; progressions de
11 % en France et 22 % dans le monde en 2020.

**Le piège à éviter** : pour chaque phrase écrite, se demander si elle décrit la **démarche** du groupe, qui
existe, ou le **certificat**, qui n'existe pas. La moitié des mauvais dossiers de certification confond les
deux, et un client, un assureur ou un acheteur public ne s'y trompera pas.

## Les cinq questions du cas

1. **Analyser** la clause transmise : ce qu'elle exige exactement, la portée de « couvrant les services
   fournis à ce tiers » et de « ou une démarche documentée équivalente », au moins deux lectures et leurs
   conséquences pour la réponse du groupe.
2. **Établir** la colonne « ce que le certificat prouverait » : au moins trois audiences tirées du pack de
   filiale (§3 et §6), un bénéfice par audience, en lien avec ce que la séance 3 a établi sur ce
   qu'atteste une certification.
3. **Établir** la colonne symétrique, « ce que le certificat ne prouverait pas » : au moins trois limites,
   chacune en une phrase, dont une sur la conformité réglementaire et une sur la sécurité réelle des
   systèmes.
4. **Proposer** un périmètre de certification pour le groupe et le défendre en cinq lignes : le groupe
   entier, la seule filiale sous revue, ou seulement les services visés par le tiers ? En s'appuyant sur la
   cartographie de la séance 2 et les écarts trouvés en séance 4.
5. **Rédiger** la décision demandée au Comité Exécutif, en trois phrases au plus : la recommandation, ce
   qu'elle engage, la réponse proposée au tiers dans l'intervalle. Contrainte : aucune date de certification
   promise, aucun coût improvisé.

**Minutage de l'énoncé** : 5 min de relecture des travaux précédents, 15 min pour les questions 1 à 4,
10 min pour la question 5 — la seule que la direction lira.

## Barème de la page, sur 10

*Deux grilles, et il ne faut pas les confondre.* Celle ci-dessous, sur 10 points, est la grille de la
**page individuelle**, et ce n'est pas une reprise du format des séances précédentes : c'est le barème
officiel du module, donné par le fil rouge (`ISMS module common thread.pdf`, p. 4, *Marking scale for the
CISO's desk, written*) — exactitude et pertinence 4, posture de RSSI 3, rédaction 3. L'énoncé, lui, porte la **matrice d'évaluation du cas** (cinq critères — lecture de la
clause, équilibre du dossier, périmètre, décision demandée, honnêteté — en trois niveaux :
*insuffisant / attendu / excellent*) : elle est dépliée dans l'export PDF de la séance, elle note le
**compte rendu collectif**, et c'est à ce titre que
`Seance-8-TD-S8-01-le-business-case-de-la-certification.md` la reprend mot pour mot en auto-évaluation.
Rien ne reste « à confirmer » : les deux grilles sont connues, elles ne portent simplement pas sur le
même objet.

| Bloc | Points | Détail |
|---|---|---|
| Exactitude et pertinence | **4** | le contenu est correct, sourcé et transposé à la filiale : l'étudiant dit ce que la question signifie concrètement pour elle |
| Posture de RSSI | **3** | une page, tenue en longueur et structurée, avec une recommandation explicite adressée à la direction |
| Rédaction | **3** | lisible par un dirigeant non technicien, dans la langue choisie, sigles définis (SMSI, WMS, TMA, SoA) au premier emploi |

## Angles disponibles pour les deux pages

Les deux étudiants prennent des **angles distincts** — c'est la règle du dossier depuis la séance 1.

1. **Le silence coûte plus cher que l'anticipation** *(pris par Miguel, voir `S8-bureau-du-RSSI-Miguel-Monereo.md`)*. Le questionnaire de sécurité n'est pas encore arrivé,
   mais la Directrice Générale a déjà fixé jeudi comme échéance : attendre la question précise du client
   pour commencer à y répondre revient à laisser le calendrier du tiers dicter celui du groupe, alors que
   D3, D4 et D7 permettent de répondre dès aujourd'hui. Angle : *une démarche documentée n'attend pas le
   certificat pour produire de la valeur*.
2. **Le certificat ne répare pas E4** *(pris par Maxime, voir `S8-bureau-du-RSSI-Maxime.md`)*. L'entrepôt E4 est à la fois dédié au client pharmaceutique et équipé
   d'automates de tri, sur un réseau bureautique/industriel non cloisonné (constat C3 de D4). Angle : *dire
   « nous couvrons les services fournis à ce tiers » exige de trancher, par écrit, ce que recouvre au juste
   un bien support partagé entre un usage commercial protégé et un usage industriel qui ne l'est pas encore*
   — sous peine de découvrir la difficulté devant l'auditeur de certification plutôt que devant le Comité.
3. **La meilleure pièce du dossier est un aveu.** L'énoncé le dit : un dossier de certification se juge à
   ses phrases négatives. Angle : *lister ce que D4 ne referme pas encore (0/12 exigences pleinement
   couvertes, deux non-conformités majeures) protège le RSSI mieux qu'un dossier qui les tairait* — une
   direction qui découvre elle-même la limite s'en souvient plus longtemps qu'une direction à qui on l'a
   dite.
4. **La démarche existe, le certificat pas encore.** C'est la distinction que tout le cas organise. Angle :
   *répondre au client dès aujourd'hui, sans attendre un audit de certification non budgété ni daté, en
   s'appuyant sur ce que le groupe a déjà produit et fait vivre* — le référentiel adopté (D3), l'évaluation
   menée (D4), le plan de traitement chiffré (D7).

Une page, sigles développés au premier emploi, recommandation explicite en clôture.

---

> **Suite de la journée** : CM *ISO/IEC 27001:2022 — architecture et rôle de la direction* → TP 1
> (évaluation de conformité et déclaration d'applicabilité dans `translog-b`) → TP 2 (périmètre du SMSI,
> contrôles retenus, exclusions justifiées — livrable **D8**, 2 points — et sous-section 8 de la note de
> stratégie).
