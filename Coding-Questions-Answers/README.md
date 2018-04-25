# Coding Questions Answers

1. What is the output of below code?
```javascript
a = 10;
function f(){
    a = 1;
    return;
    var a = 5;
}
f();
console.log(a);
```

2. What is the output of below code?
```javascript
for(i=0; i<4; i++){
    setTimeout(function(){
        console.log(i);
    }, 1000);
}
```

3. What is the output of below code?
```javascript
var a = { h : 1};
var b = a;
b.h = 3;
console.log(a);
```

4. Explain why the following doesn't work as an IIFE: 
```javascript
function foo(){ 
    // code
}();.
```
5. Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5?
