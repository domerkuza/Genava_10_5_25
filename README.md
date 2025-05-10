# Genava_10_5_25
Hackathon Showcase Platform

Hackathon Showcase Platform est une application web sophistiquée conçue pour gérer, promouvoir et évaluer les projets innovants présentés lors de hackathons. Construite avec PHP, MySQL, et stylisée avec des techniques modernes de CSS, cette plateforme permet aux stagiaires et aux jurys de découvrir des projets, de voter en attribuant des scores pondérés et des commentaires, et de célébrer la créativité dans diverses catégories technologiques telles que le développement web, l’intelligence artificielle, ou l’Internet des objets (IoT). Elle s’adresse aux organisateurs de hackathons, aux participants, aux jurys, et aux spectateurs, offrant une interface utilisateur fluide, sécurisée et entièrement responsive.
L’objectif principal de la plateforme est de centraliser la gestion des projets, de garantir une évaluation équitable grâce à un système de vote pondéré, et de mettre en avant les idées les plus prometteuses. Avec une architecture modulaire et évolutive, elle est conçue pour s’adapter à des hackathons de toutes tailles, qu’ils soient locaux ou internationaux.
Table des matières

Fonctionnalités
Technologies utilisées
Captures d’écran
Prérequis
Installation
Schéma de la base de données
Utilisation
Publier le projet sur GitHub
Perspectives d’amélioration
Contribuer
Licence
Contact

Fonctionnalités
Fonctionnalités principales

Exploration des projets : Les utilisateurs peuvent parcourir une liste de projets validés, présentés sous forme de grille avec des informations clés :
Titre, catégorie (par exemple, IA & ML, Applications Mobiles, IoT), et description concise.
Membres de l’équipe (jusqu’à trois, avec noms, emails, et rôles spécifiques).
Liens vers une vidéo de démonstration (YouTube, Vimeo, etc.) et une documentation (PDF, Google Drive, etc.).


Système de vote pondéré :
Votes des stagiaires : Les stagiaires authentifiés peuvent attribuer un score de 0 à 20 et un commentaire à chaque projet. Le système empêche les votes multiples pour un même projet.
Votes des jurys : Les membres du jury soumettent des votes avec un poids supérieur, défini dans la table ponderation (par exemple, 60 % pour les jurys, 40 % pour les stagiaires).
Calcul automatique des scores moyens pondérés pour un classement équitable.


Détails des projets : Chaque projet dispose d’une page dédiée affichant :
Informations complètes sur l’équipe, incluant les rôles et emails des membres.
Description du projet et catégorie.
Liens vers la vidéo et la documentation.
Note moyenne pondérée et nombre total de votes (stagiaires + jurys).
Commentaires des votants pour fournir un retour constructif.


Recherche et filtrage :
Recherche par mots-clés dans le titre, la description, ou la catégorie.
Filtrage par catégorie pour une navigation ciblée et efficace.


Tableau de bord utilisateur : Affiche des statistiques personnalisées pour chaque utilisateur, incluant :
Nombre total de projets validés disponibles.
Nombre de votes soumis et votes restants.
Récapitulatif des projets votés, avec scores et commentaires.


Gestion multi-rôles :
Stagiaires : Accès limité à l’exploration des projets et au vote, nécessitant un compte validé.
Jurys : Interface dédiée pour voter avec un poids accru et consulter tous les projets.
Validation des projets et des comptes pour contrôler l’accès et la visibilité.



Fonctionnalités secondaires

Validation des utilisateurs et projets :
Les stagiaires doivent avoir un compte marqué comme valide dans la table stagiaire.
Seuls les projets marqués comme valide dans la table project sont visibles publiquement.


Notifications visuelles : Messages d’interface pour confirmer un vote, signaler un vote déjà soumis, ou indiquer une erreur (par exemple, projet non trouvé).
Design responsive : Interface optimisée pour tous les appareils (ordinateurs, tablettes, smartphones) grâce à une mise en page basée sur CSS Grid et Flexbox.
Sécurité renforcée :
Authentification sécurisée par email et mot de passe pour les stagiaires et jurys.
Protection contre les injections SQL grâce à l’utilisation de PDO avec des requêtes préparées.
Gestion sécurisée des sessions PHP pour maintenir la connexion des utilisateurs.


