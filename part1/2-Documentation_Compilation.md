# DOCUMENTATION COMPILATION

sequenceDiagram
    participant User
    participant API
    participant BusinessLogic
    participant Database

    User->>API: Envoi d'information (email, mot de passe)
    API->>BusinessLogic: Validation
    BusinessLogic->>Database: user exist?
    Database-->>BusinessLogic: resultat de verification
    BusinessLogic->>Database: crée un nouveau utilisateur
    Database-->>BusinessLogic: confirmation
    BusinessLogic-->>API: succes
    API-->>User: Réponse avec succès ou échec

sequenceDiagram
    participant User
    participant API
    participant BusinessLogic
    participant Database

    User->>API: détails du lieu (nom, adresse, capacité)
    API->>BusinessLogic: validation des informations du lieu
    BusinessLogic->>Database: verification des données du lieu
    Database-->>BusinessLogic: resultat de vérification
    BusinessLogic->>Database: ajout le lieu dans la base de données
    Database-->>BusinessLogic: confirmation de l'ajout du lieu
    BusinessLogic-->>API: retour de l'ID du nouveau lieu
    API-->>User: Réponse avec ID du lieu créé

sequenceDiagram
    participant User
    participant API
    participant BusinessLogic
    participant Database

    User->>API: envoi de l'avis (note, commentaire, lieu_id)
    API->>BusinessLogic: validation et traite de l'avis
    BusinessLogic->>Database: verification si l'utilisateur a réservé ce lieu
    Database-->>BusinessLogic: resultat de vérification
    BusinessLogic->>Database: ajout de l'avis dans la base de données
    Database-->>BusinessLogic: confirmation de l'ajout de l'avis
    BusinessLogic-->>API: retour un message de succès
    API-->>User: Réponse avec succès ou échec de l'ajout de l'avis

sequenceDiagram
    participant User
    participant API
    participant BusinessLogic
    participant Database

    User->>API: demande des lieux (critères : emplacement, capacité)
    API->>BusinessLogic: validation de la demande de recherche
    BusinessLogic->>Database: requête pour obtenir les lieux correspondant aux critères
    Database-->>BusinessLogic: liste des lieux
    BusinessLogic-->>API: retour de la liste des lieux
    API-->>User: réponse avec la liste des lieux
