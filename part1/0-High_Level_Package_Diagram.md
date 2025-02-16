# High-Level Package Diagram

## Diagramme de Packages
```mermaid
classDiagram
class PresentationLayer {
    <<Interface>>
    +ServiceAPI
    +registerUser()
    +createPlace()
    +submitReview()
    +fetchPlaces()
}
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
class PersistenceLayer {
    +DatabaseAccess
    +saveUser()
    +savePlace()
    +saveReview()
    +getPlaces()
}

PresentationLayer --> BusinessLogicLayer : Facade Pattern
BusinessLogicLayer --> PersistenceLayer : Database Operations