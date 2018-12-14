# Create react app by using Webpack 4 and Babel 7

This is a systematic guide to create a react app by using webpack 4 and babel 7 for beginners.

## Assumption

- [Node Js](https://nodejs.org/en/) has installed
- [Yarn](https://yarnpkg.com/en/) has installed

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
