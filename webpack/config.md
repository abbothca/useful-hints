# Example:

```
const NODE_ENV = process.env.NODE_ENV || 'development';

const path = require('path');
const webpack = require('webpack');

const UglifyJsPlugin = require('uglifyjs-webpack-plugin'),
    CleanWebpackPlugin = require('clean-webpack-plugin');

// the path(s) that should be cleaned
let pathsToClean = [
    'public/js/'
];

module.exports = {
    entry: {
        menu: './frontend/menu.js',
        popup: './frontend/popup.js'
    },
    output: {
        path: path.resolve(__dirname, 'public/js/'),
        filename: '[name].js'
    },

    watch: NODE_ENV == 'development',
    watchOptions: {
        aggregateTimeout: 150,
        ignored: /node_modules/
    },

    devtool: NODE_ENV == 'development' ? 'source-map' : 'nosources-source-map',

    devServer: {
        stats: "minimal",
        contentBase: path.join(__dirname, './public'),
        compress: true,
        port: 8000,
        open: true
    },

    plugins: [
        new webpack.NoEmitOnErrorsPlugin(),
        new webpack.DefinePlugin({
            NODE_ENV: JSON.stringify(NODE_ENV)
        }),
        new CleanWebpackPlugin(pathsToClean)
    ],

    optimization: {
        minimizer: [
            new UglifyJsPlugin({
                cache: true,
                parallel: true,
                uglifyOptions: {
                    compress: false,
                    ecma: 6,
                    mangle: true
                },
                sourceMap: true
            })
        ],
        splitChunks: {
            cacheGroups: {
                commons: {
                    name: "vendor",
                    chunks: "all",
                    minChunks: 2,
                    minSize: 0
                }
            }
        },
        occurrenceOrder: true
    },

    module: {
        rules: [
            {
                test: /\.js$/,
                exclude: /node_modules/,
                use: {
                    loader: "babel-loader"
                }
            }
        ]
    }
};
```