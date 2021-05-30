# Introduciton to RL

Reinforcement learning is a branch of machine learning (other 2: supervised & unsupervised)

## Difference with other machine learning methods
- No supervisor, a reward signal
- No instantaneous feedback
- Sequential/ time series data
- Agent’s actions affect the subsequent data it receives (?)

## Rewards
A reward $R_t$ is a scalar feedback signal

Indicates how well agent is doing at step t

The agent’s job is to maximize cumulative reward

Reward hypothesis: all goals can be described by the maximization of expected cumulative reward

## Sequential decision making
Goal: select actions to maximize total future reward

Actions may have long term consequences

Reward may be delayed

It may be better to sacrifice immediate reward to gain more long-term reward

At each step t the agent:
- executes action $A_t$
- receives observation $O_t$
- receives scalar reward $R_t$

The environment:
- receives action $A_t$
- emits observation $O_{t+1}$
- emits scalar reward $R_{t+1}$

## History and State
**History** is the sequence of observations, actions. rewards

What happens next depends on the history
- the agent selects actions
- the environment selects observations/rewards

**State** is the info used to determine what happens next
$$
S_t = f(H_t)
$$

### Environment State $S_t^e$: environment's private representation
whatever data the environment uses to pick the next ovservation/reward

not usually visible to the agent

### Agent State $S_t^a$: agent's internal representation
whatever information the agent uses to pick the next action

it is the info used by reinforcement learning algorithms

### Information State (Markov State)
Definition: A state $S_t$ is **Markov** if and only if $P[S_{t+1}|S_t] = P[S_{t+1}|S_1,...,S_t]$
- The future is independent of the past giventhe present
- The state is a sufficient statistic of the future
- The environment state and history are Markov

#### Fully observable environments: Markov decision process (MDP)
Full observability: agent directly observes environment state

Agent state = Environment State = Information State

#### Partially observable environments: partially observale Markov decision process (POMDP)
Partial observability: agent **indirectly** observes environment

agent state not equal to environment state

Agent must construct its own state representation $S_t^a$
- Complete history $S_t^a = H_t$
- Beliefs of environment state: $S_t^a = (P[A_t^e=s^1],...,P[S_t^e= s^n])$
- Recurent neural network: $S_t^a=\sigma(S_{t-1}^aW_s+O_tW_o)$

# Inside an RL Agent

## Major Components of an RL Agent

An RL agent may include one or more of these componments
- Policy: agent's behavior function
- Value function: how good is each state and/or action
- Model: agent's representation of the environment

### Policy: agent's behavior
A map from state to action

Deterministic policy: $a=\pi(s)$
Stochastic policy: $\pi(a|s)=P[A_t=a|S_t=s]$

### Value function: a prediction of future reward
Used to evaluate the goodness/badness of states and then to select between actions
$$
v_\pi
$$

