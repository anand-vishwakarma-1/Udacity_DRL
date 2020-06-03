[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif "Trained Agent"

# Project 1: Navigation

### Introduction

For this project, you will train an agent to navigate (and collect bananas!) in a large, square world.  

![Trained Agent][image1]

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.  Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.  

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  Given this information, the agent has to learn how to best select actions.  Four discrete actions are available, corresponding to:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

### Completion
The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

### Environment

The environment is simulated by Unity application _Banana_ lying in the subdirectory _Banana_Windows_x86_64_
We start the environment as follows:

_env = UnityEnvironment(file_name="Banana_Windows_x86_64/Banana.exe")_

### Training session and parameter

We experience the following parameters:  _n_fc1_, _n_fc2_,  _eps_start_.
For the training session, 
 * _eps_start_ is played out as a value 0.9 with step 0.001, 
 * _n_fc1_ is played out as a value 64,
 * _n_fc2_ is played out as a value 64.

For the training session, we construct the **agent** with parameters
and we run the *Deep-Q-Network* procedure **dqn** as follows:

  agent = **Agent**(state_size=37, action_size=4, seed=1, n_fc1=64, n_fc2=64)       
  scores, episodes = **dqn**(n_episodes = 1000, eps_start = epsilon_start)
  
## Dependencies

To set up your python environment to run the notebook, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

	- __Linux__ or __Mac__: 
	```bash
	conda create --name drlnd python=3.6
	source activate drlnd
	```
	- __Windows__: 
	```bash
	conda create --name drlnd python=3.6 
	activate drlnd
	```
	
2. Clone the repository (if you haven't already!), and navigate to the `python/` folder.  Then, install several dependencies.
```bash
git clone https://github.com/udacity/deep-reinforcement-learning.git
cd deep-reinforcement-learning/python
pip install .
```

3. Then run the code cells of **Navigation.ipynb** one by one.
  
### Credit

Most of the code is based on the Udacity code for DQN and Pytorch tutorials.
