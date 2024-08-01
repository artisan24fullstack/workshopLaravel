
# Laravel

## Installation Concurrently

> npm i concurrently -g

```
"start": "concurrently  \"php artisan config:cache\" \"php artisan serve\" \"npm run dev \"  "
```


## Installation Jestream & Livewire

[Repo](https://github.com/artisan24fullstack/automatisationLaravel/tree/main/authLaravel)
Attention, si erreur de type, refaire un ```npm install```

 ```
 node:internal/process/promises:288
[2]             triggerUncaughtException(err, true /* fromPromise */);
[2]             ^
[2]
[2] [Failed to load PostCSS config: Failed to load PostCSS config (searchPath: workshopLaravel/becode): [Error] Loading PostCSS Plugin failed: Cannot find module 'tailwindcss'
[2] Require stack:
[2] - workshopLaravel\becode\postcss.config.js
[2]
[2] (@workshopLaravel\becode\postcss.config.js)
[2] Error: Loading PostCSS Plugin failed: Cannot find module 'tailwindcss'
[2] Require stack:
[2] - workshopLaravel\becode\postcss.config.js
[2]
[2] (@workshopLaravel\becode\postcss.config.js)
[2]     at load (file:///workshopLaravel/becode/node_modules/vite/dist/node/chunks/dep-CzJTQ5q7.js:33248:11)
[2]     at file:////workshopLaravel/becode/node_modules/vite/dist/node/chunks/dep-CzJTQ5q7.js:33273:16
[2]     at Array.map (<anonymous>)
[2]     at plugins (file:///workshopLaravel/becode/node_modules/vite/dist/node/chunks/dep-CzJTQ5q7.js:33272:8)
[2]     at processResult (file:////workshopLaravel/becode/node_modules/vite/dist/node/chunks/dep-CzJTQ5q7.js:33342:14)
[2]     at file:///C:/workshopLaravel/becode/node_modules/vite/dist/node/chunks/dep-CzJTQ5q7.js:33472:14]
[2]
[2] Node.js v18.8.0
```

## Allowing users to access a panel

[Doc](https://filamentphp.com/docs/3.x/panels/installation)


PREPARE Resources for workshop (BACKEND)

### Proposal and to test (TODO)

- To leverage PHP Enums in Laravel, Jetstream, and Filament for managing roles like ADMIN, EDITOR, and USER in your User model, follow these steps:


- Leveraging PHP Enums in Laravel with the iteks/laravel-enum Package
https://medium.com/@jeramyhing/leveraging-php-enums-in-laravel-with-the-iteks-laravel-enum-package-e826cca6e357

> Step 1: Define Enum Classes
- First, create separate Enum classes for roles and permissions. 
- This will help in maintaining a clean and organized structure for role management.


```
<?php

namespace App\Enums;

enum Role: string
{
    case ADMIN = 'ADMIN';
    case EDITOR = 'EDITOR';
    case USER = 'USER';

    public static function labels(): array
    {
        return [
            self::ADMIN => 'Admin',
            self::EDITOR => 'Editor',
            self::USER => 'User',
        ];
    }

    // Static property to hold the default role
    public static string $ROLE_DEFAULT = self::USER;
}

enum Permission: string
{
    case VIEW_ADMIN = 'view-admin';
}

```

> Step 2: Update the User Model
- Modify the User model to use these enums instead of constants. 
- Also, update the methods to utilize these enums effectively.


```
use App\Enums\Role;
use App\Enums\Permission;

   public function canAccessPanel(Panel $panel): bool
    {
        return $this->hasPermission(Permission::VIEW_ADMIN);
    }

    public function isAdmin(): bool
    {
        return $this->role == Role::ADMIN;
    }

    public function isEditor(): bool
    {
        return $this->role == Role::EDITOR;
    }
```

> Step 3 How to Use $ROLE_DEFAULT in migration

```
<?php

use Illuminate\Support\Facades\Schema;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Database\Migrations\Migration;

// Import the Role enum
use App\Enums\Role;

return new class extends Migration
{
    /**
     * Run the migrations.
     */
    public function up(): void
    {
        Schema::table('users', function (Blueprint $table) {
            // Use the $ROLE_DEFAULT property from the Role enum
            $table->string('role')->default(Role::$ROLE_DEFAULT);
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::table('users', function (Blueprint $table) {
            $table->dropColumn('role');
        });
    }
};
```
