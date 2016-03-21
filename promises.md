# Promises w/ Benji

```js
// Creating a promise

function doStuff(x) {
  var newPromise = new Promise(resolve, reject) {
    setTimeout(function resolvePromise() {
      var result = x +1;
      console.log('result inside setTimeout: ', result);
      resolve(result);
    }, 1000);
  }
}

// Resolving a promise
fn(data) {
  return Promise.resolve(result);
}

exports.isUrlInList = function(url) {
  exports.readListOrUrls(function(sites) {
    var found = _.any(sites, i) {
      return site.match(url)
    });
    Promise.resolve(found);
  });
}

exports.isUrlInList('http://www.amazon.com').then(function(found){

})

```
* A promise can only return another promise
* They're really a use case for better error and case handling.
