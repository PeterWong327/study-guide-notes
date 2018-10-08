# Javascript Notes

#### Converting a string to an integer

parseInt(string)

Example:

parseInt("2112") = 2112

parseInt("123.8") = 123 (Rounds down)

--------------------
- Give a high level overview of what an object's prototype represents
  - An object's prototype represents the properties of the object which other objects can inherit from.

- What are the differences between the  `__proto__` and prototype attributes?
  - Prototype is a property of a function, whereas '__proto__' is a property of all objects.

- What happens when we do or don't explicitly set an object's prototype?
  - If we don't explicitly set an object's prototype, the default 'prototype' is an object with the only property constructor that points back to the function itself.
  - If we do explicitly set an object's prototype, any new objects created will have the [[Prototype]] attribute from the original object's set prototype.

- What is an object's default prototype?
  - An object with the only property 'constructor' that points back to the function itself.

- What are the valid values for an object's prototype?
  - Valid values are either an object or null.

- What are the benefits of a Javascript closure?
  - Closures allow data encapsulation, where some data should not be directly exposed.

- Formally define a Javascript closure
  - A closure allows a function to access variables from an enclosing scope even after it leave the scope in which it was declared. It refers to variables in the outer scope and it can refer to outer scope variable even after the outer function has returned.


- Give an example of a closure
  ```
  function sayHi(name) {
    var message = `Hi ${name}!`;
    function greeting() {
      console.log(message)
    }
    return greeting
  }
  var sayHiToJon = sayHi('Jon');
  console.log(sayHiToJon) => f() { console.log(message) }
  console.log(sayHiToJon()) => 'Hi Jon!
  ```

- What is data encapsulation?
  - Data encapsulation is the idea that data within a function cannot be directly accessed, except through a closure.


-   What is the difference between the memory heap and call stack in javascript?
  - The memory heap executes a specific function only when a certain event happens. Once the event happens, the function is moved to a Callback Queue. A call stack stores information about active functions. It manages the order in which functions get executed.

-  What is one problem with programming languages that are fully single-threaded?
  - One problem is that only one piece of code can be processed at a time, so all code after would be blocked from running until the code is finished.

- When is using an IIFE necessary?
  Immediate Invoked Function Expression (IIFE) is used when you want to create a new variable scope to attach private data to a function. It is a function expression that is called immediately after it is defined.

- What is the syntax for an IIFE?
  - The function is surrounded with parentheses to prevent it from being treated as a function declaration. Final parentheses are placed after the function to execute the function expression.


-  What is the risk we face when using == vs ===?
  - **"=="** checks for equality with coercion, meaning that JavaScript may change the type that is being compared.
  - **"==="** checks for strict equality, so the type will not change in the comparison.


- When is the value of this evaluated?
  - The value of **this** is evaluated when the function is called (run-time).

- How does use strict affect the value of this?
  - Not using 'use strict' will cause the value of 'this' to be the global object (window in a browser).

- Without use strict, what is the value of this inside a named or anonymous function?
  - The value of 'this' without use strict would be the object that the function is called on. If there is no object, then this will be undefined.

- What is the value of this in method style syntax?
  - The value of 'this' in method style syntax is the object that calls the method.


- What's the event loop? How does it work?
  - The event loop is a queue of callback functions. When an asynchronous function executes, the callback function is pushed into the queue. Once the code after an asynchronous function has executed (the call stack has cleared), the callback functions in the event loop gets processed.
