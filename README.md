# Système de Gestion de Bibliothèque

Ce projet est un système de gestion de bibliothèque construit avec Node.js, Express, Sequelize et MySQL. Il fournit des fonctionnalités pour gérer les livres, les utilisateurs et les emprunts, y compris l'authentification des utilisateurs et les processus d'emprunt et de retour de livres.

## Fonctionnalités

- Inscription et authentification des utilisateurs (avec JWT)
- Opérations CRUD pour les livres, les utilisateurs et les emprunts
- Fonctionnalité d'emprunt et de retour de livres
- Middleware pour la protection des routes

## Points de terminaison de l'API

### Routes Utilisateur

- `POST /api/users/register`: Inscription d'un nouvel utilisateur
- `POST /api/users/login`: Connexion d'un utilisateur
- `GET /api/users`: Récupérer tous les utilisateurs
- `GET /api/users/:id`: Récupérer un utilisateur par ID
- `PUT /api/users/:id`: Mettre à jour un utilisateur par ID
- `DELETE /api/users/:id`: Supprimer un utilisateur par ID

### Routes Livre

- `GET /api/books`: Récupérer tous les livres
- `GET /api/books/:id`: Récupérer un livre par ID
- `POST /api/books`: Créer un nouveau livre
- `PUT /api/books/:id`: Mettre à jour un livre par ID
- `DELETE /api/books/:id`: Supprimer un livre par ID

### Routes Emprunt

- `POST /api/loans/borrow`: Emprunter un livre (nécessite une authentification)
- `POST /api/loans/return`: Retourner un livre emprunté (nécessite une authentification)
- `GET /api/loans/user/:id`: Récupérer tous les emprunts d'un utilisateur (nécessite une authentification)
- `GET /api/loans/borrowed`: Récupérer tous les livres empruntés par l'utilisateur actuel (nécessite une authentification)
- `GET /api/loans`: Récupérer tous les emprunts
- `GET /api/loans/:id`: Récupérer un emprunt par ID
- `POST /api/loans`: Créer un nouvel emprunt
- `PUT /api/loans/:id`: Mettre à jour un emprunt par ID
- `DELETE /api/loans/:id`: Supprimer un emprunt par ID

## Middleware d'Authentification

Le middleware d'authentification vérifie le token JWT dans l'en-tête de la requête pour protéger les routes sensibles. Si le token est valide, l'utilisateur est autorisé à accéder à la route, sinon une erreur d'authentification est retournée.

## Structure du Projet

- `src/config/db.js`: Configuration de la base de données Sequelize
- `src/controllers/`: Contrôleurs pour les différentes entités (livres, utilisateurs, emprunts)
- `src/models/`: Modèles Sequelize pour les entités
- `src/routes/`: Définition des routes de l'API
- `src/middlewares/`: Middleware d'authentification
- `app.js`: Point d'entrée principal de l'application

## Contribution

Les contributions sont les bienvenues! Veuillez créer une issue ou une pull request pour toute amélioration ou correction.

