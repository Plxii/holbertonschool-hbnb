# High-Level Package Diagram
Le diagramme de packages de haut niveau montre l'architecture en trois couches de l'application HBnB et la communication entre ces couches via le motif façade. Les trois couches principales sont : la couche de présentation, la couche logique métier, et la couche de persistance.

Diagramme de Packages
1. Presentation Layer (Couche de Présentation)
Cette couche gère l'interaction entre l'utilisateur et l'application. Elle comprend tous les services et les points de terminaison API exposés aux utilisateurs.

```mermaid
class PresentationLayer {
    <<Interface>>
    +ServiceAPI
    +registerUser()
    +createPlace()
    +submitReview()
    +fetchPlaces()
}
Attributs et Méthodes :

ServiceAPI : Interface fournissant les services pour les interactions utilisateur.

registerUser() : Méthode pour l'inscription des utilisateurs.

createPlace() : Méthode pour la création de lieux.

submitReview() : Méthode pour la soumission d'avis.

fetchPlaces() : Méthode pour récupérer la liste des lieux.

2. Business Logic Layer (Couche Logique Métier)
Cette couche contient la logique métier principale et les modèles représentant les entités dans le système (par exemple, Utilisateur, Lieu, Avis, Équipement).

```mermaid
class BusinessLogicLayer {
    +UserModel
    +PlaceModel
    +ReviewModel
    +AmenityModel
    +register()
    +createPlace()
    +addReview()
    +listPlaces()
}
Attributs et Méthodes :

UserModel : Modèle pour les utilisateurs.

Attributs :

id : Identifiant unique de l'utilisateur.

first_name : Prénom de l'utilisateur.

last_name : Nom de famille de l'utilisateur.

email : Adresse email de l'utilisateur.

password : Mot de passe de l'utilisateur.

is_admin : Booléen indiquant si l'utilisateur est un administrateur.

Méthodes :

register() : Méthode pour enregistrer un nouvel utilisateur.

updateProfile() : Méthode pour mettre à jour le profil de l'utilisateur.

PlaceModel : Modèle pour les lieux.

Attributs :

id : Identifiant unique du lieu.

title : Titre du lieu.

description : Description du lieu.

price : Prix du lieu.

latitude : Latitude du lieu.

longitude : Longitude du lieu.

Méthodes :

createPlace() : Méthode pour créer un nouveau lieu.

update() : Méthode pour mettre à jour un lieu.

ReviewModel : Modèle pour les avis.

Attributs :

id : Identifiant unique de l'avis.

user_id : Identifiant de l'utilisateur ayant écrit l'avis.

place_id : Identifiant du lieu concerné par l'avis.

rating : Note attribuée au lieu.

comment : Commentaire sur le lieu.

Méthodes :

addReview() : Méthode pour ajouter un avis.

update() : Méthode pour mettre à jour un avis.

AmenityModel : Modèle pour les équipements.

Attributs :

id : Identifiant unique de l'équipement.

name : Nom de l'équipement.

description : Description de l'équipement.

Méthodes :

create() : Méthode pour créer un nouvel équipement.

update() : Méthode pour mettre à jour un équipement.

3. Persistence Layer (Couche de Persistance)
Cette couche est responsable du stockage et de la récupération des données, interagissant directement avec la base de données.

```mermaid
class PersistenceLayer {
    +DatabaseAccess
    +saveUser()
    +savePlace()
    +saveReview()
    +getPlaces()
}
Attributs et Méthodes :

DatabaseAccess : Interface pour accéder à la base de données.

saveUser() : Méthode pour enregistrer un utilisateur dans la base de données.

savePlace() : Méthode pour enregistrer un lieu dans la base de données.

saveReview() : Méthode pour enregistrer un avis dans la base de données.

getPlaces() : Méthode pour récupérer des lieux depuis la base de données.

Communication entre les Couches via le Motif Façade
Motif Façade : Simplifie les interactions entre les couches en fournissant une interface unifiée. Par exemple :

La couche de présentation appelle des méthodes dans la couche logique métier via la façade (Facade Pattern).

La couche logique métier appelle des méthodes dans la couche de persistance pour interagir avec la base de données (Database Operations).

