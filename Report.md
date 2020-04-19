# Project Report
This project utilised the Multi-agent DDPG to train the 2 agents.
## State and Action Space
In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.  Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 state variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation.  2 continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

Unlike the 
## Hyperparameters
BUFFER_SIZE(int): The size of replay buffer, set to 100,000

BATCH_SIZE(int): The size of mini batch, set to 128

LR_ACTOR(float): The learning rate of the actor, set to 0.001

LR_CRITIC(float): The learning rate of the critic, set to 0.001

WEIGHT_DECAY(int): L2 weight decay

LEARN_EVERY(int): The learning timestep interval, set to 1

LEARN_NUM(int): The number of learning passes, set to 5

GAMMA(float): The discount factor, set to 0.99

TAU(float): The parameter for soft update of target parameters, set to 0.008

EPS_START(float): The initial value for epsilon in noise decay process in Agent.act(), set to 5.0

EPS_EP_END(int): The number of episode to end the noise decay process, set to 300

EPS_FINAL(float): The final value for epsilon after decay, set to 0.0

## Neural Network
Actor and Critic network models were defined in the class Actor and Critic in the notebook. 

The Actor networks utilised two fully connected layers with 256 and 128 units with relu activation and tanh activation for the action space. The network has an initial dimension the same as the state size.

The Critic networks utilised two fully connected layers with 256 and 128 units with relu activation. The critic network has  an initial dimension the size of the state size plus action size.

The algorithm is Multi-agent DDPG. The implementation is based on the previous project (p2_continuous-control). The difference is that the agents in project 2 shared the same weights, while the two agents in this project are trained to have different weights. For each Actor / Critic, both agents' states are the input to the neural network therefore the size of input layer is doubled. And for Critic, both agents' action are fed.


## Plot of Rewards
[image1]:./score.png

Episode 1 - 100	Max Score 0.20	Average Score 0.01

Episode 101 - 200	Max Score 0.30	Average Score 0.03

Episode 201 - 300	Max Score 0.20	Average Score 0.02

Episode 301 - 400	Max Score 0.30	Average Score 0.05

Episode 401 - 500	Max Score 0.50	Average Score 0.09

Episode 501 - 600	Max Score 0.80	Average Score 0.16

Score of 0.5069000075757504 achieved in 697 episodes

![Plot of Rewards][image1]

## Ideas of Future Work
The training is not very stable. The same model / hyperparameters sometimes converge quickly but the other times don't. If there is more time, more hyperparameters will be tried.
Also other algorithms can be tried, such as A3C.


