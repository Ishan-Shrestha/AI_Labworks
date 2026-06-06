# Lab-1: Intelligent agents and problem formulation:

## Objectives:
1. To implement depth first search algorithm with backtracking to solve various problems.
2. To implement Dijkstra algorithm to find cost efficient path.

## Theory:

### Intelligent Agents:
Agents are the entities that perceives the environment through the sesnsors, processes the data ti build a world model and execute actions through the actuators.

```text
       +-----------------------------------------+
       |               Environment               |
       +-----------------------------------------+
            |                               ^
            | Sensors                       | Actuators
            v                               |
       +-----------------------------------------+
       |                AI Agent                 |
       |  [Perceive -> Formulate -> Optimize]    |
       +-----------------------------------------+

       fig: simple agent workflow
```
**Types of Agents:**
- **Simple Reflex Agents:** operate on a basis of direct condition-action rule, if particular condition>particular action else another action
- **Model-Based Agents:** operates on basis of rules + internal history, It combines its current sensory input with its memory of past states to guess how the unobserved world is evolving.
- **Goal-Based Agents:** operates on basis of targets & Search/Planning, The agent evaluates multiple possible sequences of actions to see which path will lead to the goal state.
- **Utility-Based Agents:** operates on basis of optimization Functions, It rates different trade-offs on a continuous scale of utility (e.g., scoring paths from 0 to 100).
- **Learning Agents:** operates on basis of self-generated feedback, It begins operating in an unfamiliar environment and learns from its own experiences to improve its performance over time.

### Problem Formulation:
In Agentic AI, the strategy an agent uses to find a solution depends heavily on how the problem is structured. Problems are generally classified into two major structural types based on whether they require the optimization of a path or the strict fulfillment of environmental constraints.

**Well-Defined Problems:**
A problem is considered well-defined if its initial state, operators, transition models, and goal criteria are explicitly stated without ambiguity. In AI, well-defined problems are typically formulated as a Graph-Based Search Space, where nodes represent states and edges represent actions with specific path costs.
**Core Attributes:**
- **Explicit State Space:** The agent knows exactly what constitutes a valid configuration and how to transition from state A to state B.
- **Path-Dependent Cost Optimization:** The path taken to reach the goal state matters. 

**Constraint Satisfaction Problems (CSPs):**
A Constraint Satisfaction Problem is a mathematical problem where the solution must meet a number of constraints. In A Constraint Satisfaction Problem the objective is to assign values to variables such that all the constraints are satisfied.
**Core Attributes:**
- **Goal-State Focus:** The agent does not care about how many steps it took to fill a board; it only cares that the final configuration breaks zero constraints.
- **Uninformed State-Space Pruning:** Because the agent has no mathematical heuristic to calculate how close it is to a solution, it must build a State-Space Decision Tree and guess values systematically.

### Algorithms used:
- **Backtracking algorithm**
The backtracking algorithm is a depth-first search method used to systematically explore possible solutions in CSPs. It operates by assigning values to variables and backtracks if any assignment violates a constraint.
**How it works:**
- select a variable and assign it a value.
- recursively assigns value to subsequent variable.
- If a conflict arises i.e a variable cannot be assigned a valid value then algorithm backtracks to the previous variable and tries a different value.
- The process continues until either a valid solution is found or all possibilities have been exhausted.

## Discussion
The implementation of the Maze Explorer, Sudoku Solver, and Network Router exposes the fundamental realities of designing intelligent agents. The behavior of these agents proves that an algorithm's performance is completely dependent on how the underlying problem space is formulated.

In the Constraint Satisfaction Problems, the Maze and Sudoku, the agents operate blindly without a mathematical heuristic to judge distance to a goal while in well defined problems we use Dijkstra algorithm to give a optimal cost efficient path.

## Conclusion
The development and systematic analysis of these three distinct agent architectures reveal clear architectural lessons regarding intelligent system design:
- Problem Formulation Defines the Algorithm: The mathematical definition of the state-space dictates the boundaries of agent capability. If an environment features uniform, unweighted steps (like our Maze or Sudoku boards), uninformed search with backtracking remains the most effective strategy to verify feasibility.
- Weighted Environments Enable Optimization: : The moment an environment introduces varied edge weights, trial-and-error exploration becomes highly inefficient. By formalizing explicit cost metrics, greedy optimization algorithms like Dijkstra can replace backtracking entirely, trading graph frontier memory for deterministic speed.