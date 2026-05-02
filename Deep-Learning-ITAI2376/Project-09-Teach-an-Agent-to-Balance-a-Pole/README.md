# Project 09 — Teach an Agent to Balance a Pole

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Reinforcement Learning](https://img.shields.io/badge/topic-Reinforcement_Learning-blueviolet.svg)
![Q-Learning](https://img.shields.io/badge/algorithm-Q--Learning-orange.svg)
![OpenAI Gym](https://img.shields.io/badge/environment-OpenAI_Gym-00BFFF.svg)
![CartPole](https://img.shields.io/badge/task-CartPole--v1-success.svg)
![Google Colab](https://img.shields.io/badge/tool-Google_Colab-F9AB00.svg)
![Markov Decision Process](https://img.shields.io/badge/theory-MDP-9cf.svg)
![Bellman Equation](https://img.shields.io/badge/theory-Bellman_Equation-yellow.svg)
![ITAI 2376](https://img.shields.io/badge/course-ITAI_2376-4B0082.svg)

---

## Project Overview

![Q-Learning Agent Training Progress on CartPole-v1](./Results-%26-Visualizations/Q-Learning-Agent-Training_Progress_On_CartPole-V1.png)

This project implements a **Q-Learning reinforcement learning agent** to solve the classic **CartPole-v1** environment from OpenAI Gym/Gymnasium. The challenge: teach an agent to balance a pole on a moving cart — using only trial-and-error feedback from the environment — with no human supervision, labeled data, pre-built rules, or physics knowledge.

This is an introduction to the fundamental paradigm of **Reinforcement Learning (RL)**: an agent that learns by acting, observing consequences, and updating its strategy to maximize cumulative reward over time. Starting from complete ignorance (random action selection, ~8-15 steps per episode), the agent converges to a policy that achieves **200-500+ steps** — the CartPole win condition.

---

## Problem Statement

The CartPole task seems simple on the surface: push a cart left or right to keep a pole balanced upright. But a naive agent fails immediately — it has no knowledge of physics, no instructions, and no examples to learn from. Only a single reward signal: **+1 for every timestep the pole stays up, 0 when it falls**.

Without any domain knowledge, the agent must discover:
- That moving in the direction the pole is falling helps stabilize it
- That anticipating velocity (not just position) prevents runaway oscillation
- That the optimal policy balances both the cart position and pole angle simultaneously

This project asks: **Can a Q-Learning agent, starting from complete ignorance, discover an effective balancing policy through pure trial-and-error experience — and what does watching it learn reveal about the reinforcement learning paradigm?**

---

## Approach and Methodology

### Environment: CartPole-v1 (OpenAI Gym)

| State Variable | Range | Meaning |
|---|---|---|
| **Cart position** | [-4.8, 4.8] | Horizontal position of the cart |
| **Cart velocity** | (-∞, +∞) | Speed of cart movement |
| **Pole angle** | [-0.418, 0.418] rad | Angle from vertical (±24°) |
| **Pole angular velocity** | (-∞, +∞) | Rate of angle change |

- **Action space:** 2 discrete actions — push left (0) or push right (1)
- **Reward:** +1 for every timestep the pole remains balanced
- **Episode termination:** Pole angle > 12°, cart position > 2.4, or 500 timesteps (win condition)

### Algorithm: Q-Learning (Tabular)

Q-Learning builds a **Q-table** mapping (state, action) pairs to expected future rewards using the **Bellman equation**:

```
Q(s, a) ← Q(s, a) + α × [r + γ × max Q(s', a') − Q(s, a)]
```

Where:
- `α` = learning rate — how aggressively we update our estimates
- `γ` = discount factor — how much we value future vs. immediate rewards
- `r` = immediate reward received
- `s'` = next state observed
- `max Q(s', a')` = best possible future value from next state

**Q-table convergence:** As the agent accumulates experience, the Q-values converge toward the true expected return from each (state, action) pair — the Bellman optimality condition.

### State Discretization

Q-tables require discrete states, so the continuous 4D state space was discretized into bins:

```python
num_bins = 10  # Per dimension → 10^4 = 10,000 possible states
bins = [
    np.linspace(-4.8, 4.8, num_bins),       # Cart position bins
    np.linspace(-4, 4, num_bins),            # Cart velocity bins
    np.linspace(-0.418, 0.418, num_bins),    # Pole angle bins
    np.linspace(-4, 4, num_bins)             # Pole angular velocity bins
]

def discretize_state(state):
    return tuple(np.digitize(state[i], bins[i]) for i in range(4))
```

**Trade-off:** Finer discretization → better resolution → larger Q-table → slower convergence. The choice of 10 bins per dimension (10,000 states) was tuned empirically.

### Exploration Strategy: Epsilon-Greedy

The agent balances exploration (trying new actions) with exploitation (using learned knowledge):

```python
if random.random() < epsilon:
    action = env.action_space.sample()  # Explore randomly
else:
    action = np.argmax(Q[state])        # Exploit best known action

# Decay epsilon after each episode:
epsilon = max(epsilon_min, epsilon * epsilon_decay)
```

**Key insight:** The decay rate of epsilon is one of the most critical hyperparameters. Too fast → the agent gets locked into a suboptimal policy before it's explored enough. Too slow → the agent wastes episodes on random exploration long after a good policy has been found.

### Hyperparameter Configuration

| Hyperparameter | Value Used | Role |
|---|---|---|
| **Learning rate (α)** | 0.1 | How fast Q-values update |
| **Discount factor (γ)** | 0.99 | Strong emphasis on future rewards |
| **Initial epsilon** | 1.0 | Start fully exploratory |
| **Epsilon decay** | 0.995 | Slow, smooth exploration reduction |
| **Minimum epsilon** | 0.01 | Always retain 1% exploration |
| **Episodes** | 1000+ | Training budget |
| **State bins** | 10 per dimension | Discretization resolution |

---

## Results & Visualizations

### Baseline: Random Agent

![Random Agent — CartPole Scores (10 Episodes)](./Results-%26-Visualizations/Random_Agent-Cartpole_Scores-10-Episodes.png)

A random agent (choosing actions uniformly at random) achieves an average of **8-15 steps** per episode — barely better than immediately dropping the pole. This establishes the performance floor that Q-Learning must exceed to demonstrate genuine learning.

### Exploration Rate Decay Analysis

![Effect of Exploration Rate Decay on Learning Speed](./Results-%26-Visualizations/Effect_of_Exploration_Rate_Decay_On_Learning_Speed.png)

This visualization compares different epsilon decay schedules — demonstrating that the learning curve shape is highly sensitive to how quickly the agent transitions from exploration to exploitation.

### Q-Learning Training Progress

![Q-Learning Agent Training Progress on CartPole-v1](./Results-%26-Visualizations/Q-Learning-Agent-Training_Progress_On_CartPole-V1.png)

**Experiment Results:**

| Phase | Average Score | Description |
|---|---|---|
| **Random Agent (Baseline)** | ~8-15 steps | Pure random action selection — no learning |
| **Q-Learning (Early Training)** | ~20-50 steps | Agent begins associating actions with better outcomes |
| **Q-Learning (Mid Training)** | ~80-150 steps | Policy improves; agent anticipating velocity |
| **Q-Learning (Converged)** | **~200-500 steps** | Near-perfect balance achieved consistently |

**Key Observations:**
- The random baseline barely keeps the pole balanced for 8-15 steps.
- Q-Learning converges within ~500-1000 episodes to consistently achieving 200+ steps.
- Exploration rate decay is critical: too fast → poor policy; too slow → slow learning.
- The agent discovered a non-obvious strategy: **anticipate angular velocity**, not just pole angle — preventing oscillation before it starts.
- Training runs entirely on CPU in minutes — no GPU required.

---

## Learning Outcomes

- Understood the **Reinforcement Learning framework** in full: Agent, Environment, State, Action, Reward, Policy, Value Function — and how they interact in the agent-environment loop.
- Implemented **Q-Learning from scratch**: building the Q-table data structure, writing the Bellman equation update rule, and implementing epsilon-greedy exploration with manual decay.
- Grasped the **exploration vs. exploitation trade-off** — one of RL's most fundamental challenges: an agent that never explores gets stuck; one that always explores never learns.
- Learned **state discretization** as a technique to apply tabular RL to continuous environments — and understood why Deep Q-Networks (DQN) eliminate this limitation by using a neural network to approximate Q(s,a) directly.
- Analyzed **training curves** to diagnose convergence, instability, and exploration dynamics — reading the noise pattern in reward curves as a signal of learning progress.
- Understood the path from tabular Q-Learning → Deep Q-Networks (DQN) → Policy Gradient methods → Actor-Critic → PPO — the full modern RL progression.

---

## Project Structure

```text
Project-09-Teach-an-Agent-to-Balance-a-Pole/
├── P09_Teach-an-Agent-to-Balance-a-Pole.ipynb                 # Main Jupyter Notebook
├── P09_Teach-an-Agent-to-Balance-a-Pole.pdf                   # PDF export of the notebook
├── Results-&-Visualizations/
│   ├── Q-Learning-Agent-Training_Progress_On_CartPole-V1.png  # Training progress over episodes
│   ├── Random_Agent-Cartpole_Scores-10-Episodes.png           # Baseline random agent performance
│   └── Effect_of_Exploration_Rate_Decay_On_Learning_Speed.png # Epsilon decay analysis
└── README.md
```

---

## Dependencies / Requirements

```bash
pip install gymnasium numpy matplotlib jupyter
```

**Python:** 3.8+

```
gymnasium >= 0.26   # OpenAI Gym successor (or gym >= 0.21)
numpy >= 1.21
matplotlib >= 3.5
jupyter / Google Colab
```

> **Note:** If using the legacy `gym` package: `pip install gym`
> If using the modern successor: `pip install gymnasium`

---

## Running the Notebook

```bash
# Option 1: Local Jupyter
pip install gymnasium numpy matplotlib
jupyter notebook P09_Teach-an-Agent-to-Balance-a-Pole.ipynb

# Option 2: Google Colab
# Upload .ipynb to Google Colab → Install in a cell → Run all
```

**Colab setup cell:**
```python
!pip install gymnasium
import gymnasium as gym
```

---

## Data Access

This project uses **no external datasets**. The environment is fully simulated:

```python
import gymnasium as gym
env = gym.make('CartPole-v1')  # Automatically creates the simulation
```

**Environment Details:**
- **Source:** [gymnasium.farama.org/environments/classic_control/cart_pole](https://gymnasium.farama.org/environments/classic_control/cart_pole/)
- **No download required** — procedurally generated physics simulation
- Training runs entirely on CPU in minutes

---

## Extension: From Q-Learning to Deep Q-Networks (DQN)

The limitation of tabular Q-Learning is the need for state discretization — which loses information and scales poorly to high-dimensional state spaces. The natural extension is Deep Q-Networks (DQN):

```python
# Instead of Q[state][action], use a neural network:
class DQN(nn.Module):
    def forward(self, state):
        return q_values_for_all_actions  # No discretization needed
```

DQN (Mnih et al., 2015) used this approach to achieve human-level performance on 49 Atari games from raw pixel input — the same Q-Learning algorithm, but with a CNN replacing the Q-table.
