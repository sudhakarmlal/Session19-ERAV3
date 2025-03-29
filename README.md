# reinforcement_learning grid world
Value based reinforcement learning on gird world

## Problem Statement

You are given a 4x4 GridWorld where an agent starts at the top-left corner (state 0) and tries to reach the bottom-right corner (state 15). The agent can move up, down, left or right with equal probability. The rewards are -1 for each move, and the terminal state (bottom-right) has a reward 0. There are no obstacles. Your task is to:

    - initialize V(s) to 0 for all states
   -  Iteratively apply the Bellman equation until convergence:    
    where P(s'|s, a) is the transition probability (equal for all moves)
    Use gamma = 1 (no discounting)
    Stop when maximum change in V(s) across all states is < 1e - 4

## Pseudocode:

Initialize:
    set grid size (NxN)
    Define rewards for each state (-1 per move, 0 for terminal state)
    initialize value function V(s) = 0 for each states
    set discount factor (gamma) and convergence threshold (theta) 

Define possible actions: up, down, left, right.
Repeat until value converges:

    track maximum changes in values
    create a copy of current value function V_new
    for each state s (excluding the terminal state):
        compute new value using the Bellman Equation:
            for each action, calculate:
                next state s' (handling grid boundaries)
                expected value update: sum over all possible s'
            update V_new(s)
            track max change (to see if converged)
        Set V = V_new (update value function)
        if threshold reached, then stop

## Result:

-44.57  -43.57  -41.21  -38.78

-43.57  -41.93  -38.28  -34.35

-41.21  -38.28  -31.64  -23.00

-38.78  -34.35  -23.00  0.00

