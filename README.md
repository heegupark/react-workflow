# react-workflow
The basic workflow to start a react project 

## Required
### 1. Initialize the NPM package
npm init -y 
### 2. Install dev-dependencies
npm i -D webpack webpack-cli babel-loader @babel/core @babel/plugin-transform-react-jsx
### 3. Install dependencies
npm i react react-dom
### 4. Create 2 directories for production and distribution
mkdir src dist 
### 5. Create the minimum nessacery files for production and distribution
touch src/index.jsx dist/index.html dist/style.css webpack.config.js
### 6. Make a basic HTML skeleton
make sure to add the main.js script and link your css
```html
<!DOCTYPE html>
<html lang="en">

    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>react-accordion-component</title>
      <link rel="stylesheet" href="style.css">
    </head>

    <body>
      <div id="root"></div>
      <script src="./main.js"></script>
    </body>

    </html>
```

## Optional:
* add font-awesome
```html
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.9.0/css/all.css">
```

