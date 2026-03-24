<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>API Blog - Documentation</title>
</head>
<body>
<h1>Projet : API Blog Node.js / MySQL</h1>

<h2>1. Présentation du projet</h2>
<p>L’API Blog est une application backend développée avec <strong>Node.js</strong>, <strong>Express</strong>, et <strong>MySQL</strong>, permettant la gestion d’un blog. Elle inclut :</p>
<ul>
<li>Gestion des utilisateurs (inscription, connexion)</li>
<li>Authentification avec <strong>JWT</strong></li>
<li>Gestion des articles (CRUD)</li>
<li>Pagination et filtrage par catégorie et date</li>
<li>Documentation avec <strong>Swagger</strong></li>
<li>Test via <strong>Postman</strong></li>
</ul>

<h2>2. Technologies utilisées</h2>
<ul>
<li>Node.js v24+</li>
<li>Express v5+</li>
<li>MySQL / mysql2</li>
<li>JWT pour sécuriser les routes</li>
<li>bcryptjs pour le hash des mots de passe</li>
<li>Swagger pour la documentation</li>
<li>Nodemon pour le développement</li>
</ul>

<h2>3. Installation et configuration sur VS Code</h2>
<h3>a) Cloner le projet</h3>
<pre><code>git clone &lt;lien-du-repo&gt;
cd blog_api
</code></pre>

<h3>b) Installer les dépendances</h3>
<pre><code>npm install</code></pre>

<h3>c) Créer le fichier .env</h3>
<pre><code>PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=ton_motdepasse
DB_NAME=blog
JWT_SECRET=ma_cle_secrete</code></pre>

<h3>d) Créer la base MySQL et les tables</h3>
<pre><code>CREATE DATABASE IF NOT EXISTS blog;
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
);</code></pre>

<h2>4. Lancement du serveur</h2>
<pre><code>npm run dev</code></pre>
<p>- Serveur : http://localhost:3000</p>
<p>- Swagger : http://localhost:3000/api-docs</p>

<h2>5. Architecture du projet</h2>
<pre><code>blog_api/
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
└─ swagger.js           # Swagger configuration</code></pre>

<h2>6. Description des routes</h2>
<h3>a) Authentification</h3>
<table border="1">
<tr><th>Route</th><th>Méthode</th><th>Description</th><th>Body JSON</th></tr>
<tr><td>/auth/signup</td><td>POST</td><td>Créer un utilisateur</td><td>{ "username": "nom", "password": "motdepasse" }</td></tr>
<tr><td>/auth/login</td><td>POST</td><td>Connexion et récupération JWT</td><td>{ "username": "nom", "password": "motdepasse" }</td></tr>
</table>

<p>Exemple de réponse Login :</p>
<pre><code>{
  "message": "Connecté !",
  "token": "&lt;JWT&gt;"
}</code></pre>

<h3>b) Articles</h3>
<table border="1">
<tr><th>Route</th><th>Méthode</th><th>Description</th><th>Sécurité</th></tr>
<tr><td>/articles</td><td>GET</td><td>Liste des articles avec pagination et filtres</td><td>Non</td></tr>
<tr><td>/articles</td><td>POST</td><td>Créer un article</td><td>JWT</td></tr>
</table>

<h4>Paramètres GET /articles :</h4>
<table border="1">
<tr><th>Paramètre</th><th>Type</th><th>Description</th></tr>
<tr><td>page</td><td>int</td><td>Numéro de page (pagination)</td></tr>
<tr><td>limit</td><td>int</td><td>Nombre d’articles par page</td></tr>
<tr><td>category</td><td>string</td><td>Filtrage par catégorie</td></tr>
<tr><td>date</td><td>date</td><td>Filtrage par date (YYYY-MM-DD)</td></tr>
</table>

<h4>Exemple POST Article (JWT requis)</h4>
<pre><code>{
  "title": "Mon article",
  "content": "Contenu de l'article",
  "category": "Tech"
}</code></pre>

<h3>c) Swagger et Postman</h3>
<ul>
<li>Swagger : http://localhost:3000/api-docs</li>
<li>Permet de tester toutes les routes directement</li>
<li>Postman : importer les routes pour tester JWT, filtres, pagination</li>
</ul>

<h3>d) Authentification JWT</h3>
<p>Les routes POST /articles sont protégées par JWT.</p>
<p>Ajouter dans le header Authorization :</p>
<pre><code>Bearer &lt;ton_token&gt;</code></pre>

<h3>e) Pagination et filtrage</h3>
<p>Exemple GET /articles :</p>
<pre><code>GET /articles?page=1&limit=5&category=Tech&date=2026-03-23</code></pre>
<p>Retourne maximum 5 articles de la catégorie Tech créés le 23 mars 2026</p>

<h2>7. Conclusion</h2>
<p>API Blog complète avec sécurité, Swagger, pagination et filtres. Fonctionne avec VS Code, MySQL, Node.js et Postman. Prête à être intégrée dans un rapport ou présentée.</p>

</body>
</html>

