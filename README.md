## Udacity Deep Reinforcement Nanodegree
</hr>
This repository contains my project submission for project 1 of Udacity's [Deep RL Nanodegree program](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893)

## Project 1: Navigation

</hr>

### Environment Details
This environment provided by Udacity is similar to Unity's [Banana Collector Environment](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#banana-collector) where we have to collect randomly spawned bananas in a fixed area.</br>
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
### Installation requirements
- You first need to configure a Python 3.6 / PyTorch 0.4.0 environment with the needed requirements as described in the [Udacity repository](https://github.com/udacity/deep-reinforcement-learning#dependencies).</br>
- You then have to clone this project and have it accessible in your Python environment</br>
- Following that, install the unity environment as described [here]()
- Then, Follow the instructions in Navigation.ipynb to get started with training your own agent!

### Misc : Configuration used
This agent has been trained on the Udacity provided online workspace. This environment allows to use a Nvidia K80 GPU that is used for the training. (The headless / no visualization version of the Unity environment was thus used)

My setup is a "Deep Learning Dev Box", and is basically a Linux GPU Server, running Docker containers (using Nvidia Docker 2), serving Jupyter Lab notebooks which are accessed remotely via a web interface (or a ssh connection) : unfortunately this setup does not seem suitable to run Unity ML agent, with the GPU and providing a display for for the agent (See [Unity documentation](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Using-Docker.md) for more details)


