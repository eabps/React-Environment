# React-Environment
This document describes step by step to prepare the environment with React, webpack and Babel

## Install Dependencies ##
```sh
$ sudo apt install nodejs yarn
```
Check installed version of ```nodejs``` and ```yarn```
```SH
$ node -v
$ yarn -v
```
## Start Project ##
In your ```directory_project``` do:
```sh
$ yarn init
```
After run ```yarn init``` will have in your ```directory_project```:
 - ```node_modules```
 - ```package.json```
 - ```yarn.lock```

## Install Project Dependencies ##
```sh
$ yarn add webpack webpack-dev-server path react react-dom html-webpack-plugin
```
```sh
$ yarn add babel-loader babel-core babel-preset-es2015 babel-preset-react --dev
```

## Config webpack ##
In ```directory_project``` create a file called ```webpack.config.js``` with the following content:

```js
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const HtmlWebpackPluginConfig = new HtmlWebpackPlugin({
    template: './src/index.html',
    filename: 'index.html',
    inject: 'body'
});

module.exports = {
    entry: './src/index.js',
    output: {
        path: path.resolve('dist'),
        filename: 'index_bundle.js'
    },
    module: {
        loaders: [
            {test: /\.js$/, loader: 'babel-loader', exclude: /node_modules/}, // for browser read js written in ES6
            {test: /\.jsx$/, loader: 'babel-loader', exclude: /node_modules/} // for browser read jsx written in ES6
        ]
    },

    plugins: [HtmlWebpackPluginConfig],
}
```

## Config Babel ##
In ```directory_project``` create a file called ```.babelrx``` with the following content:

```js
{
    "presets": [
        "es2015", "react"
    ]
}
```

## Add Start Command for webpack-dev-server ##
 Update file  ```package.json``` add the key  ```scripts ``` above key  ```dependencies ```:
  ```js
"scripts": {
    "start": "webpack-dev-server"
},
// dependecies here
```
Now, when you wish to run ```webpack-dev-server``` do:
```sh
 $ yarn start 
```
## Start with React (Little Test) ##
1. In ```directory_project``` create new directory called ```src```:
2. In ```src``` create two files: ```index.html``` and ```index.js```

```html
 <!-- index.html -->
<!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>litle test</title>
    </head>
    <body>
        open console
    </body>
</html>
 ```
 
 ```js
// index.js
console.log('Working!')
 ```
3. Run ```webpack-dev-server```:
```sh
yarn start
```
4. Open http://127.0.0.1:8080 in browser and see the console

Ref: https://scotch.io/tutorials/setup-a-react-environment-using-webpack-and-babel