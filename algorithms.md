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


- Explain the steps of topological sort.
  1. Initialize a set and a stack.
  2. Pick any vertex and add it to the set ('visited') if not visited already. Check all children of vertex and place each child into visited.
  3. Explore all children of each visited vertex. Once done exploring, push the visited vertex into the stack, and move up to each parent, pushing each parent if there are no more children to explore.
  4. Repeat step 2 for another vertex until all vertices have been visited.
  5. Pop off each vertex from the stack into a an array, which is sorted.

 - Give an example of a use-case for Topological Sort
  - Topological Sort can be used to order the packages of a build system. The child node of a vertex would have a dependency on its parent node, so a parent node is always ordered before a child node in a topological sort.


 - What is a difference between Topological Sort and DFS?
    - Topological sort traverses a graph only as far as a child node needs from its dependencies on its parent nodes, while DFS traverses through a graph until there are no more child nodes before traversing back up to the parent node. There can be more than one way to topologically sort a graph, while there is only one way to perform a DFS traversal for a graph.


 - On which types of Graphs can we do a topological sort?
    - On directed acyclic graphs(DAG).

- What data structure do we use to assist with the topological sort algorithm?
    - Stacks and sets. A set would be used to store all the visited vertices, while a stack has all the vertices in topological sorted order (pushed from the set when it has no more adjacent vertices).


-  Explain the steps of Djikstra shortest-path algorithm.
  1. Create a min heap and add all the vertices with infinite distance from source vertex.
  2. Set distance of source vertex to 0.
  3. Put the source vertex in a 'distance' hash map, used to **store shortest distances** from root to every vertex.
  4. Set parent for source vertex equal to null, using a 'parent' hash map that **stores parent** of every vertex in shortest distance.
  5. Iterate while heap is not empty:
    a. Extract the minimum value vertex from the min heap. Use the extracted heap node to get the current vertex and update the distance hash map.

    b. Iterate through all the neighbors of the current vertex and check if the adjacent vertex is present in the min heap. If not present, then the shortest distance for the adjacent vertex already exists.

    c. If present, find the total distance (newDistance) from source vertex to the adjacent vertex.

    d. Check if the adjacent vertex distance in the min heap is greater than the newDistance. If so, decrease the value in the min heap to this new distance. Update the parent of the adjacent vertex to current vertex.

    e. Repeat until all neighbors have been explored, and then repeat step A.

- What is the time complexity of Djikstra's algorithm?
  O(E*log(V)), where E is the # of edges and V is the # of vertices.


-  What is a base case in recursion? Why do we need one? Do we always need one?
  - A base case is a condition that stops a function from calling itself recursively in an infinite loop. We need the base case to prevent Stack Overflow.

- What exactly is a Stack Overflow?
  - Stack Overflow is a function that is repeatedly called recursively and never reaches a base case to stop the recursive call. This will result in too many function calls on the stack, resulting in memory exhaustion.

- Describe direct and indirect recursion
  - Direct recursion is when a function calls itself.
  - Indirect recursion is when a function1 calls another function2, which calls the original function1 directly or indirectly.


- What is tail call recursion? Why is it helpful, if at all?
  - Tail call recursion is when a function ends with a recursive call, so that the last thing executed is the recursive call. It is helpful because the function can be optimized by the compiler. Since the recursive call is the last to be executed, there would be no need to save the current function's stack frame, thus saving memory.

- Discuss advantages/disadvantages of recursion
  - The advantages of recursion include being able to easily solve a complex problem using a recursive function, resulting in clean and simple code.
  - The disadvantages include the possibility of stack overflow if the function is not set up properly, and the function can become memory intensive as as the stack frame increases. Also, recursion has greater time requirements because of additional function calls.

- How is memory allocated during recursive function calls?
  - During a recursive call, memory is allocated on the stack to the main function making the recursive call. As another recursive call occurs, memory is allocated on top of the memory allocated to calling the function. Once a base case is reached, the function return its value to the function which called it, de-allocating the memory until the stack is cleared.


-  What is the difference between Memoization and Tabulation?
  - Memoization is a top-down approach in dynamic programming in which the values of a problem can be stored as the result and reused to solve the rest of the problem (until the base case).
  - Tabulation is a bottom-up approach in which the value of a problem starts at the base case and is used to build up (iteratively) to the top (result of the problem).


- Why is memoization helpful?
  - Memoization is helpful because it avoids the running of duplicated code by storing the values of previously run code, to be used again in the same function.


-  What is an optimal substructure? When might a problem have one?
  - An optimal substructure is when a problem has an optimal solution that can be obtained by using optimal solutions of its subproblems. A problem has an optimal substructure when it has subproblems that can be solved and the results can be used to solve the original problem.


In a Binary Heap with N elements, the **height** will not be taller than O(log N):
  - The size N of a full binary tree of height 'h' is always N = (2^(h+1)) - 1, so:
   **h = log2(N+1)-1 ~= log2 N**.

**ExtractMax()** in a Binary Heap reports and deletes the maximum element(the root) and then replaces it with the last index N. This last index N is then compared and swapped with its child (larger of the 2) until Binary Max Heap property is not violated (ShiftDown or BubbleDown or Heapify).


-  What are the constraints of (any type of) Heap?
  - (Shape) A binary tree must be **complete** to be a heap. Every single level of the tree must be completely filled, except the last level. The last level must have the left-most nodes filled first. To add an element to a heap, it must be added to the lowest level and too the left-most available position.
  - (Order) In a **max heap**, the parent node is always greater than its children nodes. In a **min heap**, the parent node is always less than its children nodes.


- What type of Data Structure might we use to implement a heap?
  - We use an array to implement a heap because it is an efficient way of representing a priority queue.


- What is the formula for getting the left child of a Heap root node? Right child?
  - "i" is the root node's index.
  - Left child of a Heap root node: (2i + 1)
  - Right child of Heap root node: (2i + 2)


-  What is a Priority Queue?
  - A priority queue is a data structure (FIFO) where every element has a priority associated it. An element with a high priority is dequeued before an element of a lower priority. Two elements with the same priority are then dequeued based on the order of the elements in the queue.
