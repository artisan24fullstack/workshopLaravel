
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
