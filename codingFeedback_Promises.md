# Promises

* Using Promises
  * Every then method call and every catch method call returns a new promise
```js
var p = buttonPromise(1);

p
.then(function success(data) {
  console.log(data);
})
.catch(function failure(data) {
  console.log(data);
});
```
