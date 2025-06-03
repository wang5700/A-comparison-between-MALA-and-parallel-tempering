# A-comparison-between-MALA-and-parallel-tempering

A Comparison Between MALA and Parallel Tempering
This repository contains code and analysis for comparing two Markov Chain Monte Carlo (MCMC) sampling methods: Metropolis Adjusted Langevin Algorithm (MALA) and Parallel Tempering. The comparison focuses on their performance in sampling from a double-well potential, a common challenge in computational statistics due to its multimodal nature.
Overview
The goal of this project is to implement and evaluate MALA and Parallel Tempering for sampling from a double-well potential ( V(x) = 2(x^2 - 1)^2 ). The repository includes:

Implementations of both algorithms.
Scripts to run simulations as described in the associated exercises.
Analysis of the results, including trajectory plots and transition time comparisons.

Algorithms

MALA (Metropolis Adjusted Langevin Algorithm): A gradient-based MCMC method that uses Langevin dynamics with a Metropolis-Hastings accept/reject step to sample from the target distribution. It incorporates gradient information to propose moves, making it efficient for certain distributions.
Parallel Tempering: An MCMC method that runs multiple chains at different temperatures, allowing swaps between chains to improve exploration of multimodal distributions. It is particularly effective for escaping local minima in complex landscapes.




Usage
Running the Simulations
The repository includes scripts to replicate the experiments described in the exercises.
MALA Implementation
To run MALA for sampling from the double-well potential with ( 10^5 ) samples and step-size ( \epsilon = 0.05 ):
python mala_sampling.py

This script will:

Generate ( 10^5 ) samples using MALA.
Plot the trajectory of the samples.

Parallel Tempering Implementation
To run Parallel Tempering with 4 chains at temperatures 1, 1/2, 1/4, 1/8, generating ( 10^5 ) samples per chain:
python parallel_tempering_sampling.py

This script will:

Run 4 chains with the specified temperatures.
Attempt swaps between chains every 10 samples using the Metropolis criterion.
Plot the trajectories for all chains.

Transition Time Analysis
To compare the average transition times between MALA and Parallel Tempering:
python transition_analysis.py

This script will:

Perform 10 runs for each method.
Record the number of steps for transitions between ( x < 0 ) and ( x > 0 ).
Compute and compare the average transition steps.

Directory Structure

mala_sampling.py: Script for MALA implementation and trajectory plotting.
parallel_tempering_sampling.py: Script for Parallel Tempering implementation and trajectory plotting.
transition_analysis.py: Script for comparing transition times.
plots/: Directory where trajectory plots and analysis figures are saved.

Results
Trajectory Plots

MALA: The trajectory often shows slower transitions between the two wells of the double-well potential due to its reliance on local gradient information, which can struggle with multimodal distributions.
Parallel Tempering: The trajectories across chains demonstrate better exploration, with high-temperature chains facilitating transitions between wells, leading to more frequent swaps and better sampling of the target distribution.

Transition Times
Parallel Tempering generally exhibits faster average transition times compared to MALA, as the swapping mechanism allows chains to escape local minima more effectively. MALA, while efficient in unimodal settings, can get trapped in one well for longer periods.
Efficiency and Computational Cost

MALA: Lower computational cost per step but may require more steps to achieve adequate sampling in multimodal settings.
Parallel Tempering: Higher computational cost due to running multiple chains, but the improved exploration often justifies the overhead for complex distributions like the double-well potential.
