Approximation Algorithms
========================
It does not appear feasible to solve NP-hard problems in polynomial time
* Can we find an approximate solution instead?
    * The approximate solution should certainly be feasible
    * Ideally, we need to give **a-priori** bounds for the quality of the solution
    * We may also be able to give an **a-posteriori** bound after solving the problem
* For example, for a minimization problem, we may guarantee that the approximate solution is at most twice the optimal solution: Approx ≤ 2 OPT
    * How can we give a bound if we cannot calculate the value of the optimal solution?

## Self-Reducibility
* NP-hard problems are usually self-reducible
    * If you can solve the decision problem in polynomial time, then you can find the solution in polynomial time
* Example: Vertex Cover Problem
    * Given a graph G = (V, E), a vertex cover is a subset V’ ⊆ V such that if (u, v) is an edge of G, then either u ∈ V’ or v ∈ V’
    * Find a vertex cover of smallest cardinality
* If the decision problem can be solved, then the size of the vertex cover too can be found in |V| or lg |V| iterations of the decision problem
    * Solve the decision problem (G, k) for k between 1 and |V| - 1
    * The smallest k with a ‘YES’ answer is the optimum

## Approximation
* It is not realistic to expect to find the value of the optimum solution for NP-hard problems
    * Instead, find bound, OPT_B, on the solution
* Let OPT_B ≤ OPT
    * If we can prove APPROX ≤ 2 OPT_B, then APPROX ≤ 2 OPT
* **Approximation ratio**: ρ(n)
    * max( APPROX/OPT, OPT/APPROX) ≤ ρ(n)
    * We want ρ(n) as close to 1 as possible
    * Note: Some use approximation factor: δ(n)
* APPROX ≤ δ(n) OPT for minimization
* APPROX ≥ δ(n) OPT for maximization

## Approximation Types
* ρ(n) may be an increasing function of n
    * Ideally, we want it to be small, and close to 1
    * Many algorithms have constant ρ(n)
* Polynomial time approximation scheme (PTAS)
    * For any ε, the scheme can produce a (1 + ε) approximation in time polynomial in n
        * Example time complexities: n^2(1/ε), n^{2/ε}
* Fully polynomial time approximation scheme (FPTAS)
    * For any ε, the scheme can produce a (1 + ε) approximation in time polynomial in n and 1/ε
        * Example time complexities: n^2(1/ε), but not n^{2/ε}
    * FPTAS is the best one can hope from an NP-hard problem
