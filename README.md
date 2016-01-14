# err-code

[![NPM version][npm-image]][npm-url] [![Downloads][downloads-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency status][david-dm-image]][david-dm-url] [![Dev Dependency status][david-dm-dev-image]][david-dm-dev-url]

[npm-url]:https://npmjs.org/package/err-code
[downloads-image]:http://img.shields.io/npm/dm/err-code.svg
[npm-image]:http://img.shields.io/npm/v/err-code.svg
[travis-url]:https://travis-ci.org/IndigoUnited/js-err-code
[travis-image]:http://img.shields.io/travis/IndigoUnited/js-err-code.svg
[david-dm-url]:https://david-dm.org/IndigoUnited/js-err-code
[david-dm-image]:https://img.shields.io/david/IndigoUnited/js-err-code.svg
[david-dm-dev-url]:https://david-dm.org/IndigoUnited/js-err-code#info=devDependencies
[david-dm-dev-image]:https://img.shields.io/david/dev/IndigoUnited/js-err-code.svg

Create new error instances with a code and additional properties.


## Installation

`$ npm install err-code` - `NPM`   
`$ bower install err-code` - `bower`


## Why

I find myself doing this repeatedly:

```js
var err = new Error('My message');
err.code = 'ESOMECODE';
throw err;
```


## Usage

Simple usage.

```js
var errcode = require('err-code');

// fill error with message + code
throw errcode(new Error('My message'), 'ESOMECODE');
// fill error with message + code + props
throw errcode(new Error('My message'), 'ESOMECODE', { some: 'property' });
// fill error with message + props
throw errcode(new Error('My message'), { some: 'property' });


// You may also pass a string in the first argument and an error will be automatically created
// for you, but stack trace will contain err-code so it's not advisable unless you don't really care.

// create error with message + code
throw errcode('My message', 'ESOMECODE');
// create error with message + code + props
throw errcode('My message', 'ESOMECODE', { some: 'property' });
// create error with message + props
throw errcode('My message', { some: 'property' });
```


## Tests

`$ npm test`


## License

Released under the [MIT License](http://www.opensource.org/licenses/mit-license.php).
