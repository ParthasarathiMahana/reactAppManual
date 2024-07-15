### Steps
----------

1. Install React and ReactDOM:
    - npm install react react-dom
2. Set Up Babel for JSX and ES6 Support:
    - npm install -D @babel/core @babel/preset-env @babel/preset-react babel-loader
    - babel.config.js ---> module.exports = {
                                presets: ['@babel/preset-env', '@babel/preset-react'],
                            };
3. Set Up Webpack for Bundling:
    - npm install -D webpack webpack-cli webpack-dev-server html-webpack-plugin style-loader css-loader
    - webpack.config.js ---> const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js',
  },
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        use: ['babel-loader'],
      },
      {
        test: /\.css$/,
        use: ['style-loader', 'css-loader'],
      },
    ],
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './public/index.html',
    }),
  ],
  devServer: {
    static: {
        directory: path.join(__dirname, 'dist'),
    },
    compress: true,
    port: 3000,
  },
};
4. index.html in public folder:
    - HTML Code
5. Create Your React App:
    - mkdir src
      touch src/index.js
6. Create a react component APP.js
7. Mount app in 'src/index.js'
8. Add script to 'package.json'
    - "start": "webpack serve --mode development --open",
    - "build": "webpack --mode production"
