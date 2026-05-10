# Traveling Salesman Problem Optimization using AOA and AGWO

## Overview

This project presents a comparative implementation and evaluation of two metaheuristic optimization algorithms for solving the Traveling Salesman Problem (TSP):

* Arithmetic Optimization Algorithm (AOA)
* Adaptive Grey Wolf Optimizer (AGWO)

The Traveling Salesman Problem is a classical NP-hard combinatorial optimization problem in which the objective is to determine the shortest possible route that visits a set of cities exactly once and returns to the starting city.

This repository focuses on:

* Implementing both algorithms in Python
* Adapting continuous optimization techniques to discrete permutation-based TSP representations
* Benchmarking algorithm performance using the TSPLIB berlin52 dataset
* Evaluating convergence behavior, runtime, stability, and solution quality

The project was developed as part of the Fundamentals of Artificial Intelligence course at the University of Doha for Science and Technology.

---

## Key Results

Experiments were conducted on the berlin52 benchmark instance from TSPLIB, which contains 52 cities and a known optimal distance of 7542.

| Algorithm | Best Distance | Average Distance | Standard Deviation | Average Runtime | Optimality Gap |
| --------- | ------------- | ---------------- | ------------------ | --------------- | -------------- |
| AOA       | 7742.6        | 8351.6           | 250.4              | 7.87 s          | 2.66%          |
| AGWO      | 8001.9        | 8271.1           | 201.4              | 11.92 s         | 6.10%          |
| Optimal   | 7542.0        | —                | —                  | —               | 0%             |

Key observations:

* AOA achieved the best overall solution and faster runtime
* AGWO demonstrated greater consistency and lower variance across multiple runs
* Both algorithms benefited from 2-opt local search post-processing

---

## Features

* Implementation of Arithmetic Optimization Algorithm (AOA)
* Implementation of Adaptive Grey Wolf Optimizer (AGWO)
* Largest Order Value (LOV) permutation mapping
* 2-opt local search refinement
* Statistical benchmarking across multiple runs
* Convergence and route visualization
* Comparative performance analysis

---

## Installation

### Requirements

* Python 3.8 or higher

### Required Libraries

```bash
pip install numpy matplotlib pandas
```

### Clone the Repository

```bash
git clone https://github.com/your-username/tsp-metaheuristic-optimization.git
cd tsp-metaheuristic-optimization
```

---

## How to Run

### Run Arithmetic Optimization Algorithm (AOA)

```bash
python src/aoa_tsp.py
```

### Run Adaptive Grey Wolf Optimizer (AGWO)

```bash
python src/agwo_tsp.py
```

### Run Benchmark Comparison

```bash
python src/benchmark_comparison.py
```

This script:

* Executes multiple runs for both algorithms
* Computes statistical performance metrics
* Generates convergence plots and comparison charts
* Exports benchmarking results

---

## Problem Formulation

The Traveling Salesman Problem is defined on a complete weighted graph where each city must be visited exactly once while minimizing the total travel distance.

The objective function is:

f(T)=\sum_{i=1}^{n-1} d(c_i,c_{i+1}) + d(c_n,c_1)

where:

* (T) represents the tour
* (d(c_i,c_j)) represents the Euclidean distance between cities

The project uses permutation-based solution encoding to ensure valid tours.

---

## Algorithms

### Arithmetic Optimization Algorithm (AOA)

AOA is a population-based metaheuristic inspired by arithmetic operators including:

* Addition
* Subtraction
* Multiplication
* Division

The algorithm dynamically balances exploration and exploitation using the Math Optimizer Probability (MOP) and Math Optimizer Accelerated (MOA) parameters.

### Adaptive Grey Wolf Optimizer (AGWO)

AGWO is based on the social hierarchy and hunting behavior of grey wolves. The algorithm uses:

* Alpha wolf leadership
* Beta and delta guidance
* Adaptive exploration and exploitation control

The continuous search mechanism was adapted for discrete TSP optimization using permutation repair operators and crossover-based updates.

---

## Dataset

The experiments use the berlin52 benchmark instance from TSPLIB.

Dataset characteristics:

* 52 cities
* Euclidean distance metric
* Known optimal distance: 7542

---

## Performance Evaluation

The algorithms were evaluated using:

* Best tour distance
* Average distance
* Worst distance
* Standard deviation
* Average runtime
* Optimality gap
* Convergence behavior

Each algorithm was executed:

* 10 independent runs
* Population size of 30
* 500 iterations per run

---

## Results and Analysis

The experimental results demonstrate the trade-off between:

* Solution quality
* Computational efficiency
* Stability across runs

AOA achieved stronger best-case performance and faster execution time, while AGWO provided more consistent convergence behavior and lower variance.

Both methods produced near-optimal solutions within practical computational time for an NP-hard optimization problem.

---

## Future Improvements

Potential improvements include:

* Hybrid AOA-AGWO frameworks
* Dynamic 2-opt integration during optimization
* Hyperparameter tuning using grid search
* Evaluation on larger TSPLIB datasets
* Opposition-Based Learning (OBL)
* 3-opt and advanced local search techniques

---

## References

1. Abualigah, L., et al. (2021). The Arithmetic Optimization Algorithm. Computer Methods in Applied Mechanics and Engineering.

2. Mirjalili, S., et al. (2014). Grey Wolf Optimizer. Advances in Engineering Software.

3. Toaza, B., and Esztergár-Kiss, D. (2023). A Review of Metaheuristic Algorithms for Solving TSP-Based Scheduling Optimization Problems.

4. Xu, Z., and Zhang, X. (2024). An Improved Grey Wolf Optimizer Algorithm for Traveling Salesman Problems.

---

## Authors

Developed by Group Oswalds
Fundamentals of Artificial Intelligence
University of Doha for Science and Technology

---

## License

This project is released under the MIT License.
