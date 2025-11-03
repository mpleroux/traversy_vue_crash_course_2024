# README

## Description

These are the local files I created while following the Traversy Media tutorial [Vue.js Crash Course](https://www.youtube.com/watch?v=VeNfHj6MhgA).

- [Project repository](https://github.com/bradtraversy/vue-crash-2024)

I didn't clone or fork the project repo because I wanted to create everything from scratch. I enjoyed this tutorial and the job board project. It was a good review of Vue.js and Tailwind CSS while providing an opportunity to work with an API locally.

### Technologies used

- Vue 3/Composition API
- Vite
- Tailwind CSS 4
- Vue Router
- Axios
- JSON
- JSON Server
- Prime Icons
- Vue-Spinner
- Vue-Toastification
- Fill All Inputs with Dummy Data (Chrome extension)
- Netlify

## To install and run from repo

```sh
npm install
npm run dev
```

### Notes about tutorial

Create application:

```sh
cd `~/Dev/traversy_vue_crash_course_2024
npm create vue@latest
```

- Use default directory
- Select features: Prettier
- Don't skip example code

`vite.config.js`: Use server port 3000

```js
  server: {
    port: 3000,
  },
```

Run the project:

```sh
npm install
npm run dev
```

Skip Brad's instructions for installing Tailwind/PostCSS and generating the Tailwind/PostCSS config files

[Get started with Tailwind CSS v4](https://tailwindcss.com/docs/installation/using-vite):

`npm install tailwindcss @tailwindcss/vite`

Add `@tailwindcss/vite` plugin to Vite config:

```js
// link the CSS here instead of in the HTML
import tailwindcss from '@tailwindcss/vite'
...
export default defineConfig({
  plugins: [
    tailwindcss()
  ],
});
```

There is no `tailwind.config.js` file anymore and there's no need to specify directories for watching Tailwind files. The `content` property has been replaced by an automatic system that scans project files for Tailwind classes.

Add `@import "tailwindcss"` to the top of my CSS file

VSCode:

- Install the [Tailwind CSS Intellisense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) extension by Tailwind Labs
- When viewing a CSS file that uses Tailwind at-rules change the language mode from "CSS" to "Tailwind CSS"

`JobView.vue`: As a temporary workaround for stylesheet errors I replaced `md:grid-cols-70/30` with `md:grid-cols-[70%_30%]`

I split `main.css` into two stylesheets and imported them both in `@/main.js`:

fonts.css:

```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');
```

tailwind.css:

```css
/* tailwind.css — only Tailwind stuff here */
@import 'tailwindcss';

@theme {
  --font-sans: 'Poppins', sans-serif;
}
```

main.js:

```js
import './assets/fonts.css'; // Google Fonts
import './assets/tailwind.css'; // tailwind + @theme
```

As of Vue 3 there's no need to import `defineProps` from `vue` anymore so I removed all the import statements.

I encountered the Vue Router warning "[Vue Router warn]: No match found for location with path "/index.html".

- The URL I was using the test the project had changed from `localhost:3000` to `localhost:3000/index.html`. Changing it back fixed the problem.
- That probably happened when I clicked on some nav links before they had been fully implemented

## Screenshot

![Screenshot of WDS weather app](./public/screenshot.png "Screenshot of WDS weather app")
