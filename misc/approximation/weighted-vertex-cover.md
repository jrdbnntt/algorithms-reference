Approximation: Weighted Vertex Cover as Integer Linear Program
==============================================================

## Integer Linear Program (ILP) Algorithm
```
min(Σ_{v ∈ V}(w(v) x_v))

Subject to:
x_u + x_v ≥ 1 for each {u, v} ∈ E
x_v in {0, 1} for each v ∈ V
```

=> Select the minimum sum of the weights of the included vertex
* x = 1 => included
* x = 0 => not included
* First subjection is to make sure at least one of the two vertices of every edge are covered
* Second subjection is to say x may either be *only* included (1) OR excluded (2)

## Linear Program (LP) Relaxation
```
min(Σ_{v ∈ V}(w(v) x_v))

Subject to:
x_u + x_v ≥ 1 for each {u, v} ∈ E
x_v ≥ 0 or each v ∈ V
```

* Same as above except for the fact that x_v may now be a range of values
* To get the real answer you must convert each x back to either 0 (exclude) or 1 (include) by rounding it.
    * if `x >= 0.5`, then round to 1, otherwise to 0
* Still gives vertex cover, because for any edge, at least one end must have been `>= 0.5` in the LP


## Approximating LP
* `OPT_LP <= OPT_ILP`
    * So, `APPROX <= 2*OPT_LP <= 2*OPT_ILP`
* We can use OPT_LP and APPROX to get an **a-posteriori** bound


## Example
Given the following LP solution, calculate approximate a solution, a-priori & a-posteriori bounds and determine the quality of the approximation.

**LP:**

| v | x | w(v) |
| --- | --- | --- |
| 1 | 0.1 | 1 |
| 2 | 0.9 | 4 |
| 3 | 0.5 | 3 |
| 4 | 0.6 | 10 |
| 5 | 0.1 | 4 |

### Solution
Convert to ILP via rounding

**ILP:**

| v | x |
|--- | --- |
| 1 | 0 |
| 2 | 1 |
| 3 | 1 |
| 4 | 1 |
| 5 | 0 |

* `Approx = 1*0 + 4*1 + 3*1 + 10*1 + 4*0 = 21`
* `21 <= 2 OPT_ILP` (a-priori)
* `10.5 <= OPT_ILP` (a-posteriori)
* Quality = a-priori/approx, `21/10.5`

Answer
* Approximation = 21
* a-posteriori bound = 21
* a-priori bound = 10.5
* Quality = within 50% of optimal
