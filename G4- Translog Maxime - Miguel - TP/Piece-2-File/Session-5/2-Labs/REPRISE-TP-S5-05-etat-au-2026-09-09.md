> ## ⛔ FICHIER CLOS — le TP 1 a été terminé le 9 septembre 2026
>
> Ce fichier était la note de reprise d'une session interrompue. **Il est conservé comme trace, mais il n'est plus à jour**, et il contient une erreur de constat :
>
> - il affirme qu'**ER2 n'avait pas été enregistré**. C'est faux : ER2 **était** enregistré dans l'instance, mais avec la qualification `Availability` héritée d'ER1 au lieu d'`Integrity`. L'erreur a été **corrigée** à la reprise (ER2 porte désormais `Integrity`), et aucun doublon n'a été créé.
>
> **La trace de référence du TP 1 est désormais** [`Seance-5-TP-S5-05-feuille-de-travail-saisie-EBIOS-RM.md`](Seance-5-TP-S5-05-feuille-de-travail-saisie-EBIOS-RM.md) : elle porte l'inventaire, les trois phrases sur la matrice, les six écarts relevés, les compteurs finaux et la clôture de F3.

---

# REPRISE — TP S5-05, arrêt en cours de séance (2026-09-09)

Arrêt demandé par l'utilisateur en cours de saisie. Aucune donnée n'a été perdue par erreur : le formulaire ouvert au moment de l'arrêt **n'a pas été enregistré** et a été abandonné tel quel.

## 1. Où j'en étais

- §1 (inventaire), §2 (import matrice) et §3 (création de l'étude + cadrage + liaison des 17 actifs + rattachement de l'audit) sont **terminés**.
- §4 (six événements redoutés) : **ER1 est créé et enregistré**. J'étais en train de saisir **ER2** dans la boîte de dialogue "Add feared event" quand l'arrêt est arrivé — champs ID et Name déjà corrigés pour ER2, Severity passée à `Important`, Justification d'ER2 tapée, mais le champ **Qualifications affichait encore `Availability` (hérité d'ER1, pas encore changé en `Integrity`)**, et **je n'ai PAS cliqué sur Save**. J'ai abandonné la boîte de dialogue sans l'enregistrer, conformément à la consigne d'arrêt. ER2 n'existe donc pas dans l'outil.

## 2. Ce qui existe déjà dans l'instance (ne rien recréer)

