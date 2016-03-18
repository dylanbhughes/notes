# Town Hall

* Eventing System

```js

// infant.js

var infant = {};
addEventSystem(infant);

// eventSystemMixin.js
var addEventSystem = function(target) {
  target.reactionsTo = {};
  target.on = function(e, cb) {
    this.reactionsTo[e] = this.reactionsTo[e] || [];
    this.reactionsTo[e].push(cb);
  };
  target.trigger = function(e) {
    _.each(this.reactionsTo[e], function(cb) {
      cb();
    });
  };
};

// mom.js
var mom = {
  sing: function() {};
};
infant.on('cry', mom.sing);
data.on('cry', mom.sing);

// dad.js
var dad = {
  play: function() {}
};
infant.on{'cry', dad.play};
addEventSystem(dad);

infant.on('laugh', dad.play);
```


* jQuery's event system is different from the DOM API event system, etc.
* Different systems can't listen to each other
