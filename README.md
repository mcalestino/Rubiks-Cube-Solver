# Rubiks-Cube-Solver

This program was done for an Algorithm Design class. It was and still is my favorite class for my Computer Science 
graduate studies.

Problem 6-3. Rubik’s Cube
In this problem, you will develop algorithms for solving the 2 × 2 × 2 Rubik’s Cube, known as the
Pocket Cube. Call a configuration of the cube “k levels from the solved position” if it can reach
the solved configuration in exactly k twists, but cannot reach the solved configuration in any fewer
twists.
The rubik directory in the problem set package contains the Rubik’s Cube library and a graphical
user interface to visualize your algorithm.
We will solve the Rubik’s Cube puzzle by finding the shortest path between two configurations
(the start and goal) using BFS.
A BFS that goes as deep as 14 levels (the diameter of the pocket cube) will take a few minutes (not
to mention the memory needed). A few minutes is too slow for us: we want to solve the cube very
quickly!
Problem Set 6 3
Instead, we will take advantage of a fact that we saw in lecture: the number of nodes at level 7
(half the diameter) is much smaller than half the total number of nodes.
With this in mind, we can instead do a two-way BFS, starting from each end at the same time, and
meeting in the middle. At each step, expand one level from the start position, and one level from
the end position, and then check to see whether any of the new nodes have been discovered in both
searches. If there is such a node, we can read off parent pointers (in the correct order) to return the
shortest path.
Write a function shortest path in solver.py that takes two positions, and returns a list of
moves that is a shortest path between the two positions.
Test your code using test solver.py. Check that your code runs in less than 5 seconds
