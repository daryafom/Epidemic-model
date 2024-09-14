# Epidemic Agent-Based Model
This repository implements a simple agent-based epidemic model. The simulation consists of multiple agents scattered across a 2D plane. Each agent can be in one of several states, and they move and interact according to predefined rules, which drive the spread of infection and recovery.

## Agent States
0. **Healthy** (State 0)
Can move freely within a certain distance (d1) in any direction.
May become infected if near an infected agent.

1. **Infected** (State 1)
Moves similarly to a healthy agent.
Infects other healthy agents within distance d2 with a probability p1.
After a time period of td1 steps, either recovers (moves to State 4) or progresses to a more severe condition (State 3).

2. **Mildly Sick** (State 2)
Movement range is reduced to d1/2.
Has a higher chance of infecting others within the same radius, with a probability p2, where p2 > p1.

3. **Severely Sick** (State 3)
Movement is limited to a smaller radius d2.
Infects others within range with a higher probability p3, where p3 > p2.
Has a probability pd1 of dying within a time period td2 steps. If the agent survives, it transitions to State 4.

4. **Immune** (State 4)
Cannot be infected or infect others.
Moves freely like a healthy agent.

## Simulation
The simulation runs for a total of 10 steps, where at each step:
The agents move according to their current state.
Agents interact with others within the infection radius.
The state of the simulation is updated based on infection, recovery, or death probabilities.
At each step, key statistics such as the number of agents in each state (healthy, infected, mildly sick, etc.) are calculated and displayed. These statistics can also be plotted to visualize the progression of the epidemic over time.
