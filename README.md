# Wan WNS Namehash 

[![CircleCI][circle-image]][circle-url]
[![Coverage Status][coveralls-image]][coveralls-url]
[![dependency status][dep-image]][dep-url]
[![NPM][npm-image]][npm-url]

A javascript library for generating Wanchain Name Service (WNS) namehashes per [spec](https://github.com/wanchain/EIPs/issues/137).

## Installation

`npm install wan-wns-namehash -S`

## Usage

```javascript
var namehash = require('wan-wns-namehash')
var hash = namehash.hash('foo.wan')
// '0xde9b09fd7c5f901e23a3f19fecc54828e9c848539801e86591bd9801b019f84f'

// Also supports normalizing strings to WNS compatibility:
var input = getUserInput()
var normalized = namehash.normalize(input)
```

## Security Warning

WNS Supports UTF-8 characters, and so many duplicate names are possible. For example:

- faceboоk.wan
- facebook.wan

The first one has non-ascii chars. (control+F on this page and search for facebook, only the second one will match).

namehash.normalize() doesn't automagically remap those, and so other precautions should be taken to avoid user phishing.

## Development

This module supports advanced JavaScript syntax, but exports an ES5-compatible module. To re-build the exported module after making changes, run `npm run bundle` (must have [browserify](http://browserify.org/) installed).

[circle-image]: https://circleci.com/gh/wandevs/wan-wns-namehash.svg?style=svg
[circle-url]: https://circleci.com/gh/wandevs/wan-wns-namehash
[dep-image]: https://david-dm.org/wandevs/wan-wns-namehash.svg
[dep-url]: https://david-dm.org/wandevs/wan-wns-namehash
[coveralls-image]: https://coveralls.io/repos/github/wandevs/wan-wns-namehash/badge.svg?branch=dev
[coveralls-url]: https://coveralls.io/github/wandevs/wan-wns-namehash?branch=dev
[npm-image]: http://img.shields.io/npm/v/wan-wns-namehash.svg
[npm-url]: https://www.npmjs.org/package/wan-wns-namehash
