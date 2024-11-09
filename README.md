# Reinforcement Game

## Introduction

This project demonstrates how to build an intelligent agent using **reinforcement learning (RL)**, specifically for a game environment. Rather than relying on heuristics, the agent refines its strategy through repeated gameplay, aiming to maximize its winning rate over time.

This repository provides an overview and code for training an RL agent to play a Connect Four-style game using neural networks and stable baselines.

## Neural Networks

Creating a perfect heuristic for game-playing can be challenging and tedious. Instead, replace heuristics with a neural network that:
- Accepts the current game board as input.
- Outputs probabilities for each possible move.
  
This allows the agent to make decisions based on learned weights, assigning higher probabilities to better moves. 

## Setup

Our approach for training the agent includes a **reward system**:
- Reward `+1` for winning moves.
- Reward `-10` for invalid moves.
- Reward `-1` if the agent fails to prevent an opponent’s win.
- Small positive rewards (`1/42`) to encourage longer game duration.

The goal is to find neural network weights that maximize the agent's cumulative reward.

## Reinforcement Learning Approach

Various RL algorithms can be used to train agents, such as **DQN**, **A2C**, and **PPO**. These algorithms work by adjusting the weights to improve cumulative rewards over multiple games.

- Initially, weights are randomized.
- The agent plays multiple games, adjusting weights based on observed rewards to improve its strategy.

The project uses **Proximal Policy Optimization (PPO)**, a popular algorithm for training RL agents.

## Code Overview

The `ConnectFourGym` class is implemented to make the game compatible with Stable-Baselines3:
- `reset()`: Initializes a new game.
- `change_reward()`: Customizes the reward system.
- `step()`: Takes the agent’s action, returns the new board, reward, and game status.

The agent is trained using **Stable-Baselines3** to beat a random opponent. To improve performance further, the agent can be trained against more advanced opponents.

