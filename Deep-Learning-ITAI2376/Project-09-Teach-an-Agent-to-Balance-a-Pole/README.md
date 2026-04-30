# Project 09 — Teach an Agent to Balance a Pole

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Reinforcement Learning](https://img.shields.io/badge/topic-Reinforcement_Learning-blueviolet.svg)
![Q-Learning](https://img.shields.io/badge/algorithm-Q--Learning-orange.svg)
![OpenAI Gym](https://img.shields.io/badge/environment-OpenAI_Gym-00BFFF.svg)
![CartPole](https://img.shields.io/badge/task-CartPole--v1-success.svg)
![Jupyter](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![Q-Learning Agent Training Progress on CartPole-v1](./Results-%26-Visualizations/Q-Learning-Agent-Training_Progress_On_CartPole-V1.png)

This project implements a **Q-Learning reinforcement learning agent** to solve the classic **CartPole-v1** environment from OpenAI Gym. The challenge: teach an agent to balance a pole on a moving cart — using only trial-and-error feedback from the environment — with no human supervision, labeled data, or pre-built rules.

This is an introduction to the fundamental paradigm of **Reinforcement Learning (RL)**: an agent that learns by acting, observing consequences, and updating its strategy to maximize cumulative reward.

---

## Problem Statement

The CartPole task seems simple: push a cart left or right to keep a pole balanced upright. But a naive agent fails immediately — it has no knowledge of physics, no instructions, and no examples to learn from. Only a reward signal (+1 for every timestep the pole stays up, 0 when it falls). This project asks: **Can a Q-Learning agent, starting from complete ignorance, discover an effective balancing policy through pure trial-and-error experience?**

---

## Approach and Methodology

### Environment: CartPole-v1 (OpenAI Gym)
- **State space:** 4 continuous values (cart position, cart velocity, pole angle, pole angular velocity)
- **Action space:** 2 discrete actions (push left = 0, push right = 1)
- **Reward:** +1 for every timestep the pole remains balanced
- **Episode termination:** Pole angle > 12°, cart position > 2.4, or 500 timesteps reached (win condition)

### Algorithm: Q-Learning (Tabular)

Q-Learning builds a **Q-table** that maps (state, action) pairs to expected future rewards.

**Q-Update Rule:**
```
Q(s, a) ← Q(s, a) + α × [r + γ × max Q(s', a') − Q(s, a)]
```
Where:
- `α` = learning rate (how fast we update)
- `γ` = discount factor (how much we value future rewards)
- `r` = immediate reward
- `s'` = next state

### State Discretization
Since Q-tables require discrete states, the continuous state space was discretized into bins:
```python
# Discretize continuous states into bins
bins = [
    np.linspace(-4.8, 4.8, num_bins),       # Cart position
    np.linspace(-4, 4, num_bins),            # Cart velocity
    np.linspace(-0.418, 0.418, num_bins),    # Pole angle
    np.linspace(-4, 4, num_bins)             # Pole angular velocity
]
```

### Exploration Strategy: Epsilon-Greedy
- **High ε (early training):** Agent explores randomly — trying many actions.
- **Decaying ε:** As training progresses, the agent exploits learned knowledge more and explores less.
- **ε decay:** `ε = max(ε_min, ε × decay_rate)` after each episode.

---

## Results and Evaluation

![Random Agent — CartPole Scores (10 Episodes)](./Results-%26-Visualizations/Random_Agent-Cartpole_Scores-10-Episodes.png)

![Effect of Exploration Rate Decay on Learning Speed](./Results-%26-Visualizations/Effect_of_Exploration_Rate_Decay_On_Learning_Speed.png)

**Experiment Results:**

| Phase | Average Score | Description |
|---|---|---|
| **Random Agent (Baseline)** | ~8-15 | Pure random action selection |
| **Q-Learning (Early Training)** | ~20-50 | Agent begins to associate actions with better outcomes |
| **Q-Learning (Converged)** | **~200-500** | Agent achieves near-perfect balance |

**Key Observations:**
- The random baseline barely keeps the pole balanced for 8-15 steps.
- Q-Learning converges within ~500-1000 episodes to consistently achieving 200+ steps.
- Exploration rate decay is critical — too fast → poor policy; too slow → slow learning.
- The agent discovered a non-obvious strategy: anticipate velocity, not just position.

---

## Learning Outcomes

- Understood the **Reinforcement Learning framework**: Agent, Environment, State, Action, Reward, Policy.
- Implemented **Q-Learning from scratch**: building the Q-table, Bellman equation updates, and epsilon-greedy exploration.
- Grasped the **exploration vs. exploitation trade-off** — one of RL's fundamental challenges.
- Learned **state discretization** as a technique to apply tabular RL to continuous environments.
- Analyzed **training curves** to diagnose convergence, instability, and exploration dynamics.
- Understood the path from tabular Q-Learning to **Deep Q-Networks (DQN)** — the neural network extension that eliminates the need for discretization.

---

## Project Structure

```text
Project-09-Teach-an-Agent-to-Balance-a-Pole/
├── P09_Teach-an-Agent-to-Balance-a-Pole.ipynb                 # Main Jupyter Notebook
├── Results-&-Visualizations/                                  # Output images and plots
│   ├── Q-Learning-Agent-Training_Progress_On_CartPole-V1.png  # Training progress over episodes
│   ├── Random_Agent-Cartpole_Scores-10-Episodes.png           # Baseline random agent performance
│   └── Effect_of_Exploration_Rate_Decay_On_Learning_Speed.png # Epsilon decay analysis
└── README.md                                                  # Project documentation (this file)
```

---

## Dependencies / Requirements

```bash
pip install gymnasium numpy matplotlib jupyter
```

**Python:** 3.8+

```
gymnasium >= 0.26  # OpenAI Gym successor (or gym >= 0.21)
numpy >= 1.21
matplotlib >= 3.5
jupyter / Google Colab
```

> **Note:** If using the legacy `gym` package: `pip install gym`  
> If using the modern `gymnasium` package: `pip install gymnasium`

---

## Running the Notebook

```bash
# Option 1: Local Jupyter
pip install gymnasium numpy matplotlib
jupyter notebook P09_Teach-an-Agent-to-Balance-a-Pole.ipynb

# Option 2: Google Colab
# Upload .ipynb to Google Colab → Install gym in a cell → Run all
```

**Colab setup cell:**
```python
!pip install gymnasium
import gymnasium as gym
```

---

## Data Access

This project uses **no external datasets**. The environment is fully simulated by OpenAI Gym/Gymnasium:

```python
import gymnasium as gym
env = gym.make('CartPole-v1')  # Automatically creates the simulation
```

**Environment Details:**
- **Source:** [gymnasium.farama.org/environments/classic_control/cart_pole](https://gymnasium.farama.org/environments/classic_control/cart_pole/)
- **No download required** — the environment is generated procedurally.
- Training runs entirely on CPU in minutes.
