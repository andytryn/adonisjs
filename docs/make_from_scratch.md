## 🧠 How to install AdonisJS, InertiaJS and Svelte

```bash
npm init adonis-ts-app@latest belajar-adonis
# Select the project structure » web
# Configure webpack encore for compiling frontend assets? (y/N) » Y
```

```bash
npm i @adonisjs/lucid
node ace configure @adonisjs/lucid
# Select the database driver you want to use » mysql
```

```bash
npm i ts-loader@latest
# Edit webpack.config.json
# |--------------------------------------------------------------------------
# const sveltePreprocess = require('svelte-preprocess')

# add above Encore.setPublicPath('/assets')
# /*
# |--------------------------------------------------------------------------
# | Svelte Loader Config
# |--------------------------------------------------------------------------
# */
# Encore.addLoader({
#   test: /\.svelte$/,
#   loader: 'svelte-loader',
#   options: {
#     emitCss: true,
#     preprocess: sveltePreprocess({})
#   }
# })

# Edit on Entrypoints
# Encore.addEntry('app', './resources/js/app.ts')
# Encore.enableTypeScriptLoader()

# add above config.stats = 'errors-warnings'
# /*
# |--------------------------------------------------------------------------
# | Svelte Webpack Config
# |--------------------------------------------------------------------------
# */
# config.resolve.mainFields = ['svelte', 'browser', 'module', 'main']
# config.resolve.extensions = ['.mjs', '.js', '.svelte']

# let svelte = config.module.rules.pop()
# config.module.rules.unshift(svelte)
```

```bash
npm i @eidellev/inertia-adonisjs
node ace configure @eidellev/inertia-adonisjs
# Select the database driver you want to use » app
# Would you like to install Inertia.js? (Y/n) » true
# Which client-side adapter would you like to set up? » svelte
```

```bash
npm i @inertiajs/inertia @inertiajs/inertia-svelte
node ace configure @inertiajs/inertia-svelte
```

```bash
# Install the rest of dependencies
npm i svelte
npm i svelte-preprocess
npm i svelte-loader
```

```bash
# Edit resources/js/app.ts
# import '../css/app.css'
# import { createInertiaApp } from '@inertiajs/inertia-svelte'

# createInertiaApp({
#     resolve: (name: string) => require(`./Pages/${name}.svelte`),
#     setup({ el, App, props }: any) {
#         new App({ target: el, props })
#     },
# })
```

```bash
# Edit resources/views/app.edge
# Add above icon
# <script src="{{ asset('assets/app.js') }}" defer></script>
```

```bash
# Add Folder & File
# resources/js/Pages/Test.svelte
# <script>
#   export let nama = "Danang";
# </script>

# <h1>Halo {nama}</h1>

# <style>
#   h1 {
#     color: chartreuse;
#   }
# </style>
```

```bash
# Add Routes start/routes.ts
# Route.get('/', async ({ inertia }) => {
#   return inertia.render('Test')
# })

# Route.get('/test', async ({ inertia }) => {
#   return inertia.render('Test', { nama: 'Danang Ponorogo' })
# })
```
