# Bureau du RSSI — séance 6

**Question du jour** : *« Ce qui est arrivé aux clients de ce logiciel de comptabilité, est-ce que ça
peut nous arriver par un de nos prestataires ? »*

**Consigne** (énoncé, « Working method ») : *« The answer is a written, individual page, filed in the
session 6 folder; it is marked out of 10 according to the answer key's scale. »* — une page au plus, par
étudiant, transposée à MERIDIAN Logistique, close par une recommandation à la direction. Note
individuelle — 10 points sur les neuf séances, coefficient 1.

| Étudiant | Fichier | État |
|---|---|---|
| Miguel Monereo | `S6-bureau-du-RSSI-Miguel-Monereo.md` | ✅ rendu — angle 1 (la seconde question du réflexe de méthode : notre réponse est vide) |
| Maxime | `S6-bureau-du-RSSI-Maxime.md` | ✅ rendu — angle 2 (le pivot est signé, pas piraté : le traitement passe par le contrat et par le cadrage des projets) |

`Seance-6-TD-S6-01-attaque-par-la-chaine-d-approvisionnement.md` — le compte rendu collectif du TD (les
cinq questions guidées), conservé comme matière de travail. **Ce n'est pas le bureau du RSSI** : il est
collectif et bien plus long qu'une page.

**Source** : `../../../../S6 - Sources/TD 1/The CISO's Desk_ Supply Chain Attack _ Lockbay Academy.pdf`
(énoncé ; corrigé et barème repliés dans la page, « cliquer pour révéler »). Travail conduit à partir du
corpus : pack de filiale §3, §4, §5, §6 · reference pack §3, §5, §6 · D1, D2, D4, D5 · CM de la séance 6.

## Les trois notions du matin

| Notion | En une phrase | Sa limite |
|---|---|---|
| **Chaîne d'approvisionnement du SI** | Fournisseurs, prestataires et flux entrants — matériels, logiciels, **mises à jour**, services, maintenance — dont le SI dépend pour fonctionner ; chaque maillon détient un accès que l'attaquant extérieur n'aura jamais | Elle ne se lit pas sur un organigramme : les dépendances sont contractées par les métiers, sans passer par le RSSI |
| **Attaque par rebond** (*pivot*) | Compromettre un acteur qui détient un accès légitime à la cible, puis rebondir — par le **logiciel**, par le **prestataire**, ou par l'**interconnexion** | Décrit le **chemin**, pas la **gravité** |
| **Risque tiers** | La part de risque née d'acteurs non contrôlés dont on a accepté la présence, par contrat ou par usage. **35 %** des cyberattaques significatives sont passées par un tiers — 3ᵉ vecteur (CESIN 2026) | Il se **gère**, il ne s'élimine pas |

