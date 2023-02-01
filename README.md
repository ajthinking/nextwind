# nextwind
Alias to quickly create a nextjs + tailwindcss app.

```bash
nextwind() {
  local APPNAME=$1
  npx create-next-app $APPNAME
  cd $APPNAME
  yarn add prisma --dev
  npx prisma init
  yarn add tailwindcss postcss autoprefixer --dev
  npx tailwindcss init -p
  echo "/** @type {import('tailwindcss').Config} */
module.exports = {
content: [
\"./pages/**/*.{js,ts,jsx,tsx}\",
\"./components/**/*.{js,ts,jsx,tsx}\",
],
theme: {
extend: {},
},
plugins: [],
}" > tailwind.config.js
  echo "@tailwind base;
@tailwind components;
@tailwind utilities;
" > styles/globals.css
  yarn dev
}
```
