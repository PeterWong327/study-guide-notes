- Explain the time complexity of Quicksort
  - The time complexity of Quicksort depends on the input array and the partition strategy:
    1. Worst case O(n^2): when the partition step picks the largest or smallest element as the pivot each time and the array is already sorted in ascending or descending order.
    2. Best and average case O(nLogn): when the partition process picks the middle element as pivot each time.


- Explain the partition method
  - In the partition method, the function takes an element as pivot, then places the pivot element at its correct position in a sorted array. Then all smaller elements are placed to the left of the pivot and greater elements are placed to the right of the pivot.


- What is partial function application?
  - Partial function application is when a new function is created from an existing function by fixing some parameter from the existing function.


- What is the difference between class inheritance and class composition?
  - Class inheritance is when one class (a child) inherits all of the members from its parent class, which inherits all members from its parent class. Class composition is when the parent class and the child class have a 'has-a' relationship, where the child does not inherit methods from the parent class because the parent is composed of different child class fields.


- What is method overriding?
  - Method overriding is redefining a method (of the same name) that has been inherited from a parent class. Child classes will then inherit from the newer method.


- What is polymorphism?
  - Polymorphism is when the method being invoked depends on the type of the object that is invoking the method. This happens when there are more than 1 method with the same name, but defined in different classes, so the method would depend on which class the instance of the object belongs.


- What are class fields and class methods?
  - Class fields are global variables that live inside a class. Class methods are functions that live inside a class. These do not belong to an instance of the class.


- How do static and dynamic languages treat interfaces differently?
  - Dynamic languages can invoke methods from an interface on any object, whether that object has the method or not (discovered at runtime). Static languages require that the objet has access to the method before the code would run (prevents runtime errors).


- Compare and contrast CSRF and XSS. How do you prevent them?
  - CSRF (Cross-Site Request Forgery) is when you log into a domain, then visit an attacker's site, which leads you to performing some action that the attacker set, on your account's behalf. The attacker is able to do this by mimicking the URL of the domain that you are logged into and modifying it to perform a specific action. You can prevent CSRF by using POST for sensitive actions, use CAPTCHAs, or prompting the user to re-login. XSS (Cross-site scripting) occurs when a user clicks on a link or an image tag, activating an injected script set up by the attacker. The script would then run and retrieve sensitive information from the user to the attacker. You can prevent XSS by not clicking on links, not trusting user input, and encode (escape) all user input.
