---
title: "Post-Quantum Cryptography in Quantum Networks"
collection: research
date: 2022-09-02
header:
  teaser: /assets/images/pqc.gif
excerpt: "This work analyzes a security model where noisy Bell states and PQC-protected classical channels constrain the information accessible to an adversary."
tags:
  - Quantum Security
  - PQC
  - Quantum Networks
  - Cryptography
---

### The Challenge: Securing Next-Generation Quantum Networks
As we build the quantum internet, securing it is a primary challenge. A practical quantum network will be a hybrid system, relying on quantum channels to distribute entanglement (like Bell states) and classical channels for coordination and control. These classical channels must be secured against adversaries who may one day possess a quantum computer, which requires the use of Post-Quantum Cryptography (PQC). This project investigates the security of such a realistic, hybrid network.

### Our Approach: A Hybrid Security Model
We analyze a security model that considers the practical limitations of a hybrid quantum network. Our model assumes two key conditions:
1.  The quantum links produce **noisy Bell states**, not perfect ones.
2.  The classical control channels are protected by **PQC**, but may be subject to potential key leakage.

### Key Research Questions and Contributions
This research aims to formally quantify the information an adversary can gain in this constrained environment. Our main contributions are:
* We analyze the **fidelity** of the distributed quantum states to understand how they degrade under the combined effects of channel noise and potential vulnerabilities in the classical channel.
* We use the **Holevo information** as a precise measure to quantify the amount of information that leaks to an adversary, particularly modeling the dynamics of how a partial key leakage from the PQC system impacts the overall security of the quantum communication.

A full paper and code repository for this project are currently in preparation.
