## Dependencias

- `npm init -y`
- `npm install tailwindcss autoprefixer postcss-cli`

### Inicializamos las herramientas instaladas:

<!-- Genera archivo configuracion vacio de nombre tailwind.config.js -->

- `npx tailwindcss init`
<!-- Genera archivo configuracion completo -->
- `npx tailwindcss init tailwind.config.full.js --full`

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

- `"scripts": { "build": "postcss css/tailwind.css -o public/css/styles.css",`
<!-- Para autoregenerar el tailwind.css cuando creamos paquetes -->
- `"dev": "postcss css/tailwind.css -o public/css/styles.css --watch"}`
<!-- Ejecutar para compilar -->
- `npm run dev`

### Inicializamos script para crear el css

<!-- genera una directorio css con su styels.css en la carpeta public -->

- `npm run build`
