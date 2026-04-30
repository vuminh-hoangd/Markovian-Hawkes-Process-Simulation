# Markovian-Hawkes-Process-Simulation
---
## Overview
This repository rigorous explored the **Hawkes Processes**—a class of self-exciting point processes—specifically focusing on the **exponential kernel**. While general Hawkes processes are typically non-Markovian, the exponential kernel allows the system to be a Markov Jump Process.
This project includes mathematical derivations and a Python implementation (Jupyter Notebook) to simulate these processes and verify their theoretical properties.
---
## Theoretical Framework
### Definition: Hawkes Process with Exponential Kernel
Consider a counting process $N(t)$. Using $\{t_1, t_2, \ldots, \}$ to
denote the observed sequence of past arrival times of the point process. The Hawkes process' conditional intensity function is supposed to be of the form
$$\lambda^{*}(t) = \mu  + \int_{(0,t) } \alpha e^{-\beta (t-s)} d N(s) = \mu  +  \sum_{t_i < t} \alpha e^{-\beta (t-t_i)}$$
**Parameters:**
*   $\mu$: The baseline intensity (exogenous background rate).
*   $\alpha$: The "jump" or excitation size per event.
*   $\beta$: The exponential decay rate of the excitation.
### Key Propositions
#### 1. Markov Property of the Pair
We rigorously demonstrate that the pair $(N(t), \lambda^{*}(t))$ is a **Markov process**.
$$\mathbb{E}[h(N(t+u), \lambda^{*}(t+u)) \mid \mathcal{F}_t] = \mathbb{E}[h(N(t+u), \lambda^{*}(t+u)) \mid N(t), \lambda^{*}(t)] \quad \text{a.s.}$$
#### 2. Long-term Convergence
If the branching ratio $\frac{\alpha}{\beta} < 1$, the expected intensity converges to a stationary value.
**Proposition:** As $t \to \infty$, the expected intensity satisfies:
$$\mathbb{E}[\lambda^{*}(t)] \to \frac{\mu \beta}{\beta -\alpha}$$
---
## Features
*   **Mathematical Rigor:** Detailed proofs for the Markov property and stationarity limits.
*   **Simulation:** Implementation of the **Ogata Thinning Algorithm** to generate sample paths of the Hawkes process.
*   **Visualization:** Plots showing the jump dynamics of $\lambda^{*}(t)$ and its convergence toward the theoretical mean.
---
**Authors:** Hoang Dung Vu, Minh Anh, and Christopher Won
