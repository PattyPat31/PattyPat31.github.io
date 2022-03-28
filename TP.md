# Résultats du TP

**Présentation des cas étudiés et interprétation des résultats**

Vous décrirez ici vos cas tests (propagation d'un pulse dans un vaisseau, 
étude des réflexions aux conditions aux limites, etc...)
Préciser bien les valeurs de vos paramètres. Par exemple:
 - Elastance du tube E<sub>L</sub>=``1367000`` dyn/cm<sup>2</sup>
 - Section au repos A<sub>0</sub>=``0.1361`` cm<sup>2</sup>
 - Longueur du vaisseau L=``25`` cm
 - etc...

Bien entendu, vous illustrerez vos résultats par des figures pertinentes:
<p align="center">
<img src="Images/TP/Arterial_tree.jpg" alt="Arterial Tree" style="width:20%; border:0;">
</p>


**Cas d'une artère bouchée :**

Dans ce cas-ci on a mis en place un pulse à l'entrée de l'artère et on impose un débit nul en sortie afin de simuler une artère bouchée. 
On obtient l'évolution du débit à l'entrée suivant :
<p align="center">
<img src="Images/TP/debit_illustre.png" alt="Débit" style="width:20%; border:0;">
</p>
On voit clairement l'onde qui revient, en débit négatif, puis qui repart après un rebond, ce sont les réflexions de l'onde. Les pics du débits décroissent en fonction du temps, cela est dû à la viscosité. On peut essayer de l'estimer en modélisant sur matlab la pente.
