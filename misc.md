Name 5 benefits of HTML5
  1. Audio and video support through <audio> <video> tags.
  2. Using <!DOCTYPE html> to declare the doctype.
  3. Using semantic code (ex: <nav>) to write cleaner code.
  4. Ability to use <canvas> to create more interactive and animated websites (games).
  5. Ability to create mobile sites and apps.

What is localStorage? How might you use it?
  - LocalStorage allows you to store user information, cache data, and load the user's previous application state, all through the user's browser locally. LocalStorage can be used to store the current state of a game, or to speed up web service use and avoid exceeding the quota.


Why are media queries useful?
  - Media queries are useful to make a webpage responsive, depending on the screen size. We can use media queries to add a breakpoint to define what CSS properties to display when the browser window gets smaller or larger than a defined breakpoint (ex: max-width: 768px).



What is mobile-first design? Be as specific as possible.
  - It is when CSS properties and styles are set to change when the screen width gets larger than a mobile size. This is done by using media queries to conditionally change the CSS properties when the screen width is larger than the mobile screen property.


- Give a high level overview of how CSS grids work.

  - A grid is made up of a wrapper (parent) and the items (children). A display of grid is used to turn a div into a grid. The grid consists of columns and rows, which can be defined with grid-template-columns/grid-template-rows. The child items can be positioned and resized by grid-column-start/grid-column-end.


-  In which order do the React Lifecycle methods (including the optional ones) run?
  1. **componentWillMount**: App configuration in root component.
  2. **componentDidMount**: do setup here to get data for component (start AJAX calls).
  3. **componentWillReceiveProps**: updates when receive new props.
  4. **shouldComponentUpdate**: takes in nextProps as first argument and nextState as second. Returns boolean on whether to re-render component. (Only update if the props you care about change).
  5. **componentWillUpdate**: used instead of componentWillReceiveProps on a component that also has shouldComponentUpdate.
  6. **componentDidUpdate**: updates the DOM when prop or state changes.
  7. **componentWillUnmount**: cleans up anything from component (ex: removeEventListener)



-  In which lifecycle methods should you make asynchronous fetches for data?
  - componentDidMount
  - componentWillReceiveProps
  - componentDidUpdate


-  In which lifecycle methods can you call setState?
  - componentDidMount
  - componentWillReceiveProps
  - componentDidUpdate


- What lifecycle methods get called in the mounting phase? What are the use cases for each of those methods?
  - componentWillMount: app configuration in the root component, connecting to external APIs.
  - componentDidMount: start AJAX calls to load in data for component.


- What lifecycle methods get called in the update phase? What are the use cases for each of those methods? What method gets called in the unmounting phase?
  - Update:
    - componentWillReceiveProps: trigger state changes when a prop changes.
    - shouldComponentUpdate: controls when component will re-render, using a boolean.
    - componentWillUpdate: used instead of componentWillReceiveProps, in conjunction with shouldComponentUpdate.
    - componentDidUpdate: updates the DOM when a prop/state changes.
  - Unmounting:
    - componentWillUnmount: used to call any actions required after a component unmounts.



- Give one explanation for why we have to make AJAX requests in componentDidMount.
  - An AJAX request might resolve before the component mounts, which would mean that setState would be called on an unmounted component. Making AJAX requests in componentDidMount would mean that there is always a component to update.


-  What is a state tree in the context of Redux?
  - A state tree is a JavaScript object that represents everything that can change in an application, including the data and the UI state.


-  Why don't we want to modify (i.e. mutate) our redux state?
  - We want to keep the state tree as read only, and to make any changes by dispatching an action, which is a plain JavaScript object. This helps to speed up the rendering of the application.


- What is a pure function? Impure function?
  - A pure function is a function whose returned value depends on the values of its arguments. It does not modify the values that are passed to it.
  - An impure function is a function that may call the database or network, operate on the DOM, or override the values that are passed to it.


- Describe in detail what a redux reducer is. What makes it a pure function?
  - A redux reducer is a function that calculates the next state tree based on the previous state tree and the action being dispatched. It is a pure function because it does not modify the state given to it, and it has to return a new object.


- What is the role of the store in Redux?
  - The store binds together the three principles of Redux. It holds the current application's state object (store.getState), it dispatches actions, and it contains the reducer that tells how state is updated with actions.


- What does the subscribe method do in Redux?
  - The subscribe method lets you register a callback that the Redux store will call any time an action has been dispatched.


- What are presentational components?
  - Presentational components are components that do not specify any behaviors. They are only concerned with how things render or look.


- Explain Context in React
  - Context in React is used when some data needs to be accessible by many components at different nesting levels. It is designed to share data that can be considered "global" for a tree of React components (eg. current authenticated user, theme, or preferred language). Using Context, these values can be shared between components without the need to explicitly pass a prop through every level of the tree.


- What does the <Provider> component do?
  - The <Provider> component is used to pass the store down to the context so that the container components can read the store from the context and subscribe to changes.


