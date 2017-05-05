Graph Basics
============

* A *graph* is a collection of vertices (V) that may be connected by edges (E).
* A *digraph* is a graph with directed edges.
* Weights may be applied to edges
* |V| = total number of vertices
* |E| = total number of edges
* **Handshaking Theorem** - 2|E| = sum of all vertex degrees

## Terms
* Degree of vertex = num. of adj vertices
    * In/out degrees for digraphs

## Representation
Example digraph:
```
 1 ------> 2
   \       |
     \     |
       \   V
         > 3
```

### Adjacency Matrix
```
  123
 +---
1|000
2|100
3|110
```

### Adjacency List
Store adjacencies in a Linked List
```
1 -> [2] -> [3] -> null
2 -> [3] -> null
3 -> null
```
