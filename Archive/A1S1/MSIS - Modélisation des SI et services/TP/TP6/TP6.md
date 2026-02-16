## I) 
1. RI2 : La date d'achat d'un billet est antérieure ou égale à celle du concert concerné
   - Billet : 
	   - Lorsqu'on crée un nouveau Billet, on lui attribue une date d'achat, il y a donc un risque
	   - Supprimer un billet n'a aucune influence et les règles sont respectées
	   - Une fois modifiée la date d'achat pourrait être postérieure au concert, il y a donc un risque
   - Concert
	   - Créer un nouveau concert ne change rien aux autre propriétés, les règles sont respectées
	   - Supprimer un concert ne rend pas sa date antérieure à celle des billets pour autant, règles respectées
	   - Certains billets peuvent voir leur date devenir postérieure à celle du concert si la date du concert est modifiée. Il y a un risque

Tableau corrigé : 

| _Classe_    | **Créer** | **Supprimer** | **Modifier** |
| ----------- | --------- | ------------- | ------------ |
| **Concert** | Non       | Non           | DateConcert  |
| **Billet**  | Oui       | Non           | DateAchat    |

2. RI3 : Un spectateur ne peut pas acheter plus de 4 billets pour le même concert.
- Concert 
	- Créer => OK car billets pas concernés par nouv. concert
	- Supprimer => Risque car billets achetés liés directement au concert
	- NoGroupe, DateConcert et HeureDebut, s'ils sont changés, peuvent créer une confusion entre plusieurs concerts pour un seul ensemble de billets => Risque
- Billet
	- Créer => Risque si nombre == 4
	- Supprimer => Pas de risque à priori puisqu'il n'y a pas de limite négative
	- Modifier => Si l'on attribue à un billet un IdSpectateur qui a déjà 4 billets, la règle n'est plus respectée 

Tableau corrigé :

| _Classe_    | **Créer** | **Supprimer** | **Modifier**                      |
| ----------- | --------- | ------------- | --------------------------------- |
| **Concert** | Non       | Oui           | NoGroupe; DateConcert; HeureDebut |
| **Billet**  | Oui       | Non           | IdSpectateur                      |

3. RI4 Un groupe ne peut pas faire plus de deux concerts le même jour.
- Groupe 
	- Créer => Aucun risque
	- Supprimer => Aucun risque
	- Modifier 
- Concert
	- Créer => Risque car ajouter un concert crée le risque que le groupe associé en ait déjà deux pour ce jour
	- Supprimer => Pas de risque car au pire cela réduit le nb de concerts d'un groupe mais cela ne le fera jamais dépasser 2
	- Modifier => Modifier DateConcert peut ajouter un concert à une date pour laquelle un groupe a déjà 2 concerts. De plus, modifier NoGroupe pour un concert peut avoir le même effet

Tableau corrigé : 

| _Classe_    | **Créer** | **Supprimer** | **Modifier**          |
| ----------- | --------- | ------------- | --------------------- |
| **Groupe**  | Non       | Non           |                       |
| **Concert** | Oui       | Non           | DateConcert; NoGroupe |

4. RI5 :  Le nombre des billets vendus pour un concert ne peut pas excéder la capacité de la salle où le concert a lieu.
- Scène
	- Créer => Pas de risque
	- Supprimer => Pas de risque
	- Modifier => Modifier Capacité (réduire) peut faire que le nombre de billets devient supérieur à la capacité
- Concert
	- Créer => Pas de risque
	- Supprimer => Pas de risque
	- Modifier => Si l'on modifie NomScène, il se pourrait que la nouvelle scène ait une Capacité inférieure au nombre de billets
- Billet
	- Créer => Risque que le nombre soit déjà égal à la Capacité
	- Supprimer => Pas de risque en retirant des billets
	- Modifier => Pas de risque à modifier EtatBillet car le nombre reste le même

Tableau corrigé :

| _Classe_    | **Créer** | **Supprimer** | **Modifier** |
| ----------- | --------- | ------------- | ------------ |
| **Scène**   | Non       | Non           | Capacité     |
| **Concert** | Non       | Non           | NomScène     |
| Billet      | Oui       | Non           |              |

## II) 
1. RI6 : Un spectateur ne peut pas acheter plus de 8 billets au total
	- Classes concernées : Spectateur, Billet

| _Classe_       | **Créer** | **Supprimer** | **Modifier** |
| -------------- | --------- | ------------- | ------------ |
| **Spectateur** | Non       | Non           |              |
| **Billet**     | Oui       | Non           | IDSpectateur |
2. RI7 : On enregistre maximum trois instruments par musicien. 
	- Classes concernées : Instrument, Musicien

| _Classe_           | **Créer** | **Supprimer** | **Modifier** |
| ------------------ | --------- | ------------- | ------------ |
| **MembreGroupe**   | Non       | Non           |              |
| **JoueInstrument** | Oui       | Non           | NoMembre     |

3. RI8 : Un billet ne peut pas être vendu que pour un concert qui est 'en vente'
	- Classes concernées : Billet, Concert

| _Classe_    | **Créer** | **Supprimer** | **Modifier**                      |
| ----------- | --------- | ------------- | --------------------------------- |
| **Billet**  | Oui       | Non           | NoGroupe, DateConcert, HeureDebut |
| **Concert** | Oui       | Non           | EtatConcert                       |

4. RI9 : Un concert ne peut être déplacé sur une autre scène que si cette dernière a une capacité suffisante – supérieure ou égale au nombre de billets vendus. 
	- Classes concernées : Concert, Scène, Billets

| _Classe_    | **Créer** | **Supprimer** | **Modifier**                      |
| ----------- | --------- | ------------- | --------------------------------- |
| **Concert** | Non       | Non           | NomScène                          |
| **Billet**  | Oui       | Non           | NoGroupe, DateConcert, HeureDébut |
| **Scène**   | Oui       | Non           | Capacité                          |

5. RI10 : Un billet utilisé ne peut pas être annulé.
	- Classe concernée : Billet

| _Classe_   | **Créer** | **Supprimer** | **Modifier** |
| ---------- | --------- | ------------- | ------------ |
| **Billet** | Non       | Oui           | EtatBillet   |
## III)
1. Achat d'un billet de concert : 
	- RI2 : La date du concert doit être postérieure à la date du jour lors de l'achat
	- RI3 : Le spectateur doit avoir - de 4 billets pour ce concert
	- RI5 : Le nombre de billet vendu + 1 doit être inférieur à la capacité de ka salle
	- RI6 : Le spectateur doit avoir - de 8 billets au total
	- RI8 : Le concert doit être "en vente"

2. Reprogrammation d'un concert à un autre jour et/ou heure : 
	- RI1 : Le concert doit finir avant 23h
	- RI4 : Le concert ne doit pas être d'un groupe qui a déjà fait 2 concerts le jour déplacé
