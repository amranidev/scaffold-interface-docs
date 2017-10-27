# Getting started

### Installation and setup

1. Instrallation through composer. 

	- Add package dependencies to composer.json in your larave project and run `$ composer update` command.

	```json
		require : {
			"Amranidev/scaffold-interface": "v1.7.*"
		}
	```

	- Or run in your terminal this command `$ composer require amranidev/scaffold-interface`.

 <hr>

2. Add the service providers to config/app.php.

	```php
	Amranidev\ScaffoldInterface\ScaffoldInterfaceServiceProvider::class,
	Amranidev\Ajaxis\AjaxisServiceProvider::class,
	Spatie\Permission\PermissionServiceProvider::class,
	Pusher\Laravel\PusherServiceProvider::class,
	```

 <hr>

3. Publish the assets in your application with.

	`$ php artisan vendor:publish` 

	- **What does this command publishes:**

	- app/Http/Controllers/UserController.php

	- app/Http/Controllers/RoleController.php
		
	- app/Http/Controllers/PermissionController.php
		
	- resources/views/scaffold-interface (dashboard,users,roles,permissions blade)
		
	- resources/views/scaffold-interface/layouts (you can edit your layouts before making crud)
		
	- public/js/scaffold-interface-js
		
	- public/css/scaffold-interface-css
		
	- config/amranidev/config.php
		
	- database/migrations/migration_file

 <hr>

4. Migrate for the Scaffold Interface table.

	`$ php artisan migrate`

 <hr>

5. Authentication scaffolding.

	`$ php artisan make:auth`

6. Add HasRole dependency to app/User.php:

 <hr>

	```php
	<?php

	namespace App;

	use Illuminate\Foundation\Auth\User as Authenticatable;
	use Illuminate\Notifications\Notifiable;
	use Spatie\Permission\Traits\HasRoles;

	class User extends Authenticatable
	{
    	use Notifiable;
    	use HasRoles;
	}
 	```
 
Congratulations, you have successfully installed Scaffold Interface!