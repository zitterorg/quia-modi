# @zitterorg/quia-modi <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Is this value a JS WeakSet? This module works cross-realm/iframe, and despite ES6 @@toStringTag.

## Example

```js
var isWeakSet = require('@zitterorg/quia-modi');
assert(!isWeakSet(function () {}));
assert(!isWeakSet(null));
assert(!isWeakSet(function* () { yield 42; return Infinity; });
assert(!isWeakSet(Symbol('foo')));
assert(!isWeakSet(1n));
assert(!isWeakSet(Object(1n)));

assert(!isWeakSet(new Set()));
assert(!isWeakSet(new WeakMap()));
assert(!isWeakSet(new Map()));

assert(isWeakSet(new WeakSet()));

class MyWeakSet extends WeakSet {}
assert(isWeakSet(new MyWeakSet()));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@zitterorg/quia-modi
[npm-version-svg]: https://versionbadg.es/inspect-js/@zitterorg/quia-modi.svg
[deps-svg]: https://david-dm.org/inspect-js/@zitterorg/quia-modi.svg
[deps-url]: https://david-dm.org/inspect-js/@zitterorg/quia-modi
[dev-deps-svg]: https://david-dm.org/inspect-js/@zitterorg/quia-modi/dev-status.svg
[dev-deps-url]: https://david-dm.org/inspect-js/@zitterorg/quia-modi#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@zitterorg/quia-modi.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@zitterorg/quia-modi.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@zitterorg/quia-modi.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@zitterorg/quia-modi
[codecov-image]: https://codecov.io/gh/inspect-js/@zitterorg/quia-modi/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/inspect-js/@zitterorg/quia-modi/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/inspect-js/@zitterorg/quia-modi
[actions-url]: https://github.com/zitterorg/quia-modi/actions
