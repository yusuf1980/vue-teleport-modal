# Vue Teleport Modal Tailwind

This template should help get you started developing with Vue 3 in Vite.

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Install Tailwind
    
    npm install -D tailwindcss postcss autoprefixer

### Create Tailwind Config and PostCSS

    npx tailwindcss init -p

tailwind.config.js
...

    export default {
        content: [
            "./index.html",
            "./src/**/*.{vue,js,ts,jsx,tsx}",
        ],
        theme: {
            extend: {},
        },
        plugins: [],
    }

style.css(src/assets/main.css)

    @tailwind base;
    @tailwind components;
    @tailwind utilities;

    npm run dev

