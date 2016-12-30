
# slugify

[![npm-version]][npm] [![travis-ci]][travis] [![coveralls-status]][coveralls]

```js
var slugify = require('slugify')

slugify('some string') // some-string

// if you prefer something other than '-' as separator
slugify('some string', '_')  // some_string
```

- Vanilla ES5 JavaScript
- No dependencies
- Coerces foreign symbols to their english equivalent (check out the `charMap` in [index.js][index] for more details)
- Works in the browser (window.slugify) and AMD/CommonJS-flavored module loaders

Out of the box `slugify` comes with support for a handfull of Unicode symbols. For example the `☢` (radioactive) symbol is not defined in the `charMap` in [index.js][index] and therefore it will be stripped by default:

```js
slugify('unicode ♥ is ☢') // unicode-love-is
```

However you can extend the supported symbols, or override the existing ones with your own:

```js
slugify.extend({'☢': 'radioactive'})
slugify('unicode ♥ is ☢') // unicode-love-is-radioactive
```

> This module was originally a vanilla javascript port of [node-slug][node-slug].<br>
> Note that the original [slug][slug] module has been ported to vanilla javascript too.<br>
> One major difference between the two modules is that `slugify` does not depend on the external [unicode][unicode] module.


  [npm-version]: http://img.shields.io/npm/v/slugify.svg?style=flat-square (NPM Package Version)
  [travis-ci]: https://img.shields.io/travis/simov/slugify/master.svg?style=flat-square (Build Status - Travis CI)
  [coveralls-status]: https://img.shields.io/coveralls/simov/slugify.svg?style=flat-square (Test Coverage - Coveralls)

  [npm]: https://www.npmjs.com/package/slugify
  [travis]: https://travis-ci.org/simov/slugify
  [coveralls]: https://coveralls.io/r/simov/slugify?branch=master

  [node-slug]: https://github.com/dodo/node-slug
  [slug]: https://www.npmjs.com/package/slug
  [unicode]: https://www.npmjs.com/package/unicode
  [index]: https://github.com/simov/slugify/blob/master/index.js
