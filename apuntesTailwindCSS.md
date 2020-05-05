## Dependencias

- `npm init -y`
- `npm install tailwindcss autoprefixer postcss-cli`

### Inicializamos las herramientas instaladas:

<!-- Genera archivo configuracion vacio de nombre tailwind.config.js -->

- `npx tailwindcss init`
<!-- Genera archivo configuracion completo -->
- `npx tailwindcss init tailwind.config.full.js --full`

<!-- Para extender los css -->

- `npx tailwindcss build css/tailwind.css -o public/css/styles.css`

<!-- Plugin recomendado para VSCode: Tailwind CSS IntelliSense -->

### Creamos archivo de configuracion postcss.config.js

<!-- Instrucciones archivo postcss.config.js: -->

- `touch postcss.config.js`
- `module.exports = { plugins: [require('tailwindcss'), require('autoprefixer')], };`

### Creacion archivo html y origen CSS

- `mkdir css`
- `touch css/tailwind.css`

### Configuracion archivo css/tailwind.css

- `@tailwind base; @tailwind components; @tailwind utilities;`

### Completamos script en package.json

- `"scripts": { "build": "postcss css/tailwind.css -o public/css/styles.css -w",`
<!-- Para autoregenerar el tailwind.css cuando creamos paquetes -->
- `"dev": "postcss css/tailwind.css -o public/css/styles.css --watch"}`
<!-- Ejecutar para compilar -->
- `npm run dev`

### Inicializamos script para crear el css

<!-- genera una directorio css con su styels.css en la carpeta public -->

- `npm run build`

### Instalacion PurgeCss

- `npm i -D @fullhuman/postcss-purgecss`
- En el archivo postcss.config.css pegar: `const purgecss = require('@fullhuman/postcss-purgecss')`
- `const purgecss = require('@fullhuman/postcss-purgecss');
<!-- En el mismo archivo, pegar en la seccion de plugins -->
- `purgecss({content: ['./**/*.html']},`

### Comando para instalar nanoCss

- `$ npm i cssnano --save-dev`

<!-- El archivo postcss.config.js queda asi; -->
<!--
const purgecss = require('@fullhuman/postcss-purgecss');

module.exports = {
  plugins: [
    require('tailwindcss'),
    require('autoprefixer'),
    purgecss({
      content: ['./**/*.html'],
      defaultExtractor: content => content.match(/[\w-/:]+(?<!:)/g) || [],
    }),
    require("cssnano")({
      preset: "default",
    }),
  ],
}; -->
