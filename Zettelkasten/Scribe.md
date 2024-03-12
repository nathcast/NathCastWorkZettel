202310311120
Status: #idea
Tags: 

# Scribe

A laravel DEV plugin to write documentation 
https://scribe.knuckles.wtf/

Demo version at https://demo.scribe.knuckles.wtf/

HOW? 

```bash
composer require --dev knuckleswtf/scribe
php artisan vendor:publish --tag=scribe-config
```

Note while installing scribe@ 
1 package suggestions were added by new dependencies, use `composer suggest` to see details.
Package spatie/data-transfer-object is abandoned, you should avoid using it. Use spatie/laravel-data instead.
Generating optimized autoload files

```PHP
php artisan scribe:generate

```

Use https://en.wikipedia.org/wiki/Docblock to add comments to the code 

---

## References
