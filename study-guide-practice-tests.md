1. Choose the correct statement(s) about BSTs. A, C, D

A) Pre-order traversal visits all parent nodes before their children
B) BSTs must be complete in order to be traversed with in-order traversal
C) Post-order traversal alone can be used to reconstruct a BST
D) In-order traversal alone can be used to reconstruct a BST
E) A BST is balanced if the heights of its left tree and its right tree differ by no more than 1
D) If you have nodes of value 3 and value 10, and the root is of value 5, then the root is guaranteed to be the Least Common Ancestor of the two nodes
E) Finding the Least Common Ancestor of two nodes has a time complexity of nlog(n) because you must look at each child as you move up or down the tree
F) Deleting a node in a BST requires having a .parent method on the node


2. Given this code, which statement(s) evaluate(s) to true? A, C, D, F
  const a = 'string';
  const b = 'string';
  const c = '1';
  const d = 1;
  const e = a;
  const f = [1,2,3];
  const g = [1,2,3];
  const h = f;
  const i = {
    'name': ['object']
  };
  const j = {
    'name': i.name
  };
  const k = new String('string');
  const l = k;

A) a === b
B) c === d
C) c == d
D) e === a
E) f === g
F) h === f
G) h === g


3. Choose the correct statement(s) about Networking and Scalability. A, E, F

A) Manchester coding is a strategy to deal with clock slip
B) Round Robin DNS binding is handled by the load balancer at the request destination
C) Session stickiness refers to the need for users to be able to log back into their account and have access to the data that was transmitted in past requests
D) Clock slip is not an issue when you have a checksum attached to the transmitted packet
E) RAID0 allows you to use multiple hard drives as one, but does not give you the ability to recover data if one of them fails
F) Sending the actual server id back to the requester in a cookie is not feasible because you don't want to expose private IP addresses
G) Caching compiled assets in memory can't increase server response times because it is expensive to determine which assets need to be cached


4. Choose the correct statement(s) about prototypal inheritance. B

A) An object created with Object.create(a) will share a prototype with a
B) Object.assign() is used to compose objects with only the features they need
C) Object.assign takes in an object and an arbitrary number of subsequent objects, merges them all with the first object and returns a brand new object
D) Calling super() in the constructor lets you choose which properties you want to inherit


5. Given this code, what will be logged? A

  let a = {name: "A"};
  let b = Object.create(a);
  b = Object.assign(b, {count: 1});

  console.log(b);

  let c = Object.assign(a, {height: 2});

  console.log(b.height);
  console.log(b.__proto__ === a);
  console.log(c === a);

  a.name = "new name";

  console.log(b.name);


A)
{ count: 1 }
2
true
true
'new name'

B)
{ count: 1 }
undefined
true
true
undefined  

C)
{name: "A", count: 1 }
2
false
true
'new name'

D)
{name: "A", count: 1 }
2
true
false
'new name'

E)
{ count: 1 }
undefined
true
false
undefined


6. Given this code, what will be logged? D

  const dFact = function(name) {
    const message = `Hello, ${name}`;
    return {greet: message};
  };
  const d = dFact('Bob');

  console.log(d.greet);

  d.name = 'Alice';

  console.log(d.greet);

  const dee = Object.assign(new dFact("Cody"), {age: 10});
  console.log(dee);
  console.log(d.__proto__ === dee.__proto__);


A)
Hello, Bob
Hello, Bob
{ greet: 'Hello, Cody', age: 10 }
false

B)
Hello, Bob
Hello, Alice
{ greet: undefined, age: 10 }
true

C)
Hello, Bob
Hello, Alice
{ greet: 'Hello, Cody', age: 10 }
true

D)
Hello, Bob
Hello, Bob
{ greet: 'Hello, Cody', age: 10 }
true

E)
Hello, Bob
Hello, Bob
{ greet: undefined, age: 10 }
false


7. Choose the correct statement(s) about AVL trees. C, F

A) AVL trees require completeness at all times
B) AVL trees cannot delete in log(n) time because they may have to perform tree rotations
C) In a right tree rotation the right tree of the rotating node becomes the left tree of its parent
D) In a rightleft double rotation the left tree of the rotating node becomes the left tree of its grandparent
E) As long as the root node is balanced, not every subtree needs to be an AVL tree for the entire tree to be considered an AVL tree
F) AVL trees are incompatible with heapsort


8. Choose the correct statement(s) about the JS global object. B, D

A) Both node.js and browser JS engines share a reference to the same global object
B) The global object can be used to check whether a function or object is available in the browser API
C) let and const can be defined on the global object as long as you do so in the highest scope
D) The global object can be used to access information about the visual layout of the window
