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
### 7. Configure webpack
add the following to webpack.config.js
```
     module.exports = {
      resolve: {
        extensions: ['.js', '.jsx']
      },
      module: {
        rules: [
          {
            test: /\.jsx?$/,
            use: {
              loader: 'babel-loader',
              options: {
                plugins: [
                  '@babel/plugin-transform-react-jsx'
                ]
              }
            }
          }
        ]
      }
    };
```

## Optional:
* add bootstrap
```html
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.5.0/css/bootstrap.css"/>
```
* add font-awesome
```html
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.9.0/css/all.css">
```
* add build/watch/dev shell scripts to your json.package under the scripts
```json
    "dev": "webpack-dev-server",
    "build": "webpack --mode=production",
    "watch": "webpack --mode=development --watch"
```
* add additional functionality if you chose to use the watch/dev shell script (adding sourcemap tool/server tool, respectively)
Replace the content of the webpack.config.js file
```
const path = require('path');

const srcPath = path.resolve(__dirname, 'src');
const publicPath = path.resolve(__dirname, 'dist');

module.exports = {
  resolve: {
    extensions: ['.js', '.jsx']
  },
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        include: srcPath,
        use: {
          loader: 'babel-loader',
          options: {
            plugins: [
              '@babel/plugin-transform-react-jsx'
            ]
          }
        }
      }
    ]
  },
  devtool: 'source-map',
  devServer: {
    host: '0.0.0.0',
    port: 3000,
    contentBase: publicPath,
    watchContentBase: true,
    stats: 'minimal'
  }
};
```
