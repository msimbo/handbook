# Setting up TailwindCSS

1. If you're on windows, [Install Git command-line](https://git-scm.com/downloads)
2. Next, we [install npm & node](https://nodejs.org/en/download/) ([What is node and npm?](https://www.hostinger.com/tutorials/what-is-npm))
3. After installation, open the command-line (On windows that's "Git Bash", on mac, open "Terminal")
4. In the command-line, type `npm install --global yarn` ([what is this doing?](https://engineering.fb.com/2016/10/11/web/yarn-a-new-package-manager-for-javascript/))
5. From your command-line, create a new folder (for example, "project-tailwindcss"). Type `mkdir project-tailwindcss`
6. Go to https://v2.tailwindcss.com/docs/installation (have this open on the side as a reference)
7. Now enter the new folder, type `cd project-tailwindcss`
8. Now let's install the TailwindCSS package:
9. Type, `yarn add -D tailwindcss@2.2.19 postcss@latest autoprefixer@latest` (note, this is slightly different from what is in the official documentation)
10. Next, still in the terminal, type `npx tailwindcss init`. This should create a "tailwind.config.js" file
11. Open your project folder in VS Code (in our example, that will be "project-tailwindcss")
12. With the folder open in VS Code, confirm your "tailwind.config.js" file has this content

    ```javascript
    // tailwind.config.js
    module.exports = {
      purge: [],
      darkMode: false, // or 'media' or 'class'
      theme: {
        extend: {},
      },
      variants: {},
      plugins: [],
    }
    ```
13. Now, let's create a "tailwind.css" file with this content

    ```css
    /* tailwind.css */
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```
14. Now, let's dynamically generate a "styles.css" file from this file. From the command-line, run `npx tailwindcss -i ./tailwind.css -o ./styles.css`
15. Finally, create an "index.html" file to reference our generated "styles.css"
16. ```html
    <!doctype html>
    <html>
    <head>
      <!-- ... -->
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <link href="styles.css" rel="stylesheet">
    </head>
    <body>
       <h1 class="text-3xl"> Welcome to Tailwind </h1>
    </body>
    </html>
    ```

