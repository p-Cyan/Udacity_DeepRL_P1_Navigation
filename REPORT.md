# Project 1: Navigation

</hr>

## Environment Details
This environment provided by Udacity is similar to Unity's [Banana Collector Environment](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#banana-collector) where we have to collect randomly spawned bananas in a fixed area.</br>
</br>
![navigation](https://github.com/p-Cyan/Udacity_DeepRL_P1_Navigation/blob/main/images/navigation.gif)</br>
</br>
The agent is in first person and the goal is to collect as many yellow bananas as possible while avoiding blue bananas.</br>
The task is episodic where each episode terminates after 1000 steps. The environment is considered solved when the trained agent obtains an average score of 13 over 100 consecutive episodes.</br>

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available:
>- 0 - move forward.</br>
>- 1 - move backward.</br>
>- 2 - turn left.</br>
>- 3 - turn right.</br>

To achieve our goal, the environment rewards the following:
> +1 when a yellow banana is picked</br>
> &nbsp;-1 when a blue banana is picked</br>
> &nbsp;&nbsp;0 for every other event</br>

In this specific case, when the cumulative reward exceeds 13 the training is stopped as the agent is considered to have generalized well to the task.</br>
</br>


## Learning Algorithm

### Deep Q-Networks

The solution implemented is a simple [Deep Q-Learning (DQN) algorithm](https://deepmind.com/research/dqn/) Human-level control through deep reinforcement learning.

Deep Q Learning combines 2 approaches :
- A Reinforcement Learning method called [Q Learning](https://en.wikipedia.org/wiki/Q-learning) (aka SARSA max)
- A Deep Neural Network to learn a Q-table approximation (action-values)

Especially, this implementation includes the 2 major training improvements by [Deepmind](https://deepmind.com) and described in their [Nature publication : "Human-level control through deep reinforcement learning (2015)"](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf)
- Experience Replay 
- Fixed Q Targets

### Code implementation
The code used here is derived from the "Lunar Lander" tutorial from the Deep Reinforcement Learning Nanodegree, and has been slightly adjusted for being used with the banana environment.

### Model architecture
A range of neural models were tried exploring wide, deep and shallow configurations. Overall, the simpler models performed as well or better than deeper ones and wide models performed worse than narrow ones. All models started with a 37 x 1 input vector from the environment, constructed two or more fully connected hidden layers and ended with a fully connected layer outputing 4 outputs, one for each action. 
 
The final solution used two hidden layers of 64 and 64 neurons respectively. 

```
QNetwork(
  (fc1): Linear(in_features=37, out_features=64, bias=True)
  (fc2): Linear(in_features=64, out_features=64, bias=True)
  (out): Linear(in_features=64, out_features=4, bias=True)
)
```

The following configurations were also tested

* 64 64 64 32 - Solved in 395 episodes
* 64 128 - Solved in 522 episodes
* 128 64 - Solved in 482 episodes
* 128 256 - Did not solve in under 1000 episodes

The interesting observation from this is that narrow and shallow networks worked best and the wide networks failed to converge.

### Hyper parameters

Replay buffer size 1e5
Discount factor 0.99 (gamma)
Soft update factor 0.001 (tau)
Learning rate 0.0004 (alpha)
Network update step interval 4

### Results
![results](https://github.com/p-Cyan/Udacity_DeepRL_P1_Navigation/blob/main/images/history.JPG)
![plot](https://github.com/p-Cyan/Udacity_DeepRL_P1_Navigation/blob/main/images/final%20graph.JPG)


## Future

Other option that could be implmented are below.
-  [Double Deep Q-Network](https://arxiv.org/abs/1509.06461)
-  [Dueling Q-Network](https://arxiv.org/abs/1511.06581)
-  [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952)

## Config

I ended up using Udacity's built in workspace and training on CPU and only took a few minutes to train. No visual was used.
