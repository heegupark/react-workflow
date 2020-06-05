# react-workflow
The basic workflow to start a react project 

## 1. Initialize the NPM package
npm init -y 
## 2. Install dev-dependencies
npm i -D webpack webpack-cli babel-loader @babel/core @babel/plugin-transform-react-jsx
## 3. Install dependencies
npm i react react-dom
## 4. Create 2 directories for production and distribution
mkdir src dist 
## 5. Create the minimum nessacery files for production and distribution
touch src/index.jsx dist/index.html dist/style.css webpack.config.js
