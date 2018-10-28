# Data Structure Notes

#### Graphs

- How do we define a graph mathematically?
  - A graph G is an ordered pair of a set of V of vertices and a set E of edges.
  - G = (V, E)


- What is the difference between directed, undirected, weighted, and unweighted?
  - Directed is when a graph has edges that point from the origin to the destination vertex, but only in one direction.
  - Undirected is when a graph has edges that do not have a fixed origin and destination vertices. The connection is bi-directional.
  - Weighted is when the lengths of the edges are different from each other.
  - Unweighted is when the lengths of the edges do not matter.


- Give an example of various types of graphs (Weighted Undirected, Unweighted Directed, Unweighted Undirected, etc.)
  - weighted undirected = two-way roads connecting cities, distance between cities (nodes) vary
  - weighted directed = one-way roads within a city, distance between nodes may vary
  - unweighted directed = web pages on the world wide web, each URL is a node that links from one page to another
  - unweighted undirected = social networks (Facebook), friendship goes both ways


- What makes a graph a simple graph? What attributes would make it not simple?
  - If a graph contains no multi-edges or self loops, it is a simple graph.
  - Self loops = both endpoints (origin and destination) of an edge are the same (can be in directed and undirected graph). Ex: a link on a webpage that directs to the current page.
  - Multi-edge = an edge that occurs more than once in a graph (directed and undirected). Ex: Multiple flights from one city to another.


- What is the maximum number of edges in a directed simple graph? Undirected simple graph? Answer should be in terms of N
  - Directed = N(N - 1)
  - Undirected = N(N-1)/2


- Describe the levels of connectivity a graph can have (strongly connected, weakly connected).
  - Connected when a graph is undirected.
  - Strongly connected when there is a path from any vertex to any other vertex (directed graph). One vertex has access to any other vertex through connected vertices.
  - Weakly connected = when a directed graph that can be turned into a connected graph. Not all vertices have access to all other vertices.

- What are cycles?
  - Cycles are paths in a graph where a vertex can be reached from itself as an origin.

- What are some naive ways we can store and traverse graphs? Be able to discuss time/space complexity of these approaches, and what issues we may face.
  - We can store the vertices and edges of a graph in two lists. The space complexity would be Big O of the number of vertices plus the number of edges. The time complexity would be Big O of the number of edges. An issue is that the number of edges can be almost as much as vertices squared, so that can be very costly in terms of time.


- Dense = too many edges in a graph
- Sparse = too few edges in a graph
- Path(walk) = a sequence of vertices where each adjacent pair is connected by an edge.
  - simple path = no vertices (and no edges) are repeated.
  - trail = a walk in which no edges are repeated.


#### Linked Lists

```
class Node {
  constructor(val, nextNode) {
    this.val = val;
    this.next = nextNode;
  }
}

class LinkedList {
  constructor(value) {
    this.head = new Node(value, null);
    this.add(value);
    this.delete(value);
  }

  add(value) {
    let current = this.head;
    while (current.next !== null) {
      current = current.next;
    }
    current.next = new Node(value, null);
  }

  delete(value) {
    let current.next = this.head;
    if (current.val = value) {
      this.head = current.next;
    } else {
      while (current.next !== null) && (current.next.val !== value) {
        current = current.next;
      }
      if (current.next !== null) {
        current.next = current.next.next;
      }
    }
  }

  showList() {
    let elements = [];
    let current = this.head;
    while (current.next !== null) {
      elements.push(current);
      current = current.next;
    }
    elements.push(current);
  }
}
```
