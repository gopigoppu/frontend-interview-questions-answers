# Javascript Question Answers

**Note : Pull requests for suggestions and corrections are welcome!**

### 1. What is closure in javascript? Give an example.

A closure is the combination of a function and the lexical environment within which that function was declared. In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

To use a closure, simply define a function inside another function and expose it. To expose a function, return it or pass it to another function.

The inner function will have access to the variables in the outer function scope, even after the outer function has returned.

In this example, each call to the main function creates a separate closure

```javascript
function newClosure(someNum, someRef) {
    // Local variables that end up within closure
    var num = someNum;
    var anArray = [1,2,3];
    var ref = someRef;
    return function(x) {
        num += x;
        anArray.push(num);
        console.log('num: ' + num +
            '; anArray: ' + anArray.toString() +
            '; ref.someVar: ' + ref.someVar + ';');
      }
}
obj = {someVar: 4};
fn1 = newClosure(4, obj);
fn2 = newClosure(5, obj);
fn1(1); // num: 5; anArray: 1,2,3,5; ref.someVar: 4;
fn2(1); // num: 6; anArray: 1,2,3,6; ref.someVar: 4;
obj.someVar++;
fn1(2); // num: 7; anArray: 1,2,3,5,7; ref.someVar: 5;
fn2(2); // num: 8; anArray: 1,2,3,6,8; ref.someVar: 5;
```

