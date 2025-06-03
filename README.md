# A-comparison-between-MALA-and-parallel-tempering

This repository contains code and analysis for comparing two Markov Chain Monte Carlo (MCMC) sampling methods: Metropolis Adjusted Langevin Algorithm (MALA) and Parallel Tempering. The comparison focuses on their performance in sampling from a double-well potential, a common challenge in computational statistics due to its multimodal nature.
Overview
The goal of this project is to implement and evaluate MALA and Parallel Tempering for sampling from a double-well potential ( V(x) = 2(x^2 - 1)^2 ). The repository includes:

Implementations of both algorithms.
Scripts to run simulations as described in the associated exercises.
Analysis of the results, including trajectory plots and transition time comparisons.

### Algorithms

MALA (Metropolis Adjusted Langevin Algorithm): A gradient-based MCMC method that uses Langevin dynamics with a Metropolis-Hastings accept/reject step to sample from the target distribution. It incorporates gradient information to propose moves, making it efficient for certain distributions.
Parallel Tempering: An MCMC method that runs multiple chains at different temperatures, allowing swaps between chains to improve exploration of multimodal distributions. It is particularly effective for escaping local minima in complex landscapes.
