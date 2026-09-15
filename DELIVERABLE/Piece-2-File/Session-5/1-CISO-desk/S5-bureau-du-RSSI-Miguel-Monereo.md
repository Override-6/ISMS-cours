# Bureau du RSSI — Séance 5

**« Qui fixe l'appétence au risque, et comment se rédige-t-elle ? »**

**Miguel Monereo** · Groupe 4 (Translog) · filiale MERIDIAN Logistique · une page

---

**Le danger de jeudi n'est pas que le Comité refuse la règle : c'est qu'il l'adopte en croyant adopter
autre chose.** L'**appétence** dit ce que le groupe accepte de dégrader, durablement et pour tous les cas.
Le **seuil d'acceptation** est sa traduction sur une grille : au-dessus de cette ligne, un risque coté
appelle une décision. La **tolérance** est autre chose — un écart assumé entre l'appétence et la réalité,
qui doit se refermer. Les deux premières s'écrivent une fois ; la troisième porte une date, sinon elle
n'existe pas.

**Le glissement va toujours dans le même sens : une tolérance non datée se fait passer pour une
appétence.** Une appétence engage la direction pour toutes les décisions à venir ; une tolérance engage
*quelqu'un*, sur *un* écart, jusqu'à *une* date. Quand la seconde prend le costume de la première, un écart
temporaire devient une orientation permanente sans que personne ne l'ait décidé — et il sort du registre,
parce qu'on ne surveille pas une orientation.

**L'exemple est sous nos yeux, sur notre actif le plus critique.** « On garde l'interconnexion entre réseau
bureautique et réseau industriel (IT/OT) jusqu'à la prochaine fenêtre hors pic, avec surveillance
renforcée, et on réexamine au trimestre prochain » : dite ainsi, c'est une tolérance en bonne et due forme.
Confrontée à nos faits, il lui manque les trois choses qui en feraient une.

- **La surveillance n'existe pas.** Le centre opérationnel de sécurité du groupe (SOC) ne reçoit **rien**
  des automates, rien de la liaison 4G de l'intégrateur, rien du logiciel de gestion d'entrepôt (WMS). Nous
  tolérerions un écart que nous ne regardons pas : ce n'est pas une tolérance, c'est une ignorance datée.
- **L'échéance ne referme pas.** « 12/7/2027, hors pic » est une cible adossée à une fenêtre
  d'exploitation, pas un engagement assorti d'une escalade si la date est manquée. Une fenêtre se déplace ;
  un engagement se tient ou se justifie.
- **Le propriétaire n'a pas les deux côtés.** La liaison 4G a été installée par l'Exploitation précisément
  pour ne plus dépendre de la DSI de la filiale. Un porteur qui n'a autorité que sur la moitié du réseau ne
  porte rien.

**Et une tolérance ne s'étend pas par voisinage.** Tolérer le calendrier du cloisonnement ne tolère pas le
secret du compte de service WMS↔automates, identique sur les six entrepôts depuis 2019 et en clair dans un
fichier de configuration : celui-là est au-dessus de la ligne, se corrige sans fenêtre d'exploitation, et a
déjà sa mesure au rapport d'audit.

**Ce que je ne dirai pas au Comité** : ni que ces manques disqualifient la tolérance sur le principe —
l'écart est réel et le cloisonnement demande une fenêtre —, ni que les combler relève de la technique.
Dater, surveiller et nommer un propriétaire sont trois décisions de direction.

---

## Recommandation à la direction

> Je recommande que le Comité n'accorde **aucune tolérance qui ne porte ses trois signatures** — échéance
> ferme avec escalade, surveillance effective, propriétaire nommé ayant autorité sur tout le périmètre de
> l'écart — plus une mesure compensatoire. Appliqué à l'interconnexion IT/OT, cela signifie l'accorder **sous
> condition** : raccorder au SOC les journaux des automates, de la liaison 4G et du WMS **avant** la fenêtre
> de bascule. Je tiens le registre de ces tolérances et j'en rends compte chaque trimestre ; ce que je demande
> à la direction, c'est de refuser d'en inscrire une qui n'aurait pas de date.

---

*Note : cette page est individuelle et engage son seul auteur. Maxime rend la sienne, sur la même
question, avec son propre angle.*
