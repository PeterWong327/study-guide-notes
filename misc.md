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
