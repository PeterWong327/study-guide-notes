Name 5 benefits of HTML5
What is localStorage? How might you use it?
Why are media queries useful?
What is mobile-first design? Be as specific as possible.


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
