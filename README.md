# CS-520
Projects
CS 520 : Project 1 - Voyage Into the Unknown
This project is intended as an exploration of a variant of the A* search algorithm covered in class, in the traditional
application of Robotic Path Planning. In particular, we are going to look at a situation where the environment is
not fully known in advance, and must be learned by the agent as it moves through it.
A gridworld is a discretization of terrain into square cells that are either unblocked (traversable) or blocked. Consider the following problem: an agent in a gridworld has to move from its current cell (S) to a goal cell, the location of
a stationary target. The layout of the gridworld (what cells are blocked or unblocked) is unknown. These kinds of
challenges arise frequently in robotics, where a mobile platform equipped with sensors builds a map of the world as it traverses an unknown environment

Assume that the initial cell of the agent is unblocked. The agent can move from its current cell in the four main
compass directions (east, south, west, north) to any adjacent cell, as long as that cell is unblocked and still part of
the gridworld. All moves take one timestep for the agent, and thus have cost 1. (We can consider this in terms of
energy consumption for the agent, for instance.) The agent always knows which (unblocked) cell it is currently in,
and which (unblocked) cell the target is in. The agent knows that blocked cells remain blocked and unblocked cells
remain unblocked but does not know initially which cells are blocked. However, it can observe or sense the
status of some of its surrounding cells (corresponding to its field of view) and remember this information for future
use. By exploring the maze, collecting information on blockages, and integrating that into the whole, the agent must
reach the target as efficiently as possible.
We may structure a basic agent in the following way: the agent assumes that all cells are unblocked, until it observes
them to be blocked, and all path planning is done with the current state of knowledge of the gridworld under this
freespace assumption. In other words, it moves according to the following strategy:
??? Based on its current knowledge of the environment, it plans a path from its current position to the goal.
??? This path should be the shortest (presumed) unblocked path available.
??? The agent attempts to follow this path plan, observing cells in its field of view as it moves.
??? Observed blocked cells or unblocked cells are remembered, updating the agent???s knowledge of the environment.
??? If the agent discovers a block in its planned path, it re-plans, based on its current knowledge of the environment

1 Implementation
2 Execution, Analysis, and Report
In order to analyze algorithms for this problem, we need to generate consistent environments for comparison. Do
the following: for a dim by dim array, let each cell independently be blocked with probability p, and empty with
probability 1 ??? p. Exclude the upper left corner (chosen to be the start position) and the lower right corner (chosen
to be the end position) from being blocked. Write a function to generate random gridworlds in this way for a given
value of p (0 < p < 1)

???????????????????????????????????????????????????????????????Q122929048?????? codingtutor
