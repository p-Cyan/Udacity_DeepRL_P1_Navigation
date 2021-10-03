## Udacity Deep Reinforcement Nanodegree
</hr>
This repository contains my project submission for project 1 of Udacity's [Deep RL Nanodegree program](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893)

## Project 1: Navigation

</hr>

### Environment Details
This environment provided by Udacity is similar to Unity's [Banana Collector Environment](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#banana-collector) where we have to collect randomly spawned bananas in a fixed area.</br>
The agent is in first person and the goal is to collect as many yellow bananas as possible while avoiding blue bananas.</br>

</br>

### State & Action Space
The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available:
>- 0 - move forward.</br>
>- 1 - move backward.</br>
>- 2 - turn left.</br>
>- 3 - turn right.</br>

</br>

### Reward system
To achieve our goal, the environment rewards the following:
> +1 when a yellow banana is picked</br>
> &nbsp;-1 when a blue banana is picked</br>
> &nbsp;&nbsp;0 for every other event</br>

</br>

### Termination condition for training
In this specific case, when the cumulative reward exceeds 13 the training is stopped as the agent is considered to have generalized well to the task.

