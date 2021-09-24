# ReacTypeScript-reloaded
This repository is set for revision of ReacTypeScript for including GraphQL knowledge.


### What is webpack?
> Webpack is module bundle for javascript.
### Webpack configuration
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
#### package.json | scripts | devDependencies
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