Personnalisation visuelle : Les projets sont présentés avec des vignettes dynamiques (si fournies) et des couleurs associées à chaque catégorie pour une exploration visuellement attrayante.

Technologies utilisées
Frontend

HTML5 : Structure sémantique pour une accessibilité et une compatibilité optimales.
CSS3 :
Utilisation de gradients dynamiques, animations, et transitions pour un design moderne.
CSS Grid et Flexbox pour une mise en page responsive et flexible.
Modals pour afficher les formulaires de vote et les messages d’erreur.


JavaScript (optionnel) :
Validation des formulaires côté client pour une meilleure expérience utilisateur.
Interactions dynamiques comme le filtrage en temps réel ou l’affichage des commentaires.


Icônes : Intégration possible de FontAwesome ou Material Icons pour enrichir l’interface (si utilisé dans votre projet).

Backend

PHP 7.4+ :
Gestion des requêtes HTTP pour afficher les projets et traiter les formulaires de vote.
Authentification des stagiaires et jurys via des sessions PHP sécurisées.
Calcul des scores pondérés en fonction des valeurs de la table ponderation.


PDO (PHP Data Objects) :
Requêtes sécurisées avec des déclarations préparées pour interagir avec la base de données.
Gestion des relations entre les tables pour garantir l’intégrité des données.



Base de données

MySQL 5.7+ : Base de données relationnelle nommée Geneva, optimisée pour des requêtes rapides.
Tables principales : stagiaire, project, ponderation, jury, voteJury, voteStagiaire.

Sécurité

Prévention des injections SQL : Utilisation de requêtes préparées avec PDO.
Hachage des mots de passe : Les mots de passe dans les tables stagiaire et jury devraient être hachés avec password_hash() pour une sécurité accrue.
Validation des entrées : Vérification des scores (0-20) et des commentaires (limite de 300 caractères).
Protection des fichiers sensibles : Le fichier connexion.php est exclu du contrôle de version via .gitignore.

Captures d’écran
Page d’accueil (home_sta.php)
Explorez une grille de projets validés, filtrez par catégorie, et consultez vos statistiques de vote.
Page des détails du projet (project_sta.php)
Découvrez les informations détaillées d’un projet, votez, et lisez les commentaires des autres votants.
Formulaire de vote
Attribuez un score (0-20) et laissez un commentaire constructif pour un projet.
(Note : Remplacez les liens par des captures d’écran réelles placées dans le dossier screenshots/. Si vous n’avez pas encore de captures, conservez ces placeholders.)
Prérequis
Pour exécuter la plateforme localement ou sur un serveur, vous aurez besoin des éléments suivants :

PHP : Version 7.4 ou supérieure.
MySQL : Version 5.7 ou supérieure.
Serveur web : Apache, Nginx, ou tout autre serveur compatible avec PHP.
Navigateur web : Chrome, Firefox, Safari, ou Edge (versions récentes).
Git : Pour cloner le dépôt et gérer le contrôle de version.
Composer (optionnel) : Pour gérer les dépendances PHP, si nécessaire.
Accès à un terminal : Pour exécuter les commandes d’installation et de configuration.

Installation
Étape 1 : Cloner le dépôt
Clonez le dépôt GitHub dans votre environnement local :
git clone https://github.com/your-username/hackathon-showcase.git
cd hackathon-showcase

Étape 2 : Configurer la base de données

Créez la base de données Geneva :
CREATE DATABASE Geneva;


Importez le script SQL suivant (enregistrez-le dans un fichier nommé database.sql) pour créer les tables nécessaires :
USE Geneva;

