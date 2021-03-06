# node-chaching [![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][daviddm-image]][daviddm-url] [![Coverage percentage][coveralls-image]][coveralls-url]

> Reusable single-purpose caching class for node

## Installation

```sh
$ npm install --save node-chaching
```

## Usage

```js
const Cache = require('node-chaching');

// create a new Cache instance with a 10 sec TTL and a get Promise
// that provides values when a cache miss occurs
const myCache = new Cache(10, (key) => Promise.resolve({key, value: 10}));

const args = {
  key: 'key-1',
  options: {
    opt1: [],
    opt2: 'opt2'
  }
};
// retrieve value for given key
const value = await myCache.get(args);

// delete key and its value from cache
myCache.del('key-1');
```

## License

Apache-2.0 © [Trey Briggs](http://treybriggs.com/)

[npm-image]: https://badge.fury.io/js/node-chaching.svg
[npm-url]: https://npmjs.org/package/node-chaching
[travis-image]: https://travis-ci.com/tebriggs86/node-chaching.svg?branch=master
[travis-url]: https://travis-ci.com/tebriggs86/node-chaching
[daviddm-image]: https://david-dm.org/tebriggs86/node-chaching.svg?theme=shields.io
[daviddm-url]: https://david-dm.org/tebriggs86/node-chaching
[coveralls-image]: https://coveralls.io/repos/tebriggs86/node-chaching/badge.svg
[coveralls-url]: https://coveralls.io/r/tebriggs86/node-chaching
