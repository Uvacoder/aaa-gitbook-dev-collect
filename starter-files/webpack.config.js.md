# webpack.config.js

```javascript
const path = require("path");
const UglifyJSPlugin = require("uglifyjs-webpack-plugin");
const MiniCssExtractPlugin = require("mini-css-extract-plugin");
const OptimizeCSSAssetsPlugin = require("optimize-css-assets-webpack-plugin");
const BrowserSyncPlugin = require("browser-sync-webpack-plugin");

module.exports = {
  entry: ["./assets/js/main.js", "./assets/css/sass/styles.scss"],
  output: {
    filename: "./assets/build/main.min.js",
    path: path.resolve(__dirname)
  },
  plugins: [
    new UglifyJSPlugin(),
    new MiniCssExtractPlugin({
      //output for the css minification
      filename: "./assets/build/main.min.css"
    }),
    new BrowserSyncPlugin(
      {
        // set proxy to your MAMP local dev env
        proxy: "http://website.local:8888",
        files: [
          {
            // Tell browserSync which files to watch for
            match: [
              "**/*.php",
              "**/template-parts/**/*.php",
              "**/assets/build/*.js",
              "**/assets/build/*.css"
            ],
            fn: function(event, file) {
              // callback the watches for an on change event and triggers browsersync to reload site with updates
              if (event === "change") {
                const bs = require("browser-sync").get("bs-webpack-plugin");
                bs.reload();
              }
            }
          }
        ]
      },
      {
        // prevents BrowserSyn from reloading page and allows webpack dev server to handle it
        reload: true
      }
    )
  ],
  watchOptions: {
    aggregateTimeout: 500,
    poll: 1000,
    //devtool: "inline-cheap-module-source-map"
  },
  optimization: {
    minimizer: [
      // enable the js minification plugin
      new UglifyJSPlugin({
        cache: true,
        parallel: true
      }),
      // enable the css minification plugin
      new OptimizeCSSAssetsPlugin({})
    ]
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /(node_modules|bower_components)/,
        use: {
          loader: "babel-loader",
          options: {
            presets: ["babel-preset-env", "babel-polyfill"]
          }
        }
      },
      {
        test: /\.(sass|scss)$/,
        use: [MiniCssExtractPlugin.loader, "css-loader", "sass-loader"]
      }
    ]
  }
};

```