CREATE TABLE stagiaire (
    IdStagiaire INT PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255),
    prenom VARCHAR(255),
    institut VARCHAR(255),
    filier VARCHAR(255),
    anner VARCHAR(255),
    tele VARCHAR(255),
    email VARCHAR(255),
    mdp VARCHAR(255),
    valiadtion ENUM('invalide', 'valide') DEFAULT 'invalide'
);

CREATE TABLE project (
    IdProject INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(255),
    category VARCHAR(255),
    description_pr VARCHAR(255),
    membre1 VARCHAR(255),
    email_membre1 VARCHAR(255),
    role_membre1 VARCHAR(255),
    membre2 VARCHAR(255),
    email_membre2 VARCHAR(255),
    role_membre2 VARCHAR(255),
    membre3 VARCHAR(255),
    email_membre3 VARCHAR(255),
    role_membre3 VARCHAR(255),
    video_url VARCHAR(255),
    doc_url VARCHAR(255),
    validation_pr ENUM('invalide', 'valide') DEFAULT 'invalide'
);

CREATE TABLE ponderation (
    Id INT PRIMARY KEY AUTO_INCREMENT,
    P_jury INT,
    P_stagiaires INT
);

CREATE TABLE jury (
    Idjury INT PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255),
    prenom VARCHAR(255),
    email VARCHAR(255),
    mdp VARCHAR(255)
);

INSERT INTO jury (nom, prenom, email, mdp)
VALUES ('kalid', 'reda', 'kalid@example.com', '2080');

CREATE TABLE voteJury (
    id INT PRIMARY KEY AUTO_INCREMENT,
    Idjury INT,
    Idprojet INT,
    score INT,
    comments VARCHAR(300),
    pup VARCHAR(300),
    FOREIGN KEY (Idjury) REFERENCES jury(Idjury),
    FOREIGN KEY (Idprojet) REFERENCES project(IdProject)
);

CREATE TABLE voteStagiaire (
    id INT PRIMARY KEY AUTO_INCREMENT,
    IdStagiaire INT,
    Idprojet INT,
    score INT,
    comments VARCHAR(300),
    pup VARCHAR(300),
    FOREIGN KEY (IdStagiaire) REFERENCES stagiaire(IdStagiaire),
    FOREIGN KEY (Idprojet) REFERENCES project(IdProject)
);

Exécutez le script pour importer les tables :
mysql -u your_username -p Geneva < database.sql


Configurez les paramètres de connexion à la base de données dans un fichier connexion.php :
<?php
$host = 'localhost';
$dbname = 'Geneva';
$username = 'your_username';
$password = 'your_password';

try {
    $pdo = new PDO("mysql:host=$host;dbname=$dbname", $username, $password);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    echo "Connection failed: " . $e->getMessage();
}
?>



Étape 3 : Configurer le serveur web

Placez les fichiers du projet dans le répertoire racine de votre serveur web (par exemple, /var/www/html/hackathon-showcase pour Apache).
Assurez-vous que le serveur dispose des permissions nécessaires pour lire et écrire les fichiers de session PHP.
Si vous utilisez Apache, activez le module mod_rewrite pour prendre en charge des URL propres (facultatif).

Étape 4 : Lancer l’application

Accédez à la plateforme via votre navigateur :
http://localhost/hackathon-showcase/home_sta.php


Connectez-vous avec un compte stagiaire ou jury pour commencer à explorer les projets et voter.


Étape 5 : (Optionnel) Configurer un environnement de développement

Installez XAMPP, WAMP, ou MAMP pour un environnement local tout-en-un incluant PHP, MySQL, et Apache.
Utilisez un éditeur comme VS Code avec des extensions telles que PHP Intelephense pour faciliter le développement PHP.
Gérez la base de données avec un outil comme phpMyAdmin pour visualiser et modifier les tables.

