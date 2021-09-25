# ReacTypeScript-reloaded
This repository is set for revision of ReacTypeScript for including GraphQL knowledge.

### What is webpack?
> Webpack is module bundle for javascript.
### Webpack configuration
- Install `webpack` & `webpack-dev-server` using following commands
  `npm i -D webpack webpack-cli`
  `npm i -D webpack-dev-server`
- Create `webpack.config.js` file
    ```node
    const HtmlWebpackPlugin = require('html-webpack-plugin')
    module.exports = {
        plugins: [
            new HtmlWebpackPlugin({
                template: './src/index.html',
                filename: 'index.html'
            })
        ],
    }
    ```
- Add into `package.json` for `scripts` and `devDependencies`
    ```json
    "scripts": {
        "build": "webpack --mode production",
        "start": "webpack-dev-server --open --mode development"
    },
    "devDependencies": {
        "html-webpack-plugin": "^5.3.2",
        "webpack": "^5.54.0",
        "webpack-cli": "^4.8.0",
        "webpack-dev-server": "^4.2.1"
    }
    ```

### Install TypeScript and create configuration for ts-loder
- Install `TypeScript` command

    `npm i -D typescript ts-loader`

- Create `tsconfig.json` file and add following
    ```json
    {
        "compilerOptions": {
            "target": "ES6",
            "module": "ES6",
            "strict": true
        }
    }
    ```
- Add configurations into the `webpack.config.js` for `ts-loader` configurations
  ```json
   entry: "./src/index.ts",
    resolve: {
        extensions: ['.js', '.ts', '.tsx']
    },
    module:{
        rules: [{
            test: /\.tsx?$/,
            loader: 'ts-loader',
            exclude: /node_modules/,
        }]
    },
  ```
### What is Babel?
> Babel is a JavaScript compiler that includes the ability to compile JSX into regular JavaScript.
#### Install Babel and babel-presets
- Command to install babel `npm i -D @babel/core @babel/preset-env @babel/preset-typescript`
- Create `.babelrc.json` file and put following configurations
  ```
  { 
    "presets": ["@babel/preset-env", "@babel/preset-typescript"]
  }
  ```
- Command to install `babel-loder` `npm i -D babel-loader`
- In `webpack.config.js` to replace the `ts-loader` with `babel-loader`
  ```json
   entry: "./src/index.ts",
    resolve: {
        extensions: ['.js', '.ts', '.tsx']
    },
    module:{
        rules: [{
            test: /\.tsx?$/,
            loader: 'babel-loader',
            exclude: /node_modules/,
        }]
    },
  ```
  - Command to install class properties convertor proposal using following command.
    `npm i -D @babel/plugin-proposal-class-properties`
  - Need to add `plugin` configuration in the `.babelrc.json` file.
    ```node
    { 
    "presets": ["@babel/preset-env", "@babel/preset-typescript"],
    "plugins": ["@babel/plugin/-proposal-class-properties"]
    }
   ```









