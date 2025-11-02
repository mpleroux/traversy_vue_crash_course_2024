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

Install [Tailwind v4](https://tailwindcss.com/docs/installation/using-vite):

`npm install tailwindcss @tailwindcss/vite`

Add `@tailwindcss/vite` plugin to Vite config:

```js
import tailwindcss from '@tailwindcss/vite'
...
export default defineConfig({
  plugins: [
    tailwindcss()
  ],
});
```

There is no `tailwind.config.js` file anymore so there's no need to specify directories for watching Tailwind files. The `content` property has been replaced by an automatic system that scans project files for Tailwind classes.

According to the [Tailwind installation guide](https://tailwindcss.com/docs/installation/using-vite) it's no longer necessary to link the CSS from the HTML. It's already imported in `main.js`

There is a new way to configure Brad's `extend` settings from the old `tailwind.config.js` file but I could never get his 70%/28% grid column style working, even after a lot of suggestions from ChatGPT. To continue the tutorial I did the following:

- In the CSS file, I removed the `--grid-cols-70/30` rule
- I replaced the Tailwind class `md:grid-cols-70/30` with the standard `md:grid-cols-[70%_30%]`
- I split `main.css` into two stylesheets and imported them both in `@/main.js`:

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

I still get an error on `@theme`. The Poppins font seems to work fine.

As of Vue 3 there's no need to import `defineProps` from `vue` anymore so I removed all the import statements.

I encountered the Vue Router warning "[Vue Router warn]: No match found for location with path "/index.html".

- The URL I was using the test the project had changed from `localhost:3000` to `localhost:3000/index.html`. Changing it back fixed the problem.
- That probably happened when I clicked on some nav links before they had been fully implemented

## Screenshot

![Screenshot of WDS weather app](./public/screenshot.png "Screenshot of WDS weather app")
