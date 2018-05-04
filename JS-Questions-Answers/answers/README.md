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










### Promises Example:

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
  },
  error => {
    console.log("Promise rejected.");
    console.log(error.message);
  }
  
);


```

