# CI2024_lab2

### Problem specifications
Given a list of cities and the distances between
each pair of cities, what is the shortest possible
route that visits each city exactly once and
returns to the origin city?


Solve the given TSP instances using both a fast but approximate algorithm and a slower, yet more accurate one.
Report the _final cost_ and the number of _steps_

### References
https://www.wolframcloud.com/obj/giovanni.squillero/Published/Lab2-tsp.nb

### Notes about Genetic Algorithms (GA)
In EA, there are 4 main components:
1) **Generational model Vs Steady-state model**
    - Generational: Offspring replace parent, then they are selected for survival
    - Steady-state: Offspring are added to the population, then they
    compete against parents for survival
2) **Parent Selection**
    - Uniform: every individual has the same probability to be selected
    - Roulette Wheel: choose an individual randomly from a set according to the relative weights
    - Fitness-proportional
    - Rank-based: Rank population according to fitness and then
    base selection probabilities on rank
    - Tournament selection: pick t members at random then select the best out of these
3) **Survivor selection**
    - usually deterministic (the best ones according to the fitness function)
4) **Genetic operators**:
    - Historic algortimhs flow: 
        1. select parents
        2. mutate them with probability p
        3. performf crossover with probability q
    - Modern algortimhs flow:
        1. select parents
        2. perform crossover
        3. mutate the offspring with probability p
    - Hyper-modern algortimhs flow:
        1. select a genetic operator with probability p
        2. select the correct number of parents (i.e. 1 for mutations)
        3. generate offspring

#

TSP is a _one-time items_ problem. 

For these type of problems it's possible to apply Scramble Mutation, Insert Mutation, **Inversion Mutation**, Order Crossover, Partially Mapped Crossover, Cycle Crossover, Edge Recombination Crossover, Position-Based Crossover, Order-Based Crossover, Precedence Preservative Crossover, **Inver Over**. Try to apply someone of them (in bold, operators suggested by the teacher for TSP).

#

My thoughts:
- _Individual_ (genome) is an array of all cities (considered one time)
- _Fitness function_ is given by the negative distance of the whole path (sum of all distances between adjacent cities in the array + distance from the last city in the array to the first one, since we have to come back in the initial city) --> fitness = - tot_distance
- For the rest, try different approaches (generational or steady-state) and different parent selection, survivor selection, genetic operators.


