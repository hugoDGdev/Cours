## Partie 1 : Etats, évènements et transitions du modèle
### Etats :
- Vérification - L'œuvre a été envoyée par un client, un expert la vérifie
- Retirée - L'œuvre a été retirée de la vente et doit être restituée
- Rendue - L'œuvre a été rendue à son propriétaire
- En vente - L'œuvre peut être réservée
- Réservée - L'œuvre n'est plus en vente, la confirmation est attendue pour valider la vente
- Vendue - L'œuvre a été vendue et doit être expédiée au client

### Evènements : 
- Retrait - L'œuvre est retirée de la vente
- Mise en vente - L'œuvre est mise en vente
- Restitution - L'œuvre est restituée à son propriétaire
- Annulation réservation - La réservation est annulée
- Vente - L'œuvre est vendue
- Réservation - L'acheteur demande à réserver

### Transitions : 
- Vérification - > Retirée : Retrait
- Vérification -> En Vente : Mise en vente
- Retirée -> Rendue : Restitution
- Réservée -> En Vente : Annulation réservation
- En Vente -> Réservée : Réservation
- Réservée -> Vendue : Vente
- En Vente -> Retirée : Retrait
--------------------------
![[Pasted image 20251207233938.png]]

----------------------

## Partie 2 : Modélisation sous forme de diagramme 

Voici un diagramme complet du CVO détaillé précédemment : 
![[tp7.svg]]