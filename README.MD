## 📖 Library

- [AdonisJS](https://adonisjs.com/)
- [InertiaJS](https://inertiajs.com/)
- [Svelte](https://svelte.dev/)

## 🧶 Installation

```bash
# Clone the project
git clone https://github.com/andytryn/adonisjs.git

# Go to the project directory
cd adonisjs

# Install dependencies
npm install

# Copy file .env.example to file .env
cp .env.example .env

# Re-generate key
node ace generate:key

# Start the server
node ace serve --watch
```

## Guides

 - [How to install AdonisJS, InertiaJS and Svelte](https://github.com/andytryn/adonisjs/blob/master/docs/make_from_scratch.md)
 - [Adding Tailwind to Adonis](https://github.com/andytryn/adonisjs/blob/master/docs/adding_tailwind.md)
 - [Adding Bootstrap or Etc. template](https://github.com/andytryn/adonisjs/blob/master/docs/adding_template.md)
 - [Adding Sweetalert2](https://github.com/andytryn/adonisjs/blob/master/docs/sweetalert2.md)


## Note

```bash
# Migration & Models
node ace make:migration (tabel name)
node ace make:model Category -m
node ace make:model Tag -m
node ace make:model Post -m
node ace make:model Category -m

node ace make:migration post_tag

node ace migration:run

# Controller
node ace make:controller Dashboard -rm
node ace make:controller Post -r
node ace make:controller Category -r
node ace make:controller Tags -r

```
