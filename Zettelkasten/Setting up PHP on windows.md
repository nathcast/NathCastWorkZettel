232023-07-12 - 18-00
Status: #idea
Tags: [[laravel]] , [[php]], [[server]], [[fullstack]]


# Setting up PHP on windows

From PHP.net download windows, zip, 
extract all. 
rename folder [[PHP]]
Add the path the environment variable [[PATH]]
try run cmd > PHP --version  : should work
move folder to C:\Program Files\
edit php.ini: 
	enable [extensions]: curl, fileinfo, mbstrings, gd, [[pdo_msql]], zip
	provide full path to extension_dir 
	memory_limit: 256M

To run [[server]] in PHP> PHP -S localhost:8000

Run Server
## Get Composer
getcomposer.org, download, install, restart machine. 


## a new [[laravel]] project
in code/laravel projects>[[composer]] create-project laravel/laravel ourfirstapp


---
## References
https://www.udemy.com/course/lets-learn-laravel-a-guided-path-for-beginners/learn/lecture/35422268#overview

https://www.daggerhartlab.com/autoloading-namespaces-in-php/
