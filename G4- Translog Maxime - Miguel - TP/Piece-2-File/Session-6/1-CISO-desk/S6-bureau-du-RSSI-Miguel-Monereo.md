# Bureau du RSSI — Séance 6

**« Ce qui est arrivé aux clients de ce logiciel de comptabilité, est-ce que ça peut nous arriver ? »**

**Miguel Monereo** · Groupe 4 (Translog) · filiale MERIDIAN Logistique · une page

---

**La réponse honnête à la question de la Directrice Générale tient en deux questions, et notre seconde
réponse est vide.** Devant un incident « chez un fournisseur », on demande d'abord *que peut faire ce
fournisseur sur notre système d'information en temps normal ?* — cela mesure l'exposition — puis
*qu'est-ce qui nous alerterait si ce pouvoir était utilisé par quelqu'un d'autre ?* — cela mesure la
détection. Sur nos trois dépendances les plus puissantes, je sais répondre à la première avec précision.
À la seconde, je n'ai rien à dire. **C'est ce silence, et non le nom d'un prestataire, qui est le constat
que je porte jeudi.**

**Ce que nos trois tiers peuvent faire.** La tierce maintenance applicative (TMA) de notre logiciel de
gestion d'entrepôt (**WMS**) pose ses mises à jour la nuit, quand elle le décide, et nous les découvrons
le matin ; elle intervient avec un compte de domaine partagé dont **personne n'établit le nombre de
porteurs** — l'audit interne du holding a demandé la liste nominative, il a reçu un nom de compte.
L'intégrateur de nos automates de tri entre par une **box 4G placée hors du réseau supervisé**, sous un
contrat sans réversibilité ni exigence de sécurité, et nos six chefs d'entrepôt appellent ses techniciens
sur leur mobile personnel. Le logiciel des sondes de température, qui porte la preuve produite à l'audit
annuel du client pharmaceutique, est hébergé chez son fournisseur, et notre Responsable Qualité dit
elle-même qu'elle ne saura pas répondre à *« qui a accès aux relevés ? »*.

**Ce qui nous alerterait : rien.** Le centre de supervision de la sécurité (**SOC**) du groupe reçoit les
journaux de notre réseau bureautique — et **aucun** journal des automates, de la box 4G, ni du WMS
lui-même. Une mise à jour qui ferait autre chose que ce qu'elle annonce entrerait exactement comme les
précédentes ; un accès de maintenance utilisé par quelqu'un d'autre que l'intégrateur ressemblerait trait
pour trait à une intervention légitime. Nous serions, comme Mærsk en 2017, **client du mauvais logiciel
au mauvais moment** : ce transporteur n'a pas été piraté, il a installé de bonne foi la mise à jour d'un
logiciel légitime, pour 250 à 300 millions de dollars sur ses seules activités *Transport & Logistique*
en un trimestre. Nous exerçons son métier, et un arrêt du WMS de plus de six heures bloque **40 % du
volume expédié du groupe**, avec une reprise qui n'est pas démontrée : les sauvegardes quotidiennes n'ont
jamais été restaurées depuis la mise en service.

**Pourquoi je refuse de répondre « oui, mais nous avons un SOC ».** Ce serait vrai et faux à la fois, et
un dirigeant qui l'entendrait cesserait de m'écouter au bon moment. Le SOC couvre deux filiales sur
quatre et, chez nous, la moitié bureautique d'un réseau qui n'est même pas cloisonné de l'industriel.
Dire que nous sommes surveillés parce qu'un SOC existe, c'est confondre l'organe et la couverture — et
c'est précisément ce genre de phrase qui fait qu'un comité découvre son exposition le jour de l'incident.

**Ce que je ne dirai pas non plus** : ni qu'une compromission est en cours — je n'en ai **aucun élément**,
et l'annoncer serait dépasser ce que le dossier prouve —, ni que le sujet est propre à Logistique. Éducation
confie ses sauvegardes à un sous-traitant de second rang **absent de son contrat**, et l'infogérant de
Territoires détient des clés de chiffrement qu'il a refusé **par écrit** de rendre, jusqu'en 2028. Le
problème est un problème de groupe ; c'est ce qui le rend traitable par une règle de groupe.

---

## Recommandation à la direction

> Je recommande que le Comité Exécutif **donne jeudi une date et un propriétaire** à la recommandation n°5
> du rapport d'audit — la remontée au SOC des journaux du WMS, de la liaison 4G de l'intégrateur et des
> automates. C'est la seule des cinq recommandations qui n'en a toujours pas, c'est la moins coûteuse, et
> c'est celle qui remplit la case vide : tant qu'elle n'est pas tenue, **toute clause que nous ajouterons
> à nos contrats sera invérifiable**, et nous continuerons de dépendre de la bonne foi de nos prestataires
> pour savoir ce qui se passe chez nous. Je demande en conséquence que la surveillance de ces trois flux
> devienne une **condition de la tolérance** accordée à l'interconnexion bureautique/industriel jusqu'à la
> fenêtre hors pic de 2027 : un écart qu'on ne surveille pas n'est pas une tolérance, c'est un pari.

---

*Note : cette page est individuelle et engage son seul auteur. Maxime rend la sienne, sur la même
question, avec son propre angle.*
