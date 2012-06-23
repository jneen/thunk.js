# Thunk

Usage:

``` js
var thunk = require('thunk');

var factorial = thunk.makeTrampoline(function(recurse) {
  return function(cc, n) {
    if (n <= 1) return cc(1);

    return recurse(function(result) { return n * result }, n - 1);
  };
});

factorial(5) // 120, with a constant stack size.  Aww, yiss.
```
