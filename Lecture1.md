# Introduciton to RL

Reinforcement learning is a branch of machine learning (other 2: supervised & unsupervised)

## Difference with other machine learning methods
- No supervisor, a reward signal
- No instantaneous feedback
- Sequential/ time series data
- Agent’s actions affect the subsequent data it receives (?)

## Rewards
A reward R_t is a scalar feedback signal
Indicates how well agent is doing at step t
The agent’s job is to maximize cumulative reward

Reward hypothesis: all goals can be described by the maximization of expected cumulative reward

Sequential decision making
Goal: select actions to maximize total future reward
Actions may have long term consequences
Reward may be delayed
It may be better to sacrifice immediate reward to gain more long-term reward

$$
x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}
$$
