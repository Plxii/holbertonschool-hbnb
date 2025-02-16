
---

### Tâche 2 : Sequence Diagrams for API Calls
**Nom du fichier** : `2-Sequence_Diagrams_API_Calls.md`

**Objectif**
Développer des diagrammes de séquence pour au moins quatre appels API différents pour montrer l'interaction entre les couches et le flux d'information.

**Description**
1. **Diagrammes de Séquence** : Crée des diagrammes de séquence UML pour les appels API suivants : inscription utilisateur, création de lieu, soumission d'avis, et récupération de la liste des lieux.
2. **Notes Explicatives** : Décris le flux d'information et les interactions pour chaque appel API.

**Exemple de Contenu du Fichier**

```markdown
# Sequence Diagrams for API Calls

## Diagramme de Séquence : Inscription Utilisateur
```mermaid
sequenceDiagram
User ->> ServiceAPI: registerUser()
ServiceAPI ->> UserModel: create()
UserModel ->> DatabaseAccess: saveUser()
DatabaseAccess -->> UserModel: User saved
UserModel -->> ServiceAPI: User created
ServiceAPI -->> User: Registration success