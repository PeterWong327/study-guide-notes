# Javascript Notes

#### Converting a string to an integer

parseInt(string)

Example:

parseInt("2112") = 2112

parseInt("123.8") = 123 (Rounds down)

--------------------
- Give a high level overview of what an object's prototype represents

- What are the differences between the  `__proto__` and prototype attributes?

- What happens when we do or don't explicitly set an object's prototype?

- What is an object's default prototype?

- What are the valid values for an object's prototype?

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
