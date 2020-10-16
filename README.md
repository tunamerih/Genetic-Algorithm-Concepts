Genetic Algorithm

Population = (Number of)Possible Solutions
For Knapsack Problem it is combination of items in our backpack

Each possible combination can be encoded with binary
If an item exist in backpack it is represented with 1 
If an item does not exist in backpack it is represented with 0

For example:

All possible items = Laptop, Sunglasses, Mug, Cellphone, Mouse, Keyboard

Possible Solution 1
Laptop, Sunglasses -> [1,1,0,0,0,0]

Possible Solution 2
Laptop, Mug, Mouse, Keyboard -> [1,0,1,0,1,1]

Possible Solution 3 
Laptop, Sunglasses, Mug, Cellphone, Mouse -> [1,1,1,1,1,0]

Every (item) 1 or 0 is gene.
0 -> gene
1 -> gene
[0,0,1] -> chromosome

The set of all current solutions are called <b>Generation</b>

Natural Selection

We use a Fitness Function to determine how good a given solution is.
In our case the fitness function returns Sum of the weight of items (as long as it fits the weight limit rule)
If weight limit is exceeded, then fitness function returns 0

We are selecting the parents of next solutions
We take two parents and cut their genomes at random spot and switch the endings
This is called single point crossover function and it generates two new solutions for next generation
Example:
Parent 1 -> 1 0 0 1
Parent 2 -> 0 1 1 0

Random point -> * * * [*]
Parent 1 and Parent 2 switches
Parent 1 -> 1 0 0 [1]
Parent 2 -> 0 1 1 [0]

new Parent 1 -> 1 0 0 0
new Parent 2 -> 0 1 1 1

Example 2:
Parent 1 -> 0 0 0 1 1 1
Parent 2 -> 1 1 1 0 0 0

Random point -> * * * [*] * *
Parent 1 and Parent 2 switches
Parent 1 -> 0 0 0 [1 1 1]
Parent 2 -> 1 1 1 [0 0 0]

new Parent 1 -> 0 0 0 0 0 0
new Parent 2 -> 1 1 1 1 1 1

We repeat the process until we have enough solutions(Population(Integer))

Because of randomness there is no guarentee that we dont destroy our best solutions.
That is where elitism comes in. Elitism means we will copy our best n (for example 2) solutions to the next generations untouched.

Using the same gene pool limits our discovery of better solutions.To discover better solutions we use mutations.
During the mutation phase we randomly switch a bit in our binary representations.
Example:
0 0 0 1
  |
Randomly selected spot

0 0 0 1 becomes
0 1 0 1

This loop continues until;
1) No possible solution is found
or
2) For maximum number of generations

Parts needed for genetic algorithms
1) Genetic representation of a solution
2) A function to generate new solutions
3) Fitness Function
4) Selection Function (to select the solutions for next generation)
5) Crossover Function
6) Mutation Function
