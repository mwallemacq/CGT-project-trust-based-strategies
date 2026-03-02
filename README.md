# Evolutionary Trust Dynamics in Repeated Games

Reimplementation and reproduction of the evolutionary game-theoretic model from:

**Han, Perret & Powers (2021)**  
*“When to (or not to) trust intelligent machines: Insights from an evolutionary game theory analysis of trust in repeated games”*  
Cognitive Systems Research, 68, 111–124.

---

## Overview

This project reproduces the evolutionary dynamics of trust-based strategies in repeated Prisoner's Dilemma games under monitoring (verification) costs.

The original paper introduces two trust-based strategies:

- **TUC (Trust-based Conditional Cooperator)**
- **TUD (Trust-based Unconditional Defector)**

These strategies reduce verification costs by introducing a trust threshold mechanism, allowing agents to stop constantly monitoring their opponent after sufficient cooperative interaction.

This repository implements the full model from scratch and reproduces the experimental results reported in the paper.

---

## Technical Implementation

The project includes:

- Construction of the payoff matrix based on Equation (2) of the original paper
- Explicit modeling of opportunity cost (ε)
- Implementation of trust threshold (θ) and trustfulness parameter (1/p)
- Simulation of evolutionary dynamics using:
  - Small Mutation Limit (SML)
  - Pairwise comparison (Fermi update rule)
- Stationary distribution computation using `egttools`

All simulations were implemented in Python using:

- `egttools`
- `numpy`
- `matplotlib`
- Jupyter Notebook

---

## Reproduced Experiments

We successfully reproduced the key findings of the original study, including:

- Impact of opportunity cost (ε) on cooperation
- Effect of trust-based strategies on overall population cooperation
- Influence of interaction length (r)
- Impact of game importance (γ)
- Sensitivity to trustfulness parameter (1/p)
- Effect of trust threshold (θ)

Our results closely match those reported in the original paper.

---

## Numerical Stability Observation

During reproduction of short interaction experiments (r = 20), we observed numerical instability at high selection intensity.

This was caused by degeneracy in the Markov transition matrix when transition probabilities approached 0 or 1, leading to floating-point precision limitations (64-bit).

This artifact does not reflect a model inconsistency but a computational limitation.

---

## Project Structure

- `core_implementation.ipynb` – main simulation notebook
- `paper.pdf` – reproduction report
- `README.md` – project overview

---

## Key Insights

- Trust acts as a cost-saving shortcut in environments where monitoring is expensive.
- Trust-based cooperation outperforms Tit-for-Tat when verification cost is non-zero.
- Excessive trust increases vulnerability to exploitation.
- Cooperation is most stable in long interactions of intermediate importance.

---

## Possible Extensions

- Evolution of the trust threshold θ
- Noisy or imperfect verification
- Higher-precision numerical solvers
- Comparison with additional strategies (WSLS, Grim Trigger, etc.)

---

## Authors

Matthieu Wallemacq  
Apoorva Gupta  
Nareg Nawasartian  

Vrije Universiteit Brussel – Computational Game Theory