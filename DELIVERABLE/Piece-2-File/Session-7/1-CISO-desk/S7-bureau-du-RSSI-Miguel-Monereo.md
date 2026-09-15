# Bureau du RSSI — Séance 7

**« Combien tout cela va nous coûter, et surtout, combien coûte le fait de ne rien faire ? »**

**Miguel Monereo** · Groupe 4 (Translog) · filiale MERIDIAN Logistique · une page

---

**À la seconde question, je ne peux répondre aujourd'hui qu'un seul chiffre certain : 12 000 € par jour
d'arrêt.** C'est la pénalité contractuelle du client pharmaceutique, et c'est tout ce que le dossier
documente. Ce n'est pas notre perte — c'est la part de notre perte que quelqu'un a pris la peine d'écrire
dans un contrat. **Ce que cette réponse révèle m'intéresse plus que la réponse : nous ne savons pas
chiffrer notre propre arrêt, et cette ignorance est un constat de pilotage avant d'être un problème de
sécurité.**

**Trois nombres manquent, et ils ne se demandent pas au même endroit.** Deux sont chez vous, Monsieur le
Directeur Financier, et je vous les demande nommément : le **chiffre d'affaires moyen expédié par jour**,
sans lequel les 40 % du volume du groupe bloqués au-delà de six heures restent un pourcentage et non une
somme ; et le **coût moyen d'un avoir ou d'un retour sur erreur de préparation**. Le troisième est chez
nous, et c'est le plus gênant.

**Ce troisième nombre est le temps qu'il nous faudrait pour revenir.** Nos sauvegardes du logiciel de
gestion d'entrepôt (WMS) tournent tous les jours et **n'ont jamais été restaurées depuis la mise en
service** : nous ignorons notre délai de reprise réel (RTO). Or la borne haute du coût de l'inaction, c'est
la perte quotidienne multipliée par une durée — et tant que cette durée est inconnue, cette borne n'est pas
« floue », elle est **indéterminée**. Je peux citer des incidents documentés qui parlent de jours à des
semaines de mode dégradé ; je ne peux pas dire ce que *nous* ferions, parce que personne ne l'a jamais
essayé.

**D'où la mesure que je place en tête, et ce n'est pas la plus chère.** Le test de restauration du WMS est
la seule du plan qui **transforme une borne inconnue en nombre** : les autres réduisent la vraisemblance
d'un scénario, celle-là nous rend capables de répondre à votre question. Tant qu'elle n'est pas faite,
chaque discussion budgétaire rejouera celle d'aujourd'hui, avec le même unique chiffre contractuel sur la
table.

**Ce que je ne dirai pas au Comité** : ni que ces 12 000 € mesurent notre perte — ils ne contiennent ni
chiffre d'affaires perdu, ni reconstruction, ni avoirs —, ni que le plan produira un retour sur
investissement chiffrable. La sécurité produit des incidents évités, et un incident évité ne se compte pas.
Ce que j'offre en échange du budget, c'est une fourchette dont chaque terme porte sa source et son année,
et la liste explicite de ce qu'elle ne sait pas encore.

---

## Recommandation à la direction

> Je recommande d'inscrire le **test de restauration du WMS avec mesure du délai de reprise réel** en
> première mesure du plan de traitement, avant les mesures plus coûteuses : c'est la seule qui remplace une
> inconnue par un nombre, et elle conditionne la qualité de tous les arbitrages budgétaires suivants. Je
> demande au Directeur Financier de fournir, sous la même échéance, le chiffre d'affaires moyen expédié par
> jour et le coût moyen d'un avoir sur erreur de préparation. Avec ces trois nombres, la fourchette que je
> rapporterai au Comité sera celle de MERIDIAN, et non plus un ordre de grandeur emprunté à d'autres.

---

*Note : cette page est individuelle et engage son seul auteur. Maxime rend la sienne, sur la même
question, avec son propre angle.*
