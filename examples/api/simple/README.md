# API: Simple Server

While it's recommended to run `webpack-dev-server` via the CLI, you may also
choose to start a server via the API. This example starts a simple server setup.

```console
node server.js
```

## Code for a simple webpack-dev-server

```javascript
const Webpack = require('webpack');
const WebpackDevServer = require('webpack-dev-server');
const webpackConfig = require('./webpack.config');

const compiler = Webpack(webpackConfig);
const devServerOptions = Object.assign({}, webpackConfig.devServer, {
  stats: {
    colors: true
  }
});
const server = new WebpackDevServer(compiler, devServerOptions);

server.listen(8080, '127.0.0.1', () => {
  console.log('Starting server on http://localhost:8080');
});
```

## What should happen

1. Open `http://localhost:8080/` in your preferred browser.
2. You should see the text on the page itself change to read `Success!`.
3. In `app.js`, uncomment the code that results in an error and save. This error
should be visible in the console/terminal and in browser devtools.
4. In `app.js`, uncomment the code that results in a warning. This warning should
be visible in the console/terminal and in browser devtools.
