# Q Learning and SARSA Implementation
This project showcases the implementation of two reinforcement learning algorithms: Q Learning and SARSA. These algorithms are evaluated across various grid world maps to analyze their performance and behavior.

## Key Concepts
### Q Learning
- **Off-policy Learning**: Q Learning is an off-policy reinforcement learning algorithm, meaning it learns from the actions taken by the optimal policy, rather than the ones it actually follows during training.
- **Q-Value Iteration**: Q Learning updates the Q-values of state-action pairs iteratively based on the Bellman equation, aiming to maximize the total expected reward.
- **Exploration vs. Exploitation**: Q Learning balances exploration of new actions with exploitation of learned knowledge to achieve optimal policy.

The Bellman equation for Q-learning is:

Q(s, a) = Q(s, a) + α * (r + γ * max_a Q(s', a) - Q(s, a))

### SARSA
- **On-policy Learning**: SARSA (State-Action-Reward-State-Action) is an on-policy reinforcement learning algorithm, which learns and updates Q-values based on the policy it follows during training.
- **TD Learning**: SARSA uses Temporal Difference (TD) learning to estimate the value of state-action pairs, updating Q-values based on the observed rewards and future state-action pairs.
- **Policy Improvement**: SARSA updates its policy based on the Q-values and the exploration strategy, aiming to improve performance while learning.

The Bellman equation for SARSA is:

Q(s, a) = Q(s, a) + α * (r + γ * Q(s', a') - Q(s, a))

### Perforamance

#### Worlds Description

The different worlds have dimensions NxN and in the most cases the agent starts at the (0,0) coordinate and the target coordinate is represented with the letter F, in the other hand the letter T in the maps represent the teletransportation. Additionaly the X represents obtacles where the agent can't move. 
The solution of the world is represented with this arrows and only this acctions are available:
    - move down (v)
    - move up (^)
    - move right (>)
    - move left (<)

#### Q Learning
- World 1:

Converged after 44 episodes.

 V  X  >  >  V  X  >  >  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 >  >  ^  X  >  >  ^  X  F <br>

- World labyrinth:
  
Converged after 64 episodes.

 V  X  V  X  ^  ^  >  >  V  X  ^  ^  ^  ^  ^  X  X  X  ^  X  ^ <br>
 V  X  V  X  X  X  X  X  V  X  X  X  X  X  ^  <  <  X  ^  X  ^ <br>
 V  X  >  >  V  <  <  <  <  X  V  <  V  X  ^  X  X  X  ^  X  ^ <br>
 V  X  ^  X  V  X  ^  X  ^  X  ^  X  ^  <  >  V  X  V  ^  X  ^ <br>
 >  >  ^  X  V  X  ^  X  X  X  X  X  X  X  X  V  X  ^  X  X  ^ <br>
 X  X  X  X  V  X  ^  <  <  X  >  >  >  >  >  V  X  >  V  <  ^ <br>
 >  >  >  >  V  X  X  X  ^  X  X  X  X  X  X  V  X  X  V  X  ^ <br>
 X  X  X  X  V  X  V  X  ^  X  V  <  <  <  <  <  <  <  <  X  ^ <br>
 V  <  <  X  V  <  <  X  X  X  V  <  X  X  X  X  X  X  X  X  ^ <br>
 V  X  ^  X  V  X  ^  X  >  >  V  X  X  V  <  <  <  <  <  X  X <br>
 V  X  ^  X  V  X  X  X  ^  X  V  X  V  <  X  X  X  X  ^  <  < <br>
 V  X  ^  X  V  X  >  >  ^  X  V  X  V  X  X  V  V  X  X  X  ^ <br>
 V  X  ^  <  <  X  X  ^  X  X  V  X  V  X  >  >  >  >  V  X  ^ <br>
 V  X  X  X  X  X  >  ^  X  >  >  >  >  >  ^  X  X  X  V  X  ^ <br>
 >  >  >  V  X  >  ^  X  X  ^  X  ^  X  X  ^  X  V  <  <  X  ^ <br>
 X  X  X  >  >  ^  X  X  >  ^  X  ^  <  X  X  X  V  X  X  X  X <br>
 >  V  X  X  ^  X  X  X  X  X  X  X  ^  <  <  X  V  X  >  >  V <br>
 X  >  V  X  ^  X  >  >  V  X  >  >  ^  X  X  X  V  X  ^  X  V <br>
 X  X  >  >  ^  X  X  X  V  X  X  X  ^  <  <  X  >  >  ^  X  V <br>
 V  X  X  ^  X  X  V  <  <  <  <  X  ^  X  X  X  X  X  X  X  V <br>
 >  >  >  ^  <  <  <  X  X  X  ^  X  ^  <  <  <  <  V  V  X  F <br>

- CliffWorld:
  - In this world the beggining is at (3,0) coordinate.
    
Converged after 14 episodes.

 V  V  >  V  >  >  V  V  >  >  V  V <br>
 >  >  >  >  >  >  >  >  >  V  V  V <br>
 >  >  >  >  >  >  >  >  >  >  >  V <br>
 ^  X  X  X  X  X  X  X  X  X  X  F <br>

#### SARSA
- World 1:
  
Converged after 119 episodes.

 V  X  >  >  V  X  >  >  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 V  X  ^  X  V  X  ^  X  V <br>
 >  >  ^  X  >  >  ^  X  F <br>

- World labyrinth:
  
Converged after 155 episodes.

 V  X  V  X  >  ^  >  >  V  X  >  >  >  >  V  X  X  X  V  X  ^ <br>
 V  X  V  X  X  X  X  X  V  X  X  X  X  X  V  >  <  X  ^  X  V <br>
 V  X  >  >  V  <  <  <  V  X  >  <  <  X  V  X  X  X  V  X  ^ <br>
 V  X  ^  X  V  X  ^  X  ^  X  ^  X  >  <  >  V  X  V  <  X  V <br>
 >  >  ^  X  V  X  V  X  X  X  X  X  X  X  X  V  X  V  X  X  V <br>
 X  X  X  X  V  X  >  <  V  X  >  >  >  >  >  V  X  >  >  >  V <br>
 >  <  >  >  V  X  X  X  ^  X  X  X  X  X  X  ^  X  X  V  X  ^ <br>
 X  X  X  X  V  X  V  X  ^  X  >  V  <  <  <  <  <  <  ^  X  ^ <br>
 V  <  <  X  V  <  <  X  X  X  V  ^  X  X  X  X  X  X  X  X  ^ <br>
 V  X  ^  X  V  X  ^  X  >  >  V  X  X  V  <  <  >  >  <  X  X <br>
 V  X  ^  X  V  X  X  X  ^  X  V  X  V  <  X  X  X  X  ^  <  V <br>
 V  X  ^  X  V  X  >  >  ^  X  V  X  V  X  X  >  <  X  X  X  ^ <br>
 V  X  ^  <  <  X  X  ^  X  X  V  X  V  X  >  >  >  >  V  X  > <br>
 V  X  X  X  X  X  >  ^  X  >  >  >  >  >  ^  X  X  X  V  X  ^ <br>
 >  >  >  V  X  >  ^  X  X  ^  X  ^  X  X  ^  X  V  <  <  X  ^ <br>
 X  X  X  >  >  ^  X  X  >  ^  X  ^  <  X  X  X  V  X  X  X  X <br>
 >  V  X  X  ^  X  X  X  X  X  X  X  >  <  <  X  V  X  >  >  V <br>
 X  >  V  X  V  X  >  >  V  X  >  >  ^  X  X  X  V  X  ^  X  V <br>
 X  X  >  <  ^  X  X  X  V  X  X  X  ^  <  <  X  >  >  ^  X  V <br>
 V  X  X  ^  X  X  V  <  <  <  <  X  ^  X  X  X  X  X  X  X  V <br>
 >  >  >  ^  V  V  <  X  X  X  ^  X  ^  V  V  <  <  V  <  X  F <br>

- CliffWorld:
- In this world the beggining is at (3,0) coordinate.
  
Converged after 31 episodes.

 >  >  >  >  >  >  >  >  >  >  V  V <br>
 ^  ^  ^  ^  ^  ^  ^  ^  ^  ^  V  V <br>
 ^  ^  ^  ^  ^  ^  ^  ^  ^  ^  >  V <br>
 ^  X  X  X  X  X  X  X  X  X  X  F <br>

#### Comparison

