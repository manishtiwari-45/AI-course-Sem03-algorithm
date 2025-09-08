**A* Pathfinding Adventure: A Visual Guide to Heuristics**

Welcome to this interactive exploration of the A* (A-Star) search algorithm! This project is designed for beginners to see, with their own eyes, how A* finds the shortest path in a maze and how its performance changes based on the "heuristic" or guessing strategy it uses.

We will implement A* from scratch and run three experiments to test:

A perfect heuristic.
A non-admissible (pessimistic) heuristic.
An inconsistent (unreliable) heuristic.

Let's dive in!

**what is A* Search, Anyway?**
Imagine you need to get from your home (start) to a friend's house (goal) in a city with lots of streets and buildings. How would you find the shortest route? You wouldn't just wander randomly. You'd probably use a map and try to head in the general direction of your friend's house.

A* works just like that! For every possible step it can take, it calculates a score called the f-score. The path with the lowest f-score is explored first.

The score is calculated with a simple formula:

f(n) = g(n) + h(n)
Where:
n is the next possible square (or "node") on the path.
g(n) is the actual cost of the path from the start to this square n. (Think of it as the distance you've already traveled).
h(n) is the heuristic or estimated cost from the square n to the goal. (This is our "smart guess" of the remaining distance).
The magic of A* lies in the h(n) part—the heuristic. Let's look at what makes a heuristic good or bad.

**The Brain of A*: Understanding Heuristics**

A heuristic is just a function that helps A* make smart decisions. But for A* to work perfectly, its heuristic must follow two important rules.

**1. Admissible Heuristic (The Optimist )**
An admissible heuristic is always optimistic. It never overestimates the actual cost to get to the goal.

The Rule: The guessed cost must be less than or equal to the real cost.
h(n) ≤ true_cost(n)

Think of it this way: If the goal is 10 steps away, an admissible heuristic might guess it's 8 steps away, or 10, but it will never guess it's 11 steps away. This optimism is key to finding the shortest path.

**2. Consistent Heuristic (The Logical Guide )**
A consistent heuristic follows the "triangle inequality." It means that as you move from one square to a neighbor, the heuristic cost shouldn't drop by more than the cost of that single step.

The Rule: h(current) ≤ cost(current, neighbor) + h(neighbor)

This makes the search logical and efficient. It prevents the algorithm from getting confused by wild jumps in its own estimates.

**How to Run This Project**
This project is in a Jupyter Notebook (A_Star_Experiments.ipynb). It's easy to run!