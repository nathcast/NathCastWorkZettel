202310251133
Status: #idea #e-RAdata

Tags: [[eRAdata]], 
next: [[Create API using LARAVEL]]

# eRAbones

@due(2023-11-9)
eRAbones is the name I give to the bare bones proof of concept for eRAdata. In here I can make the list of things I need and the places I could help plan that. I need a place to have a list of things to have and what to do. 

- [x] Start new project LARAVEL 10
- [x] install livewire 3?
- [x] Install Social Stream 
- [x] filament
- [x] add one dataset BKOAT
- [x] build API access for that dataset
- [x] build API login for that dataset not needed
- [x] build documentation for the API 

- [x] [[ Set up admin panel in filament]] so that it only allows admin users 
- [x] add users in admin panel
- [x] add experiments in admin panel 
- [x] add [[Filament table]] with filter and export for that dataset outside of admin panel 



I started in eRAbones 
deleted all the tables, 
ran the migrations again
```bash
composer require filament/filament:"^3.0-stable" -W 
```

```bash
php artisan filament:install --panels
```

## 2023-10-26

Note: this is probably not working - so read on for proper : I have recorded my own research, but actual working protocol is here https://docs.socialstream.dev/guides/filament-with-jetstream  and also [[Create API using LARAVEL]] 
In dbeaver, delete all the tables created by socialstream in previous try
```SQL
DROP TABLE eraSandpit.dbo.users;
DROP TABLE eraSandpit.dbo.user_types;
DROP TABLE eraSandpit.dbo.personal_access_tokens;
DROP TABLE eraSandpit.dbo.password_reset_tokens;
DROP TABLE eraSandpit.dbo.migrations;
DROP TABLE eraSandpit.dbo.connected_accounts;
DROP TABLE eraSandpit.dbo.failed_jobs;
DROP TABLE eraSandpit.dbo.sessions;
```


```bash
laravel new eRAbones-2023-10-16
cd eRAbones-2023-10-16
code .
composer require livewire/livewire
php artisan livewire:publish --config
composer require joelbutcher/socialstream
composer require laravel/jetstream
php artisan socialstream:install jetstream livewire
composer require filament/filament:"^3.0-stable" -W
php artisan filament:install --panels

```

modify .env to match a previous one, 

```
composer install
php artisan migrate
npm install
php artisan serve
```

At this point, when trying log in: 
```
Unable to locate a class or view for component [authentication-card-logo].
```


So let's try again using the socialstream filament installer instead:
first: 
```
php artisan migrate:rollback
```

a few times, until there is nothing to rollback. 

```bash
laravel new eRAbones-2023-10-26
cd eRAbones-2023-10-26
code .

```

in visual code

```bash
composer require joelbutcher/socialstream
composer require laravel/jetstream
php artisan socialstream:install filament
php artisan migrate
composer install
php artisan serve
history
php artisan socialstream:install jetstream livewire
php artisan migrate
php artisan serve
```

Error: Unable to locate a class or view for component [authentication-card-logo].

To do again - but this time, check before installing filament that it is working:) 


```
composer create-project laravel/laravel eRAbones-2023-10-26-03
cd eRAbones-2023-10-26-03
code .
composer require joelbutcher/socialstream
composer require laravel/jetstream
php artisan socialstream:install jetstream livewire
/// don't forget to update the .env file
php artisan migrate
nom run dev
php artisan serve

```

add 
```php
# file: config\services.php
    'github' => [

        'client_id' => env('GITHUB_CLIENT_ID'),

        'client_secret' => env('GITHUB_CLIENT_SECRET'),

        'redirect' => env('GITHUB_REDIRECT_URI')

    ],

    'google' => [

        'client_id' => env('GOOGLE_CLIENT_ID'),

        'client_secret' => env('GOOGLE_CLIENT_SECRET'),

        'redirect' => env('GITHUB_REDIRECT_URI')

    ],
   
```

then let's try to add filament: 

```bash
php artisan socialstream:install filament
```


That had a problem with the phot that couldnt be updated. 

