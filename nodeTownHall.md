# Node Sprint Solution

* Introduction to the RESTApi Diagram
  * Blah blah blah
* How to treat routes
  * like user input
  * scrub all routes
  * scrub all query parameters
* Go through solution
  * abstracted out actions

  ```js
  exports.collectData = function(request,callback) {
    var data = "";
    request.on('data', function(chunk){
      data += chunk;
    });
    request.on('end' function(){
      callback(JSON.parse(data));
    });
  };
  ```
* 