References : 
* [https://stackoverflow.com/a/111111](https://stackoverflow.com/a/111111)
* [https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)





### 2. Explain OOPS concepts in javascript?

Object-oriented programming (OOP) is a programming paradigm that uses abstraction to create models based on the real world. OOP uses several techniques from previously established paradigms, including modularity, polymorphism, and encapsulation. 

#### Terminology
* Namespace - 
A container which lets developers bundle all functionality under a unique, application-specific name.
* Class - 
Defines the object's characteristics. A class is a template definition of an object's properties and methods.
* Object - 
An instance of a class.
* Property - 
An object characteristic, such as color.
* Method - 
An object capability, such as walk. It is a subroutine or function associated with a class.
* Constructor - 
A method called at the moment an object is instantiated. It usually has the same name as the class containing it.
* Inheritance - 
A class can inherit characteristics from another class.
* Encapsulation - 
A method of bundling the data and methods that use the data.
* Abstraction - 
The conjunction of an object's complex inheritance, methods, and properties must adequately reflect a reality model.
* Polymorphism - 
Poly means "many" and morphism means "forms". Different classes might define the same method or property.

#### Prototype-based programming
Prototype-based programming is an OOP model that doesn't use classes, but rather it first accomplishes the behavior of any class and then reuses it (equivalent to inheritance in class-based languages) by decorating (or expanding upon) existing prototype objects. (Also called classless, prototype-oriented, or instance-based programming.)

#### The class
JavaScript is a prototype-based language and contains no class statement, such as is found in C++ or Java. This is sometimes confusing for programmers accustomed to languages with a class statement. Instead, JavaScript uses functions as constructors for classes. Defining a class is as easy as defining a function. In the example below we define a new class called Person with an empty constructor.
```javascript
var Person = function () {};
```
#### The object (class instance)
To create a new instance of an object obj we use the statement new obj, assigning the result (which is of type obj) to a variable to access it later.
```javascript
var person1 = new Person();
```

#### The constructor
The constructor is called at the moment of instantiation (the moment when the object instance is created). The constructor is a method of the class. In JavaScript the function serves as the constructor of the object, therefore there is no need to explicitly define a constructor method. Every action declared in the class gets executed at the time of instantiation.

Check full article about OOPS concepts here : [https://developer.mozilla.org/ms/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript](https://developer.mozilla.org/ms/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript) 

* [http://www.javascriptkit.com/javatutors/oopjs.shtml](http://www.javascriptkit.com/javatutors/oopjs.shtml)
* [https://stackoverflow.com/questions/8453887/why-is-it-necessary-to-set-the-prototype-constructor](https://stackoverflow.com/questions/8453887/why-is-it-necessary-to-set-the-prototype-constructor)




### 3. Explain about Array Prototype?

The Array.prototype property represents the prototype for the Array constructor and allows you to add new properties and methods to all Array objects.

Array instances inherit from Array.prototype. As with all constructors, you can change the constructor's prototype object to make changes to all Array instances.


```javascript
if (!Array.prototype.first) {
  Array.prototype.first = function() {
    return this[0];
  }
}

Array.isArray(Array.prototype); // true
```
Array.prototype itself is an Array.

Note: Array.prototype does not refer to a single array, but to the Array() object itself.

Note: Prototype is a global object constructor which is available for all JavaScript objects.

References : 
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype)


### 4. What is an Object in JS?

An instance of class. An object is a collection of properties, and a property is an association between a name (or key) and a value. A property's value can be a function, in which case the property is known as a method.

```javascript
var myCar = new Object();
myCar.make = 'Ford';
```

References : 
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)


### 5. What is a defered object in JS?

The Deferred object, introduced in jQuery 1.5, is a chainable utility object created by calling the jQuery.Deferred() method. It can register multiple callbacks into callback queues, invoke callback queues, and relay the success or failure state of any synchronous or asynchronous function.

The Deferred object is chainable, similar to the way a jQuery object is chainable, but it has its own methods. After creating a Deferred object, you can use any of the methods below by either chaining directly from the object creation or saving the object in a variable and invoking one or more methods on that variable.

According to our requirements and the list of methods provided, it’s clear than we can use either the done() or the then() method to manage the successful cases. Since many of you might already be accustomed to the JavaScript’s Promise object, in this example I’ll employ the then() method. One important difference between these two methods is that then() has the ability to forward the value received as a parameter to other then(), done(), fail(), or progress() calls defined after it.

```javascript
function timeout(milliseconds) {
  // Create a new Deferred object
  var deferred = $.Deferred();

  // Resolve the Deferred after the amount of time specified by milliseconds
  setTimeout(deferred.resolve, milliseconds);

  // Return the Deferred's Promise object
  return deferred.promise();
}

timeout(1000).then(function() {
  console.log('I waited for 1 second!');
});
```

* `deferred.always()`
Add handlers to be called when the Deferred object is either resolved or rejected.

* `deferred.catch()`
Add handlers to be called when the Deferred object is rejected.

* `deferred.done()`
Add handlers to be called when the Deferred object is resolved.

* `deferred.fail()`
Add handlers to be called when the Deferred object is rejected.

* `deferred.notify()`
Call the progressCallbacks on a Deferred object with the given args.

* `deferred.notifyWith()`
Call the progressCallbacks on a Deferred object with the given context and args.

* `deferred.pipe()`
Utility method to filter and/or chain Deferreds.

* `deferred.progress()`
Add handlers to be called when the Deferred object generates progress notifications.

* `deferred.promise()`
Return a Deferred’s Promise object.

* `deferred.reject()`
Reject a Deferred object and call any failCallbacks with the given args.

* `deferred.rejectWith()`
Reject a Deferred object and call any failCallbacks with the given context and args.

* `deferred.resolve()`
Resolve a Deferred object and call any doneCallbacks with the given args.

* `deferred.resolveWith()`
Resolve a Deferred object and call any doneCallbacks with the given context and args.

* `deferred.state()`
Determine the current state of a Deferred object.

* `deferred.then()`
Add handlers to be called when the Deferred object is resolved, rejected, or still in progress.

* `jQuery.Deferred()`
A factory function that returns a chainable utility object with methods to register multiple callbacks into callback queues, invoke callback queues, and relay the success or failure state of any synchronous or asynchronous function.

* `jQuery.when()`
Provides a way to execute callback functions based on zero or more Thenable objects, usually Deferred objects that represent asynchronous events.

* `.promise()`
Return a Promise object to observe when all actions of a certain type bound to the collection, queued or not, have finished.

References :
* [https://api.jquery.com/category/deferred-object/](https://api.jquery.com/category/deferred-object/)
* [https://www.sitepoint.com/introduction-jquery-deferred-objects/](https://www.sitepoint.com/introduction-jquery-deferred-objects/)
* [https://www.sitepoint.com/overview-javascript-promises/](https://www.sitepoint.com/overview-javascript-promises/)


### 6. How to make a http external api call and display data?

We can make api call in lot of ways. Here i'm gonna give example using jQuery's $.ajax function.

**Using $.ajax ==>** 

```javascript

$.ajax({
    url: 'users.php',
    dataType: 'json',
    type: 'post',
    contentType: 'application/json',
    data: JSON.stringify( { "first-name": $('#first-name').val(), "last-name": $('#last-name').val() } ),
    processData: false,
    success: function( data, textStatus, jQxhr ){
        $('#response pre').html( JSON.stringify( data ) );
    },
    error: function( jqXhr, textStatus, errorThrown ){
        console.log( errorThrown );
    }
});


```


### 7. In JS, Is multiplethread possible or not?

 JavaScript is single-threaded in the same context, but browser Web APIs are not. Also we have possibility of simulating parallelism by using setTimeout function or, with some limitations, by the use of the real parallelism provided by WebWorkers.

Your JavaScript code is single-threaded in the same context, but all other stuff which is done by browser (AJAX request, rendering, event triggers etc.) is not. Even Google Chrome will not let a single web page’s JavaScript run concurrently because this would cause massive concurrency issues in existing web pages. All Chrome does is separate multiple components (different tabs, plug-ins, etcetera) into separate processes, but I can’t imagine a single page having more than one JavaScript thread.

**Note :** Dedicated Web Workers provide a simple means for web content to run scripts in background threads. Once created, a worker can send messages to the spawning task by posting messages to an event handler specified by the creator.

References :
* [https://stackoverflow.com/a/39961](https://stackoverflow.com/a/39961)
* [https://coderwall.com/p/x7k_sa/did-you-know-you-can-multithread-in-javascript](https://coderwall.com/p/x7k_sa/did-you-know-you-can-multithread-in-javascript)
* [https://www.red-gate.com/simple-talk/dotnet/asp-net/javascript-single-threaded/](https://www.red-gate.com/simple-talk/dotnet/asp-net/javascript-single-threaded/)


### 8. Explain timeout concept in JS and why do we need it?

The setTimeout() method calls a function or evaluates an expression after a specified number of milliseconds.

Because by calling long-executing code via setTimeout, you actually create 2 events: setTimeout execution itself, and (due to 0 timeout), separate queue entry for the code being executed.

```javascript
var myVar;

function myFunction() {
    myVar = setTimeout(function(){ alert("Hello") }, 3000);
}

function myStopFunction() {
    clearTimeout(myVar);
}
```


References :
* [https://www.w3schools.com/jsref/met_win_settimeout.asp](https://www.w3schools.com/jsref/met_win_settimeout.asp)
* [https://stackoverflow.com/questions/779379/why-is-settimeoutfn-0-sometimes-useful](https://stackoverflow.com/questions/779379/why-is-settimeoutfn-0-sometimes-useful)


### 9. What is Promises?  How do you achieve? What are the pros and cons of using Promises instead of callbacks?

A Promise object represents a value that may not be available yet, but will be resolved at some point in the future. It allows you to write asynchronous code in a more synchronous fashion.

It will be in one of 3 possible states:

* Fulfilled: onFulfilled() will be called (e.g., resolve() was called)
* Rejected: onRejected() will be called (e.g., reject() was called)
* Pending: not yet fulfilled or rejected

A promise is settled if it’s not pending (it has been resolved or rejected). Sometimes people use resolved and settled to mean the same thing: not pending. Once settled, a promise can not be resettled. Calling resolve() or reject() again will have no effect. The immutability of a settled promise is an important feature.

We start by instantiating a new Promise object and passing it a callback function. The callback takes two arguments, resolve and reject, which are both functions. All your asynchronous code goes inside that callback. If everything is successful, the promise is fulfilled by calling resolve(). In case of an error, reject() is called with an Error object. This indicates that the promise is rejected.

 Example:

```javascript
function getPromise(url){
  return new Promise((resolve, reject) => {
  const request = new XMLHttpRequest();

  request.open("GET", url);
  request.onload = () => {
    if (request.status === 200) {
      resolve(request.response); 
    } else {
      reject(Error(request.statusText));
    }
  };

  request.onerror = () => {
    reject(Error("Error fetching data."));
  };

  request.send();
});
}
const promise = getPromise("https://api.github.com/users/gopigoppu");

console.log("Asynchronous request made.");

promise.then( result => {
  
  console.log("Got data! Promise fulfilled.");
  console.log(JSON.parse(result).followers_url);
  //we have our result here
              
  return getPromise(JSON.parse(result).followers_url); //return a promise here again
}).then(
  data => {
    
    console.log("Got data! Promise fulfilled.", data);
   
    document.body.textContent = data;
}).catch(function(err) {
  console.log("It failed!", err);
});
```

References :
* [https://www.sitepoint.com/overview-javascript-promises/](https://www.sitepoint.com/overview-javascript-promises/)
* [https://developers.google.com/web/fundamentals/primers/promises](https://developers.google.com/web/fundamentals/primers/promises)


### 10. Node.js is single threaded or multi threaded?

All Node JS applications uses “Single Threaded Event Loop Model” architecture to handle multiple concurrent clients. So Yes NodeJS is single threaded, but this is a half truth, actually it is event-driven and single-threaded with background workers. The main event loop is single-threaded but most of the I/O works run on separate threads, because the I/O APIs in Node.js are asynchronous/non-blocking by design, in order to accommodate the event loop.

Node.js was created explicitly as an experiment in async processing. The theory was that doing async processing on a single thread could provide more performance and scalability under typical web loads than the typical thread-based implementation.

References:
* [https://codeburst.io/how-node-js-single-thread-mechanism-work-understanding-event-loop-in-nodejs-230f7440b0ea](https://codeburst.io/how-node-js-single-thread-mechanism-work-understanding-event-loop-in-nodejs-230f7440b0ea)
* [https://stackoverflow.com/questions/17959663/why-is-node-js-single-threaded](https://stackoverflow.com/questions/17959663/why-is-node-js-single-threaded)
* [https://www.journaldev.com/7462/node-js-architecture-single-threaded-event-loop](https://www.journaldev.com/7462/node-js-architecture-single-threaded-event-loop)



### 11. What is event looping?

