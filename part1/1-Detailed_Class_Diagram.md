# Detailed Class Diagram for Business Logic Layer

classDiagram

class User {
    +id: IdentifiantUnique
    +nom: String
    +email: String
    +date_creation: DateTime
    +date_mise_a_jour: DateTime
    +creerLieu(): void
    +ajouterAvis(avis: Review): void
    +reserverLieu(lieu: Place): void
    +modifierProfil(): void
}

class Place {
    +id: IdentifiantUnique
    +nom: String
    +adresse: String
    +capacite: int
    +date_creation: DateTime
    +date_mise_a_jour: DateTime
    +ajouterAmenite(amenite: Amenity): void
    +supprimerAmenite(amenite: Amenity): void
    +ajouterAvis(avis: Review): void
    +mettreAJourLieu(): void
}

class Review {
    +id: IdentifiantUnique
    +note: int
    +comment: String
    +userid: UUID4
    +lieu_id: UUID4
    +date_creation: DateTime
    +modifierAvis(): void
    +supprimerAvis(): void
}

class Amenity {
    +id: IdentifiantUnique
    +nom: String
    +description: String
    +lieu_id: UUID4
    +serviceassocie(): void
    +desassocierAmenite(): void
}

User --> Place : "Créer"
Place o-- Amenity : "Possède"
Place --> Review : "A"
Review --> User : "Écrit par"
Review --> Place : "Concernant"
