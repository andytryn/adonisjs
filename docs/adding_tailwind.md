## 🪔 Adding Tailwind to Adonis

1. On your project directory, install the dependencies:

```bash
# Install Dependencies
npm install -D tailwindcss@latest postcss@latest autoprefixer@latest

# Create Postcss Config File
touch postcss.config.js

# Also Install Postcss-Load
npm i -D postcss-loader

# Create Tailwind Config File
npx tailwindcss init
```

2. Set the postcss.config.js

```bash
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  }
}
```

3. Set the tailwind.config.js

```bash
module.exports = {
  mode: 'jit',
  purge: {
    content: [
      './resources/views/**/*.svelte',
    //   './resources/css/**/*.css',
    //   './resources/js/**/*.js',
    //   './resources/js/**/*.ts',
    ],
    // enabled: production // disable purge in dev
  },
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {},
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  }
}
```

4. Set the webpack.config.js
   Enable `CSS loaders`

```bash
Encore.enablePostCssLoader()
Encore.configureCssLoader(() => {})
```

Add above `/resources/views'),`

```bash
options.static.push({
  directory: join(__dirname, './tailwind.config.js'),
  watch: true,
})
```
