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


- Give one explanation for why we have to make AJAX requests in componentDidMount.
  - An AJAX request might resolve before the component mounts, which would mean that setState would be called on an unmounted component. Making AJAX requests in componentDidMount would mean that there is always a component to update.
