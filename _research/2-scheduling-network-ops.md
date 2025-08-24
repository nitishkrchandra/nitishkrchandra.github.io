---
title: "Scheduling Network Operations in Distributed Quantum Architectures"
collection: research
date: 2024-05-01
order: 2
header:
  teaser: /assets/images/schedule.png
excerpt: "This work, in collaboration with Cisco Research, compares resource-constrained project scheduling (RCPSP) and greedy heuristic methods for minimizing execution time in distributed quantum circuits."
links:
  - label: "[Paper]"
    url: "https://doi.org/10.1109/TPS-ISA62245.2024.00068"
  - label: "[Code]"
    url: "https://github.com/nitishkrchandra/DQC"
tags:
  - Quantum Networks
  - Scheduling
  - Distributed Systems
  - RCPSP
---

### The Challenge of Scaling Quantum Computers
As quantum computers grow, supporting tens of thousands or millions of qubits with a single monolithic hardware piece becomes infeasible. A more viable approach is Distributed Quantum Computing (DQC), where a large computation is executed over multiple, smaller Quantum Processing Units (QPUs) connected by a quantum network. A critical component for this to work is an efficient scheduler that coordinates the network operations needed to perform non-local entangling gates between the different QPUs. The primary goal is to find a schedule that minimizes the total execution time, known as the "make span".

### A Three-Step Workflow
This research focuses on the final scheduling task within a DQC workflow. Given a quantum circuit, the process is as follows:
1.  **Quantum Circuit Partitioning**: The computational circuit is first divided among the available QPUs. We use the METIS solver to achieve a partition that minimizes the number of non-local gates between QPUs while keeping the qubit workload balanced.
2.  **Extracting Nonlocal Gates**: The non-local entangling gates required by the partitioned circuit are identified.
3.  **Network Operations Scheduling**: The underlying network operations (like link-level entanglement and swaps) are scheduled to create the necessary entanglement for the non-local gates, with the goal of minimizing the total time.

### Comparing Scheduling Strategies: RCPSP vs. Greedy
To find the optimal schedule, we compare and contrast two distinct methods:
* **Resource-Constrained Project Scheduling (RCPSP)**: This is a formal optimization framework that schedules activities (quantum operations) while respecting resource limitations (e.g., a finite number of communication and memory qubits) and precedence constraints. We used PuLP, a Python library, to model and solve the RCPSP instance.
* **Greedy Heuristic Algorithm**: This is a simpler, faster algorithm that makes locally optimal decisions at each time step. It schedules operations as soon as their prerequisite tasks are complete and the necessary resources are available, aiming for a near-optimal solution with much lower computational overhead.

### Key Findings
We tested these strategies by implementing a 4-qubit Quantum Fourier Transform (QFT) circuit on a star network topology with a central quantum switch.
* In a scenario with **two QPUs**, the RCPSP approach clearly outperformed the Greedy algorithm, producing a more efficient schedule by making better use of the limited quantum resources.
* In a more complex scenario with **four QPUs**, both the RCPSP and Greedy methods achieved the exact same make span. While RCPSP uses a holistic strategy, the Greedy algorithm's focus on immediate gains produced a comparably effective result in this specific case.

This research illustrates the effectiveness of the formal RCPSP framework for complex, resource-constrained quantum networks, while also highlighting that simpler greedy heuristics remain a useful and viable option, especially when scalability and computational speed are primary concerns.
