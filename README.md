# 8-Puzzle Solver
This repository contains a Python implementation for solving the 8-puzzle game using various search algorithms.

# Table of Content
- [Puzzle Structure and Objective](https://github.com/KimiyaVahidMotlagh/8PuzzleSolver#puzzle-structure-and-objective)
- [Search Algorithms Implementation](https://github.com/KimiyaVahidMotlagh/8PuzzleSolver#search-algorithms-implementation)
- [Puzzle Generation and Solvability](https://github.com/KimiyaVahidMotlagh/8PuzzleSolver/blob/main/README.md#puzzle-generation-and-solvability)
- [User Interaction and Puzzle Solving](https://github.com/KimiyaVahidMotlagh/8PuzzleSolver/blob/main/README.md#user-interaction-and-puzzle-solving)
- [Conclusion](https://github.com/KimiyaVahidMotlagh/8PuzzleSolver/blob/main/README.md#conclusion)

# Puzzle Structure and Objective
The 8-puzzle game consists of a 3x3 grid with 8 numbered tiles and one empty space. The goal is to move the tiles until they are in order from 1 to 8, with the empty space at the end. Solving the puzzle requires
ransitioning from an initial disordered state to the ordered goal state through a series of tile movements.

# Search Algorithms Implementation
The code includes implementations of various search algorithms:

- Breadth-First Search (BFS): Explores the puzzle state space level by level, ensuring the shortest path to the solution.
- Depth-First Search (DFS): Explores as far as possible along each branch before backtracking, suitable for deep state spaces.
- Iterative Deepening Search (IDS): Combines the depth-first search's space-efficiency and breadth-first search's completeness.
- A* Search: Uses a heuristic function (Manhattan distance) to guide the search towards the goal state more efficiently.
- Iterative Deepening A (IDA): Integrates the benefits of IDS and A* search, using a cost threshold to limit the search.
- Recursive Best-First Search (RBFS): An advanced variant of A* search that uses recursion to find the least costly path.
- Bidirectional Search: Simultaneously searches from both the initial state and the goal state, meeting in the middle. <br/>
Each algorithm utilizes specific functions for expanding nodes, building paths, and calculating costs or distances.

# Puzzle Generation and Solvability
The functions relevant to creating and assessing the solvability of the puzzle are as follows:

- generate_random_puzzle(moves=100): This function generates a random initial state for the 8-puzzle. It starts with the puzzle in its goal state and makes a series of random moves (default 100) to shuffle the tiles. This approach 
ensures the generated puzzle is solvable.
- is_solvable(state): This function determines whether a given puzzle state is solvable. The solvability of an 8-puzzle is based on the number of inversions (where a larger numbered tile precedes a smaller numbered tile in the puzzle 
sequence). For the puzzle to be solvable, the number of inversions must be even.
- move_tile(state, direction): This function takes the current state of the puzzle and a direction (up, down, left, right) as inputs. It moves the blank space (represented by '0') in the specified direction if possible, resulting in a new state of the puzzle. <br/>
These functions play a crucial role in setting up the puzzle for the searc

# User Interaction and Puzzle Solving
The script allows for user interaction to input custom puzzle states. It checks the solvability of the input puzzle and applies the appropriate search algorithm to find a solution. get_initial_state_from_user function Prompts the user to input a custom initial state 
for the puzzle, validating the input for correctness and solvability. Then using any of search algorithms will solve the initial state,print solution path and depth: If a solution is found, it prints the sequence of moves and the depth of the solution.

# Conclusion
This project demonstrates the application of various search algorithms to solve the 8-puzzle. Each algorithm has its unique characteristics:

- Breadth-First Search (BFS) ensures the shortest path but can be memory-intensive.
- Depth-First Search (DFS) is memory-efficient but may find suboptimal solutions.
- Iterative Deepening Search (IDS) combines BFS's completeness with DFS's space efficiency.
- A* Search is efficient and optimal with an appropriate heuristic.
- Iterative Deepening A (IDA)** reduces memory usage of A* at the expense of increased computation.
- Recursive Best-First Search (RBFS) optimizes memory usage while maintaining A*'s properties.
- Bidirectional Search can significantly reduce search time by simultaneously searching from both ends. <br/>
The choice of algorithm depends on the specific requirements of space efficiency, optimality, and execution time. This project illustrates the practical trade-offs between these algorithms in a real-world problem.

