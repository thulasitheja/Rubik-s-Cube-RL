# Rubik's Cube
The Rubik's Cube is a 3-D combination puzzle invented in 1974 by Hungarian sculptor and professor of architecture Ernő Rubik.

## Move notation:
Many 3×3×3 Rubik's Cube enthusiasts use a notation developed by David Singmaster to denote a sequence of moves, referred to as "Singmaster notation". 
Its relative nature allows algorithms to be written in such a way that they can be applied regardless of which side is designated the top or how the colours are organised on a particular cube.

* F (Front): the side currently facing the solver
* B (Back): the side opposite the front
* U (Up): the side above or on top of the front side
* D (Down): the side opposite the top, underneath the Cube
* L (Left): the side directly to the left of the front
* R (Right): the side directly to the right of the front
* f (Front two layers): the side facing the solver and the corresponding middle layer
* b (Back two layers): the side opposite the front and the corresponding middle layer
* u (Up two layers): the top side and the corresponding middle layer
* d (Down two layers): the bottom layer and the corresponding middle layer
* l (Left two layers): the side to the left of the front and the corresponding middle layer
* r (Right two layers): the side to the right of the front and the corresponding middle layer
* x (rotate): rotate the entire Cube on R
* y (rotate): rotate the entire Cube on U
* z (rotate): rotate the entire Cube on F

## Algorithms used:
We created 2 ML agents using Deep Q-Learning and SARSA(State Action Reward State Action) to solve the 2x2x2 and 3x3x3 size cube

> ### Deep Q-Learning:
>>Q-learning is a model-free reinforcement learning algorithm to learn the value of an action in a particular state. 
It does not require a model of the environment (hence "model-free"), and it can handle problems with stochastic transitions and rewards without requiring adaptations.
For any finite Markov decision process (FMDP), Q-learning finds an optimal policy in the sense of maximizing the expected value of the total reward over any and all successive steps, starting from the current state.
Q-learning can identify an optimal action-selection policy for any given FMDP, given infinite exploration time and a partly-random policy.
"Q" refers to the function that the algorithm computes the expected rewards for an action taken in a given state.

> ### SARSA:
>>State–action–reward–state–action (SARSA) is an algorithm for learning a Markov decision process policy, used in the reinforcement learning area of machine learning.
A SARSA agent interacts with the environment and updates the policy based on actions taken, hence this is known as an on-policy learning algorithm. 
The Q value for a state-action is updated by an error, adjusted by the learning rate alpha. 
Q values represent the possible reward received in the next time step for taking action a in state s, plus the discounted future reward received from the next state-action observation.

## Instructions to run the code:

### To run the Deep Q-Learning Algorithm. 
Run this command in the command prompt.

`python ai_learner.py [OPTIONS]`

### Options:
	-s N | --size=N: Cube size (number of squares per edge). Default: 2
	-l N | --layers=N: Number of layers in the neural network. Default: 3
	--seed=N: Set the RNG seed
	--random: Only use random choice
	-h | --help: Display the help page and exit
	
### To run the SARSA Algorithm.

`python Run.py`

It will display the goal state and ask the user to input the number of moves by which it will scramble the goal state to a start state . 

## Results:

### Deep learning Output:

When we train and run the RL agent by using Deep Learning feature, we get 24 solved cubes for 2x2x2 cube in 45 minutes of training and 38 solved cubes for 3x3x3 in 3.5hrs of training for 2.9% randomness. We can see the results as follows.

![image](https://user-images.githubusercontent.com/33855600/166731416-6e9d2a36-0470-4875-bb3d-426965eb1a0f.png)

![image](https://user-images.githubusercontent.com/33855600/166731629-97e6ce41-1b24-4bfc-b317-425c6a37889d.png)

### Final statistics we get after solving 2x2x2 cube

![2x2 stats](https://user-images.githubusercontent.com/33855600/166733925-4cfe670f-49d9-4b98-b699-9efbe5042f79.png)

We get the 3x3x3 cube stats if we keep running the agent for almost 12hrs.

### SARSA Output:

![image](https://user-images.githubusercontent.com/33855600/166736121-83cd8772-802c-450d-bab4-0566e39302dd.png)
 
The SARSA gives an expected cube in 11 episodes and the last episode is 73 as shown as in the figure.

## Conclusion:

SARSA is preferable over Q Learning to minimize errors. If we want to fast in a fast-iterating environment, QL should be your choice. However, if mistakes are costly then SARSA is the better option. If your state space is too large, try exploring the deep q network.



