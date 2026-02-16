Notation formelle :
Cours (NoCours // Titre, Semestre, Jour, HeureDeb, HeureFin)
// représente les associations : tout ce qui est avant est la clé de ce qui est relié ou relie

-----------------
Forme normale classe : 
- a une clé
- uniquement attributs atomiques (simples) => nouv. classe
- "                          ""     monovalués => creer nouv. classe
--------
Domaines d'attributs :
Mot, Texte, Entier, entier positif, décimal, réel, Booléen, date
Dom MOIS : Mot  {janvier, février...etc}

----
Attributs multivalués (plusieurs valeurs) => Attribut*
Attributs composites (plusieurs attributs en un) =>
Attributs dérivés (calculés d'un autre) => Age/
Valeurs obscures (possiblement undefined) => noVehicle-
Attribut permanent (valeur initiale définitive) => catégorie=

----------
Association : 
voiture -0..10---appartient à>-------1..2-personne
 1 à 2 pers max peuvent posseder même voit mais 1 à 2 personne peuvent posséder de 0 à 10 voit

association ternaire :
cours ----- (planning) ------ salle
			|
		enseignant

il est recommandé de transformer l'association "planning" en classe ("séance" par exemple)

Contraintes :
Ordonnancement - ordre entre objets associés => {ordonné}
Exclusion - deux associations qui ne peuvent pas être simultanées entre deux objets => {ou exclusif}
Inclusion (l'inverse)

Associations complexes :
- Composition - objet fait partie d'un autre
- Agrégation - Relation m/s entre 2 obj - 1 peut exi sans autre mais pas dans l'autre sens
- Spécialisation - objets + précis : eau ------> boisson
	- types : - disjointe (OU) vs chevauchante (ET/OU) - totale (au moins 1) vs partiel (facultatif)
-----------------
RI - tableaux de portée :
Pour chaque RI, on écrit un tableau avec classes (lignes) et colonnes "creer"//"supprimer"//"modifier". Creer et supprimer == oui/non risque et modifier, attributs à risque.

-----------
CVO
état initital = disque noir; final = disque noir entouré noir
transition = événement [condition] / action
choix (if else) => carré à 45°

états composites : abstraction = en activité et en vacances, sous états de en activ = au bureau, en déplacement
modélisation = plus petit diagramme avec état initial et titre dans boite

--------------------------------
usecases
formalisation : numéro, nom, contexte d'utilisation, portée, acteur, parties prenantes et intérêts, conditions, garanties minimales, garanties de succès, déclencheur, scénario de réussite (#n. action), extensions (#n.k condition action ou subcase)

extensions : ligne pointillé flèche sens inverse <<extend>> + grosse boite condition fléchée vers fleche
inclusion