Schéma de la base de données
La base de données Geneva est conçue pour être relationnelle, efficace, et adaptée à la gestion des projets et des votes dans un hackathon. Voici les détails des tables :
Table stagiaire
Stocke les informations des participants au hackathon.
CREATE TABLE stagiaire (
    IdStagiaire INT PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255),
    prenom VARCHAR(255),
    institut VARCHAR(255),
    filier VARCHAR(255),
    anner VARCHAR(255),
    tele VARCHAR(255),
    email VARCHAR(255),
    mdp VARCHAR(255),
    valiadtion ENUM('invalide', 'valide') DEFAULT 'invalide'
);


Note : Le champ valiadtion semble contenir une faute de frappe (devrait être validation).
Recommandation : Hacher les mots de passe dans le champ mdp avec password_hash().

Table project
Contient les détails des projets soumis.
CREATE TABLE project (
    IdProject INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(255),
    category VARCHAR(255),
    description_pr VARCHAR(255),
    membre1 VARCHAR(255),
    email_membre1 VARCHAR(255),
    role_membre1 VARCHAR(255),
    membre2 VARCHAR(255),
    email_membre2 VARCHAR(255),
    role_membre2 VARCHAR(255),
    membre3 VARCHAR(255),
    email_membre3 VARCHAR(255),
    role_membre3 VARCHAR(255),
    video_url VARCHAR(255),
    doc_url VARCHAR(255),
    validation_pr ENUM('invalide', 'valide') DEFAULT 'invalide'
);

Table ponderation
Définit le poids des votes des jurys et des stagiaires pour le calcul des scores.
CREATE TABLE ponderation (
    Id INT PRIMARY KEY AUTO_INCREMENT,
    P_jury INT,
    P_stagiaires INT
);


Exemple : Si P_jury = 60 et P_stagiaires = 40, les votes des jurys comptent pour 60 % du score final, et ceux des stagiaires pour 40 %.

Table jury
Stocke les informations des membres du jury.
CREATE TABLE jury (
    Idjury INT PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255),
    prenom VARCHAR(255),
    email VARCHAR(255),
    mdp VARCHAR(255)
);


Note : Comme pour stagiaire, hacher les mots de passe dans mdp.

Table voteJury
Enregistre les votes soumis par les jurys.
CREATE TABLE voteJury (
    id INT PRIMARY KEY AUTO_INCREMENT,
    Idjury INT,
    Idprojet INT,
    score INT,
    comments VARCHAR(300),
    pup VARCHAR(300),
    FOREIGN KEY (Idjury) REFERENCES jury(Idjury),
    FOREIGN KEY (Idprojet) REFERENCES project(IdProject)
);


Note : Le champ pup est ambigu (peut-être une date ou un horodatage ? Clarifiez son usage).

Table voteStagiaire
Enregistre les votes soumis par les stagiaires.
CREATE TABLE voteStagiaire (
    id INT PRIMARY KEY AUTO_INCREMENT,
    IdStagiaire INT,
    Idprojet INT,
    score INT,
    comments VARCHAR(300),
    pup VARCHAR(300),
    FOREIGN KEY (IdStagiaire) REFERENCES stagiaire(IdStagiaire),
    FOREIGN KEY (Idprojet) REFERENCES project(IdProject)
);

Relations entre les tables

Un projet (project) peut recevoir plusieurs votes de stagiaires (voteStagiaire) et de jurys (voteJury), liés par la clé IdProject.
Un stagiaire (stagiaire) peut voter pour plusieurs projets, lié par IdStagiaire.
Un jury (jury) peut voter pour plusieurs projets, lié par Idjury.
La table ponderation influence le calcul des scores finaux en définissant les poids des votes.

Utilisation
Page d’accueil (home_sta.php)

Vue d’ensemble : Affiche une grille de projets validés (validation_pr = 'valide') avec leurs titres, catégories, et descriptions courtes.
Filtres : Permet de rechercher par mots-clés ou de filtrer par catégorie (par exemple, IA, IoT).
Statistiques : Présente le nombre total de projets, les votes soumis, et les votes restants pour l’utilisateur connecté.
Actions : Cliquez sur un projet pour accéder à ses détails ou pour voter.

Page des détails du projet (project_sta.php)

