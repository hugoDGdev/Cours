## I) Identifiants : 
- Pour Groupe, la clé primaire est NoGroupe, et NomGroupe est une clé également.
- Pour Scène, la clé primaire est NomScène
- Pour Concert, il est possible d'utiliser DateConcert et HeureDébut comme clé

## II) Questions :
1. Non, un membre ne peut appartenir qu'à un groupe car l'attribut NoGroupe est à priori monovalué 
2. Oui car un MembreGroupe peut à priori être associé à plusieurs JoueInstrument
3. Oui car Instrument est seulement un attribut textuel donc il peut être utilisé dans un nombre indéfini d'objets
4. Oui car un Spectateur peut à priori être associé à plusieurs objets de Billet
5. Oui car comme mentionné précédement, un concert dépend d'une scène mais aussi d'une heure, donc pour plusieurs heures il est possible d'avoir plusieurs concerts dans la même journée à condition qu'ils ne se chevauchent pas.
6. Oui, de la même manière, un groupe peut jouer plusieurs concerts car il est possible de lier plusieurs objets de Concert au même NoGroupe
7. En théorie cela n'est pas possible car l'heure de début est censée être unique par rapport à une scène
8. Oui car il existe une association entre Concert et Groupe, entre Groupe et MembreGroupe, et entre MembreGroupe et JoueInstrument, donc les 2 sont liés
9. Non car chaque billet est lié à un spectateur mais un spectateur n'est pas nécessairement associé à un billet
10. De la même manière, oui car chaque membre est associé à un groupe mais chaque groupe n'est pas nécessairement associé à un ou des membres
11. Non, toujours pour la même raison : tout objet de JoueInstrument est associé à un MembreGroupe mais un MembreGroupe n'est pas nécessairement associé à un JoueInstrument
12. Non, du moins pas de manière pratique : cela voudrait soit dire changer le NoGroupe du Membre, et donc le retirer de son vrai groupe, soit créer un deuxième objet pour lequel seul le NoGroupe diffère, et donc créer un doublon.

## III) Diagramme :

![[Untitled Diagram.drawio.png]]
*petit bug de draw.io sur le NoGroupe de MembreGroupe, remarqué trop tard pour réexporter le fichier.. désolé pour ça.*
