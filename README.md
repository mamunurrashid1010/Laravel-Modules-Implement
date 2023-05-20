# Laravel-Modules-Implement
In this project, i implement laravel modules and also show that step by step how to implement modularized app.

nwidart/laravel-modules is a Laravel package which was created to manage your large Laravel app using modules. A module is like a Laravel package, it has some views, controllers or models

## Implementation Process
##### 1. Create new laravel project via composer
```
composer create-project laravel/laravel Laravel-Modules-Implement
```

Go to project directory ```cd Laravel-Modules-Implement``` or open project with IDE.

##### 2. Create a new database
Here I'm using my MySQL PHPMyAdmin to create a database.<br>
Open ``` .env ``` file and add your database credentials.
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=testdb
DB_USERNAME=root
DB_PASSWORD=
```
Run migration artisan command
```
php artisan migrate
```

##### 3. Install laravel module package "nwidart/laravel-modules"
```
composer require nwidart/laravel-modules
```
Publish the package's
```
php artisan vendor:publish --provider="Nwidart\Modules\LaravelModulesServiceProvider"
```
Autoload your modules using psr-4
```
{
  "autoload": {
    "psr-4": {
      "App\\": "app/",
      "Modules\\": "Modules/"
    }
  }
}
```
Then run 
```
composer dump-autoload
```

##### 4. Artisan command
Create module
```
php artisan module:make <module-name>
```
Migrate module
```
php artisan module:migrate <module-name>
```
Seed module
```
php artisan module:seed <module-name>
```
Create controller
```
php artisan module:make-controller DemoController <module-name>
```
Create model
```
php artisan module:make-model Post <module-name>
```
Create migration file
```
php artisan module:make-migration create_posts_table <module-name>
```
For more information, follow "nwidart/laravel-modules" documentation.

