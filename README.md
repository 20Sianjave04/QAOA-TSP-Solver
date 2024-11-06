# Quantum Approximate Optimization Algorithm (QAOA) on the Traveling Salesman Problem (TSP)

**Authors**: Oscar Arana and Simon Jaimes

## Overview

This project explores the application of the Quantum Approximate Optimization Algorithm (QAOA) to solve the Traveling Salesman Problem (TSP), a classic combinatorial optimization challenge. The TSP requires finding the shortest possible route that visits each city exactly once and returns to the starting point. Traditional algorithms for TSP run with a time complexity of O(n!), making them inefficient as the number of cities grows. This project presents a quantum approach leveraging QAOA to find an optimal or near-optimal solution more efficiently.

## Problem Definition: Traveling Salesman Problem

The Traveling Salesman Problem asks:
> What’s the shortest possible route that visits every city exactly once and returns to the starting point?

Classical solutions for TSP, including the best-known branch-and-bound algorithm, have O(n!) runtime complexity. To address the scalability issues of TSP, we explore a quantum computing approach using QAOA.

## Quantum Approach

### What is QAOA?

The Quantum Approximate Optimization Algorithm (QAOA) is a quantum algorithm designed to solve combinatorial optimization problems by approximating the ground state of a problem’s Hamiltonian. QAOA has shown promise in finding solutions for complex problems like TSP by minimizing energy in quantum states.

### Applying QAOA to TSP

To apply QAOA to TSP, we translate the problem into a Hamiltonian cycle with the lowest possible energy. Each route is represented on a graph using quantum bits (qubits), where:

- **1** represents an edge in the route.
- **0** represents no edge in the route.

This setup enables QAOA to explore all potential paths in superposition, seeking the minimum-energy state that corresponds to the optimal route.

### Steps

1. **Initial State Preparation**: We create a superposition of all possible routes using the Hadamard operator, allowing the quantum state to represent multiple cities simultaneously.
2. **Cost Hamiltonian Construction**: The Cost Hamiltonian, which includes energy penalties for invalid routes, guides QAOA towards valid, lower-energy solutions.
3. **QAOA and its Ansatz**: Using unitary operators in a layered Ansatz, QAOA iteratively applies these operators to find the minimum energy state that corresponds to the shortest path.

## Results and Future Work

### Results

With a setup of `n = 3` cities, our implementation of QAOA successfully demonstrated optimized route-finding. However, we encountered computational noise and runtime challenges as `n` approached 4 on a 16-qubit system.

### Future Directions

Further work is planned to reduce noise and improve computational efficiency, especially for `n >= 4`. Research will continue to explore methods for scaling QAOA in high-node TSP scenarios.

## Getting Started

### Prerequisites

To run this code, you’ll need:

- Python 3.x
- [Qiskit](https://qiskit.org/)

