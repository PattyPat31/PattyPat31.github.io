# Résultats du TP : 

**Présentation des cas étudiés et interprétation des résultats**


La première partie de notre travail dans ce cours s'est basée sur une simulation numérique 1D (considérant que le temps et la position longitudinale dans le tube comme variables), qui permet de modéliser la manière dont le sang s’écoule dans un vaisseau sanguin. 

C'est en retravaillant ce programme, en y ajoutant de nouvelles conditions d'entrée, de sortie et en testant différents paramètres de pression, élastance ou viscosité que nous avons pu mettre au point les résultats de cette page.






| **Sommaire**   | 
|:---------------| 
| [Présentation du programme initial](#Presentation)|
| [Nouvelle condition d'entrée - pulse](#2)|
| [Variations de la densité du sang passant dans le tube ](#3)|
| [Prise de pression et de débit à différents endroits dans le tube](#Diff)|




## Présentation du programme initial <a id="Presentation"></a>








## Nouvelle condition d'entrée - pulse <a id="2"></a>

Comme le coeur envoie du sang dans les artères de manière pulsée, il fut rapidement envisagé de reproduire une pulsation à l'entrée du vaisseau que l'on souhaite modéliser.

Nous souhaitons donc reproduire une surpression à l'entrée du tube.
Pour représenter cela, nous avons changé les paramètres de pression en entrée pour y faire intervenir une sinusoïde (pour obtenir des résultats plus lisibles).

La pression aurait donc la forme suivante en entrée :

<p align="center">
<img src="https://render.githubusercontent.com/render/math?math=P_{entree}(t)=P_{max} * sin\left(\frac{\pi t}{T_{pulse}}\right)">
</p>

puis, cette perturbation se propagerait tout le long du tube.
Si nous traçons cette perturbation de pression en entrée en fonction du temps, nous pouvons obtenir la figure suivante :

<p align="center">
<img src="Images/TP/testpulse.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>

Les résultats relatifs aux essais avec cette nouvelle condition d'entrée seront développés par la suite.





## Variations de la densité du sang passant dans le tube <a id="3"></a>


Nous avons choisi de tester le comportement de ce modèle 1D en mettant en évidence l'impact de la densité du sang qui le traverse sur l'évolution de la pression et du débit, en entrée et en sortie du tube.

Ici, le tube choisi a une longueur de 20cm, les paramètres sont similaires à ce qui a été établi précédemment (nous conservons un pulse en entrée).



En considérant que le fluide traversant le tube possède une densité de 0.01, puis une densité de 0.1, la pression et le débit - en entrée et en sortie du tube - sont de la forme suivante : 


<img src="Images/TP/densité 0.01 PM.png" alt="image1" style="display:inline-block; width:48%; border:0;"/> <!-- Image à gauche -->
<img src="Images/TP/densité 0.1 PM.png" alt="image2" style="display:inline-block; width:48%; border:0;"/> <!-- Image à droite -->

<p align="center">
pulse pour une densité de 0.01/ de 0.1
</p>



On remarque ainsi que la pression baisse entre l’entrée et la sortie quand la densité est inférieure à 1. Pour vérifier si ce phénomène persiste avec une densité égale ou supérieure à l'unité, nous l'augmentons encore : 


<p align="center">
<img src="Images/TP/densité 1 PM.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>

<p align="center">
pulse pour une densité de 1
</p>


Au delà de l'unité, il n'y a plus de distinction notable entre l'entrée et la sortie du tube.



<img src="Images/TP/densité 5 PM.png" alt="image1" style="display:inline-block; width:48%; border:0;"/> <!-- Image à gauche -->
<img src="Images/TP/densité 10 PM.png" alt="image2" style="display:inline-block; width:48%; border:0;"/> <!-- Image à droite -->

<p align="center">
pulse pour une densité de 5/ de 10
</p>

<img src="Images/TP/densité 25 PM.png" alt="image1" style="display:inline-block; width:48%; border:0;"/> <!-- Image à gauche -->
<img src="Images/TP/densité 50 PM.png" alt="image2" style="display:inline-block; width:48%; border:0;"/> <!-- Image à droite -->

<p align="center">
pulse pour une densité de 25/ de 50
</p>


<img src="Images/TP/densité 100 PM.png" alt="image1" style="display:inline-block; width:48%; border:0;"/> <!-- Image à gauche -->
<img src="Images/TP/densité 250 PM.png" alt="image2" style="display:inline-block; width:48%; border:0;"/> <!-- Image à droite -->

<p align="center">
pulse pour une densité de 100/ de 250
</p>

<img src="Images/TP/densité 500 PM.png" alt="image1" style="display:inline-block; width:48%; border:0;"/> <!-- Image à gauche -->
<img src="Images/TP/densité 1000 PM.png" alt="image2" style="display:inline-block; width:48%; border:0;"/> <!-- Image à droite -->

<p align="center">
pulse pour une densité de 500/ de 1000
</p>


Augmenter la densité décale les courbes de sorties par rapport à celles d’entrée. On en déduit que la vitesse de propagation augmente, car celles-ci mettent plus de temps à atteindre la fin du tube. 


On peut par ailleurs déduire la vitesse des ondes en mesurant la différence de temps entre les 2 sommets des courbes. 
Puisque nous connaissons la longueur L du tube, ainsi que la vitesse, nous pouvons obtenir t :

on calcule le t = d/v. 








## Prise de pression et de débit à différents endroits dans le tube  <a id="Diff"></a>


Les résultats présentés ici seront basés sur les paramètres suivants :

- Elastance du tube E<sub>L</sub> : ``1367000`` dyn/cm<sup>2</sup>
- Section du tube : ``0.1361`` cm<sup>2</sup>
- Longueur du tube  L : ``25`` cm
- Densité du fluide : ``1.06`` kg/m<sup>3</sup>
- Viscosité du fluide : ``35`` millipoises [mP]

Ces données réfèrent à du sang passant dans une carotide.
On travaille ici sur un fluide supposé newtonien, la viscosité sera donc supposée constante. De même, on suppose ici la section A<sub>0</sub> constante.

En reprenant la condition d'entrée introduite précédemment et en traçant la pression à la sortie du tube, il vient :

<p align="center">
<img src="Images/TP/entreesortie.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>

La pression en sortie est significativement supérieure au pulse imposé en entrée (plus de deux fois supérieure). Cela est dû notamment aux refléxions tout au long du tube, qui pousse une plus grande quantité à la fois à la sortie du tube et provoque une surpression.




Nous pouvons d'ailleurs mettre cela en parallèle avec l'évolution du débit à ces deux points de mesure : 

<p align="center">
<img src="Images/TP/entreesortiedebit.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>

Le débit en sortie du tube est bien moins important qu'en entrée, tandis qu'un important pic négatif (courbe bleue) se profile après le signal en sortie.
Cela peut venir des conditions de sortie imposées dans notre programme. En effet, nous considérons une condition de type Windkessel en sortie du tube. La résistance  
périphérique (résistance le long des parois du tube lors de l'écoulement du sang) y est définie par : 


<p align="center">
<img src="https://render.githubusercontent.com/render/math?math=P_{entree}(t)=R_{parois} = \frac{P_{entree} - P_{sortie}}{Q}">
</p>

Où Q est le débit à l'endroit considéré. Ainsi, le débit est d'autant plus faible en sortie que la résistance considérée est importante (elle est de 34875 dyme.s/cm  dans notre cas). Une quantité notoire de sang va être réfléchie en sortie du tube et seulement une partie traversera effectivement la sortie. De fait, le débit en sortie est bien plus moindre qu'ailleurs.

Le sang réfléchi dans le sens inverse de l'écoulement peut même ressortir du tube par l'entrée, d'où le débit négatif observé quelques temps après le pic de débit en sortie.



Ce phénomène peut également expliquer l'intensité du pic de pression en sortie, puisque l'on s'attend bien à avoir plus de pression dans une cette même zone, celle amenée initialement par l'onde de pulsation ainsi que celle du flux renvoyé.







Un des problèmes pouvant limiter notre analyse dans ce TP est dû aux endroits choisis dans le tube pour tracer l'évolution des paramètres. Si nous ne prenions que l'évolution au cours du temps de ce qu'il se passe en entrée et/ou en sortie, nous ne pourrions pas vérifier le fonctionnement intermédiaire du programme.

Pour y remédier et avoir un meilleur aperçu de l'évolution des paramètres le long du tube, nous prenons des mesures également au milieu de celui-ci.




<p align="center">
<img src="Images/TP/entreemilieusortie.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>

Le même phénomène de reflux est perceptible au milieu du tube, même s'il est moins prononcé qu'en sortie.

Autrement, on peut déjà voir ici que la pression n'a plus la même allure au milieu du tube, le pic y étant plus faible qu'en entrée. 
La résistance périphérique n'étant pas nulle pour notre essai, il se peut que des pertes de charge tout au long du tube soient à l'origine de cette modification.

Pour vérifier cela, on peut augmenter encore le nombre de points de mesure :



<p align="center">
<img src="Images/TP/touslespointspression.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>

En réalité, les pics de pression relevés tout au long du tube semblent décroître, en partant de la sortie du tube et jusqu'au quart de celui-ci.
L'hypothèse des pertes de charge ne permet donc pas à priori d'expliquer une telle évolution de la pression dans le tube.


Nous avons donc pu envisager que ces résultats étaient peut-être dûs à un mauvais relevé des pressions au cours du temps. 
En effet, pour relever les données de pression, il nous faut mettre en place un schéma de calcul suffisamment en avance sur l'onde à analyser pour pouvoir relever des résultats, sans pour autant être trop rapide pour ne pas omettre des informations pouvant être trop éloignées temporellement de ce que l'on souhaite obtenir.
Cette condition de 'vitesse de relevé' à respecter, la condition CFL, pourrait être à l'origine de nos résultats inexplicables.

Nous sommes partis de base sur un CFL valant 3 fois la vitesse de l'onde produite dans notre modèle. En prenant une condition CFL de 2.5 fois la vitesse de l'onde, nous obtenons la figure suivante : 

<p align="center">
<img src="Images/TP/touslespointspression25.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>



Il apparaît en effet bien, cette fois-ci, que le pic diminue jusqu'à ce que l'on arrive aux trois quarts du tube. Le niveau du pic repart cependant encore à la hausse après ce passage. 

Nous essayons donc encore de réduire cette condition CFL, cette fois ci à 2.2 fois la vitesse de l'onde :



<p align="center">
<img src="Images/TP/touslespointspression22.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>

Nous obtenons enfin des résultats cohérents avec ce que nous aurions pu imaginer jusqu'à la fin du tube. 
Il est donc à présent plus envisageable de reconsidérer que les pertes de charge soient bien à l'origine des différences tout au long du tube.

L'écoulement étant freiné au cours de son évolution notamment au niveau des parois et à cause de sa viscosité, il ne peut pas y avoir exactement la même quantité de sang à chaque endroit du tube à un instant t, une partie étant restée en arrière. Cela peut bien expliquer cette différence de pression dans notre tube.


La condition CFL n'étant pas remplie indéfiniment, nous ne pouvons plus obtenir de résultats pour une vitesse de relevé égale ou inférieure à 2.1 fois celle de l'onde. L'onde étant déjà passée dans la zone 'traitée' par notre schéma de calcul à un instant t, nous ne pouvons plus rien en retirer.

Le meilleur résultat que nous pourrons donc obtenir est celui présenté ci-dessus.




D'autre part, ce même affichage peut être mis en place pour la mesure des débits en fonction du temps :

<p align="center">
<img src="Images/TP/entreesortiedebit22.png" alt="Arterial Tree" style="width:70%; border:0;">
</p>


Ici, le débit en sortie diminue drastiquement à cause de la condition imposée en sortie mais les pics de débit diminuent à priori de la même manière que pour la pression et à cause des mêmes pertes de charge au long du tube.



## Essai de nouvelles conditions de sortie :
**Cas d'une artère bouchée :**

Dans ce cas-ci on a mis en place un pulse à l'entrée de l'artère et on impose un débit nul en sortie afin de simuler une artère bouchée. 
On obtient l'évolution du débit à l'entrée suivant :
<p align="center">
<img src="Images/TP/debit_illustre.png" alt="Débit" style="width:75%; border:0;">
</p>
On voit clairement l'onde qui revient, en débit négatif, puis qui repart après un rebond, ce sont les réflexions de l'onde. Les pics du débits décroissent en fonction du temps, cela est dû à la viscosité. On peut essayer de l'estimer en modélisant sur matlab la pente.












Pour tous nos affichages précédents, il est clair que nos résulats restent peu lisibles, en grande partie à cause des non-linéarités présentes de base dans le modèle utilisé lors de l'élaboration de ce tube 0D. 
Il sera donc présenté par la suite une amélioration de cette modélisation, ne présentant plus qu'une évolution linéaire.


