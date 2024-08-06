
# Blog

## Tailwind.css / Inertia / Vue.js / Laravel 
Installation Vue.js in Laravel with Tailwind.css

## Tech Stack

**Client:** 

Tailwind.css - Framework Vue.js 

> Framework for tailwind.css

- https://daisyui.com/docs/install/
daisyUI adds component class names to Tailwind CSS so you can make beautiful websites faster than ever.

```
npm i -D daisyui@latest

  plugins: [
    require('daisyui'),
  ],

  plugins: [require("@tailwindcss/typography"), require("daisyui")],

<article class="prose"></article>

```

- https://flowbite.com/
Start developing with an open-source library of over 600+ UI components, sections, and pages built with the utility classes from Tailwind CSS.

- https://preline.co/
Preline UI is an open-source set of prebuilt UI components based on the utility-first Tailwind CSS framework.


**Server:** 

Laravel 

**Packages:** 

 Jetstream 


--------------------------------

## StepByStep

### installation Jestream Inertia Vue.js

```
composer require laravel/jetstream
php artisan jetstream:install inertia
```

> php artisan migrate

```
   WARN  The SQLite database does not exist: C:\database\database.sqlite.

  Would you like to create it? (yes/no) [no]
❯ yes

   INFO  Preparing database.

  Creating migration table ................................................................................................................ 8ms DONE

   INFO  Running migrations.

  2014_10_12_000000_create_users_table .................................................................................................... 7ms DONE
  2014_10_12_100000_create_password_reset_tokens_table .................................................................................... 3ms DONE
  2014_10_12_200000_add_two_factor_columns_to_users_table ................................................................................. 9ms DONE
  2019_08_19_000000_create_failed_jobs_table .............................................................................................. 6ms DONE
  2019_12_14_000001_create_personal_access_tokens_table ................................................................................... 9ms DONE
  2024_08_06_122733_create_sessions_table ................................................................................................. 8ms DONE
```
