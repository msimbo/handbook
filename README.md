# Setting up TailwindCSS

* If you're on windows, [Install Git command-line](https://git-scm.com/downloads)
* Next, we [install npm & node](https://nodejs.org/en/download/) ([What is node and npm?](https://www.hostinger.com/tutorials/what-is-npm))
* After installation, open the command-line (On windows that's "Git Bash", on mac, open "Terminal")
* In the command-line, type `npm install --global yarn` ([what is this doing?](https://engineering.fb.com/2016/10/11/web/yarn-a-new-package-manager-for-javascript/))
* From your command-line, create a new folder (for example, "project-tailwindcss"). Type `mkdir project-tailwindcss`
* Go to https://v2.tailwindcss.com/docs/installation (have this open on the side as a reference)
* Now enter the new folder, type `cd project-tailwindcss`
* Now let's install the TailwindCSS package:
* Type, `yarn add -D tailwindcss@2.2.19 postcss@latest autoprefixer@latest` (note, this is slightly different from what is in the official documentation)
* Next, still in the terminal, type `npx tailwindcss init`. This should create a "tailwind.config.js" file
* Open your project folder in VS Code (in our example, that will be "project-tailwindcss")
*   With the folder open in VS Code, confirm your "tailwind.config.js" file has this content

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
*   Now, let's create a "tailwind.css" file with this content

    ```css
    /* tailwind.css */
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```
* Now, let's dynamically generate a "styles.css" file from this file. From the command-line, run `npx tailwindcss -i ./tailwind.css -o ./styles.css`
* Finally, create an "index.html" file to reference our generated "styles.css"
* ```html
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

