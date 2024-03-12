202311031053
Status: #workflow
Tags: 
previous: [[documenting the API]] , [[Create API using LARAVEL]]

# configuring Filament Admin

```bash
  php artisan make:migration AddUserTypeIdToUsersTable
  
  ```

```php
//see add_user_type migration 
     Schema::table('users', function (Blueprint $table) {

            $table->integer('user_type_id')

            ->after('current_team_id')

            ->default(0);

        });
```

```php
// user model
    public function canAccessPanel(Panel $panel): bool

    {

        return $this->user_type_id >= 3  ;

    }
```

made myself a 3 
and now, only me can access teh filament admin panel. 


```php 
php artisan migrate
```

Creating some tables in the admin panel. 
```bash

composer require doctrine/dbal
php artisan make:filament-resource User --generate
php artisan make:filament-resource Bkoat --generate
php artisan make:filament-resource Experiment --generate
```
 
I have added a table for Experiment in the APP, but I have problem integrating it in th layout.. TOD) try to understand how the blade layout works in this version of laravel UI> 


---
## References