Informations : Affiche les membres de l’équipe (noms, rôles, emails), la description du projet, les liens vers la vidéo et la documentation, ainsi que la note moyenne pondérée.
Vote : Si l’utilisateur (stagiaire ou jury) n’a pas encore voté, il peut soumettre un score (0-20) et un commentaire.
Commentaires : Consultez les retours des autres votants pour mieux comprendre le projet.
Navigation : Retournez à la page d’accueil ou explorez d’autres projets via la barre de navigation.

Interface pour les jurys

Une page dédiée (par exemple, home_jury.php) pourrait exister pour les jurys, offrant un accès à tous les projets (validés ou non) et un poids de vote supérieur défini dans ponderation.

Bonnes pratiques

Votes : Fournissez des commentaires constructifs pour encourager les équipes et favoriser l’amélioration des projets.
Validation : Assurez-vous que les comptes stagiaires et les projets sont marqués comme valide avant de permettre les votes.
Liens multimédias : Vérifiez que les URLs des vidéos et documents sont accessibles et fonctionnelles.

Publier le projet sur GitHub
Pour partager votre projet avec la communauté et le rendre accessible aux collaborateurs, suivez ces étapes pour publier le dépôt sur GitHub :
Étape 1 : Initialiser un dépôt Git local

Créez un dossier pour votre projet (par exemple, hackathon-showcase).
Placez les fichiers home_sta.php, project_sta.php, connexion.php, database.sql, ainsi que tout autre fichier nécessaire (CSS, images, scripts JavaScript) dans ce dossier.
Ouvrez un terminal dans ce dossier et exécutez :git init
git add .
git commit -m "Initial commit with Hackathon Showcase Platform"



Étape 2 : Créer un dépôt sur GitHub

Connectez-vous à votre compte GitHub.
Cliquez sur New Repository dans le coin supérieur droit.
Nommez le dépôt (par exemple, hackathon-showcase).
Ajoutez une description concise, comme : "A PHP-based platform for managing and voting on hackathon projects."
Choisissez si le dépôt doit être public (visible par tous) ou privé (accès restreint).
Ne cochez pas l’option "Initialize this repository with a README", car vous allez créer votre propre fichier README.
Cliquez sur Create Repository.

Étape 3 : Lier le dépôt local à GitHub

Associez votre dépôt local au dépôt GitHub nouvellement créé :git remote add origin https://github.com/your-username/hackathon-showcase.git


Poussez les fichiers vers GitHub :git push -u origin main



Étape 4 : Ajouter le fichier README.md

Créez un fichier README.md dans le dossier de votre projet.
Copiez-collez le contenu de ce document dans README.md.
(Optionnel) Ajoutez des captures d’écran pour illustrer l’interface :
Prenez des captures des pages home_sta.php et project_sta.php.
Placez-les dans un dossier screenshots/ dans votre projet.
Mettez à jour les liens dans le README (par exemple, screenshots/home_page.png).


Validez et poussez les modifications :git add README.md screenshots/
git commit -m "Add README and screenshots"
git push origin main



Étape 5 : Configurer le fichier .gitignore

Créez un fichier .gitignore pour exclure les fichiers sensibles ou inutiles du contrôle de version :# Fichiers sensibles
connexion.php
# Fichiers de session PHP
*.sess
# Fichiers de configuration serveur
.htaccess
# Fichiers générés par les IDE
.vscode/
.idea/
# Fichiers temporaires
*.log


Validez et poussez :git add .gitignore
git commit -m "Add .gitignore for sensitive files"
git push origin main



Étape 6 : Ajouter une licence

Créez un fichier LICENSE dans votre dépôt avec le texte de la licence MIT :MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


Validez et poussez :git add LICENSE
git commit -m "Add MIT License"
git push origin main



Étape 7 : Vérifier le dépôt sur GitHub

Visitez https://github.com/your-username/hackathon-showcase pour vérifier que tous les fichiers, le README, les captures d’écran, et la licence sont correctement affichés.
Assurez-vous que la description du dépôt et les sections du README (notamment les captures d’écran) sont bien formatées et visuellement attrayantes.

