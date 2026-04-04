**TailWind CSS setup in react.**

in your projects folder;
`npm install tailwindcss @tailwindcss/vite`

now in your project look for vite.config.js
add line
`import tailwindcss from '@tailwindcss/vite'`

add function next to react(), `tailwindcss()`.

in Index.css file
`@import "tailwindcss";`


**TailWind CSS in the normal htmlcss**
create
  dist, src
folders in you project folder 
in your dist folder create index.html file

in your project folder write this command
npx tailwindcss init


--------------------- working ------------------
------------------------------------------------

## Best Setup for Tailwind v4

**1. Create your project folder and open it in VS Code**
```
mkdir my-project
cd my-project
```

---

**2. Initialize npm**
```
npm init -y
```

---

**3. Install Tailwind v4**
```
npm install tailwindcss @tailwindcss/cli
```

---

**4. Create your folder structure**
```
my-project/
├── src/
│   └── input.css
├── index.html
└── package.json
```

---

**5. Add this single line to `src/input.css`**
```css
@import "tailwindcss";
```

---

**6. Add build script to `package.json`**
```json
"scripts": {
  "build": "tailwindcss -i ./src/input.css -o ./src/output.css",
  "watch": "tailwindcss -i ./src/input.css -o ./src/output.css --watch"
}
```
Two scripts — `build` for one-time, `watch` for development.

---

**7. Run the watch script during development**
```
npm run watch
```

---

**8. Create `index.html` and link the output CSS**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="./src/output.css">
  <title>My Project</title>
</head>
<body>
  <h1 class="text-3xl font-bold text-blue-500">Hello Tailwind v4!</h1>
</body>
</html>
```

---

**9. Open `index.html` in browser — done ✅**

The `output.css` gets auto-generated and updated every time you save a file while `npm run watch` is running. No config file needed in v4.
