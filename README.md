# Reinforcement-learning
# 1. Implementation of Monte Carlo Off policy - Monte Carlo Methods sample and average returns for each state-action pair. On-policy methods attempt to evaluate or improve the policy that is used to make decisions. Off-policy methods evaluate or improve a policy different from that used to generate the data.

➢ The main difference between Monte Carlo control and Off-policy MC control is that, Offpolicy evaluates and improves the optimal policy, allowing the agent to explore without damaging the State-Action values. Here, the method has two policies,
• Target Policy, which is a policy that is being learnt, which becomes the optimal policy, and
• Behaviour Policy, which is based on the behaviour,
➢ The idea here is that we use one policy to explore the state-action space, while we construct an optimal deterministic greedy policy.
➢ This is not the case in Monte Carlo control (On-policy), where the agent must perform nonoptimal behaviour to learn the State-Action values.


# 2. Solving Reinforcement Learning Taxi problem: 
 Problem specification:
Starting at a random state, our job is to get the taxi to the passenger’s location, pick up the passenger and drive to the destination, drop the customer, and then the episode ends.
There are 4 designated locations in the grid indicated by Red — 0 , Green — 1, Yellow — 2, and Blue — 3, the blue letter correspond to pick up location and purple letter indicate the drop off location. The solid lines indicate walls that the taxi cannot pass, whereas the filled rectangle is the taxi, when it is yellow it is empty and when it is green it is carrying a passenger.
Each state is defined by a 4 entries tuple: （taxi_row, taxi_col, passenger_location, destination). For example, the image shows state (2,3,2,0), which means we are at position row index 2 (note that python index start at 0 so this means row 3), and column index 3, the passenger is at Yellow, encoded by 2 and our destination is red, encoded by 0.
State Space: We can see that our state space consist of 500 possible states, with 25 possible taxi positions, 5 possible locations of the passenger (including the case when the passenger is in the taxi), and 4 destination locations
Action space: There are 6 discrete deterministic actions: 0 — move south, 1 — move north, 2 — move east, 3 — move west, 4 — pickup passenger , 5 — drop off passenger
Rewards: Except for delivering the passenger with gets a reward of +20, each extra step has a penalty of R=-1, executing “pickup” and “drop-off” actions illegally results in R=-10
