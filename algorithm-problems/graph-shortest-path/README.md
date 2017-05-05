Shortest Path
=============
* Problem Variants
    * **Single-source**: Find shortest paths from a given source vertex s ∈ V to every vertex v ∈ V .
    * **Single-destination**: Find shortest paths to a given destination vertex.
    * **Single-pair**: Find shortest path from u to v. Known algorithms are not better in worst case than solving singlesource.
    * **All-pairs**: Find shortest path from u to v for all u, v ∈ V.
* Shortest paths may not contain cycles

## Algorithm Output
For each vertex v ∈ V:
* v.d = δ(s, v)
    * Initially, v.d = ∞.
    * Reduces as algorithms progress. But always maintain v.d ≥ δ(s, v)
    * Call v.d a **shortest-path estimate**.
* v.π = predecessor of v on a shortest path from s.
    * If no predecessor, v. π = NIL.
    * π induces a tree => **shortest-path tree**.
    * "parent" node pointer
* Initialization
    * All the shortest-paths algorithms start with INIT-SINGLE-SOURCE.

### INIT-SINGLE-SOURCE Algorithm
```
INIT-SINGLE-SOURCE (G, s)
    for each v ∈ G.V:
        v.d = ∞
        v.π = NIL
        s.d = 0
```

## Relaxing an edge (u, v)
* Can we improve the shortest-path estimate for v by going through u and then taking (u, v?)
    * Is r -~-> u -> v cheaper than r -~-> v (current est.)?

```
RELAX(u, v, w):
    if v.d > u.d + w(u, v):
        v.d = u.d + w(u, v)
        v.π = u
```

* Algorithms differ in the order and how many times they relax an edge.
* “Relaxing” can also simply be viewed as relabeling a node v, given the information at u and the edge (u, v)
