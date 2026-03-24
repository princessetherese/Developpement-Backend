<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>API Blog - Documentation</title>
</head>
<body>
<h1>Projet : API Blog Node.js / MySQL</h1>
   INF222 – EC1(Développement Backend)

                                           TAF1 : Utilisation de CleeRoute

Nom : Akamba voundi
Prénom : Thérèse armelle
Filière : Informatique
Matricule : 23V2471



                                                     Introduction 

Dans le cadre de l’unité d’enseignement INF222, ce travail pratique a pour objectif de structurer  notre apprentissage en développement web à l’aide de la plateforme CleeRoute. Il vise également à développer notre esprit critique et à produire une première application backend sous forme d’API pour la gestion d’un blog. Ce rapport représente les différentes étapes suivies sur la plateforme , l’implémentation d’une API backend, ainsi qu’une analyse critique de l’outil utilisé.

               Partie 1 : Utilisation de la plateforme CleeRoute


         Etape 1 : Création du compte    

j’ai commencé par créer un compte sur la plateforme en utilisant mon adresse email. Après inscription,j’ai validé mon compte via le lien envoyé par email.
      page d’accueil de CleeRoute et validation de mon email
Critique :Le processus est très simple et rapide, ce qui facilite l’accès pour les nouveaux utilisateurs.
Etape 2 ,3: Définir le niveau , l’objectif et le paramétrage du profil

j’ai choisi un niveau Débutant avec un objectif avec comme objectif principal l’apprentissage du développement backend et des API. J’ai ensuite configuré mon profil en précisant mes centres d’intérêt et mes objectifs d’apprentissages.


Critique :La plateforme propose des choix pertinents qui permettent  d’adapter le contenu au profil de l’utilisateur. De plus cette étape permet de personnaliser l’expérience de l’utilisateur.

Etape 4 : Génération du parcours

Après configuration , la plateforme a générée automatiquement un parcours d’apprentissage structuré.

 Critique :Le parcours est bien organisé et progressif.

Etape 5 : Suivi des modules
J’ai suivi plusieurs modules portant sur le développement backend, notamment les bases des API et 
de Node.js.
 Critique :Les modules sont clairs et progressifs.

comment créer un serveur
le cours sur Express



Etape 6:Prise de notes

J’ai utilisé l’outil de prise de notes intégré pour noter les concepts importants.
a) Node.js

Node.js est un environnement d'éxécution du code javascript à la partie Serveur . Cette communication est faite sur la partie Client


b) Serveur

URL est une addresse qui précise la localisation d'une ressources d'un réseau en indiquant les protocoles adoptés. Cet addresse est constitué par le protocole( communication entre Client et Serveur) , domaine( addresse de la machine) , port(porte d'entrée/sortie du serveur) et ressources( chemin d'addresse).

c) Express
Express.js est un from work de Node.js qui permet de créer des applications très rapidement et facilement avec les bases de code propre et facile à maintenir.

d) Middleware

Les fonctions middlewares sont des fonctions qui peuvent accéder à l'objet request (req) , l'objet response (res) et la fonction middleware suivant dans le cycle demande-réponse de l'application désignée par une variable nommée (next). les roles : exécuter tout type de code, apporter des modifications aux objets requêtes et /réponse , terminer le cycle requête-reponse, appeler la fonction middleware suivante.


 

e) Mysql

Mysql est un système de gestion de base des données relationnel open source qui fonctionne sous l'architecture client-serveur. Une base de données est un ensemble de données structurée. SGBDR est un logiciel ou service permettant de stocker les données , de les mettre à jour et d'y accéder , lesquelles données sont décomposées et organisées dans des tables. Les opérations d'algèbre relationnel (insertion, sélection produit cartésien , etc ...). Open source parce qu'on peut l'utiliser sans toute fois payer. Le langage utilisé pour établir la communication entre le Client et le serveur est SQL. Il peut avoir 5 sous langages : langage de définition de données , langage de manipulation de données , langage de contrôle des données , langage de contrôle des transactions ,langage de requête de données.
  
Critique :Cette fonctionnalité est utile pour retenir les notion clés.
 
Etape 7:Ajouter des sources + chat

J’ai ajouté des ressources et utilisé l’assistant pour poser des questions et approfondir ma compréhension.








