# Activity Selection Problem

## Problem
* n *activities* (jobs) require *exclusive* use of a
common resource. For example use of a classroom.
* Set of activities S = {a_1, …, a_n}
* job a_j needs resource during period [s_j, f_j)
    * s_j is the start time of the job
    * f_j is the finish time of the job
* Goal: select the largest possible set of non-overlapping (mutually compatible) jobs


## Greedy Algorithm

### Take Options
Which activity should you select next? Possible options include:
* **Earliest Finish Time** => GOOD
    * The *Latest Start Time* is the same concept, but in reverse
* *Earliest Start Time* => bad, it could be very long and overlap multiple
* *Shortest Interval* => bad, short could overlap multiple
* *Fewest Conflicts* => bad, more conflicts could still be have one that is the better choice

### Procedure
1. Sort by finish time, ascending
2. Pick in that order as long as they are compatible with the last chosen

### Example 1
#### Question
Form {(i, a_is, a_if)...}
Activities = {(1, 4, 5), (2, 3, 6), (3, 2, 5), (4, 5, 8), (5, 8, 9)}

#### Solve
It is best to make a chart of all the activities and their times to check incompatibilities easily.
* Sort by end time = (1, 4, 5), (3, 2, 5), (2, 3, 6), (4, 5, 8), (5, 8, 9)
* Choose activity #1
* Activity #3 is incompatible with #1
* Activity #2 is incompatible with #1
* Choose activity #4
* Choose activity #5

#### Solution
We choose the following activities: {#1, #4, #5} => {(1, 4, 5), (4, 5, 8), (5, 8, 9)}.

*Note: The answer may differ based on how ties in finish times are handled*
