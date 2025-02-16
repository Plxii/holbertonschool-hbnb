# HBnB - UML

## Description

Ce projet consiste à développer une application de type AirBnB, appelée HBnB Evolution
qui permet aux utilisateurs de gérer des propriétés, des avis, et des équipements. La documentation technique détaillée servira de fondation pour le développement de l'application.

## Contenu du projet

Dans cette phase initiale, l'accent est mis sur la création d'une documentation technique complète pour comprendre l'architecture globale, la conception détaillée de la logique métier, et les interactions au sein du système. L'application HBnB Evolution permettra aux utilisateurs de réaliser les opérations suivantes :
- Gestion des utilisateurs : Inscription, mise à jour du profil, identification comme utilisateur régulier ou administrateur.
- Gestion des lieux : Les utilisateurs peuvent lister leurs propriétés avec des détails tels que le nom, la description, le prix, et la localisation (latitude et longitude), ainsi qu'une liste d'équipements.
- Gestion des avis : Les utilisateurs peuvent laisser des avis sur les lieux qu'ils ont visités, incluant une note et un commentaire.
- Gestion des équipements : L'application gère les équipements qui peuvent être associés aux lieux.

## Règles et Exigences Métiers
Entité Utilisateur:
- Chaque utilisateur a un prénom, un nom, un email, et un mot de passe.
- Les utilisateurs peuvent être identifiés comme administrateurs via un attribut booléen.
- Les utilisateurs peuvent s'inscrire, mettre à jour leur profil, et être supprimés.

Entité Lieu:
- Chaque lieu a un titre, une description, un prix, une latitude, et une longitude.
- Les lieux sont associés à l'utilisateur qui les a créés.
- Les lieux peuvent avoir une liste d'équipements.
- Les lieux peuvent être créés, mis à jour, supprimés, et listés.

Entité Avis:
- Chaque avis est associé à un lieu spécifique et un utilisateur, et inclut une note et un commentaire.
- Les avis peuvent être créés, mis à jour, supprimés, et listés par lieu.

Entité Équipement:
- Chaque équipement a un nom et une description.
- Les équipements peuvent être créés, mis à jour, supprimés, et listés.

Identifiants et Audit:
- Chaque objet doit être identifié de manière unique par un ID.
- Les dates de création et de mise à jour doivent être enregistrées pour toutes les entités.

Architecture et Couches:
L'application suit une architecture en couches divisée en :
- Couche de Présentation : Services et API pour l'interaction utilisateur.
- Couche Logique Métier : Modèles et logique principale de l'application.
- Couche de persistance : Stockage et récupération des données depuis la base de données.