Cours NodeJs pour débutants /Video 1
Comment fonctionne l'environnement NodeJs en arrière plan | Tuto FR
Malakisi
Transcriptions
00:00
Node.js : Comment ça marche ? Node.js est un environnement permettant au langage de programmation JavaScript, souvent décrit comme étant destiné à être pris en charge par le navigateur web, qui, grâce à Node.js, peut désormais être exécuté directement sur la machine grâce au moteur V8, ce qui fait du langage de programmation JavaScript un langage pouvant créer des applications web, des applications mobiles, des applications desktop, ou encore des applications serveur. Nous
00:32
allons consacrer cette vidéo à expliquer en détail comment Node.js fonctionne en arrière-plan, en partant de l'exemple d'une application serveur web, afin de voir en détail comment se comporte une application serveur Node.js. Une application est une suite d'instructions qui s'exécute pour accomplir une certaine tâche. Ces instructions s'exécutent dans ce qu'on appelle un Thread ou fil d'exécution. Lorsqu'un programme a, par exemple, trois instructions à exécuter, les instructions
Cours NodeJs pour débutants
ShareVersion LiteMettre à niveau
Contenu du cours
Quiz
Notes
Sources
Chat IA
AJOUTER UNE SOURCE
DOC
Manual_Entry_16_00.txt
Nouveau ChatTester mes connaissancesCréer un résuméPrendre des notes
Demander n'importe quoi

Lite
2/3
ajouter des sources
Concentrer la requête sur
Sous-section actuelle
Daily Chats: 1/3 used
Télécharger un fichier
Téléchargez un fichier PDF, DOCX ou TXT (Max 20 Mo) comme matériel de référence.
Cliquez pour télécharger
ou glissez et déposez ici
Télécharger
Texte copié
Collez ou saisissez du texte ci-dessous pour servir de matériel de référence pour votre cours
Critique :Le chat est utile mais peut être améliorer.


Etape 8 : Quiz

J’ai effectué un quiz proposés pour tester mes connaissances


Critique :Les quiz permettent une auto-évaluation efficace .











Partie 2 : Développement de l’API Backend

1. Choix technologique

pour ce projet , j’ai utilisé 
-Node.js avec Express pour le serveur
-Mysql pour la base de données
-Swagger pour la documentation

2. Description de l’API

L’API développée permet de gérer des articles de blog avec fonctionnalités suivantes :

a) Création d’un article
Endpoint : POST /api/articles
Permet d’ajouter un nouvel article avec : titre,contenu,auteur,date,catégorie et tags.

b) Lecture des articles
Endpoint : GET /api/articles
Permet de récupérer tous les articles ou les filtrer.

c) Lecture d’un article unique
Endpoint : GET /api/articles/{id}
Permet d’obtenir les détails d’un articles

d) modification d’un articles
Endpoint : PUT /api/articles/{id}
Permet de modifier les informations  d’un articles

e) Suppression d’un articles
Endpoint : DELETE /api/articles/{id}
Permet de supprimer un article

f) Recherche d’articles
Endpoint : GET /api/articles/search?query=texte
Permet de rechercher les articles 

3. Bonnes pratiques appliquées

-validation des données
-utilisation des codes HTTP
-organisation du code (routes ,modèles,contrôleurs)

4. Tests de l’API

L’API a été testée avec Postman et Swagger ,ce qui a permis de vérifier le bon fonctionnement des endpoints

5. Dépôt Github

Lien du projet : https://github.com/armelle/blog_api_inf222.git



Partie 3 : Analyse critique de CleeRoute

Points forts

-Apprentissage structuré
-Interface intuitive
-Personnalisation des parcours
-Présence d’un assistant intelligent

Points forts

-certaines explications restent superficielles
-Peu d’exercices pratiques avancés
-Dépendance à internet

Améliorations possibles

-Ajouter plus de projets concrets
-Améliorer la précision du chat
-Ajouter des vidéos explicatives

Utilité pour un étudiant
CleeRoute est une plateforme utile pour les étudiants en informatique car elle permet un apprentissage autonome et progressif du développement web et bien d’autre.


                                                       

        Conclusion

Ce travail pratique m’a permis de découvrir une nouvelle méthode d’apprentissage basée sur la personnalisation et la structuration . J’ai également acquis des compétences en développement backend en réalisant une API fonctionnelle. Ainsi, ce Tp constitue une base solide pour la suite de mon apprentissage en développement web.

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

