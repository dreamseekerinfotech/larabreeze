# Laravel Authentications using laravel breeze

Hello Everyone Today I am going to teach to how to do user authentication in laravel 8 using laravel breeze. AS per the laravel official site laravel.com

laravel breeze is a minimal, simple implementation of all of Laravel's authentication features, including login, registration, password reset, email verification, and password confirmation. Laravel Breeze's default view layer is made up of simple Blade templates styled with Tailwind CSS.

laravel breeze is less complex then laravel Jetstream, laravel breeze comes with basic login , register, forgot password, email setup, change password etc.

so without westing a time lets get started

1st step: install laravel new app

composer create-project laravel/laravel larabreeze

or you can install laravel globally and create app like as follow

composer global require laravel/installer
laravel new larabreeze

2nd step: require laravel breeze package

after step 1 let's require laravel breeze into our project using following command

composer require laravel/breeze

image installbreeze.png

3rd step: let's migrate basic migrations and handle string bug in database

first of all let's create one database with name larabreeze and configure our env like as follow

DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=larabreeze
DB_USERNAME=root
DB_PASSWORD=123456

next step is to migrate database, before that we need to handle one bug, max string length in AppServiceProvider.php file

add Schema::defaultstringLength(191); link in boot function

and use Illuminate\Support\Facades\Schema; at top

the file will be look like as follow

image AppServiceProvider.png

now let's migrate database

php artisan migrate

image migration.png

4th step: install laravel breeze

install laravel breeze by following command

php artisan breeze:install

this command will create all blade controller and required files for basic authentications

5th step: install and compile javascript dependency

install and compile node dependency by following command

npm install
npm run dev

6th step: configure email details

we are currently using mailtrap to test mail so lets configure this by as follow

click on user google account or user github account
image mailtrapsignin.png

select latavel 7+
image mailtrap_configurations.png

copy configurations

MAIL_MAILER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=f915874e988c27
MAIL_PASSWORD=fcc1115d20f98f
MAIL_ENCRYPTION=tls

7th step: let's run our project

run following command

php artisan serve

run url 127.0.0.1:8000 in browser and you will find lending page like as below

image lendingpage.png

let's register

image register.png

and your dashboard will look like this

image dashboard.png

it's basic functionality has been created by breeze

let's checkout login

image login.png

and it's all work fine

if you have any query you can ask me on any of my social media handle or you can mail me on learning@dreamseekerinfotech.com
