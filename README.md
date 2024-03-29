<h1 align="center">Welcome to webpack-guide 👋</h1>

> 如果这个项目对您有帮助，请给一个️star！

<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://shudong.wang" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="#" target="_blank">
    <img alt="License: ISC" src="https://img.shields.io/badge/License-ISC-yellow.svg" />
  </a>
  <a href="https://twitter.com/wsd312" target="_blank">
    <img alt="Twitter: wsd312" src="https://img.shields.io/twitter/follow/wsd312.svg?style=social" />
  </a>
</p>

> webpack url loader

### 🏠 [Homepage](https://shudong.wang)

### ✨ [Demo](https://shudong.wang)

## Install

```sh
yarn
```

## Author

👤 **starkwang**

* Website: https://shudong.wang
* Twitter: [@wsd312](https://twitter.com/wsd312)
* Github: [@wsdo](https://github.com/wsdo)

## Show your support

Give a ⭐️ if this project helped you!

---
* source: https://raw.githubusercontent.com/webpack-contrib/url-loader/master/README.md
* edit: https://github.com/webpack-contrib/url-loader/edit/master/README.md
* repo: https://github.com/webpack-contrib/url-loader
---


[![npm][npm]][npm-url]
[![node][node]][node-url]
[![deps][deps]][deps-url]
[![tests][tests]][tests-url]
[![chat][chat]][chat-url]
[![size][size]][size-url]



A loader for webpack which transforms files into base64 URIs.

## Getting Started

To begin, you'll need to install `url-loader`:

```console
$ npm install url-loader --save-dev
```

`url-loader` works like
[`file-loader`](/loaders/file-loader/), but can return
a DataURL if the file is smaller than a byte limit.


```js
import img from './image.png'
```

```js
// webpack.config.js
module.exports = {
  module: {
    rules: [
      {
        test: /\.(png|jpg|gif)$/i,
        use: [
          {
            loader: 'url-loader',
            options: {
              limit: 8192
            }
          }
        ]
      }
    ]
  }
}
```

And run `webpack` via your preferred method.

## Options

### `fallback`

Type: `String`
Default: `'file-loader'`

Specifies an alternative loader to use when a target file's size exceeds the
limit set in the `limit` option.

```js
// webpack.config.js
{
  loader: 'url-loader',
  options: {
    fallback: 'responsive-loader'
  }
}
```

The fallback loader will receive the same configuration options as url-loader.

For example, to set the quality option of a responsive-loader above use:

```js
{
  loader: 'url-loader',
  options: {
    fallback: 'responsive-loader',
    quality: 85
  }
}
```

### `limit`

Type: `Number`
Default: `undefined`

A `Number` specifying the maximum size of a file in bytes. If the file is
greater than the limit,
[`file-loader`](/loaders/file-loader/) is used by
default and all query parameters are passed to it. Using an alternative to
`file-loader` is enabled via the `fallback` option.

The limit can be specified via loader options and defaults to no limit.

```js
// webpack.config.js
{
  loader: 'url-loader',
  options: {
    limit: 8192
  }
}
```

### `mimetype`

Type: `String`
Default: `(file extension)`

Sets the MIME type for the file to be transformed. If unspecified the file
extensions will be used to lookup the MIME type.

```js
// webpack.config.js
{
  loader: 'url-loader',
  options: {
    mimetype: 'image/png'
  }
}
```

## Contributing

Please take a moment to read our contributing guidelines if you haven't yet done so.

[CONTRIBUTING](https://raw.githubusercontent.com/webpack-contrib/url-loader/master/.github/CONTRIBUTING.md)

## License

[MIT](https://raw.githubusercontent.com/webpack-contrib/url-loader/master/LICENSE)

[npm]: https://img.shields.io/npm/v/url-loader.svg
[npm-url]: https://npmjs.com/package/url-loader

[node]: https://img.shields.io/node/v/url-loader.svg
[node-url]: https://nodejs.org

[deps]: https://david-dm.org/webpack-contrib/url-loader.svg
[deps-url]: https://david-dm.org/webpack-contrib/url-loader

[tests]: 	https://img.shields.io/circleci/project/github/webpack-contrib/url-loader.svg
[tests-url]: https://circleci.com/gh/webpack-contrib/url-loader

[cover]: https://codecov.io/gh/webpack-contrib/url-loader/branch/master/graph/badge.svg
[cover-url]: https://codecov.io/gh/webpack-contrib/url-loader

[chat]: https://img.shields.io/badge/gitter-webpack%2Fwebpack-brightgreen.svg
[chat-url]: https://gitter.im/webpack/webpack

[size]: https://packagephobia.now.sh/badge?p=url-loader
[size-url]: https://packagephobia.now.sh/result?p=url-loader
