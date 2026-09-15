# Bureau du RSSI — Séance 8

**« ... une certification ISO/IEC 27001 valide couvrant les services fournis à ce tiers, ou une démarche documentée équivalente. »**

**Maxime** · Groupe 4 (Translog) · filiale MERIDIAN Logistique · une page

---

**La clause a l'air simple jusqu'à ce qu'on essaie de tracer sa frontière sur notre propre carte.** Le
client pharmaceutique reçoit ses services de deux entrepôts sur six (pack §2) — **E1 et E4**, nommément,
dit le Responsable Exploitation à l'entretien : *« E1 and E4 are reserved for the pharma customer »*
(pack §4). Ce sont eux que vise son questionnaire de sécurité, et c'est donc sur eux que devrait porter un
certificat qui répond à sa clause. Sauf que la même phrase du même entretien range E4 aussi parmi les
sites équipés d'automates de tri — *« E2 and E3 have sorting machines, E4 too since last year »* (pack §4,
repris en D2 §1) —, sur un réseau bureautique et industriel **interconnecté sans aucun cloisonnement**
(constat `C3` de D4, non-conformité majeure, la totalité du périmètre). Le service que le client regarde
et le service que personne ne veut encore montrer à un auditeur **partagent le même site et le même
réseau plat** — ce n'est pas un rapprochement que nous faisons de loin, les deux phrases sont dans le même
paragraphe du pack.

**Ce n'est pas une surprise que nous découvririons aujourd'hui : c'est un angle mort que nous avions déjà
écrit nous-mêmes.** D3 le disait noir sur blanc dès le choix du référentiel, en séance 3 : *« aucun
périmètre ISO incluant l'industriel ne serait honnêtement déclarable »* avant le cloisonnement IT/OT,
chantier alors sans date. Il en a une désormais — `PT-03` de D7, 14 juin 2027 — mais cette date est **après**
n'importe quel audit de certification qu'on lancerait à un rythme normal. Ce que je veux que le Comité
retienne, c'est que ce n'est plus un angle mort abstrait sur « le périmètre industriel » en général : c'est
un site précis, nommé, dont le client pharmaceutique dépend déjà.

**Deux façons de le découvrir, et une seule que nous choisissons.** Si nous déclarons un périmètre « E1 et
E4, activités pharmaceutiques » sans écrire l'exclusion de l'automatisation, l'auditeur de certification qui
visite E4 verra les automates, posera la question de leur cloisonnement, et nous découvrirons devant lui ce
que nous savons déjà depuis la séance 3. Si nous l'écrivons nous-mêmes dans `D8`, la même information
devient une **exclusion motivée**, datée, adossée à `C3` et à l'échéance de `PT-03` — exactement ce que la
grille d'évaluation de ce matin appelle une phrase négative qui protège le dossier plutôt qu'une
découverte qui le dessert.

**Ce que je ne dirai pas au Comité** : ni qu'exclure l'automatisation d'E4 du périmètre de certification la
rend sûre — elle reste un risque `C3` ouvert, traité par le plan de D7, pas par le certificat —, ni qu'un
périmètre restreint aux seules activités pharmaceutiques nous met à l'abri d'une question du client sur le
reste du site. Un certificat ne prouve rien au-delà de ce qu'il couvre : c'est vrai pour les trois autres
filiales, et c'est tout aussi vrai à l'intérieur d'un seul entrepôt.

---

## Recommandation à la direction

> Je recommande au Comité Exécutif d'inscrire dans `D8`, dès la déclaration du périmètre, une **exclusion
> écrite et datée** : l'automatisation de tri d'E4 et le réseau bureautique/industriel qui la porte restent
> hors du périmètre de certification tant que la segmentation IT/OT (`PT-03`, échéance 14 juin 2027) n'est
> pas effective, avec réexamen du périmètre à cette date. Je recommande que cette même exclusion figure,
> en une phrase, dans la réponse écrite au client pharmaceutique — pas seulement dans notre dossier interne
> — précisément parce qu'une limite que nous énonçons nous-mêmes vaut mieux, devant ce client comme devant
> un futur auditeur, qu'une limite qu'on nous fait découvrir.

---

*Note : cette page est individuelle et engage son seul auteur. Miguel rend la sienne, sur la même
question, avec son propre angle.*
