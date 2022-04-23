# curso-webpack-react

clase 22

npm install react react-dom -S

npm init -y

se crearon los archivos
public/index.html
src/index.js
src/componentes/App.jsx


Clase 23

npm install -D @babel/core @babel/preset-env @babel/preset-react babel-loader

npm install -D webpack webpack-cli webpack-dev-server


creacion del archivo
.babelrc

clase 24

npm install html-loader html-webpack-plugin -D

se agrego en el package.json
    "start": "webpack serve --mode production",


Debido a un error se agrego en el module.exports de webpack.config

            performance: {
                    maxEntrypointSize: 512000,
                    maxAssetSize: 512000
                },


siempre dentro de webpack

        devServer: {
                static: path.resolve(__dirname, 'dist'),
                compress: true,
                port: 3006
            }

dentro de .babelrc

        {
            "presets": [
                "@babel/preset-env",
                "@babel/preset-react"
            ]
        }

se corrigieron errores en los archivos de App.jx, e index.html

clase 25 webpack y sass css


npm install mini-css-extract-plugin css-loader style-loader sass sass-loader -D



dentro de webpack.config

const MiniCssExtractPlugin = require('mini-css-extract-plugin');

rules

            {
                test: /\.s[ac]ss$/,
                use: [
                    'style-loader',
                    'css-loader',
                    'sass-loader'
                ]
            }

dentro de plugin

            new MiniCssExtractPlugin({
            filename: '[name].css'

se creo el archivo
src/styles/global.scss

            $base-color: #c6538c;
            $color: rgba(black, 0.88);

            body {
                background-color: $base-color;
                color: $color;
            }

se agrego en index.js
import './styles/global.scss';



clase 26

npm install css-minimizer-webpack-plugin terser-webpack-plugin clean-webpack-plugin -D

se creo el archivo webpack.config.dev.js

se quito el recurso de webserve y se agrego el de optimizacion en webpack.config.js

se realiza configuracion en el package.json para el start y build