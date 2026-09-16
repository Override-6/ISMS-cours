# Bureau du RSSI — séance 9

**Question du jour** : *« J'ai reçu le rapport de suivi mensuel : quarante pages, je n'ai lu que la
première. La semaine prochaine, le Comité Exécutif consacre trente minutes à la sécurité avant la revue
budgétaire. Je veux un tableau de bord d'une page : cinq indicateurs, pas un de plus. Si un indicateur est
rouge, je veux savoir quoi décider. »* — le Directeur Général du groupe, au RSSI Groupe.

**Consigne** (format constant depuis la séance 4) : une page écrite, **individuelle**, par étudiant, déposée
dans le dossier de la séance, transposée à MERIDIAN Logistique et close par une recommandation à la
direction. Note individuelle — 10 points sur les neuf séances, coefficient 1.

| Étudiant | Fichier | État |
|---|---|---|
| Miguel Monereo | `S9-bureau-du-RSSI-Miguel-Monereo.md` | 🔴 **à écrire** |
| Maxime | `S9-bureau-du-RSSI-Maxime.md` | 🟢 **fait** — angle : le taux de sensibilisation groupe (64 %) tient sur une moyenne dont Logistique n'a jamais mesuré sa part (`A.6.3` non évalué, D4 §6, orphelin en D8 §2.4) |

`Seance-9-TD-S9-01-indicateurs-du-comite-executif.md` — le **compte rendu collectif** du TD (les cinq
questions guidées), conservé comme matière de travail. **Ce n'est pas le bureau du RSSI** : il est collectif
et bien plus long qu'une page. C'est la matière première des deux pages individuelles, exactement comme aux
séances 5 à 8.

**Source** : `../../../../S9 - Sources/TD 1/The CISO's Desk_ Indicators for the Executive Committee _ Lockbay Academy.pdf`
(énoncé ; corrigé et grille d'évaluation repliés dans la page, « cliquer pour révéler », non consultés — nos
réponses sont construites directement sur l'énoncé et sur D1/D4/D7/D8). Corpus mobilisé : le tableau de bord
esquissé en séance 1 (D1, feuille de travail S1-05 exercice 3, quatre indicateurs cibles et leurs
relevés du trimestre) · D4 (taux de conformité, constats `C3`/`C4`, angle mort `A.6.3`) · D7 (plan de
traitement daté et chiffré, mesures `PT-02`, `PT-03`, `PT-07`) · D8 (déclaration d'applicabilité, écarts
sans mesure de traitement `A.5.24`/`A.6.3`).

## Les trois notions du matin

| Notion | En une phrase | Sa limite |
|---|---|---|
| **Reporting exécutif** | Convertit le flux du SOC, de l'outil GRC et des filiales en quelques informations décidables, en partant des décisions du Comité vers les données | Il agrège, donc il perd du détail — un bon reporting assume cette perte et donne le chemin vers le détail |
| **Indicateur stratégique / métrique technique / indicateur de vanité** | Un indicateur stratégique informe une décision du Comité, une métrique technique nourrit l'indicateur sans monter telle quelle, un indicateur de vanité rassure sans informer | Le test d'appartenance : si l'indicateur passe au rouge, le Comité sait-il quoi décider ? |
| **Tableau de bord stratégique** | L'assemblage d'indicateurs avec cible, seuil d'alerte et tendance, construit pour durer | Il ne mesure que ce qu'on a décidé d'y mettre — il peut rester vert pendant qu'un angle mort brûle |

**Règle d'or, rappelée avant l'exercice** : tout indicateur se présente en une phrase de la forme *« ce
chiffre vous dit si…, et s'il franchit le seuil, la décision à prendre est… »*. Si la phrase ne se termine
pas, l'indicateur redescend d'un étage.

**Les quatre relevés du trimestre, niveau groupe, qui font foi pour toute la journée** : couverture PSSI
82 % · délai moyen de détection 5 h · obsolescence du parc 9 % · taux de sensibilisation 64 %.

## Les cinq questions du cas

1. **Classer** les douze candidats de l'adjoint en trois familles — indicateur stratégique présentable en
   l'état, métrique technique à agréger ou traduire, indicateur de vanité à écarter — chacun justifié en une
   demi-phrase.
2. **Sélectionner** les cinq indicateurs du Comité, en respectant la consigne. Contrainte de construction :
   au moins un indicateur de conformité aux règles du groupe, au moins un d'exposition au risque, au moins un
   centré sur la réponse à incident.
3. **Compléter** chaque indicateur retenu : la cible, le seuil d'alerte, la phrase de la règle d'or. S'appuyer
   sur les cibles posées en séance 1 quand elles existent.
4. **Traduire** le candidat 5, le délai moyen de détection, en langage exécutif : trois phrases au plus, sans
   le mot « journaux », ce qu'il mesure, pourquoi il compte, ce qui est décidé s'il dérive.
5. **Rédiger** la réponse du RSSI Groupe à l'adjoint sur le candidat 3, le nombre d'attaques bloquées, que
   l'adjoint trouve « très parlant pour le Comité ». Deux phrases : le défaut fondamental de l'indicateur, ce
   qui est proposé à la place.

**Minutage de l'énoncé** : 10 min pour la classification, 10 min pour la sélection et les seuils, 10 min pour
les deux réponses rédigées.

## Barème de la page, sur 10

*Grille officielle du module (`ISMS module common thread.pdf`, p. 4, Marking scale for the CISO's desk,
written)* — exactitude et pertinence 4, posture de RSSI 3, rédaction 3.

| Bloc | Points | Détail |
|---|---|---|
| Exactitude et pertinence | **4** | le contenu est correct, sourcé et transposé à la filiale |
| Posture de RSSI | **3** | une page, tenue en longueur et structurée, avec une recommandation explicite adressée à la direction |
| Rédaction | **3** | lisible par un dirigeant non technicien, sigles définis au premier emploi |

## Angle pris

**Le chiffre moyen qui cache une case vide** *(Maxime, voir `S9-bureau-du-RSSI-Maxime.md`)*. Le taux de
sensibilisation groupe (64 %) est calculé sur quatre filiales dont l'une — la nôtre — n'a jamais mesuré sa
part (`A.6.3` non évalué depuis D4, orphelin sans mesure de traitement en D8). Angle : *un indicateur moyen
n'est prudent que si chacune de ses composantes existe réellement — sinon il rassure sur un chiffre qui peut
cacher un zéro sans que personne ne l'ait décidé*. Recommandation : ne pas retenir cet indicateur au tableau
de bord tant que sa fiabilité n'est pas vérifiée filiale par filiale, et ouvrir dès cette séance le chantier
documentaire que D8 désigne déjà pour Logistique.

Angle de Miguel à préciser à la remise de sa page.

---

> **Suite de la journée** : CM *Politique de sécurité de l'information et architecture documentaire du
> SMSI* → TP 1 (politique, fiche réflexe, tableau de bord dans `translog-b`) → livrable **D9** (politique sur
> le gabarit imposé, une procédure, une fiche réflexe, cinq à huit indicateurs avec formule, source, seuil,
> fréquence et destinataire — 3 points) et **version close de la note de stratégie** (sous-section 9).
