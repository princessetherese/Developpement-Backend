# Developpement-Backend
Projet : API Blog Node.js / MySQL
1. Présentation du projet

L’API Blog est une application backend développée avec Node.js, Express, et MySQL, permettant la gestion d’un blog. Elle inclut :

Gestion des utilisateurs (inscription, connexion)
Authentification avec JWT
Gestion des articles (CRUD)
Pagination et filtrage par catégorie et date
Documentation avec Swagger
Test via Postman

2. Technologies utilisées
   
Node.js v24+
Express v5+
MySQL / mysql2
JWT pour sécuriser les routes
bcryptjs pour le hash des mots de passe
Swagger pour la documentation
Nodemon pour le développement

3. Installation et configuration sur VS Code
 
a) Cloner le projet
git clone <lien-du-repo>
cd blog_api
b) Installer les dépendances
npm install
c) Créer le fichier .env
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=ton_motdepasse
DB_NAME=blog
JWT_SECRET=ma_cle_secrete
d) Créer la base MySQL et les tables
CREATE DATABASE IF NOT EXISTS blog;
USE blog;

CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(50) NOT NULL UNIQUE,
  password VARCHAR(255) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE articles (
  id INT AUTO_INCREMENT PRIMARY KEY,
  title VARCHAR(255) NOT NULL,
  content TEXT NOT NULL,
  category VARCHAR(100) DEFAULT 'general',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
4. Lancement du serveur

Dans VS Code, ouvrir un terminal intégré et exécuter :

npm run dev
Serveur : http://localhost:3000
Swagger : http://localhost:3000/api-docs

5. Architecture du projet
blog_api/
│
├─ app.js               # Serveur principal
├─ package.json
├─ .env                 # Variables d'environnement
├─ routes/              # Routes
│   ├─ auth.js          # Signup / Login
│   └─ articles.js      # CRUD articles
├─ controllers/         # Logique métier
├─ middleware/
│   └─ auth.js          # Middleware JWT
├─ models/
│   └─ db.js            # Connexion MySQL
└─ swagger.js           # Swagger configuration

6. Description des routes
a) Authentification
Route	Méthode	Description	Body JSON
/auth/signup	POST	Créer un utilisateur	{ "username": "nom", "password": "motdepasse" }
/auth/login	POST	Connexion et récupération JWT	{ "username": "nom", "password": "motdepasse" }

Exemple de réponse Login :

{
  "message": "Connecté !",
  "token": "<JWT>"
}
b) Articles
Route	Méthode	Description	Sécurité
/articles	GET	Liste des articles avec pagination et filtres	Non
/articles	POST	Créer un article	JWT
Paramètres GET /articles :. Description des routes
Paramètre	Type	Description
page	int	Numéro de page (pagination)
limit	int	Nombre d’articles par page
category	string	Filtrage par catégorie
date	date	Filtrage par date (YYYY-MM-DD)
c) Exemple POST Article (JWT requis)
{
  "title": "Mon article",
  "content": "Contenu de l'article",
  "category": "Tech"
}
d) Swagger et Postman
Swagger : http://localhost:3000/api-docs
Permet de tester toutes les routes directement
Postman : importer les routes pour tester JWT, filtres, pagination
e) Authentification JWT
Les routes POST /articles sont protégées par JWT
Ajouter dans le header Authorization :
Bearer <ton_token>
f) Pagination et filtrage

Exemple GET /articles :

GET /articles?page=1&limit=5&category=Tech&date=2026-03-23
Retourne maximum 5 articles de la catégorie Tech créés le 23 mars 2026
7. Conclusion
API Blog complète avec sécurité, Swagger, pagination et filtres
Fonctionne avec VS Code, MySQL, Node.js et Postman
Prête à être intégrée dans un rapport ou présentée
