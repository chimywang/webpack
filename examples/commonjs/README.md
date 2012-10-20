
# example.js

``` javascript
var inc = require('./increment').increment;
var a = 1;
inc(a); // 2
```

# increment.js

``` javascript
var add = require('./math').add;
exports.increment = function(val) {
    return add(val, 1);
};
```

# math.js

``` javascript
exports.add = function() {
    var sum = 0, i = 0, args = arguments, l = args.length;
    while (i < l) {
        sum += args[i++];
    }
    return sum;
};
```

# js/output.js

``` javascript
/******/(function(modules) {
/******/	var installedModules = {};
/******/	function require(moduleId) {
/******/		if(typeof moduleId !== "number") throw new Error("Cannot find module '"+moduleId+"'");
/******/		if(installedModules[moduleId])
/******/			return installedModules[moduleId].exports;
/******/		var module = installedModules[moduleId] = {
/******/			exports: {},
/******/			id: moduleId,
/******/			loaded: false
/******/		};
/******/		modules[moduleId](module, module.exports, require);
/******/		module.loaded = true;
/******/		return module.exports;
/******/	}
/******/	require.e = function(chunkId, callback) {
/******/		callback(require);
/******/	};
/******/	require.modules = modules;
/******/	require.cache = installedModules;
/******/	return require(0);
/******/})
/******/({c:"",
/******/0: function(module, exports, require) {

/*** .\example.js ***/

var inc = require(/* ./increment */1).increment;
var a = 1;
inc(a); // 2

/******/},
/******/
/******/1: function(module, exports, require) {

/*** .\increment.js ***/

var add = require(/* ./math */2).add;
exports.increment = function(val) {
    return add(val, 1);
};

/******/},
/******/
/******/2: function(module, exports, require) {

/*** .\math.js ***/

exports.add = function() {
    var sum = 0, i = 0, args = arguments, l = args.length;
    while (i < l) {
        sum += args[i++];
    }
    return sum;
};

/******/},
/******/
/******/})
```

# Info

## Uncompressed

```
Hash: b1075afe2e2b2fd4519bc29c86dc97b9
Compile Time: 23ms
Chunks: 1
Modules: 3
Modules including duplicates: 3
Modules first chunk: 3
main   output.js:     1455 chars/bytes 

 <id>    <size>  <filename>
       <reason> from <filename>
output.js
    0        74  .\example.js
       main
    1       103  .\increment.js
       require (1x) from .\example.js
    2       162  .\math.js
       require (1x) from .\increment.js
```

## Minimized (uglify-js, no zip)

```
Hash: e7fbffd3f8f8581e96fa46569eda7c02
Compile Time: 92ms
Chunks: 1
Modules: 3
Modules including duplicates: 3
Modules first chunk: 3
main   output.js:      510 chars/bytes 

 <id>    <size>  <filename>
       <reason> from <filename>
output.js
    0        39  .\example.js
       main
    1        69  .\increment.js
       require (1x) from .\example.js
    2        87  .\math.js
       require (1x) from .\increment.js
```