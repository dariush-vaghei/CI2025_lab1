# CI2025_lab1
Solution of the three instances of the multiple 1-0 knapasack problem.


# Simulated Annealing (SA) for problem 01
The algorithm uses Simulated Annealing to explore the solution space of a multi-dimensional knapsack problem by probabilistically accepting worse solutions early on to escape local optima. It gradually cools the temperature to converge toward high-value feasible solutions.

## Steps:
- Generate an initial solution using a greedy heuristic.
- Evaluate its value and constraint violations to compute the current “energy.”
- Repeat until maximum iterations or minimum temperature:
  - Generate a neighboring solution by randomly moving an item to another knapsack.
  - Compute the neighbor’s energy
  - Accept the neighbor if it improves energy or with a probability based on temperature.
  - Update best feasible and overall solutions if applicable.
- Gradually decrease the temperature according to the cooling rate.
- Return the best feasible solution and best overall solution found.


# Tabu Search for problem 02
The algorithm uses Tabu Search to iteratively explore the solution space of a multi-dimensional knapsack problem, avoiding cycles by keeping a memory of recent moves (tabu list). It balances exploration and exploitation, accepting the best non-tabu neighbor or aspirational moves to improve solution quality.

## Steps:
- Construct an initial feasible solution using a greedy heuristic.
- Initialize a tabu list to track recent moves and avoid cycling.
- Repeat until maximum iterations:
  - Generate a set of candidate neighbor solutions by randomly moving items to other knapsacks.
  - Evaluate neighbor solutions using value minus penalty for constraint violations.
  - Apply tabu rules: skip tabu moves unless they improve the best feasible solution.
  - Select and apply the best allowed move, update current solution and tabu list.
  - Update best feasible and best overall solutions if the move improves them.
- Return the best feasible solution found and the best overall solution.


# Iterated Local Search (ILS) for problem 03
The algorithm uses Iterated Local Search (ILS) to solve the multi-dimensional knapsack problem by repeatedly improving a candidate solution through local search and occasional perturbations. It balances exploration and exploitation to find high-value feasible solutions efficiently.

## Steps:
- Generate an initial solution using a greedy heuristic.
- Perform incremental local search to improve the solution.
- Perturb the current solution to escape local optima.
- Apply local search to the perturbed solution.
- Accept the new solution if it improves the score or probabilistically otherwise.
- Update the best feasible and overall solutions found so far.
- Repeat steps 3–6 until the maximum iterations or time limit is reached.
