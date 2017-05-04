# Time Complexities

What is important? => Worst Case / Asymptotic


## Notation
### O-Notation
* O(g(n)) ~= Upper bound of f(n)
* O(g(n)) = { f(n): there exist positive constants c and n0 such
that 0 ≤ f(n) ≤ cg(n) for all n ≥ n0}.

## Ω-Notation ("Omega" Notation)
* Ω(g(n)) ~= Lower bound of f(n)
* Ω(g(n)) = { f(n): there exist positive constants c and n0 such
that 0 ≤ cg(n) ≤ f(n) for all n ≥ n0}.

## Θ-Notation ("Theta" Notation)
* Asymptotic tight bound
* Θ(g(n)) ~= Upper + Lower bound of f(n)
* Θ(g(n)) = { f(n): there exist positive constants c1, c2 and n0
such that 0 ≤ c1g(n) ≤ f(n) ≤ c2g(n) for all n ≥ n0}.


## Time
### Basic levels
* O(1) - Constant Time
* O(n) - Linear Time
* O(n^2) - Quadratic Time
* O(n^3) - Cubic Time
* O(n^k) - Polynomial Time
* O(2^n) - Exponential Time
* O(log(n)) - Logarithmic Time
* O(n!) - Factorial Time

### Ranking
Smallest -> Greatest ([ref](http://bigocheatsheet.com/))
1. O(1)
2. O(log(n))
3. O(n)
4. O(n*log(n))
5. O(n^2)
6. O(2^n)
7. O(n!)