- **Matrice de risque importée** : `4x4 risk matrix from EBIOS-RM` (domaine `Global`) — complet.
- **Étude EBIOS RM créée** : `Étude EBIOS RM MERIDIAN - Logistique et approvisionnement d'urgence vers Santé - cycle 1`, domaine `MERIDIAN-LOGISTIQUE`, méthode de cotation `Manual`, matrice = celle ci-dessus, statut `Planned` — complet.
  - **Étape 1 (cadrage / description)** : remplie avec les 5 paragraphes (Objectif, Finalité retenue, Participants et rôles, Responsable de l'acceptation, Cycles). Auteurs = `Miguel.monereodelasota@ynov.com` + `maximebatista18@gmail.com` — **complet**.
  - **Étape 2 (actifs)** : les **17 actifs** (LOG-PA-01 à 04, LOG-SA-01 à 13) sont liés (sélectionnés via le champ "Assets", pas créés) — **complet**.
  - **Étape 4 (socle de sécurité)** : audit `MERIDIAN - ISO/IEC 27001:2022 - initial assessment` rattaché via "Select audit" — **complet**.
  - **Étape 3 (événements redoutés)** : **ER1 seul, enregistré** : Name = « Le flux d'expédition du groupe est interrompu — WMS ou liaison inter-entrepôts indisponible, les six entrepôts ne préparent plus », Asset = `LOG-PA-01`, Qualification = `Availability`, Severity = `Critical`, Justification complète saisie, `Selected` coché. **ER2 à ER6 : rien d'enregistré.**
- **Compteurs Summary constatés** (avant ER1) : Assets=17, Audits=1, Feared events=0, RO/TO couples=0. Après l'enregistrement d'ER1, la liste "Feared events" affichait bien 1 ligne (ER1) — le compteur du Summary n'a pas été revérifié après ce point.
- **Fichier de travail** `Seance-5-TP-S5-05-feuille-de-travail-saisie-EBIOS-RM.md` : **non créé** — à faire.
- **Captures d'écran** : plusieurs captures ont été prises via l'outil de screenshot mais restent dans un dossier temporaire macOS (`/var/folders/lt/kzt1mz0x00jcjxznxgjc77580000gn/T/claude-chrome-screenshots-X3oxEq/`), **pas encore copiées dans `Session-5/3-Evidence/`** avec les noms attendus par le plan. Fichiers disponibles (susceptibles d'être nettoyés par l'OS) :
  - `screenshot-1788946745020-0.jpg` — Domains (Global/MERIDIAN-LOGISTIQUE/MERIDIAN-SANTE)
  - `screenshot-1788946760891-1.jpg` — Perimeters (MERIDIAN-LOGISTIQUE-FINAL)
  - `screenshot-1788946810785-2.jpg` — Assets, liste des 17
  - `screenshot-1788946858538-3.jpg` — Audits (MERIDIAN - ISO/IEC 27001:2022 - initial assessment)
  - `screenshot-1788946874549-4.jpg` — EBIOS RM studies, liste vide
  - `screenshot-1788947000583-5.jpg` — Grille de la matrice 4x4 complète
  - `screenshot-1788947105233-6.jpg` — Formulaire de création de l'étude rempli
  - `screenshot-1788947530917-7.jpg` — Activité 2, 17 actifs liés (liste paginée)
  - `screenshot-1788947637438-8.jpg` — Summary de l'étude (Assets 17, Audits 1, etc.)

## 3. Ce qui reste à faire

- **§4** : recréer ER2 depuis zéro (rien n'a été enregistré), puis ER3, ER4, ER5 (avec la décision de rattachement à `LOG-PA-01` et la mention du problème de valeur métier propriété de Santé), ER6. Vérifier le compteur "Feared events" = 6 à la fin, pas plus.
  - ⚠️ **Piège** : la boîte de dialogue "Add feared event" se rouvre **pré-remplie avec les valeurs du dernier événement enregistré**, pas vide. Il faut vérifier/écraser CHAQUE champ (ID, Name, Severity, Justification, Assets, Qualifications) avant d'enregistrer, sous peine de dupliquer les données d'ER1.
- **§5** : intégralement à faire — les 5 couples SR/OV (rien n'a été saisi).
- **§6** : vérifier que les ateliers 3, 4, 5 sont vides — non vérifié explicitement cette session (je ne suis entré dans aucune page de ces ateliers), mais aucune donnée n'y a été saisie par moi.
- **§7** : marquage du Top 5 des actifs (`SA-01`, `SA-04`, `SA-09`, `SA-05`, `SA-03`) — non commencé. Un champ "Labels" existe dans la liste des Assets (colonne visible, vide "--" pour tous) — mécanisme probable à utiliser, à confirmer.
- Feuille de travail à rédiger.
- Captures à ranger dans `Session-5/3-Evidence/` (voir liste ci-dessus) ou à recapturer.

## 4. Ce que j'ai constaté à l'écran

- **Connexion** : déjà authentifié comme `Miguel.monereodelasota@ynov.com` (compte nominatif, visible en bas de la barre latérale) — pas `admin@lockbay.eu`.
- **Domaine `MERIDIAN-SANTE` : EXISTE** dans `translog-b` (parent `Global`), **contrairement à l'hypothèse du plan** qui l'annonçait « probablement absent ». Domaine confirmé avec sa description (filiale santé, quatre établissements de soins). C'est une divergence majeure par rapport au plan à signaler en premier dans la feuille de travail.
- **Domaine `MERIDIAN-LOGISTIQUE`** : confirmé, parent `Global`.
- **Périmètre `MERIDIAN-LOGISTIQUE-FINAL`** : confirmé, domaine `MERIDIAN-LOGISTIQUE`, assignés par défaut `admin@lockbay.eu` + `maximebatista18@gmail.com`.
- **17 actifs confirmés**, noms exacts observés :
  `LOG-PA-01` Exécution des flux logistiques · `LOG-PA-02` Maintien de la chaine du froid · `LOG-PA-03` Savoir-faire operationnel des six entrepots · `LOG-PA-04` Conformite contractuelle avec le client pharmaceutique · `LOG-SA-01` WMS (2 serveurs + BDD, site E1) · `LOG-SA-02` Scannettes d'entrepot (~300, Wi-Fi) · `LOG-SA-03` Automates de tri (E2/E3/E4) · `LOG-SA-04` Compte de service WMS-automates · `LOG-SA-05` Logiciel des sondes de temperature · `LOG-SA-06` Local serveur E1 · `LOG-SA-07` Entrepots E1-E6 · `LOG-SA-08` Chambres froides et remorques refrigerees · `LOG-SA-09` Responsable Exploitation · `LOG-SA-10` Prestataire TMA du WMS · `LOG-SA-11` Responsable Qualite (repond aux audits) · `LOG-SA-12` VLAN dedie + pare-feu d'inspection · `LOG-SA-13` **API** d'approvisionnement d'urgence (le plan disait « interface », l'outil affiche « API » — divergence mineure de libellé).
- **Référentiel** : `International standard ISO/IEC 27001:2022`, provider ISO/IEC, domaine `Global`.
- **Audit** : `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, progression 9 %, domaine `MERIDIAN-LOGISTIQUE`, périmètre `MERIDIAN-LOGISTIQUE/MERIDIAN-LOGISTIQUE-FINAL`. Le libellé exact du statut (« In progress ») n'a pas été revérifié cette session — **non vérifié**.
- **Liste EBIOS RM studies** : constatée vide avant création de l'étude.
- **Matrice 4x4 EBIOS-RM, libellés réels à l'écran** :
  - Axe vraisemblance (vertical) : `Unlikely`, `Likely`, `Very likely`, `Certain` (bas en haut).
  - Axe horizontal : **libellé réel = « Impact »**, PAS « Consequence » comme l'annonçait le plan/PDF — divergence à noter. Niveaux : `Minor`, `Significant`, `Important`, `Critical`.
  - Niveaux de risque : `Low`, `Medium`, `High` (3 niveaux), avec légende texte confirmée.
  - Case la plus élevée : croisement `Certain` × `Critical` (coin supérieur droit), couleur rouge/High.
  - Diagonale : bande en escalier de cellules `Medium` (couleur orange/tan), du coin supérieur gauche au coin inférieur droit, séparant `Low` (teal, coin inférieur gauche) de `High` (rouge, coin supérieur droit).
  - Correspondance de gravité **CONSTATÉE à l'écran** (plus « présumée ») : `Minor` / `Significant` / `Important` / `Critical` — confirme mot pour mot la correspondance `mineure/significative/grave/critique` attendue.
- **Formulaire "Add feared event"** : champs ID, Name, Description, Severity (`--`, Minor, Significant, Important, Critical), Justification, Assets (multi-select, indice affiché : « typically linked to business values (primary assets). Supporting assets are allowed here for flexibility » — plus souple que « jamais à un bien support » du plan), Qualifications (liste plus riche que prévu : `Authenticity`, `Availability`, `Confidentiality`, `Environmental`, `Financial`, … — le plan n'en citait que 4), case `Selected` cochée par défaut.
- **Mécanisme "Select audit"** confirmé distinct de la création : bouton rose = sélectionner un audit existant, bouton bleu = importer depuis bibliothèque. Le principe "relier, ne pas créer" est bien supporté par l'outil pour les audits (et de la même façon pour les actifs, testé et utilisé au §3).

## 5. Pièges rencontrés

- **MERIDIAN-SANTE existe** alors que le plan l'annonçait absent — à traiter comme information de gouvernance et non comme erreur, mais cela change la phrase à écrire dans D5 (le plan supposait un manque, il n'y en a pas ici).
- **Piège de pré-remplissage** : rouvrir "Add feared event" après un premier enregistrement affiche les valeurs du **précédent** événement, pas un formulaire vide. Vérifier et écraser tous les champs à chaque nouvelle fiche.
- **Quasi-incident sans conséquence** : au début de l'exploration de la liste des actifs, un clic de pagination a ouvert par erreur la page d'édition de l'actif `LOG-PA-04` ; j'ai quitté la page sans cliquer sur Save, donc **aucune modification n'a été enregistrée**. Vérifié.
- Les captures d'écran prises restent dans un dossier temporaire système, pas encore dans `Session-5/3-Evidence/` — voir liste des fichiers au §2.
