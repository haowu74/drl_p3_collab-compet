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

WEIGHT_DECAY = 0        # L2 weight decay

LEARN_EVERY = 1         # learning timestep interval

LEARN_NUM = 5           # number of learning passes

GAMMA = 0.99            # discount factor

TAU = 8e-3              # for soft update of target parameters

EPS_START = 5.0         # initial value for epsilon in noise decay process in Agent.act()

EPS_EP_END = 300        # episode to end the noise decay process

EPS_FINAL = 0           # final value for epsilon after decay

## Neural Network
Actor and Critic network models were defined in the class Actor and Critic in the notebook. 

The Actor networks utilised two fully connected layers with 256 and 128 units with relu activation and tanh activation for the action space. The network has an initial dimension the same as the state size.

The Critic networks utilised two fully connected layers with 256 and 128 units with relu activation. The critic network has  an initial dimension the size of the state size plus action size.
## Plot of Rewards
[image1]:./score.png

![Plot of Rewards][image1]

## Ideas of Future Work
The training is not very stable. The same model / hyperparameters sometimes converge quickly but the other times don't.