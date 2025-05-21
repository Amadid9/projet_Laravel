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
![image](https://github.com/user-attachments/assets/69c69c65-b715-47bf-998e-3695d2cda6de)
![image](https://github.com/user-attachments/assets/709af7c3-fb88-46c9-af86-e9e2feef5a63)

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
![image](https://github.com/user-attachments/assets/3e79c42a-48db-451f-b3fa-36442869aa6d)


## 4.migration :
pour cree les tables dans la base de donnees il faut cree des models et de migration on utilisant ce code la :
php artisan make:model (nom que vous vouler donnes au modele) -m,pour notre exemple c'est :
php artisan make:model User -m
php artisan make:model Project -m
php artisan make:model Skill -m

et laravel par defaut cree des models avec des migration ,les migrations contient les tables avec le nom de table en pluriel 
![image](https://github.com/user-attachments/assets/48c0c6ec-d0d2-45fe-a885-a85baa3e09fc)
![image](https://github.com/user-attachments/assets/34949ecf-198c-427b-8b3e-4b6976383b09)


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
![image](https://github.com/user-attachments/assets/c725722c-e714-4741-b045-058a4137ae94)
![image](https://github.com/user-attachments/assets/36bee9e3-9860-4d5f-98ed-34bf275eb022)

demo :
##page acceuil :
![image](https://github.com/user-attachments/assets/ec0c8516-b99b-48f4-aedc-5fcc90183094)
## page de registration :
![image](https://github.com/user-attachments/assets/390cf444-f91a-461e-8895-7163f63800ee)
##dashboard :
![image](https://github.com/user-attachments/assets/a0769304-d801-4326-8273-20698727d191)
##projet :
![image](https://github.com/user-attachments/assets/9279277b-d255-49d5-a1ac-58c40c003b7c)
##competences :
![image](https://github.com/user-attachments/assets/52561e4c-5df4-4914-aede-bf03cdec396d)
##profile public :
![image](https://github.com/user-attachments/assets/b3ae311a-943e-454a-b948-4c04580e9c38)
##exemple de cv :
![image](https://github.com/user-attachments/assets/101ab72c-0f12-49ad-9eda-0e90876eee1b)


