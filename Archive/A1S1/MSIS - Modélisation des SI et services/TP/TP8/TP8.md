## I) Lecture d'un modèle des cas d'utilisation
1. Oui, il est possible de créer un compte sans déposer une oeuvre d'art car bien que *créer un compte* soit un cas d'extension de *déposer offre*,  il y a aussi une ligne entre Vendeur et *créer un compte*
2. En revanche, il n'est pas possible de déposer une offre de vente sans créer de compte : dans ce cas, le cas d'extension *créer un compte* est déclenché car la condition est remplie, et le client aura donc finalement créé un compte.
3. La photo de l'oeuvre est obligatoire car *déposer une photo* est un cas d'inclusion de *déposer une offre* et un cas d'inclusion est obligatoire.
4. Un.e expert.e d'art ne peut pas vendre ses oeuvres car il.elle n'est pas associé.e aux cas correspondant. Il faudrait alors créer un compte de type client.
5. Non, *demander une expertise de l'oeuvre* est un cas d'extension de *valider une offre*, c'est donc un cas spécifique et facultatif dépendant du contexte.
6. Non, selon le modèle, seul un vendeur peut *retirer une offre*. Cela signifie à priori que les oeuvres non certifiées peuvent être vendues mais que l'expert peut les classer comme non authentiques.
7. Non, le responsable des ventes n'a aucun lien avec le cas *déposer une offre*, il est donc seulement possible pour un utilisateur de le faire.
8. Non, de la même manière, seul l'utilisateur a accès à ces fonctionnalités.
9. Oui, le responsable peut *consulter les offres de vente*, il peut donc voir quel client a déposé quelle offre
10. Oui, le client peut *consulter l'état de ses offres*. Par contre, il ne peut pas savoir si l'offre de quelqu'un d'autre a été validée.

## II) Modélisation des cas d'utilisation
![[Pasted image 20251222234732.png]]
```
@startuml
left to right direction
actor "Client Acheteur" as ca
actor "Responsable" as re
rectangle "Vue client" {
    usecase "Consulter le catalogue" as UC1
    usecase "Acheter une oeuvre" as UC2
    note "Condition : L'utilisateur n'a pas de compte" as N1
    usecase "Créer un compte client" as UC3
    usecase "Télécharger la brochure complète" as UC4
    usecase "Télécharger la fiche produit" as UC5
    usecase "Faire une demande d'achat" as UC6
    usecase "Analyser une demande d'achat" as UC7
    usecase "Valider une demande d'achat" as UC8
    usecase "Etablir une facture" as UC9
    usecase "Payer la facture" as UC10
    note "Demande d'achat validée" as N2
    usecase "Envoyer un rappel" as UC11
    usecase "Annuler la demande" as UC12
    usecase "Payer la pénalité" as UC13
    note "Condition : Facture déjà envoyée" as N3
}
ca -- UC1
ca -- UC2
ca -- UC3
UC2 <|.. N1 : <<extend>>
N1 .. UC3
UC1 -- UC4
UC1 -- UC5
UC2 ..> UC6 : <<include>>
re -- UC7
UC8 ..> UC9 : <<include>>
UC7 <|.. UC8 : <<extend>>
UC6 <|.. N2 : <<extend>>
N2 .. UC10
re -- UC11
ca -- UC12
UC12 <|.. N3 : <<extend>>
N3 .. UC13
@enduml
```
![[Pasted image 20251222234827.png]]