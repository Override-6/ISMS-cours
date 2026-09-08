# Bureau du RSSI — Séance 2

**Pourquoi tout inventaire d'actifs est-il faux, et qu'en fait-on ?**

**Maxime** · Groupe 4 (Translog) · filiale MERIDIAN Logistique · une page

---

Il y a deux façons pour un inventaire d'être faux, et elles n'appellent pas la même réponse. La première est **subie** : un outil ne décrit que ce qu'on l'a configuré pour voir, et un angle mort structurel n'est la faute de personne. La seconde est **produite** : quelqu'un, quelque part, a satisfait un besoin réel en dehors de tout inventaire, parce que la voie officielle était trop lente ou absente. C'est cette seconde catégorie — le Shadow IT, et sa variante aggravée, le Shadow AI — qui mérite qu'on s'y arrête, parce qu'elle est évitable et que nous venons d'en avoir la preuve dans notre propre groupe.

**Onze services, deux natures de risque.** Chez Éducation & Territoires, l'inventaire a fait remonter onze abonnements souscrits par les équipes pédagogiques hors DSI. Dix relèvent du Shadow IT ordinaire — des outils en ligne classiques, hors filtrage et hors sauvegarde, mais dont les données restent ce qu'on y a mis. Le onzième change de catégorie : un outil d'intelligence artificielle générative y reçoit des copies d'élèves pour relecture — des données personnelles de mineurs, transmises à un tiers dont personne n'a lu les conditions d'utilisation, hors de tout registre RGPD. Le Shadow IT ouvre un trou dans le périmètre ; le Shadow AI organise une fuite par l'usage lui-même, sans qu'aucun attaquant n'intervienne — c'est exactement ce que chiffre le rapport IBM 2025 : une brèche sur cinq est due au Shadow AI, pour un surcoût moyen de 670 000 $, et la cause n'est jamais un assaillant sophistiqué mais un outil que personne ne surveillait.

**Le paradoxe qu'il faut assumer devant un dirigeant.** Cette réponse d'Éducation, la plus trouée en apparence, est la **meilleure des trois** reçues par le RSSI Groupe — elle a découvert ses propres angles morts. Un inventaire qui ne révèle jamais rien n'est pas rassurant, il est suspect. La conséquence de gouvernance est directe : si découvrir un trou expose la filiale la plus honnête à la sanction, la prochaine filiale ne le déclarera plus. L'incitation doit protéger la découverte, pas seulement l'exiger.

**Le même mécanisme existe chez nous, sans porter le nom de Shadow IT.** Le compte de domaine partagé avec le prestataire de tierce maintenance de Logistique, dont personne ne connaît le nombre de porteurs réels, est né du même geste : un besoin opérationnel réel — faire intervenir la TMA vite — satisfait en dehors de toute gouvernance nominative. Ce n'est pas un outil souscrit en douce, mais le résultat est identique : un accès dont on ne sait plus qui l'utilise.

**Qu'en fait-on, alors.** Pas une interdiction service par service, qui manquerait la moitié du métier et ferait renaître ailleurs le même besoin non couvert. Le critère qui fonctionne tient en deux questions, déjà écrites pour Éducation : quelles données y transitent, et existe-t-il une alternative validée ? Trois issues seulement — documenter et régulariser, superviser avec échéance, ou fermer en ouvrant immédiatement une réponse au besoin. Ce même critère, appliqué au compte partagé de la TMA, conclut sans ambiguïté : donnée d'accès à un système critique, alternative nominative disponible (comptes individuels révocables) — c'est un cas à **superviser sous échéance**, pas à laisser prospérer au motif qu'il n'a jamais été nommé « Shadow IT ».

---

## Recommandation à la direction

> Je recommande que le Comité Exécutif étende sans attendre le prochain cycle d'inventaire le critère « données transitées / alternative validée » de la séance 2 au compte partagé de la TMA de Logistique, avec un passage à des accès nominatifs sous trente jours — le même délai que la règle de groupe déjà proposée pour tout élément hors inventaire. Le coût est nul : l'alternative existe, seule la nomination manque. Je recommande aussi que la valorisation de la découverte, actée pour Éducation, devienne une règle écrite avant le prochain incident, pas après.

---

*Note : cette page est individuelle et engage son seul auteur. Miguel rend la sienne, sur la même question, avec son propre angle.*
