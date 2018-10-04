# Algorithms Notes

#### Graphs

- Give a high level overview of an Adjacency Matrix
  - A 2-dimensional matrix of size V * V, where V is equal to the number of vertices in a graph. Each vertex has an index between 0 and V-1. The matrix shows the connections between each vertex with another vertex. Row index represents the start point, and column index represents the end point.


- If we were only concerned about time complexity, is an Adjacency Matrix efficient? Why/why not?
  - Yes, an Adjacency Matrix would be efficient to find the adjacent nodes of a vertex through a linear time complexity (# of vertices). Finding if two nodes are connected would be constant time if a hash table is used to store the names and indices of the nodes.


- If we were only concerned about space complexity, is an Adjacency Matrix efficient? Why/why not?
  - No, an Adjacency Matrix uses space complexity of V^2 to store all relationships of each vertex with every other vertex, whether there is a connection or not.


- Give a high level overview of an Adjacency List
  - An Adjacency List is a 2-D array, where each row is a 1 dimensional array of different sizes, showing only vertices that have a connection with the vertex representing the row number.


- What benefits do we get from an Adjacency List?
 - Eliminates the redundancy of storing data on whether a node is connected to another node. Using an Adjacency List, one can deduce that a node is not connected to another node if there is no connection represented by the list. This consumes less memory than an Adjacency Matrix.


 -  What are the steps for DFS on a graph?
  1. Create a stack and start from the bottom and work way up.
  2. Create a "visited" array to store results.
  3. Start from lowest vertex in the graph.
  4. Push the lowest vertex onto the stack.
  5. Push onto the stack the lowest adjacent vertex that is not in the visited array. Add the vertex to visited.
  6. Repeat step 5 for vertex at the top of the stack.
  7. When there are no more adjacent un-visited vertices, pop off the vertex from the top of the stack and repeat step 5.
  8. When stack is empty, traversal is complete.

 -  What supporting data structure might you use for BFS and DFS, respectively?
