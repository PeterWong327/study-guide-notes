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


- In which phase does hoisting occur?
  - Hoisting occurs during the compilation phase when function declarations are 'moved' to the top of the scope.


- What is the difference between function hoisting and variable hoisting?
  - Function hoisting means that a declared function can be called before it is defined, while variable hoisting only applies to the declaration of the variable (using var), but its assignments are not affected.


- What does the 'new' keyword do in Javascript?
  - The 'new' keyword creates a new object through a constructor function. The object's prototype is set as the prototype of the constructor function. It also executes the constructor function with 'this' as the newly created object and returns the created object.


- What type of function is invoked with the 'new' keyword? What does this function return?
  - A constructor function is invoked with the 'new' keyword. This function returns the object that is created.


- How can you stop event bubbling?
  - You can stop event bubbling by using event.stopPropagation(). This is placed as an onclick on a target element.

- What is the difference between event.target and event.currentTarget?
  - event.target is the most deeply nested element that caused the event. It is the target element that initiated the event (the element that was actually clicked)
  - event.currentTarget is the element that has a currently running handler on it. It refers to 'this'.


- What does stopImmediatePropagation do?
  - stopImmediatePropagation stops event bubbling AND prevent handlers on the current element from running. No other handlers would execute.

- What is event delegation?
  - Event delegation utilizes event bubbling to apply a single handler to multiple elements through the common ancestor (using onclick on the common ancestor).


-  Discuss 4 differences between ES5 and ES6 that you find important.
  - ES6 does not allow duplicate declaration of variables when declared using 'let' or 'const' in the same scope.
  - ES6 uses lexical 'this' via fat arrow function, which forces 'this' to always point to the object where it is physically located within. In ES5, 'this' refers to the window if it isn't binded to the object.
  - ES6 has 'Rest' parameters (...args), where the parameters is an array, so we can use all the Array functions. In ES5, 'arguments' acts like an array but the Array functions (sort, slice) are not available.
  - Strict Mode ('use strict') is optional in ES5, but required in many ES6 features. This helps to explicitly show what the errors are.


- What are the steps of a try..catch block in Javascript?
  1. The code in try {...} is executed.
  2. If no errors in 'try', then catch(err) does not get executed, and the rest of the code in 'try' runs, jumping over the 'catch' block.
  3. If there is an error, then the 'catch' block gets executed (error handling), skipping over the rest of the 'try' block.
  4. The rest of the code gets executed (after 'try' and 'catch').


- What type of errors do try..catch blocks work for?
  - try...catch errors only work for runtime errors (valid JavaScript).


- When creating a custom error, what attributes should it have?
  - A custom error should have the attributes of 'message', 'name' and 'stack'.


- What's the difference between the DOMContentLoaded and load event triggers?
  - A load event is triggered when a resource and all its dependent resources (images, styles, etc) have finished loading.
  - DOMContentLoaded is triggered when the initial HTML document has been completely loaded, without waiting for stylesheets, images and subframes to finish loading. 'load' should be used only to detect a fully-loaded page.


- Discuss the differences between let, const, and var. What are their respective scopings?
  - With 'var', variables and functions declared inside another function cannot be accessed outside of the function (function-scoped). Variables declared inside a block-scope ('if' and 'for') can be accessed from outside of the block (curly braces).
  - With 'let' and 'const', they are not hoisted (can't call variable before declaring it) and block-scoped alternatives for variable declaration (re-declaring a variable inside a block will only change the variable within the same block).
  - 'const' cannot be reassigned, but its properties can be changed (variable cannot be re-declared, but for example, the index of an array can be changed, or the key/value of an object can be changed).


-  What happens when you enable strict mode in javascript?
  When 'strict mode' is enabled in the global scope, one thing that you cannot do is use undeclared variables/functions **(x = 3.14 throws an error)**. If an undeclared variable/function is used outside of the scope where 'use strict' was declared, then there would be no error. Strict mode helps throw an error when a variable has been mistyped, preventing a new global variable from being created. Strict mode also prevents a variable/function from being deleted. Other actions prevented by strict mode:
    - using a duplicate parameter name.
    - putting a '0' in front of a number.
    - using "eval" or "arguments" as variables.


- How does the rest/spread operator work in JS?
  - The rest parameter is used in a function definition with three dots (...args), to gather all parameters into an array. When a function is called, any excess arguments would be put into the args array through the rest operator. The rest parameter must be at the end of a function.
  - The spread operator is used to represent all the elements of an array (used in a function call), and expands the array into a list of many arguments.


- What does the length attribute refer to on a Function in Javascript?
  - The length attribute refer to the number of parameters that are in the function, excluding any rest parameters.


- Explain the differences between a Function Expression and Function Declaration.
  - Function Expression is when a function is created and saved to a variable. The function is only usable from then on, meaning that it is not hoisted.
  - A Function Declaration is when a function is declared, and it can be called before and after it was defined, meaning that it is hoisted.


- Does JS assign variables by value or by reference?
  - JavaScript assigns variables by value if the value is a simple value (primitives), such as null, undefined, boolean, number, string, and symbol (ES6). On the other hand, if the value is a compound value (objects, arrays, functions), then the variable is assigned by reference. Compound values are equal by reference, but not value.

  Value Ex.
  ```
      let a = 2;
      let b = a;
      b++;
      console.log(a) => 2
      console.log(b) => 3
      (a === b) => false
      ```

  Reference Ex.
  ```
    let c = [1,2,3];
    let d = c;
    d.push(4)
    console.log(c) => [1,2,3,4]
    console.log(d) => [1,2,3,4]
    (c === d) => true
  ```



- What are the 7 different JS types?
  - The 7 different built-in JavaScript types are: null, undefined, boolean, number, string, object, and symbol (ES6). These are all primitives (except for object).



- Explain the difference between + and
  -&ast;/ in JS when it comes to coercion.
    - In JS, when a string is used with +, the result is a concatenation between the string and a number. (ex. 1 + "2" = "12". If a string is used with -&ast;/ operators, then a numeric operation occurs between the string and the number. The string is coerced to a number in this case (ex. "2" * 3 = 6).


- How does prototypal inheritance work?
  - Prototypal inheritance works by having objects inherit directly from other objects when the object is created. There are 3 kinds of prototypal inheritance:
    1. Prototype delegation: using a delegate prototype (Object.create() ) as a model object for another object.
    2. Concatenative inheritance: when an object inherits properties from another object by copying the object's prototype properties (Object.assign() ). Does not retain reference.
    3. Functional inheritance: when an object is created using a factory function, which adds new properties directy to the created object. It returns an object without using the 'new' keyword.
