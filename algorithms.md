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


- What is the time-complexity of Heap Sort?
  - The time-complexity of Heap sort is **O(n*log(n))**, where O(n) is from the heapify phase, when the given array is put into a heap order. The O(n*log(n)) is from the 'sortdown' phase, where the max/min is repeatedly extracted and the heap order is restored (traversing through the height of the heap).


-  What are the steps for Heap Sort?
  1. Build a max heap from an unsorted array (use a function buildMaxHeap).
  2. Swap the item at the root node (largest value) with the item at the end of the heap.
  3. Extract the largest value (at the end of the heap) to remove the last node.
  4. Perform 'heapify', moving the new root node item down to its correct position, by swapping the root node with the larger of its 2 children, until it is no longer smaller than its children.
  5. The new root node is now the largest, and so we will need to extract this next largest value by swapping it with the item at the end of the heap.
  6. Repeat steps 2-5 until the heap only has 1 node left. The last node remaining is the first element in the sorted array.


- Explain the pseudocode for Merge Sort
  1. Establish the base case (return the given array if the size of the array is less than or equal to 1).
  2. Define the midpoint as the array length / 2.
  3. Call mergeSort on the left half of the array.
  4. Call mergeSort on the right half of the array.
  5. Call and return the helper function 'merge' on the result of mergeSort of left and right half of the array.
  6. Define the helper function 'merge' by passing in a leftArray and rightArray.
  7. While both subarrays are not empty, compare the first element of each subarray, and push the smaller element into a result array (shifting the element from the subarray).
  8. Return the result array.concat(left, right).


- What is the runtime of merge sort?
  - The runtime of merge sort is O(n*logn), linearithmic, where the merge function = n, and each recursive call on the subarrays = log n.


- What are the steps for Counting Sort? What is the time complexity?
  1. Given an unsorted array of integers, create a counts array of 0s with the length of the range (eg. 0 to 9 => an array with index 0 to 9, length 10) for each integer.
  2. Iterate through given array and increment the count at the corresponding index of the counts array (the index represents the integer).
  3. Once counts are in place, modify the counts array by adding the count from the previous index to the count of the current index.
  4. Create a new array with the same length as the given array ("sorted").
  5. Place each integer of the given array into the correct position in the 'sorted' array, using the counts array to find the position (key into counts array with integer as the index, then use the element as the index (i + 1) for the integer in the sorted array). Subtract 1 from the counts array element that was used for the position.
  - The time complexity of Counting Sort is O(n + k), where n is the number of elements in the given array, and k is the range of the input from the given array.


- What is the time complexity of Bubble Sort? What are the steps for this algorithm?
  - The time complexity for Bubble Sort is O(n) for the best case, while O(n^2) for the average and worst case.
  1. Iterate through each number in the given array.
  2. If current number is greater than the next number, swap the positions of the two numbers.
  3. After you reach the 2nd to last number, if the array is not sorted yet, start at the first number again (use while loop) and repeat the swapping of numbers until the array is sorted.


- Describe when it may be ideal to utilize Bubble Sort.
  - It may be ideal to utilize Bubble Sort when tasked with a problem to find the k largest or smallest elements in an array. Since Bubble Sort sorts the last k elements in order first (the elements 'bubble' to the top), the iteration step in Bubble Sort only needs to be run k times until we can get all the elements we need (by printing the last k elements). This results in a time complexity of O(nk).


- What is the time complexity of Radix Sort? What are the steps for this algorithm?
  - The time complexity of Radix Sort is O((n+b) * log(k)), where k is the maximum possible value.

  1. Find the biggest number in given array. The number of digits in this number is N. Add leading zeros to all other numbers until they all have N digits.
  2. Perform N times using 1st digit from right of each number:
    a. Create a 'bucket' array from index 0 to 9.
    b. Iterate through given array and place each number into corresponding 'bucket' where the bucket index = the 'current' digit of each number.
    c. Iterate through each bucket from 0 - 9, and place each number into the array.
    d. Repeat Steps b and c with the results array until all digits have been accounted for.
    e. Return results array.



- What is an ideal use-case for Radix Sort?
  - The ideal use-case for Radix Sort is when the range of the array of integers is from 1 to n^c, where c is a constant, if the numbers are represented in base n (b === n), then the time complexity is O(n).


-  What are the constraints of a Binary Search Tree?
  - All elements in the left subtree must be <= the root node, while all the elements in the right subtree must be >= the root node.


- What is the big O lookup time for a value in a binary search tree?
  - The time complexity of looking up a value is O(h), where h is the height of the binary search tree.


-  How can you find the maximum depth of a BST?
  - To find the maximum depth of a BST, start at the root node of the tree. Use recursion on the root and 1 (represents the depth with a tree of just the root). Define the base case: if the root is empty, return 0 since there is no depth. Define the terminating case: if a root doesn't have a left or right child, then return the given depth value (num). Use a conditional to return a recursive call on the max value of either the right or left child of the root given the depth plus 1 (if both children exist), or return recursive call on either left or right child (if either one exists) given depth plus 1.


- How can you determine what the Least common ancestor of two nodes is?
  - Recursively traverse the BST from the root, and the first node who's value is between the two given nodes is the least common ancestor. When traversing the BST, if a node has a value that is greater than both given nodes' values, then the LCA is in the left side of the current node. If the value is less than both given nodes' value, then the LCA is on the right side of the current node.


- What is an AVL tree?
  - An AVL tree is a BST where every node's left and right children's heights differ by at most +/- 1 (balanced).


- How does an AVL tree self balance?
  - An AVL tree self balances by doing left and right rotations when a child subtree is not balanced. If a node x's right child is right-heavy or balanced, then a left rotation is performed on the node x. If a node x's right child is left-heavy, then a double rotation is performed: right rotation on node x's right child, and then a left rotation on node x. This check is done after every insert operation (starting from lowest node violating the AVL property and moving up to the node's grandparent, greatgrandparent, etc.) to maintain the balanced property.


-  Give a high level overview of how to implement a hash table.
  - A hash table utilizes a combination of an array and linked lists to store data. When a data is put into a hash function, a non-negative integer is returned. This integer is then used in the hash table as a corresponding array index. The input is then stored in that corresponding array index as the head of a linked list. If an item already exists in that linked list, then the new item becomes the head, shifting every item within the linked list down by one.


- Give a high level overview of how to implement a Linked List.
  - First, create two classes: one for creating a Node (initialized with a value, and a pointer to the next Node), and one for creating the Linked List (initialized with its head pointing to a new Node given a value).
  - Then create functions for adding a new Node (given a value), deleting a Node (given a value), and returning a list of all elements in the Linked List (in an array).
  - To implement the add function, set the current node to the head, and while the next node is not null, keep setting the current to the next node (to get to the last node). Then create a new Node with the given value as the last node.
  - To implement the delete function, find the node whose next node holds the given value, then change the pointer of the next node to the node after (bypassing the next pointer to the node with the given value).


-  Why is binary search logarithmic time?
  - Binary search is logarithmic time because we assume the given array is sorted, and therefore, we look at only one half of the array at each recursive call, shrinking the number of elements to be checked each time.


- If an element is smaller than its right neighbors, explain why there is definitely a peak to the right.
  - If an element is smaller than its right neighbors, then either the right neighbor is a peak (right neighbor is higher than everything to its right), or the highest number on the right side is the peak. A peak occurs when both left and right numbers are smaller than the middle number, or when the first/last number is the highest.
