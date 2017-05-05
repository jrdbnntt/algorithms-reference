Breadth-First Search (BFS)
==========================
* A way to visit vertices and edges of a graph, starting with the root and radiating outward, visiting vertices in order of their distance from the root.
* The closer nodes get visited first
* Traverses a connected component of a graph, and in doing so defines a tree
* Basis for many algorithms including spanning trees and single source shortest path

## BFS Algorithm
* A good visualization can be found [here](https://www.cs.usfca.edu/~galles/visualization/BFS.html)

```
/**
 * BFS Algorithm
 * vertex s = source vertex
 * bool flag[|V|]
 */
BFS(flag, s)
    // Mark all vertices that can be visited from S
    for each vertex v:
        flag[v] = false

    Q = empty queue

    // Visit source
    flag[s] = true
    enqueue(Q,s)

    while Q is not empty:
        v = dequeue(Q)
        for each w adj. to v:
            if !flag[w]:
                // Visit previously unvisited vertex
                flag[w] = true
                enqueue(Q,w)

```

### Time complexity
* Adjacency List
    * O(|V| + |E|)
    * O(n + m)
* Adjacency Matrix
    * O(|V|^2)
    *  O(n^2)


## BFS + Path Recording Algorithm
Same algorithm, but we record the predecessor. Then we use the predecessors to walk backward and get the path to any arbitrary node.
```
/**
 * BFS-Path Algorithm
 * vertex s = source vertex
 * bool flag[|V|]
 * vertex pred[|V|]
 */
BFS-Path(flag, s, pred)
    // Mark all vertices that can be visited from S
    for each vertex v:
        flag[v] = false
>       pred[v] = null

    Q = empty queue

    // Visit source
    flag[s] = true
    enqueue(Q,s)

    while Q is not empty:
        v = dequeue(Q)
        for each w adj. to v:
            if !flag[w]:
                // Visit previously unvisited vertex
                flag[w] = true
>               pred[w] = v
                enqueue(Q,w)

```