**Deux cas de référence** : **NotPetya** (27 juin 2017, mise à jour du logiciel M.E.Doc ; Mærsk chiffre
250-300 M$ sur ses activités *Transport & Logistique* au T3 2017) et **SolarWinds** (découvert en
décembre 2020, ~18 000 clients d'Orion ayant reçu la mise à jour piégée).

**Réflexe de méthode** — les deux questions, dans cet ordre : *que peut ce fournisseur sur mon SI en temps
normal ?* (exposition) puis *qu'est-ce qui m'alerterait si ce pouvoir était utilisé par quelqu'un
d'autre ?* (détection). **Une réponse vide à la seconde est déjà un constat.**

## Les cinq questions du cas

Dimanche soir, la Directrice Générale transfère au RSSI Groupe une enquête de presse sur les attaques par
la chaîne d'approvisionnement : *« Je veux que votre briefing de jeudi commence par la réponse. »* Pas de
nouvelle étude avant jeudi — la cartographie de la séance 2 est la matière de travail.

1. **Inventorier** les dépendances tierces de la filiale sous revue (§3 et §6 du pack) plus les
   dépendances de niveau groupe (§5 du reference pack), en un tableau à quatre colonnes : *tiers ou flux
   entrant · filiale concernée · nature de l'accès ou de la dépendance · ce qu'il peut atteindre*. Ne pas
   s'arrêter aux prestataires contractés : **un flux de mise à jour est aussi une dépendance**.
2. **Qualifier** chaque ligne en une phrase : qu'est-ce qui en ferait un chemin de pivot attirant, en
   logique de moindre effort, du point de vue de l'attaquant ? *(tient dans une colonne du tableau de Q1)*
3. **Transposer** les deux cas sur le groupe : pour le mécanisme « mise à jour piégée », désigner
   l'endroit qui lui ressemble le plus ; idem pour « accès de maintenance détourné ». Justifier par un
   **élément du dossier**, pas par une intuition, et nommer pour chacun la **clause contractuelle** qui
   aurait aidé.
4. **Rédiger** les trois messages du briefing : un **fait sourcé** qui cadre, une **phrase honnête** sur
   l'exposition du groupe, une **décision demandée** au Comité Exécutif. Contrainte : *rien d'affirmé ne
   dépasse ce que le dossier prouve*.
5. **Formuler** ce que l'analyse du matin ne sait pas encore faire : que manque-t-il pour passer de
   « voici nos dépendances » à « voici celles à traiter en premier » ? *(deux phrases)*

**Minutage de l'énoncé** : 10 min pour Q1-Q2, 10 min pour Q3, 10 min pour Q4-Q5.

## Barème de la page, sur 10

*Grille reprise du format des séances précédentes — à confirmer avec le corrigé officiel replié dans
l'énoncé.*

| Bloc | Points | Détail |
|---|---|---|
| Exactitude et pertinence | **4** | les trois notions distinguées sans glissement (chaîne d'approvisionnement / rebond / risque tiers) · les deux cas cités juste et sans exagération (mécanisme, chiffres, source) · les dépendances nommées d'après le dossier, § à l'appui · rien d'affirmé au-delà de ce que le matériel prouve |
| Posture de RSSI | **3** | une recommandation explicite à la direction · une décision demandée, pas un cours · l'exposition dite honnêtement, sans dramatisation ni minimisation · la transposition à Logistique, tiers et contrats nommés |
| Rédaction | **3** | une page, lisible par un dirigeant non technicien · sigles définis (WMS, TMA, SOC, API, VLAN, IT/OT) · des phrases prononçables en comité, pas de recopie du cours |

## Les angles retenus, et ceux qui restaient

**Miguel — angle 1 : la seconde question du réflexe de méthode.** L'exposition se décrit précisément ; la
détection, non. Le SOC ne reçoit rien du WMS, de la box 4G ni des automates : c'est le silence, pas le nom
d'un prestataire, qui est le constat. Clôture sur la recommandation n°5 de D4, seule des cinq sans date.

**Maxime — angle 2 : le pivot est signé, pas piraté.** Chaque accès de tiers a été ouvert par une
signature du métier, hors du bureau du RSSI ; donc le traitement est contractuel, et il remonte au
**cadrage des projets** (raccord au CM *Security by Design* de l'après-midi). Clôture sur la règle des
trois clauses + l'avis de sécurité au cadrage.

Deux autres angles, également défendables, laissés de côté :

3. **L'asymétrie SolarWinds appliquée au groupe.** Une compromission chez un fournisseur unique touche
   d'un coup les quatre filiales — l'application de paie et comptabilité du holding, l'annuaire commun
   Éducation & Territoires. Angle : le groupe a mutualisé ses fournisseurs sans jamais mutualiser ses
   exigences.
4. **Le rang 2, celui qu'on ne voit pas.** Les sauvegardes du portail des 45 000 comptes d'Éducation sont
   confiées à un sous-traitant *absent du contrat principal* ; l'infogérant de Territoires détient des
   clés qu'il refuse par écrit de rendre jusqu'en 2028. Angle : notre inventaire de tiers s'arrête au
   premier rang, et c'est au second que la donnée est copiée.

Une page, sigles développés au premier emploi, recommandation explicite en clôture.

---

> **Suite de la journée** : CM *Security by Design* → TD 2 (management des tiers, infogérance, ateliers 3
> et 4 d'EBIOS RM) → TP 1 (écosystème et scénarios dans `translog-b`) → TP 2 (exigences tiers et fiche
> projet, livrable **D6**, 7 points — le plus lourd du module).
