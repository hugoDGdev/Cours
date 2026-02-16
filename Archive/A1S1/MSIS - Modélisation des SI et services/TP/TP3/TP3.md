## I )
1. 
	- Vrai : la cardinalité de la classe moniteur dans l'association est de 1 à 2 soit entre 1 et 2 moniteurs par cours
	- Faux : Chaque moniteur doit assurer entre 0 et 10 cours. Il peut donc n'en assurer aucun ou en assurer 4
	- Faux : Un cours peut avoir entre 1 et 2 moniteurs
	- ? : Si un moniteur est malade, un autre peut être ajouté mais il n'est pas certain que chaque cours aie 2 moniteurs
2. 
	- Oui, un acteur peut jouer dans * films, soit un nombre indéterminé de 0 à l'infini
	- Oui, un film peut avoir * acteurs, soit un nombre indéterminé de 0 à l'infini
	- Oui, car la classe d'association Rôle est liée à l'association à la cardinalité * entre Acteur et Film, donc un Acteur peut être relié par un Rôle à plusieurs Films
	- Oui, car * inclut le 0, donc il pourrait n'y avoir aucun film associé par la classe Rôle
	- Plusieurs films pourraient avoir le même titre car il n'est pas spécifié que Titre est la clé de la classe, mais il semble que Titre soit la valeur la plus appropriée comme potentielle clé primaire.
	- Non car chaque association Acteur <-> Film est un objet distinct de la classe Rôle avec un TypeRôle propre, donc un acteur pourrai tout à fait jouer un type différent dans chaque film
	- Oui, comme la cardinalité est de * pour les 2 classes, il peut y avoir plusieurs associations entre le même objet d'Acteur et le même objet de Film

## II )
1. ![[tp3_1_clair.png]]
   
2. 
   ![[tp3_2.png]]
3. 
   ![[Pasted image 20251022140459.png]]
4. 
   ![[Pasted image 20251022142119.png]]

## III) 

ACTEUR (NomActeur= PrénomActeur= // DateNaissance<sup>=</sup>, Pays<sup>=</sup>)
FILM (Titre<sup>=</sup> // Année<sup>-</sup>, Description<sup>=</sup>, Réalisateur<sup>=</sup>)
ROLE (NomActeur<sup>=</sup> PrénomActeur<sup>=</sup> Titre<sup>=</sup> // NomPersonnage=, TypeRôle=)

*Je suis ici parti du principe que le film pouvait ne pas encore être sorti et donc que l'année de sortie pouvait être obscure et non permanente*