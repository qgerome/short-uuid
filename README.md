# short-uuid

[![npm](https://img.shields.io/npm/v/short-uuid.svg)](https://www.npmjs.com/package/short-uuid) 
[![Build Status](https://travis-ci.org/oculus42/short-uuid.svg?branch=master)](https://travis-ci.org/oculus42/short-uuid) 
[![Code Climate](https://codeclimate.com/github/oculus42/short-uuid/badges/gpa.svg)](https://codeclimate.com/github/oculus42/short-uuid) 
[![Test Coverage](https://codeclimate.com/github/oculus42/short-uuid/badges/coverage.svg)](https://codeclimate.com/github/oculus42/short-uuid/coverage) 
[![Dependencies](https://david-dm.org/oculus42/short-uuid.svg)](https://david-dm.org/oculus42/short-uuid) 
[![Greenkeeper badge](https://badges.greenkeeper.io/oculus42/short-uuid.svg)](https://greenkeeper.io/) 

Generate and translate standard UUIDs into shorter - or just *different* - formats and back.

## v3.1.0

### Quick Start

```javascript
var short = require('short-uuid');

// Quick start with flickrBase58 format
short.generate(); // 73WakrfVbNJBaAmhQtEeDv
```

### Details

short-uuid starts with RFC4122 v4-compliant UUIDs and translates them
into other, usually shorter formats. It also provides translators
to convert back and forth from RFC complaint UUIDs to the shorter formats.

```javascript
var short = require('short-uuid');

var translator = short(); // Defaults to flickrBase58                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       
var decimalTranslator = short("0123456789"); // Provide a specific alphabet for translation
var cookieTranslator = short(short.constants.cookieBase90); // Use a constant for translation

// Generate a shortened v4 UUID
translator.new(); // mhvXdrZT4jP5T8vBxuvm75
translator.generate(); // An alias for new.

// Translate UUIDs to and from the shortened format
translator.toUUID(shortId);// a44521d0-0fb8-4ade-8002-3385545c3318
translator.fromUUID(regularUUID); // mhvXdrZT4jP5T8vBxuvm75

// Generate plain UUIDs
// - From the library without creating a translator
short.uuid(); // fd5c084c-ff7c-4651-9a52-37096242d81c
// - Each translator provides the uuid.v4() function, too
translator.uuid(); // 3023b0f5-ec55-4e75-9cd8-104700698052

// See the alphabet used by a translator
translator.alphabet;

// View the constants
short.constants.flickrBase58; // Avoids similar characters (0/O, 1/I/l, etc.)
short.constants.cookieBase90; // Safe for HTTP cookies values for smaller IDs. 
```

## Notes

short-uuid provides RFC4122 v4-compliant UUIDs,
thanks to [`uuid`](https://github.com/kelektiv/node-uuid).

It includes Browserify support for client-side use as proposed
by [voronianski](https://github.com/voronianski), with compiled,
browser-ready files in the npm package for convenience.
The library is exposed as `ShortUUID`.

TypeScript definitions are included, thanks to
[alexturek](https://github.com/alexturek).

short-uuid is under 1.2K when compressed. Using Browserify, the library and dependencies are ~3.6K.

## Recent Release Notes

3.1.0 adds `generate()` for ease of use.  
3.0.0 updates dependencies, includes a refactor for CodeClimate, and drops Node 0.x support.  
2.3.4 corrects the behavior for UUIDs with uppercase letters. Last version to build on Node 0.x.  

Please see [Revisions](revisions.md) for information on previous versions.
