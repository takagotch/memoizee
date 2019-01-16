#### memoizee
---
https://github.com/medikoo/memoizee

```
npm install memoizee

npm install underscore lodash lru-cache secondary-cache
```

```js
var memoize = require("memoizee");
var fn = function(one, two, three){
};
memoized = memoized(fn);
memoized("foo", 3, "bar");
memoized("foo", 3, "bar");

memoized = memoize(fn, { length: 2 });
memoized("foo");
memoized("foo", undefined);

memoized = memoize(fn, { length: false });
memoize("foo");
memoize("foo", undefined);
memoize("foo", 3, {});

memoized = memoize(fn, { primitive: true });
memoize("/path/one");
memoize("/path/one");

var mfn = memoize(
  function(hash){
  },
  {
    normalier: function(args){
      return JSON.stringify(args[0]);
    }
  }
);
mfn( foo: "bar" );
mfn({ foo: "bar" });

memoized = memoize(fn, { length: 2, resolvers: [String, Boolean] });
memoized(12, [1, 2, 3].length);
memoized(
  {
    toString: function(){
      return "12";
    }
  },
  {}
);

var afn = function(a, b){
  return new Promise(function(res){
    res(a + b);
  });
};
memoized = memoize(afn, { promise: true });
memoized(3, 7);
memoized(3, 7);

memoized = memoize(afn, { promise: "done: finally" });

afn = function(a, b, cb){
  setTimeout(function(){
    cb(null, a + b);
  }, 200);
};
memoized = memoized(afn, { async: true });
memoized(3, 7, function(err, res){
  memoized(3, 7, function(err, res){
  });
});
memoized(3, 7, function(err, res){
});

var Foo = function(){
  this.bar = memoize(this.bar.bind(this), { someOption: true });
};
Foo.prototype.bar = function(){
};

var d = require("d");
var memoizedMethods = require("memoizee/methods");
var Foo = function(){
};
Object.defindProperties(
  Foo.prototype,
  memoizeMethods({
    bar: d(
      function(){
      },
      { someOptoins: true }
    )
  })
);

var memoize = require("memoizee/weak");
var memoized = memoize(function(obj){
  return Object.keys(obj);
});
var obj = { foo: true, bar: false };
memoized(obj);
memoized(obj);

memoized.delete("foo", true);
memoized.clear();
memoized = memoize(fn, { maxAge: 1000 });
memoize("foo", 3);
memoize("foo", 3);
setTimeout(function(){
  memoized("foo", 3);
  memoized("foo", 3)
}, 2000);

memoized = memoize(fn, { maxAge: 1000, preFetch: true });
memoized("foo", 3);
memoized("foo", 3);
setTimeout(function(){
  memoized("foo", 3);
}, 500);
setTimeout(function(){
  memoized("foo", 3);
}, 800);
setTimeout(function(){
  memoized("foo", 3);
}, 1300);

memoized = memoize(fn, { maxAge: 1000, preFetch: 0.6 });
memoized("foo", 3);
memoized("foo", 3);
setTimeout(function(){
  memoized("foo", 3);
}, 500);
setTimeout(function(){
  memoized("foo", 3);
}, 1300);

memoized = memoize(fn, { refCounter: true });
memoized("foo", 3);

memoized = memoize(fn, { max: 2 });
memoized("foo", 3);
memoized("bar", 7);
memoized("foo", 3);
memoized("bar", 7);

memoized = memoize(fn, {
  dispose: function(value){
  }
});
var foo3 = memoized("foo", 3);
var bar7 = memoized("bar", 7);
memoized.clear("foo", 3);
memoized.clear("bar", 7);

var memProfile = require('memoizee/profile');
memoize(fn);
memoize(fn, { profileName: 'Some Function' })
memoize(fn, { profileName: 'Another Function'})
```

```
```


