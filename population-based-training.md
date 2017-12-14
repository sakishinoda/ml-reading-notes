[Population Based Training of Neural Networks](https://arxiv.org/abs/1711.09846)
---

### Summary
- Bridges parallel search and sequential optimisation for hyperparameter tuning
- Wallclock time is no greater than that of a single optimisation process, does not require sequential runs, and requires fewer resources than random or grid (parallel) search
- Shares information between a population of concurrent optimisation processes; online propagation/transfer of parameters and hyperparameters based on performance
- Allows online adaptation of hyperparameters during training (they suggest this is particularly important in problems with non-stationary learning dynamics, such as RL)
- Inherently greedy but works well in practice
- Tested on a range of RL and SL tasks, showed empirical improvements due to: automatic selection of hyperparameters during training, online model selection for greater resource allocation, online adaptation of hyperparameters for non-stationary training and discovery of complex hyperparameter schedules
- Basic idea: 
    - Start like parallel search, with randomly sampled hyperparameters and weight initialisations
    - Each training run (member of the population) evaluates own performance periodically
    - Each run is considered "ready" to undergo explore/exploit after a certain number of learning iterations
    - If a run is underperforming relative to the population, it exploits the rest of the population by replacing itself with a better model and perturbing the new model's hyperparameters (or resampling from originally defined prior distribution) before continuing training
- Exploitation strategies used:
    - T-test selection: randomly sample another agent in the population, compare last 10 episodic rewards (for RL) using Welch's t-test; if sampled agent has significant higher mean reward, copy the sampled agent's weights and hyperparameters to current
    - Truncated selection: rank all agents, if current agent is in bottom 20%, replace with another agent uniformly sampled from top 20%
    