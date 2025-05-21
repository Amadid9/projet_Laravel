# expliquation d’installation et d’utilisation.

Ce document explique comment créer un projet Laravel simple avec :
- Authentification via Laravel Breeze
- Migration des tables users, skills et projects.
- Création des contrôleurs
- Création des vues basiques

## 1. Création du projet Laravel
 DANS LE CMD ECRIRE :
composer create-project laravel/laravel (le nom de projet que vous voullez )
cd dev (parexemple ) .
et vous ouvrant dans vs-code le projet ,voici sa structure :
![image](https://github.com/user-attachments/assets/1a962687-7d71-4f66-8745-33e1df38ca6d)

## 2. instalation du breeze :
DANS LE CMD APRES QQUE VOUS ACCEDER AUX PROJET ECRIRE :
composer require laravel/breeze --dev
php artisan breeze:install
npm install && npm run dev
php artisan migrate

REMARQUE : 
Pourquoi utiliser Node.js avec Breeze ?
Laravel Breeze installe une partie frontend moderne basée sur Tailwind CSS et 
souvent sur JavaScript (parfois avec Alpine.js ou React/Vue selon la version).
Pour compiler les fichiers CSS et JS, Laravel utilise Laravel Mix (basé sur Webpack) 
ou Vite (dans les versions plus récentes).
Ces outils de build (compilation) sont exécutés via Node.js car ils utilisent l’écosystème
JavaScript (npm, yarn) pour transformer, optimiser et bundler les fichiers CSS/JS.
Par exemple, Tailwind CSS a besoin d’être compilé pour générer le CSS final optimisé à partir de ses classes utilitaires.
apres cela , les fichiers breeze sont instaler (controllers +modele user ,et les vue profiles).

## 3. Création du base de donnees:
il faut d'abord cree une base de donner dans le phpmyadmin et ecrire le nom de la base de donnees
dans .env dans votre project laravel: 
DB_DATABASE=appcrud

## 4.migration :
pour cree les tables dans la base de donnees il faut cree des models et de migration on utilisant ce code la :
php artisan make:model (nom que vous vouler donnes au modele) -m,pour notre exemple c'est :
php artisan make:model User -m
php artisan make:model Project -m
php artisan make:model Skill -m

et laravel par defaut cree des models avec des migration ,les migrations contient les tables avec le nom de table en pluriel 
, il faut les remplir , et on a les remplit on usant le code source fornit par le prof. 
il faut ajouter ce code la : php artisan migrate , pour que les tables seront cree !! 


## 5.creation de controllers  :
apres cela on passe a cree les controlleur avec la requette suivante :
php artisan make:controller (nom de controlleur ) , et pour notre cas on ecrit ! :
controlleur  php artisan make:controller ProjectController --resource
php artisan make:controller SkillController --resource
php artisan make:controller PDFController
php artisan make:controller PublicProfileController
php artisan make:controller ProfileController 
on remplit c'est controlleur selon nos besoin ( recuperation de donnee , creation , modification , ou supression) 

## 6.creation de vues  :
et passant maintenant au views , concernant les fichier d'authentification , il sont tout cree avec des layout et coposents,
il faut just cree 2 docier , un de projet qui contient les fichier de creation et d'affichage , l'autre qui contient les skills
leur creation , et on ajout un fichier publicprofile pour qu'on affiche le profile avec ses projets et competences on
permettant de cree un cv ,cela neccessite l'installation du dompdf . 
