# GridWorld Reinforcement Learning Environment

This notebook contains a custom GridWorld environment implemented using OpenAI's Gym interface. It also includes training and testing of reinforcement learning agents using Stable Baselines3 and Ray RLlib.

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/gridworld-rl.git
    cd gridworld-rl
    ```

2. Install the required Python packages:
    ```sh
    pip install gym gymnasium stable-baselines3[extra] shimmy ray[rllib]
    ```

## Custom Environment

### GridWorldEnv

The `GridWorldEnv` class defines a grid world environment with obstacles and a goal. The agent receives rewards based on its position relative to obstacles and the goal.

- **Grid Size**: 5x5
- **Obstacles**: (1,1), (2,2), (3,3)
- **Goal Position**: (4,4)
- **Actions**: Up, Down, Left, Right

### Example Usage

```python
import gym
from GridWorldEnv import GridWorldEnv

# Create and register the environment
gym.envs.registration.register(
    id='GridWorld-v0',
    entry_point='GridWorldEnv',
    max_episode_steps=100,
)

env = gym.make('GridWorld-v0')
env.reset()
env.render()

for _ in range(10):
    action = env.action_space.sample()
    env.step(action)
    env.render()
```

## Reinforcement Learning with Stable Baselines3

### Training with PPO

The repository includes an example of training a PPO agent using Stable Baselines3.

```python
from stable_baselines3 import PPO

# Create the environment
env = gym.make('GridWorld-v0')

# Create the PPO agent
model = PPO('MlpPolicy', env, verbose=1)

# Train the agent
model.learn(total_timesteps=10000)

# Test the agent
obs = env.reset()
for _ in range(10):
    action, _states = model.predict(obs)
    obs, rewards, dones, info = env.step(action)
    env.render()
```

## Reinforcement Learning with Ray RLlib

### Training with PPO

Ray RLlib provides scalable reinforcement learning algorithms. An example of training a PPO agent using Ray RLlib is included.

```python
import ray
from ray import tune
from ray.rllib.algorithms.ppo import PPO

# Initialize Ray
ray.init(ignore_reinit_error=True)

# Define the configuration
config = {
    "env": "GridWorld-v0",
    "framework": "torch",
}

# Train the agent
tune.run(PPO, config=config, stop={"timesteps_total": 10000})

# Shutdown Ray
ray.shutdown()
```
