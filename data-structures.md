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

- What are cycles?

- What are some naive ways we can store and traverse graphs? Be able to discuss time/space complexity of these approaches, and what issues we may face.


- Dense = too many edges in a graph
- Sparse = too few edges in a graph
