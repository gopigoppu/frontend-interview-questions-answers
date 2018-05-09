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


The Event Loop is a queue of callback functions. When an async function executes, the callback function is pushed into the queue. The JavaScript engine doesn't start processing the event loop until the code after an async function has executed.

* [https://stackoverflow.com/questions/21607692/understanding-the-event-loop](https://stackoverflow.com/questions/21607692/understanding-the-event-loop)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)


### 12. What are all testing tool using in javascript?

* Unit Testing

  Unit testing is the practice of testing small pieces of code, typically individual functions, alone and isolated. If your test uses some external resource, like the network or a database, it’s not a unit test.

  Popular tools for unit testing include **Mocha, Jasmine and Tape.**

* Integration Testing

  As the name suggests, in integration testing the idea is to test how parts of the system work together – the integration of the parts. Integration tests are similar to unit tests, but there’s one big difference: while unit tests are isolated from other components, integration tests are not. For example, a unit test for database access code would not talk to a real database, but an integration test would.

  Integration tests can usually be written with the same tools as unit tests.

* Functional Testing

  Functional testing is also sometimes called E2E testing, or browser testing. They all refer to the same thing.

  Functional testing is defined as the testing of complete functionality of some application. In practice with web apps, this means using some tool to automate a browser, which is then used to click around on the pages to test the application.
  Test tools can be divided into the following functionalities. Some provide us with only one functionality, and some provide us with a combination.

  The most common tool used for functional testing is Selenium. Running Selenium is usually done with Selenium WebDriver, or Protractor. Sometimes PhantomJS and CasperJS can be used as well, especially if you don’t need to test in real browsers.


In order to get a more flexible functionality, it’s common to use a combination of tools even if one can achieve relatively the same.

* Provide a testing structure (Mocha, Jasmine, Jest, Cucumber)
* Provide assertions functions (Chai, Jasmine, Jest, Unexpected)
* Generate, display, and watch test results (Mocha, Jasmine, Jest, Karma)
* Generate and compare snapshots of component and data structures to make sure changes from previous runs are intended (Jest, Ava)
* Provide mocks, spies, and stubs (Sinon, Jasmine, enzyme, Jest, testdouble)
* Generate code coverage reports (Istanbul, Jest, Blanket)
* Provide a browser or browser-like environment with a control on their scenarios execution (Protractor, Nightwatch, Phantom, Casper)

References :
* [https://medium.com/welldone-software/an-overview-of-javascript-testing-in-2018-f68950900bc3](https://medium.com/welldone-software/an-overview-of-javascript-testing-in-2018-f68950900bc3)
* [https://codeutopia.net/blog/2015/04/11/what-are-unit-testing-integration-testing-and-functional-testing/](https://codeutopia.net/blog/2015/04/11/what-are-unit-testing-integration-testing-and-functional-testing/)


### 13. Difference between timeout and interval? Write syntax for both?

* **setTimeout(function, milliseconds)** - 
Executes a function, after waiting a specified number of milliseconds.
* **setInterval(function, milliseconds)** - 
Same as setTimeout(), but repeats the execution of the function continuously.
* **clearTimeout()** method stops the execution of the function specified in.

Note : The setTimeout() and setInterval() are both methods of the HTML DOM Window object.

```javascript
function myTimer() {
    var d = new Date();
    document.getElementById("demo").innerHTML = d.toLocaleTimeString();
}
var myVar1 = setTimeout(myTimer, milliseconds);
clearTimeout(myVar1);

var myVar2 = setInterval(myTimer, 1000);
clearInterval(myVar2);
```

References :
* [https://www.w3schools.com/js/js_timing.asp](https://www.w3schools.com/js/js_timing.asp)


### 14. What is Class in JS? How do you intiantiate?

JavaScript classes, introduced in ECMAScript 2015, are primarily syntactical sugar over JavaScript's existing prototype-based inheritance. The class syntax does not introduce a new object-oriented inheritance model to JavaScript.

Classes are in fact "special functions", and just as you can define function expressions and function declarations, the class syntax has two components: class expressions and class declarations.

The bodies of class declarations and class expressions are executed in strict mode i.e. constructor, static and prototype methods, getter and setter functions are executed in strict mode.

The constructor method is a special method for creating and initializing an object created with a class. There can only be one special method with the name "constructor" in a class. A SyntaxError will be thrown if the class contains more than one occurrence of a constructor method.

The static keyword defines a static method for a class. Static methods are called without instantiating their class and cannot be called through a class instance. Static methods are often used to create utility functions for an application.

```javascript
function Animal (name) {
  this.name = name;  
}

Animal.prototype.speak = function () {
  console.log(this.name + ' makes a noise.');
}

class Dog extends Animal {
  speak() {
    console.log(this.name + ' barks.');
  }
}

var d = new Dog('Mitzie');
d.speak(); // Mitzie barks.
```

References :
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)


### 15. What is Node.js? Explain Node.js features? Why we use Node.js specifically?

Node.js is an application runtime environment that allows you to write server-side applications in JavaScript. 

Node.js favors asynchronous APIs because it is single-threaded. This allows it to efficiently manage its own resources, but requires that long-running operations be non-blocking, and asynchronous APIs are a way to allow for control of flow with lots of non-blocking operations.

Features :
* Node.js is a JavaScript runtime built on Chrome’s V8 JavaScript engine.
* its unique I/O model, it excels at the sort of scalable and real-time situations we are increasingly demanding of our servers. 
* It’s also lightweight, efficient, and its ability to use JavaScript on both frontend and backend opens new avenues for development.
* Node.js’ package ecosystem, npm, is the largest ecosystem of open source libraries in the world.

Pros:

* If your application doesn’t have any CPU intensive computation, you can build it in Javascript top-to-bottom, even down to the database level if you use JSON storage Object DB like MongoDB. This eases development (including hiring) significantly.
* Crawlers receive a fully-rendered HTML response, which is far more SEO-friendly than, say, a Single Page Application or a websockets app run on top of Node.js.

Cons:

* Any CPU intensive computation will block Node.js responsiveness, so a threaded platform is a better approach. Alternatively, you could try scaling out the computation [*].
* Using Node.js with a relational database is still quite a pain (see below for more detail). Do yourself a favour and pick up any other environment like Rails, Django, or ASP.Net MVC if you’re trying to perform relational operations

References :
* [https://stackoverflow.com/questions/17607280/why-is-node-js-asynchronous](https://stackoverflow.com/questions/17607280/why-is-node-js-asynchronous)
* [https://www.toptal.com/nodejs/why-the-hell-would-i-use-node-js](https://www.toptal.com/nodejs/why-the-hell-would-i-use-node-js)


### 16. What is callback?

A callback function, also known as a higher-order function. A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.

A callback function is essentially a pattern (an established solution to a common problem), and therefore, the use of a callback function is also known as a callback pattern.

```javascript
function greeting(name) {
  alert('Hello ' + name);
}

function processUserInput(callback) {
  var name = prompt('Please enter your name.');
  callback(name);
}

processUserInput(greeting);
```

References :
* [https://developer.mozilla.org/en-US/docs/Glossary/Callback_function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)
* [http://javascriptissexy.com/understand-javascript-callback-functions-and-use-them/](http://javascriptissexy.com/understand-javascript-callback-functions-and-use-them/)


### 17. What is callback hell?

Callback hell is any code where the use of function callbacks in async code becomes obscure or difficult to follow. Generally, when there is more than one level of indirection, code using callbacks can become harder to follow, harder to refactor, and harder to test. A code smell is multiple levels of indentation due to passing multiple layers of function literals.

If you have lots of behavioural dependencies in your code like this, it can get troublesome fast. Especially if it branches...

```javascript
a({
    parameter : someParameter,
    callback : function(status) {
        if (status == states.SUCCESS) {
          b(function(status) {
              if (status == states.SUCCESS) {
                 c(function(status){
                     if (status == states.SUCCESS) {
                         // Not an exaggeration. I have seen
                         // code that looks like this regularly.
                     }
                 });
              }
          });
        } elseif (status == states.PENDING {
          ...
        }
    }
});
```

You can avoid callback hell problem in lot of ways. Famous one is using Promises.

References : 
* [https://stackoverflow.com/a/25098235](https://stackoverflow.com/a/25098235)
* [http://callbackhell.com/](http://callbackhell.com/)


### 18. What is async function?

The async function declaration defines an asynchronous function, which returns an AsyncFunction object.

An async function can contain an await expression that pauses the execution of the async function and waits for the passed Promise's resolution, and then resumes the async function's execution and returns the resolved value.

Remember, the await keyword is only valid inside async functions. If you use it outside of an async function's body, you will get a SyntaxError.

```javascript
async function getProcessedData(url) {
  let v;
  try {
    v = await downloadData(url); 
  } catch(e) {
    v = await downloadFallbackData(url);
  }
  return processDataInWorker(v);
}
```

References :
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
* [https://developers.google.com/web/fundamentals/primers/async-functions](https://developers.google.com/web/fundamentals/primers/async-functions)


### 19. Explain about prototype inheritance in javascript?

JavaScript is a prototype-based language, meaning object properties and methods can be shared through generalized objects that have the ability to be cloned and extended. This is known as prototypical inheritance and differs from class inheritance.

Every object in JavaScript has an internal property called `[[Prototype]]`.

**Note :** The double square brackets that enclose `[[Prototype]]` signify that it is an internal property, and cannot be accessed directly in code.

Another way to find the `[[Prototype]]` is through the `__proto__` property. `__proto__` is a property that exposes the internal `[[Prototype]]` of an object.

**Note :** It is important to note that `.__proto__` is a legacy feature and should not be used in production code, and it is not present in every modern browser.

```javascript
let x = {};

// {constructor: ƒ, __defineGetter__: ƒ, __defineSetter__: ƒ, …}
Object.getPrototypeOf(x); 

// output will be the same as if you had used getPrototypeOf().
// {constructor: ƒ, __defineGetter__: ƒ, __defineSetter__: ƒ, …}
x.__proto__;
```

It is important that every object in JavaScript has a `[[Prototype]]` as it creates a way for any two or more objects to be linked.

***Prototype Inheritance :***

When you attempt to access a property or method of an object, JavaScript will first search on the object itself, and if it is not found, it will search the object's [[Prototype]]. If after consulting both the object and its [[Prototype]] still no match is found, JavaScript will check the prototype of the linked object, and continue searching until the end of the prototype chain is reached.

At the end of the prototype chain is Object.prototype. All objects inherit the properties and methods of Object. Any attempt to search beyond the end of the chain results in null.

```javascript
let y = [];
y.__proto__ === Array.prototype;            // true
y.__proto__.__proto__ === Object.prototype; // true
y instanceof Array; // true
```

References : 
* [https://www.digitalocean.com/community/tutorials/understanding-prototypes-and-inheritance-in-javascript](https://www.digitalocean.com/community/tutorials/understanding-prototypes-and-inheritance-in-javascript)
* [https://javascript.info/prototype-inheritance](https://javascript.info/prototype-inheritance)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)


### 20. What is the difference between `Array.splice()` and `Array.slice()`?

***Array.splice()***

The splice() method adds/removes items to/from an array, and returns the removed item(s).

*Syntax :* 
```javascript
array.splice(index, howmany, item1, ....., itemX)
```

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];

// Banana,Orange,Lemon,Kiwi,Mango
fruits.splice(2, 1, "Lemon", "Kiwi");
```

***Array.slice()***

The slice() method returns the selected elements in an array, as a new array object. The slice() method selects the elements starting at the given start argument, and ends at, but does not include, the given end argument.

*Syntax :* 
```javascript
array.slice(start, end)
```

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];

// Orange,Lemon
var citrus = fruits.slice(1, 3);
```


References : 
* [https://www.w3schools.com/jsref/jsref_splice.asp](https://www.w3schools.com/jsref/jsref_splice.asp)
* [https://www.w3schools.com/jsref/jsref_slice_array.asp](https://www.w3schools.com/jsref/jsref_slice_array.asp)


### 21. What is the difference between `.bind()` , `.call()` and `.apply()`?

Use .bind() when you want that function to later be called with a certain context, useful in events. 

Use .call() or .apply() when you want to invoke the function immediately, and modify the context.

They all attach this into function (or object) and the difference is in the function invocation (see below).

* call attaches `this` into function and executes the function immediately

```javascript
function Product(name, price) {
  this.name = name;
  this.price = price;
}

function Food(name, price) {
  Product.call(this, name, price);
  this.category = 'food';
}

// expected output: "cheese"
console.log(new Food('cheese', 5).name);
```

* `apply` is similar to `call` except that it takes an array-like object instead of listing the arguments out one at a time

```javascript
function personContainer() {
  var person = {  
     name: "James Smith",
     hello: function() {
       console.log(this.name + " says hello " + arguments[1]);
     }
  }
  person.hello.apply(person, arguments);
}
personContainer("world", "mars"); 
// output: "James Smith says hello mars", note: arguments[0] = "world" , arguments[1] = "mars"    
```

* bind attaches `this` into function and it needs to be invoked separately like this
```javascript
var person = {  
  name: "James Smith",
  hello: function(thing) {
    console.log(this.name + " says hello " + thing);
  }
}

person.hello("world");  // output: "James Smith says hello world"
var helloFunc = person.hello.bind({ name: "Jim Smith" });
helloFunc("world");  // output: Jim Smith says hello world"
```

References : 
* [https://stackoverflow.com/a/31922712](https://stackoverflow.com/a/31922712)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)


### 22. Explain about javascript hoisting?

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.

It's a big topic. Go throug the reference links for understanding about hoisting behaviour. 

References : 
* [https://scotch.io/tutorials/understanding-hoisting-in-javascript](https://scotch.io/tutorials/understanding-hoisting-in-javascript)



