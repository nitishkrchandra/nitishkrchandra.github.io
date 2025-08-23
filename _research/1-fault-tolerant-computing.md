---
title: "Fault-Tolerant Measurement Based Quantum Computing"
collection: research
date: 2022-09-01
header:
  teaser: /assets/images/ftqc.gif
excerpt: "This project investigates a fault-tolerant quantum computing architecture using dual-species trapped-ion (DSTI) modules to generate topologically protected RHG cluster states."
links:
  - label: "[Paper]"
    url: "https://arxiv.org/pdf/2411.08616"
  - label: "[Code]"
    url: "https://github.com/nitishkrchandra/FTQC-Trapped-Ion"
tags:
  - Quantum Computing
  - Fault Tolerance
  - Trapped Ions
  - MBQC
---

### Overview
[cite_start]This work proposes and analyzes an architecture for fault-tolerant measurement-based quantum computation (FT-MBQC) built upon optically-networked trapped-ion modules[cite: 7]. [cite_start]The architecture uses photonic interactions for remote entanglement between modules and local Coulomb interactions for gates within modules[cite: 8]. [cite_start]We focus on generating the Raussendorf-Harrington-Goyal (RHG) lattice, a topologically protected cluster state known for its robustness against qubit noise and bond failures[cite: 9].

### Key Contributions
The main contributions of this research include:

* **Bi-Layered Realization**: We outline a method to generate the RHG lattice using a limited number of trapped-ion modules, equivalent to just two layers of the lattice. [cite_start]This is achieved by re-initializing qubits after measurement and employing space-and-time multiplexed remote entanglement[cite: 55].
* [cite_start]**Resource and Timing Analysis**: We derive the time required for a complete code cycle and calculate the ion resources needed to keep the entanglement failure rate below the fault-tolerance threshold[cite: 56, 57]. [cite_start]We also analyze the impact of incorporating quantum repeaters to mitigate the resource costs over large distances[cite: 58].
* **Noise-Tolerance Threshold**: We derive a comprehensive noise-tolerance threshold inequality. [cite_start]This accounts for depolarizing noise from realistic photonic entanglement generation (including detector noise and dark clicks), imperfect gates, and memory decoherence over time[cite: 59, 60, 61].

### Core Mathematical Results
Two key mathematical results from this work are the multiplexing requirement to overcome bond failures and the final inequality for the noise-tolerance threshold.

**1. Multiplexing Requirement**
To ensure the remote entanglement success rate ($p'$) surpasses the bond-failure tolerance threshold of the RHG lattice ($p_{th}$), we use spatial multiplexing (M) and temporal multiplexing (m). The required multiplexing product is given by:

$$ Mm = \frac{\log(1-p_{th})}{\log(1-p)} $$

[cite_start]where *p* is the success probability of a single entanglement attempt[cite: 216].

**2. Noise Tolerance Inequality**
To operate in the fault-tolerant regime, the system's noise parameters must satisfy the following inequality, which accounts for gate errors ($\epsilon$), decoherence ($T/\tau_{D}$), and depolarizing noise from remote entanglement ($\beta_{1}$):

$$ \epsilon+\frac{35}{16}\frac{T}{\tau_{D}}+\frac{35}{64}(1-\sqrt{\beta_{1}})<3.9\times10^{-3} $$

[cite_start]This inequality defines the operational window for the system, ensuring that the combined noise sources remain below the fault-tolerance threshold of the RHG lattice[cite: 602, 877].
