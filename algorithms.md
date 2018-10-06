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
  - DFS: use a stack to track the path between current vertex and start vertex.
  - BFS: use a queue to track path between current vertex and start vertex.


 - What are the steps for BFS on a graph?
   1. Create a queue and a "visited" array to store the results.
   2. Start from lowest-value vertex in graph.
   3. Add lowest-value un-visited adjacent vertex to queue, and add it to "visited".
   4. Repeat Step 3 for the same vertex until no more adjacent vertices.
   5. Move on to next vertex by dequeueing the head of the queue, and repeat Step 3-5, until queue is empty. Traversal complete.


 - Give an example of a use-case for Topological Sort
  - Topological Sort can be used to order the packages of a build system. The child node of a vertex would have a dependency on its parent node, so a parent node is always ordered before a child node in a topological sort.


 - What is a difference between Topological Sort and DFS?
    - Topological sort traverses a graph only as far as a child node needs from its dependencies on its parent nodes, while DFS traverses through a graph until there are no more child nodes before traversing back up to the parent node. There can be more than one way to topologically sort a graph, while there is only one way to perform a DFS traversal for a graph.


 - On which types of Graphs can we do a topological sort?
    - On directed acyclic graphs(DAG).

- What data structure do we use to assist with the topological sort algorithm?
    - Stacks and sets. A set would be used to store all the visited vertices, while a stack has all the vertices in topological sorted order (pushed from the set when it has no more adjacent vertices).


-  Explain the steps of Djikstra shortest-path algorithm.
  1. Create a min heap and initialize all the vertices with infinite distance from source vertex.
  2. Set distance of source vertex to 0.
  3. Put the source vertex in a 'distance' hash map, used to store distances from root to every vertex.
  4. Set parent for source vertex to null, using a 'parent' hash map that stores parent of every vertex in shortest distance.
  5. Iterate until heap is empty:
    a.

- What is the time complexity of Djikstra's algorithm?
  O(E*log(V)), where E is the # of edges and V is the # of vertices.
