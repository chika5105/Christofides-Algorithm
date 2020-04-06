# Christofides-Algorithm
This code implements the Christofides' Algorithm to find the shortest path (least distance) between 15 of the biggest airports in the United States. 
Christofides' algorithm is a complex algorithm that gives an approximate solution to the travelling salesman problem. This means that it doesn't necessarily provide the exact solution but guarantees a solution that is very close to the exact solution (which has been proven to be within 1.5 times the global optimum). The input of this algorithm is a graph which will be represented as a priority heap data structure (with justification given below) that contains the vertices (cities here) and the weighted edges between any two of the routes. These vertices and weighted edges will be stored as a key, value pair in a python dictionary. The algorithm can broken down into 6 stages. This #breakitdown approach is useful because the algorithm is very complex and it would be difficult to solve it without breaking it down. Again the division of the problem into smaller functions makes it easier for us to code because we'll be re-using some bits of code which will be packed into functions instead of coding the same logic over and over again.

1. Produce a minimum spanning tree (MST). A tree that contains all the vertices of a graph G is a spanning tree and a spanning tree T with the smallest possible weight is called a minimum spanning tree. The process of finding an MST is greedy which implies that we're not guaranteed a solution that is the global minimum. Here, all edges are sorted in an increasing order. We then initialize a new tree C. In each iteration, we choose the smallest available edge and add this edge to C (as long as it doesn't form a cycle) until all vertices have been reached. This part of Christofides' algorithm can be implemented using 2 known algorithms known as Prim-Jarnik's algorithm and Kruskal's algorithm. I would use Kruskal's algorithm because the running time is O(mlogn) which is more efficient than Prim's algorithm with O(n 2 ) for an unsorted list.
2. Extract all the odd vertices in this MST.
3. Connect each odd vertex in the graph to exactly one other odd vertex to create a perfect matching. A perfect matching is a set of edges that meet each of the odd vertices exactly once.
4. Add the edges produced into the minimum spanning tree.
5. Produce and Eulerian tour of the resulting graph. An Eulerian tour is a means of graph traversal that visits every edge once.
6. Take shortcuts by removing vertices that repeated.
7. At the end, the solutions of these 6 sub-problems will be summed to produce the final solution of this TSP.