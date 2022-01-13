# Shopify OS 2.0 Boilerplate


## Note
We have 2 versions of our Shopify theme building system.
- Version 1: Build Theme from scratch ( Shopify OS 2.0 - this git )
- Version 2: Fix the existing Theme ( [here](https://github.com/kmacoders/PusherBase-ShopifyThemeFromExistTheme) )

## How to add Vue 3 to this boilerplace ?
1. Install package ( Please pay attention to the version number )
```
  npm install @vue/compiler-sfc vue@next vue-loader vue-style-loader
```

Note: Current package version number
```json
"devDependencies": {
    "@vue/compiler-sfc": "^3.2.26",
    "vue": "^3.2.26",
    "vue-loader": "^16.3.0",
    "vue-style-loader": "^4.1.3",
  },
```

2. Change webpack config
Go to `webpack.config.common.js' and edit 
```
const { VueLoaderPlugin } = require('vue-loader')
...
...
plugins: [
    new VueLoaderPlugin(),
    ...
    ...
]
...
...
rules: [
      {
        test: /\.vue$/,
        loader: 'vue-loader',
        options: {
          loaders: {
            'scss': 'vue-style-loader!css-loader!sass-loader',
            'sass': 'vue-style-loader!css-loader!sass-loader?indentedSyntax',
          },
        },
      },
...
...
resolve: {
    alias: {
      ...
      vue: 'vue/dist/vue.esm-bundler.js',
    },
    extensions: ['.vue', '.js', '.json'],
 },
...
..
```