``
```bash
composer create-project laravel/laravel eRAbones-2023-10-26-04
cd eRAbones-2023-10-26-04
code .
composer require joelbutcher/socialstream
composer require laravel/jetstream
php artisan socialstream:install jetstream livewire
##don't forget to update the .env file
php artisan migrate
npm run dev
php artisan serve
```
the add
```php
# file: config\services.php
    'github' => [

        'client_id' => env('GITHUB_CLIENT_ID'),

        'client_secret' => env('GITHUB_CLIENT_SECRET'),

        'redirect' => env('GITHUB_REDIRECT_URI')

    ],

  

    'google' => [

        'client_id' => env('GOOGLE_CLIENT_ID'),

        'client_secret' => env('GOOGLE_CLIENT_SECRET'),

        'redirect' => env('GITHUB_REDIRECT_URI')

    ],
   
```
I had issue: first register someone without github and create a picture, then it works. 

So at this stage, I have it that works without filament 


then I loaded that on a repo: 
  2 git init
   3 git status
   4 git add --all
   5 git commit -m "Base: social stream and livewire - working"
   6 git status
   7 git remote add origin https://github.com/nathcast/SocialStreamBlank.git
   8 git push --set-upstream origin master
   9 git push --set-upstream origin main
  10 git checkout -b main
  11 git remote add origin https://github.com/nathcast/SocialStreamBlank.git
  12 git push --set-upstream origin main
  13 git fetch
  14 git push --set-upstream origin main
  15 git push
  16 git push --set-upstream origin main
  17 git pull
  18 git branch --set-upstream-to=origin/main main
  19 git push
  20 git pull
  21 git pull --allow-unrelated-histories
  22 git push
  23 git push --allow-unrelated-histories
  24 git status
  25 git add --all
  26 git commit -m "readme and so on"
  27 git push 


then I used the CLI to add this repo to another place.

```
composer install
npm run dev

```

and that works

## 2023-10-27

From Joel Butcher response in GIT 
- [x] Create project : eRAbones-2023-10-27-01
- [x] `composer require` all required deps (make sure to target the dev branch above for Socialstream, you may need to update your composer.json's `minimum-stability` property to `dev`)
	- [x] [[socialstream]]
	- [x] [[filament]]
	- [x] [[jetstream]]
	- [x] [[livewire]]

- [x]  Install Filament
- [x]  Install Jetstream (make a note of the optional features you are using)
- [x]  Install socialstream for filament: `php artisan socialstream:install filament`
- [x]  Install socialstream for jetstream: `php artisan socialstream:install jetstream livewire <jetstream features from step 4>`

**It's really important that you install for Filament first THEN install for Jetstream as both commands will overwrite the user model (which you will want to retain).**

```bash
composer create-project laravel/laravel eRAbones-2023-10-27-01
```
```bash
composer require joelbutcher/socialstream
```
```bash
composer require filament/filament:"^3.0-stable" -W
```
```bash
composer require laravel/jetstream
```
```bash
composer require laravel/livewire 
```
```bash
php artisan filament:install --panels
```
```bash
 What is the ID? [admin]
❯ admin

   INFO  Filament panel [D:\laravel2023\eRAbones-2023-10-27-01\app\Providers/Filament/AdminPanelProvider.php] created successfully.

   WARN  We've attempted to register the AdminPanelProvider in your [config/app.php] file as a service provider. If you get an error while trying to access your panel then this process has probably failed. You can manually register the service provider by adding it to the [providers] array.
```


```bash
php artisan jetstream:install livewire
```
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

    'features' => [

        Features::createAccountOnFirstLogin(),

        // Features::generateMissingEmails(),

        Features::rememberSession(),

        Features::providerAvatars(),

        Features::refreshOAuthTokens(),

    ], 
```
 - [ ] update config/services


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

In previous project:
```bash
php artisan migrate:rollback
```

In this project: 
```bash
php artisan migrate

```
and in two separate shells: 
```bash
npm run dev
php artisan serve
```

in GITHUB and google @ revoke all the tokens 

If using photos, first register a user with a normal form and add a photo, then try the GIT and google. 

**It works:)** 

in git it is repo: https://github.com/nathcast/SocialStreamBlank


## References
List here the original tutorials that I have used
I have participated in that:) 

https://docs.socialstream.dev/guides/filament-with-jetstream 
