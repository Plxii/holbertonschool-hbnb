
---

### Tâche 1 : Detailed Class Diagram for Business Logic Layer
**Nom du fichier** : `1-Detailed_Class_Diagram.md`

**Objectif**
Concevoir un diagramme de classes détaillé pour la couche logique métier, en te concentrant sur les entités User, Place, Review, et Amenity, incluant leurs attributs, méthodes, et relations.

**Description**
1. **Diagramme de Classes** : Crée un diagramme de classes UML pour représenter les entités et leurs relations.
2. **Notes Explicatives** : Décris chaque classe, ses attributs, et ses méthodes.

**Exemple de Contenu du Fichier**

```markdown
# Detailed Class Diagram for Business Logic Layer

## Diagramme de Classes
```mermaid
classDiagram
class User {
    +int id
    +String first_name
    +String last_name
    +String email
    +String password
    +boolean is_admin
    +register()
    +updateProfile()
}
class Place {
    +int id
    +String title
    +String description
    +float price
    +float latitude
    +float longitude
    +create()
    +update()
}
class Review {
    +int id
    +int user_id
    +int place_id
    +int rating
    +String comment
    +submit()
    +update()
}
class Amenity {
    +int id
    +String name
    +String description
    +create()
    +update()
}
User --> Place : owns
Place --> Review : receives
Place --> Amenity : has
Review --> User : written by