Étape 8 : (Optionnel) Créer des tags et des releases

Marquez une version stable de votre projet avec un tag Git :git tag v1.0.0
git push origin v1.0.0


Sur GitHub, allez dans l’onglet Releases, cliquez sur Create a new release, et associez le tag v1.0.0 avec une description des fonctionnalités incluses.

Perspectives d’amélioration
Pour enrichir la plateforme et répondre aux besoins futurs, voici quelques améliorations envisagées :

Mises à jour en temps réel :
Implémenter WebSocket ou AJAX pour afficher les nouveaux votes et commentaires sans recharger la page.


Tableau de bord administrateur :
Interface pour valider les projets (validation_pr) et les comptes stagiaires (validation).
Gestion des jurys et des paramètres de pondération.
Modération des commentaires pour maintenir un environnement respectueux.


Profils utilisateurs :
Page dédiée pour consulter l’historique des votes, modifier les informations personnelles, ou ajouter une photo de profil.
Options de personnalisation comme les notifications ou les thèmes visuels.


Filtres avancés :
Tri des projets par note moyenne, date de soumission, ou popularité (nombre de votes).
Filtres multiples combinant catégorie, mot-clé, et autres critères.


Notifications :
Envoi d’emails pour informer des nouveaux projets validés ou des résultats finaux.
Notifications in-app pour les votes reçus sur un projet.


Support multilingue :
Ajouter des langues comme le français, l’anglais, et l’espagnol pour une portée internationale.


Upload multimédia :
Permettre aux équipes de téléverser directement des vidéos ou documents sur la plateforme, stockés localement ou via un service cloud.


Classements dynamiques :
Afficher un classement des projets basé sur les scores pondérés, mis à jour en temps réel.


API REST :
Développer une API pour permettre à d’autres applications d’accéder aux données des projets et des votes.



Contribuer
Nous encourageons vivement les contributions de la communauté pour améliorer la plateforme. Voici comment vous pouvez participer :
Étape 1 : Forker le dépôt
Forkez le dépôt pour créer une copie sur votre compte GitHub :
git clone https://github.com/your-username/hackathon-showcase.git
cd hackathon-showcase

Étape 2 : Créer une branche
Créez une branche pour vos modifications :
git checkout -b feature/your-feature

Étape 3 : Effectuer vos modifications

Ajoutez de nouvelles fonctionnalités (par exemple, un tableau de bord administrateur).
Corrigez des bugs (par exemple, la faute de frappe dans valiadtion).
Améliorez la documentation ou l’interface utilisateur.

Étape 4 : Valider vos changements
Validez vos modifications avec un message clair :
git commit -m "Add your feature or fix"

Étape 5 : Pousser vers votre fork
Poussez votre branche vers votre dépôt GitHub :
git push origin feature/your-feature

Étape 6 : Ouvrir une Pull Request

Sur GitHub, créez une Pull Request depuis votre branche vers le dépôt principal.
Décrivez vos changements en détail et attendez les retours des mainteneurs.

Bonnes pratiques pour contribuer

Tests : Testez vos modifications localement pour vérifier le bon fonctionnement (requêtes SQL, affichage, soumission des votes).
Documentation : Mettez à jour le README ou ajoutez des commentaires dans le code pour expliquer vos changements.
Issues : Consultez les issues ouvertes sur GitHub pour identifier les tâches prioritaires ou proposez de nouvelles idées via une nouvelle issue.

Licence
Ce projet est distribué sous la licence MIT. Consultez le fichier LICENSE pour plus de détails.
Contact
Pour toute question, suggestion, ou collaboration, n’hésitez pas à nous contacter :

Nom : Votre Nom
E-mail : votre.email@example.com
GitHub : your-username
Discord : votre-discord-id (optionnel)

Merci d’utiliser Hackathon Showcase Platform ! Ensemble, faisons briller l’innovation et la créativité dans les hackathons.
