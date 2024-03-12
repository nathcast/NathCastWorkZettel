202310181204
Status: #workflow
links: [[laravel]] , [[API]], [[fullstack]] 
tags: #laravel #API #fullstack
previous: [[eRAbones]]
next: [[documenting the API]]



# Create API using LARAVEL

Next: how to write [[documentation]] using [[Scribe]] for [[laravel]]
Also using [[theme]]? 
### on 2023-10-31: 
- create folder D:\\\\laravel2023\\eRAbones-2023-10-31-01
- cloned what I did from GIT - but I am not happy with that. 

###  2023-11-01

- redo what was working from [[eRAbones]] 
- [x] create the project

```bash
composer create-project laravel/laravel eRAbones-2023-11-01-01
```
- [x] change directory
- [x] require socialstream
```bash
composer require joelbutcher/socialstream
```
- [x] require filament
```bash
composer require filament/filament:"^3.0-stable" -W
```
- [x] require jetstream
```bash
composer require laravel/jetstream
```
- [x] require livewire
```bash
composer require livewire/livewire
```
- [x] install filament
```bash
php artisan filament:install --panels
```
```bash
 What is the ID? [admin]
❯ admin

   INFO  Filament panel [D:\laravel2023\eRAbones-2023-10-27-01\app\Providers/Filament/AdminPanelProvider.php] created successfully.

   WARN  We've attempted to register the AdminPanelProvider in your [config/app.php] file as a service provider. If you get an error while trying to access your panel then this process has probably failed. You can manually register the service provider by adding it to the [providers] array.
```

- [x] install jetstream
```bash
php artisan jetstream:install livewire
```
- [x] install socialsteam filament, then jetsream
```bash
php artisan socialstream:install filament
```
```bash
php artisan socialstream:install jetstream livewire
```
```bash
code .
```

Next: in Code: 
 - [x] update .env
 - [x] update config/database.php
 - [x] update config/socialstream.php
 
When using filament, the features are not handled by socialstream, but by filament!?
 ```php
/**
* @filename socialstream.php
* 
* */

return [

    'middleware' => ['web'],

    'prompt' => 'Or Login Via',

    'providers' => [

        Providers::github(),

        Providers::google(),

    ],

```
 - [x] update config/services


```php 
/*
| @filename config/services.php
*/

'github' => [

        'client_id' => env('GITHUB_CLIENT_ID'),

        'client_secret' => env('GITHUB_CLIENT_SECRET'),

        'redirect' => env('GITHUB_REDIRECT_URI')

    ],

    'google' => [

        'client_id' => env('GOOGLE_CLIENT_ID'),

        'client_secret' => env('GOOGLE_CLIENT_SECRET'),

        'redirect' => env('GOOGLE_REDIRECT_URI')

    ],
```

In previous project: - actually, I am going to delete all the user tables in the database before I run these migrations - ```



In this project: 
```bash
php artisan migrate

```
```bash 
 INFO  Running migrations.  

  2014_10_12_000000_create_users_table .................................................................................... 84ms DONE
  2014_10_12_100000_create_password_reset_tokens_table .................................................................... 19ms DONE
  2014_10_12_200000_add_two_factor_columns_to_users_table .................................................................. 4ms DONE
  2019_08_19_000000_create_failed_jobs_table .............................................................................. 84ms DONE
  2019_12_14_000001_create_personal_access_tokens_table .................................................................... 9ms DONE
  2020_12_22_000000_create_connected_accounts_table ........................................................................ 9ms DONE  
  2022_12_21_000000_make_password_nullable_on_users_table ................................................................ 260ms DONE
  2023_11_01_151548_create_sessions_table ................................................................................. 29ms DONE
  
```
and in two separate shells: 
```bash
php artisan serve
npm run dev

```

in GITHUB and google @ revoke all the tokens 
Got to  https://github.com/settings/apps  to revoke settings
and 


If using photos, first register a user with a normal form and add a photo, then try the GIT and google. 

## adding support for API
https://www.iankumu.com/blog/laravel-rest-api/
We are using the tutorial below, but also using BKoats as a model. so a lot is already done. We are picking up at 

```PHP
php artisan make:controller BkoatsController -r
```
The -r flag will generate a Controller that is resourceful. This means it will create a controller with all the required methods for a Restful API. 
The main methods we will use are **index**, **show**, **store**, **update** and **destroy**. We **can delete** the **create** and **edit** methods as we will not need them. We can update the Bkoats Controller as shown below

We are doing the index (view all) and show (view one) 
then 
### Routes and endpoints

Let’s now create the endpoints that will be accessible over HTTP. We can add the routes in the **routes/api.php** file


Let’s now **install Laravel sanctum** and set it up

I am struggling from there: I get a file not found - 


## 2023-11-02 : 

Following tutorial as per : 
model Products 
migration ass table products
```php
php artisan make:factory ProductsFactory

```
update the database\seeders\DatabaseSeeder.php

```php
php artisan db:seed
```
```php
php artisan make:controller ProductsController -r
```
this creates a resourceful controler

Now we edit the routes. 

```php
/*routes/api.php*/

Route::get('products', [ProductsController::class, 'index'])->name('products.index');

Route::get('products/{product}', [ProductsController::class, 'show'])->name('products.show');

Route::get('bkoat', [BkoatsController::class, 'index'])->name('bkoat.index');

Route::get('bkoat/{bkoat}', [BkoatsController::class, 'show'])->name('bkoat.show');

Route::post('products', [ProductsController::class, 'store'])->name('products.store');

Route::put('products/{product}', [ProductsController::class, 'update'])->name('products.update');

Route::delete('products/{product}', [ProductsController::class, 'destroy'])->name('products.destroy');
```
To test : 
```php
php artisan serve
```
use postman and at this point, the URL to the API is 
http://127.0.0.1:8000/api/bkoat 
and 
http://127.0.0.1:8000/api/products

the routes are not yet protected by middleware

###  **What if you want to format this response**? 
One thing you **might not** want to expose is the **created_at** and **updated_at** data. You might also want to **calculate and return** a predefined **discount** back as a response.

Laravel allows us to customize our responses using [API resources](https://laravel.com/docs/10.x/eloquent-resources).

It is important to have the correct [[API response codes]]

### Setting up Authentication with [Laravel Sanctum](https://iankumu.com/blog/laravel-sanctum)

To learn more about the two authentication packages, you can read the [Laravel Sanctum](https://iankumu.com/blog/laravel-sanctum) article or the [Laravel Passport](https://iankumu.com/blog/laravel-passport) article.


However, with the set up we have: we make a token in the app, :) 

How to authenticate@ 
Login, REGISTER IN THE APP, the app, 
![[Pasted image 20231102172946.png]]

Click on API tokens and create a token. Copy in Clipboard 
In Postman: create a collection and place the token at the root of the collection - (Bearer token) and save. Build all your routes in Postman using inherit from parent. 
There is a route for loging out. 

In the next article, I will cover [how to generate/create documentation for this REST API](https://www.iankumu.com/blog/laravel-rest-api-documentation/).


For good measure, I have added a second model - Experiment



----------------------

## References
https://www.iankumu.com/blog/laravel-rest-api/
https://themeforest.net/