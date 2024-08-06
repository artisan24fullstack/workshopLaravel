
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

```
php artisan migrate

```