- In which order does SQL execute its queries? Make sure to mention SELECT, JOIN, WHERE, and aggregate functions such as GROUP BY.
  1. FROM/JOINs
  2. WHERE
  3. GROUP BY
  4. HAVING
  5. SELECT
  6. DISTINCT
  7. ORDER BY
  8. LIMIT/OFFSET


  - What problem does bind solve in Javascript? How does it accomplish this?
    - 'bind' solves the problem of 'this' being lost when a method is passed somewhere separately from the object where 'this' is referring to. This is done by calling bind on a function, passing in the object to be bound to 'this' (let sayHi = user.sayHi.bind(user)).


  - What is the syntax for passing arguments to the bind function?
    - The syntax for passing arguments to the bind function is: **let boundFunction = function.bind(argument, optionalArgs)** The argument is given the 'this' context, and any optionalArgs are prepended to the boundFunction when it gets called.


  - Where in a SQL query may we use a sub query (After which SQL keyword) ?
    - A sub query can be used in the FROM statement. The sub query will run first (must be able to produce a result on its own), then use the result in the main SQL query. It can also be used in the WHERE, JOIN / ON, or CASE statements, where conditional logic is used (no need for alias).


-  Describe the effects of using Group By and Having.
  - 'GROUP BY' will show only the data subsets that are specified in this condition, which is also specified in the SELECT statement, and groups the results by one or more columns.
  'HAVING' is basically the same function as 'WHERE', except it is used after 'GROUP BY'. Subsets resulting from the 'GROUP BY' that do not satisfy the 'HAVING' condition will be eliminated from the result. 'HAVING' acts as a secondary filter once subsets are grouped into a table.


- What is a symbol when talking about transmitting data?
  A symbol is used to represent information, like a number, when transmitting data. The symbols are different states that can be transmitted.


- How is information transmitted over wireless signal?
  - Using radiowaves (wireless router), where the antenna radiate radiowaves at different frequencies, and another antenna would read the frequencies to translate the information (symbols) into data.


-  How do two computers ensure that the signal that is sent between them is interpreted correctly?
  - The two computers must ensure that they are using the same clock rate in order for the signals to be interpreted correctly.


- What happens when the clocks become unsynchronized?
  - When the clocks become unsynchronized, clock slips occur, where bits of information either does not get sent/received correctly or extra information get sent between the two computers.


- How do computers synchronize their clocks?
  - Through GPS antenna (signals from GPS satellites have clocks)
  - Have an atomic clock in the computer (uncommon).
  - Send a separate signal (clock signal) from one computer to another computer (risk is one link can be slower than the other link, causing a clock delay vs the data being transmitted).
  - Combine the clock and the data by using different symbols to represent ones (transition from 0 to 5volts) and zeros (transition from 5 to 0 volts).


- What is manchester coding?
  - Combining data and clock into one signal, removing the need to synchronize the clocks between 2 computers. Different symbols are used to represent ones (transition from 0 to 5 volts) and zeros (transition from 5 to 0 volts).


-  What is framing?
  - Framing provides the receiver with the starting points of a series of bits so that the receiver knows where the byte boundaries are.
  - 2 types:
    1. HDLC (High Level Data Limit Control)
    2. Ethernet, inner-frame gap (IFG), no bit data for 96 bit times in the beginning. Then sends 56 bits of alternating 1's and 0's (Preamble). Gives the receiver opportunity to synchronize its clocks.


- What is a frame delimiter?
  - It is a bit pattern (flag) used by HDLC to show where the start of a frame is located at.
  - For Ethernet, it ends the Preamble with "11" to trigger the beginning of the data that comes after.


- What is bit stuffing?
  - 'Bit stuffing' occurs in HDLC when a series of bits are sent that resembles a frame delimiter by chance. It is a rule that when there are 5 consecutive 1 bits in the data being sent, an extra 0 is 'stuffed' after the 5 consecutive 1 bits. When the receiver detects 5 consecutive 1 bits, it expects a 0 to come after, and ignores it. Otherwise, it is either an issue with the data or the sequence would be treated as a flag.


- What is a frame check sequence?
  - The frame check sequence consists of the last 4 bytes of the Ethernet Frame. It is a number that is computed based the contents of everything else in the Ethernet Frame (Preamble, Destination Address, Source Address, Ethernet Type, Payload). It is used by the sender/receiver to detected corrupted data in the frame.


- What is a MAC address?
  - A MAC (media access control) address is an ethernet address, which is built into ethernet hardware, which means that every computer has a unique MAC address. The MAC address of a computer receiving data is put into the 'Destination Address' of the Ethernet Frame, while the sending computer puts its own MAC address as the 'Source Address'


- How do packets get transferred around the internet?
  - Packets get transferred around the internet through multi-link ethernet networks. An IP router has a destination address that helps it know where to transfer to the next router (forwarding) until the packets reach the target destination. This entire process is called routing.


-  What is Address Resolution Protocol?
  - Address Resolution Protocol is a protocol that sends a broadcast to the ethernet network to find out which router (MAC address) owns a specific IP address.


- What is the purpose of TCP?
  - The purpose of TCP (transmission control protocol) is to provide a Byte Stream Service between a client and a server, which is connection oriented (set-up process) and reliable. TCP controls and manages the data transmission over between networks.
