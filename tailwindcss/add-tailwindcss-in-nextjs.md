# Add tailwindcss in NextJS

## Install tailwind CSS with Next.JS

Install `tailwindcss` and its peer dependencies via npm, and then run the init command to generate both `tailwind.config.js` and `postcss.config.js`.

```sh
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

## Configure your template paths

Add the paths to all of your template files in your `tailwind.config.js` file.

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx}",
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

## Add the Tailwind directives to your CSS

Add the `@tailwind` directives for each of Tailwind's layers to your `./app/global.css` file.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Start your build process

Run your build process with `npm run dev`.

```sh
npm run dev
```
