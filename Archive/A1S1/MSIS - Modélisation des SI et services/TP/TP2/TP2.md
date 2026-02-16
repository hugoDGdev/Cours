## I.
1. Ici, la classe est la classe que l'on pourrait appeler GROUPS, et qui possède les attributs 'name', 'nbMembers', 'resp', 'telResp', 'hours' et "trainers" :

2. a) 'hours' et 'trainers' sont multivalués, les autres monovalués
   b) 'hours' et 'trainers' sont également composites, les autres simples
   c) aucune valeur ne peut à priori être obscure
   d) seule la valeur 'name' doit être permanente. Les autres peuvent changer.

3. \**voir le schéma en bas de page*\*

4. La classe a une clé primaire, l'attribut 'name', unique et permanent, mais il serait techniquement possible de créer un identifiant unique et numérique. De cette façon, l'attribut name n'aurait plus besoin d'être permanent et le club pourrait changer les noms de ses groupes.

![[tp2_1.png]]
<u>Schéma des groupes en forme non normale</u>

5. La classe n'est pas en forme normale : en effet, elle a plusieurs attributs multivalués et composites. Voici un modèle schématique de restructuration en forme normale : 
 ![[tp2_full.png]]
<u> Diagramme des 3 classes principales dont 'groupes' en forme normale</u>
