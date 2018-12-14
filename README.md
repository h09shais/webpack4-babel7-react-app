# Create react app by using Webpack 4 and Babel 7

This is a systematic guide to create a react app by using webpack 4 and babel 7 for beginners.

## Assumption

- [Node Js](https://nodejs.org/en/) has installed
- [Yarn](https://yarnpkg.com/en/) has installed

## Part 01 - Webpack

### Step 01 - Create folder and initialize new project

```sh
> mkdir simple-create-react-app
> cd simple-create-react-app
> yarn init -y
```

### Step 02 - Add webpack

```sh
> yarn add webpack webpack-cli --D
```

### Step 03 - Build your project for the first time

```javascript
// package.json
{
  "scripts": {
    "build": "webpack"
  }
}
```

```sh
> mkdir src
> touch src/index.js
> yarn build
```

### Step 04 - Introduce webpack config

```sh
> touch webpack.config.js
```

```javascript
// webpack.config.js

const path = require("path");

module.exports = {
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(__dirname, "dist")
  }
};
```

### Step 05 - Add webpack dev server

```sh
> touch src/index.html
> yarn add webpack-dev-server -D
> yarn add html-webpack-plugin -D
```

```javascript
// package.json

{
  "scripts": {
    "start": "webpack-dev-server --open"
  }
}

```

```javascript
// webpack.config.js

const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  entry: "./src/index.js",
  plugins: [
    new HtmlWebpackPlugin({
      template: "./src/index.html"
    })
  ],
  output: {
    filename: "main.js",
    path: path.resolve(__dirname, "dist")
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/
      }
    ]
  }
};
```

```html
<!-- src/index.html -->
<!DOCTYPE html>
<html>
  <head>
    <title>Title</title>
  </head>
  <body></body>
</html>
```

## Part 02 - Babel

### Step 06 - Add babel

```sh
> yarn add babel-loader @babel/core @babel/cli @babel/preset-env -D
> touch .babelrc
```

```javascript
// .babelrc
{
  "presets": ["@babel/preset-env"]
}
```

```javascript
// webpack.config.js

module.exports = {
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        loader: "babel-loader"
      }
    ]
  }
};
```

### Step 07 - Write your first ECMAScript!

```javascript
// src/index.js
[1, 3, 99].map(num => console.log(num));
```

```sh
> yarn start
```

Check your web browser’s dev console!
