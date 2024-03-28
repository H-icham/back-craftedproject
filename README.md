Development of an API for e-commerce website designed to present and sell craft products.


Specifics :

PHP Framework Laravel(v.10)

Space dedicated to artists/craftspeople to present their profiles and creations

Artisans can manage their own accounts and update their creations

Advanced search functions, such as searching by material, category or style

Intuitive shopping cart with customisation options for products

Respect safety criteria

Minimise carbon impact


Initialisation :

Installing php composer
Project creation :

composer create-project laravel/laravel:^10.0 example-app
Create your database and configure the connection in the ".env" file
Starting the server :

php artisan serve

Debugbar / IDE helper :

Debugbar :

composer require barryvdh/laravel-debugbar --dev
IDE helper :

composer require --dev barryvdh/laravel-ide-helper

Migration Generations, Models, Factories & Seeders :

php artisan make:migration create_examples_table
php artisan make:model Example
php artisan make:factory ExampleFactory
php artisan make:seeder ExampleSeeder
Run migration :

php artisan migrate
Fresh if modifications :

php artisan migrate:fresh
Run seeders :

php artisan db:seed
Run migration & seeder :

php artisan migrate:fresh --seed
Option of generating seeders in the same class (DatabaseSeeder) or creating several classes (ExampleSeeder) which will be called in DatabaseSeeder


Controllers & CRUD :

Simple controller :

php artisan make:controller ExampleController
Controller with associated CRUD functions and model specification :

php artisan make:controller ExampleController --model=Example --resource
Resources :

Enable you to display only certain attributes and expressively transform our models and model collections into JSON

php artisan make:ressource ExampleResource 
php artisan make:resource Example --collection 

Auth & policies :

Laravel Sanctum :

composer require laravel/sanctum 
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
php artisan migrate 

Use "HasApiToken" in the User model Create the controller : (user creation/connection management)

php artisan make:controller Api\\AuthController
Protect the API with authentication using the auth:sanctum middleware :

Route::apiResource('posts', PostController::class)->middleware('auth:sanctum');

Generate Policies :

php artisan make:policy ExamplePolicy 
php artisan make:policy ExamplePolicy --model=Example  
Policy Methods > Controller Methods (called immediately before the controller methods are executed) :

viewAny > index
view > show
create > store (or create)
update > edit (or update)
delete > destroy

Documentation :

https://laravel.com/docs/10.x/readme
https://cours.brosseau.ovh/cheatsheets/laravel/quick.html
https://www.linkedin.com/pulse/laravel-api-authentication-using-sanctum-muhammad-babar-cfecc/
