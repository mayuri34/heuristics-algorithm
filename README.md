# heuristics-algorithm
Prerequisites:
1. Python 3.6 installed

Description of 8 – Puzzle Formulation: 

The ​8-puzzle​ is a sliding puzzle that consists of a frame of numbered square tiles in random order with one tile missing (tile zero in our case). The object of the puzzle is to place the tiles in order by making sliding moves that use the 0​th​ tile’s space. ​Our program accepts an Initial State and a Goal State in the form of input from user. This state is a representation of a 3x3 matrix with total 9 tiles numbered from 0 to 8. Our aim is to move the tile zero in the directions up, down and sideways with one move at a time in order to obtain the Goal state position of tiles from the Initial state. The logic has been implemented with A* algorithm using two separate heuristics.  

A* Search Algorithm:  

A* Search algorithm is an informed search algorithm which uses an evaluation function at each step, 
f(n) = g(n) + h(n) 
	where, n = node
	g(n) = cost involved so far to reach this node.
	h(n) = heuristic function, approximate cost required to reach the goal via different nodes from this node. 
	
	
The idea of A* Algorithm is to avoid expanding the already costlier nodes to find the most optimal solution. It uses admissible heuristic function which means it never overestimates the h(n) value.  
h(n) <= h*(n), h*(n) is the original cost of path to reach from current node to goal state. In this example two types of Heuristic functions have been implemented.

1. Misplaced Tiles - Where the total number of tiles misplaced from their correct position is calculated as heuristic value. This value is considered to be the optimum steps required to reach the goal state. Hence, its an admissible heuristic.

2. Manhattan Distance - The summation of distance between misplaced location to expected location of each tile is the heuristic value. The heuristic obtained is always less than true cost, hence its also an admissible heuristic.


User Input & Program Results: 
User is expected to enter input of initial and goal states in the form of matrix like structure. Elements in each row should be separated by a space. Use enter for adding data to next row. 
 Enter initial state​:
 (One row at a time,with each element separated by a space)
 1 8 2
 0 4 3
 7 6 5 
 
 Enter goal state​:
 (One row at a time,with each element separated by a space)
 1 2 3
 4 5 6
 7 8 0 
 
Output will consist of results from both the heuristics with the following data: 
1. Path from initial state to goal state 
2. Total cost to reach the goal state (f(n)) 
3. Number of nodes generated (closed nodes) so far 
4. Number of nodes expanded ( open nodes or yet to explore nodes ) so far 