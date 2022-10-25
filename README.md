# La-boite-a-z

Actuellement version 2

Programme permettant de calculer différentes choses pour le moteur du Ciao :

En définissant les valeurs de bases (course du vilebrequin, entraxe de la bielle)

On va pouvoir calculer facilement :

* Le rapport entre l'angle du vilebrequin (calculé depuis un disque gradué) ET la pige de calage (descente en mm du piston) depuis le PMH
Cela permet par exemple de calculer l'angle/la pige à utiliser pour l'avance de l'allumage à rupteur qu'on souhaite

* Le rapport entre la valeur du diagramme d'échappement (ou d'admission) et la cale à choisir pour modifier ce diagramme
Cela permet par exemple de choisir la cale idéale pour passer d'un diagramme à un autre
cela permet de tester une valeur de cale et voir le diagramme que cela donnerait


![Bielle_manivelle_tech](https://user-images.githubusercontent.com/109454001/197615115-ff3e21f5-940e-4244-b759-96952d6729f9.jpg)

Les formules mathématiques utilisées sont les suivantes, à la différence que le programme utilise comme référentiel d'angle, le PMH.
Cela signifie que depuis les formules ci-dessous, l'angle à entrer dans la formule est  = 90° - angle mesuré depuis PMH
(attention excel ou certains langages necessitent de convertir les radians et degrés et donc d'appliquer un correctif en multipliant par  pi/180 )
La distance OA correspond à la demi-course dela bielle
la distance AB est l'entraxe de la bielle (pour la mesure : prendre la longueur totale et y retrancher la moitié de chaque diametre de maneton)
le PMH correspond à l'alignement de OA et AB
la pige (donc la descente du piston) correspondra alors à OA+AB (distance au PMH) - OB
Tous les calculs sont faits avec la variation de OB, ce qui par consequence est identique pour le piston, puisqu'il coulisse à la verticale.
Le piston aura donc la même variation que OB

La cale pour la modification du diagramme change tout simplement la position du point B (qui correspond lui à la position la plus haute vers le PMH de la lumiere
(d'échappement ou admission ,c'est pareil)

Petite info sur le diagramme d'achappement par exemple:
lorsqu'on dit 130° ,il faut bien comprendre que la lumiere va s'ouvrir et se fermer exactement au meme endroit sur le viebrequin en descente et en montée
donc 130° veut dire que par rapport au PMB on aura un angle de 130/2 = 65° avant le PMB et 65° apres le PMB (180°)
Ce qui correspond par rapport au PMH à une ouverture de la lumiere (point B) à 180°-65° = 115°
et une fermeture (retour au point B) à 180°+65° = 245°
donc pour un diagramme de 130°, la lumiere s'ouvre à 115° depuis le PMH et se ferme à 245° depuis le PMH
115° et 245° sont bien symétriques par rapport au PMB (angle de 65° ) et 245°-115° on a bien 130°
Donc réhausser un diagramme revient à modifier la position du point B
Connaissant la formule liant le diagramme (odnc l'angle sur le vilebrequin) à la distance OB
La cale sera un calcul entre 2 diagrammes différents, donc 2 distances OB différentes.
et à l'inverse, essayer une cale d'embase reviendra à modifier 2 distances OB différentes donc 2 angles de vilebrequin diffénts donc 2 diag différents.


![Calcul OB](https://user-images.githubusercontent.com/109454001/197621853-8681408d-8726-4d01-8c14-ea0b0721b544.jpg)

![Calcul angle](https://user-images.githubusercontent.com/109454001/197621870-e223336d-962e-409d-b341-1bc8a3fb3855.jpg)


Et pourquoi le PMH/PMB est si difficile à trouver ?
Il faut tout simplement regarder la représentation graphique de la course du piston (de la distance OB en fait) :
c'est une sinusoide et on voit que la courbe s'aplatie justement lorsque OB est max (PMH) et min (PMB)




![course piston](https://user-images.githubusercontent.com/109454001/197628168-3dccc064-100a-46e7-a9b5-89f6da704048.jpg)





source des images:
https://fr.wikipedia.org/wiki/Syst%C3%A8me_bielle-manivelle

