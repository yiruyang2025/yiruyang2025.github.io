---
layout: page
title: 2026 - Thesis - Quantum Computing
description: Acceleration (, xx)
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>


## Quantum Computing Acceleration


<br>

```
┌────────────────────────────────────────────────────────────┐
│                  Classical HPC Simulation (GPU/CUDA)       │
│  • Solving Relativistic Field Equations (Higgs, QED, QCD)  │
│  • Lattice discretization and tensor updates               │
│  • CUDA kernels for parallel PDE integration               │
│  ↓                                                         │
│  Real-time field data streams                              │
└──────────────┬─────────────────────────────────────────────┘
               │
               ▼
┌────────────────────────────────────────────────────────────┐
│       Quantum Processing Layer (QPU / Quantum Emulator)    │
│  • Quantum feature mapping of field states                 │
│  • Variational Quantum Eigensolver (VQE) for energy minima │
│  • Quantum Phase Estimation (QPE) for mass spectrum        │
│  • Quantum kernel feedback → parameter updates             │
└──────────────┬─────────────────────────────────────────────┘
               │
               ▼
┌────────────────────────────────────────────────────────────┐
│               AI Control & Optimization Loop               │
│  • Physics-Informed Neural Networks (PINN)                 │
│  • Reinforcement Learning for mesh adaptation              │
│  • Gradient alignment between GPU and QPU states           │
│  • Monitoring convergence and physical invariants          │
└────────────────────────────────────────────────────────────┘
```


<br>

| **Dimension**                             | **Description**                                                                                                                                                                                                                         |
| ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Project Title**                         | Hybrid Quantum–Classical Simulation for Higgs Field Dynamics and Relativistic Plasma Interactions                                                                                                                                       |
| **Objective**                             | Develop a scalable hybrid framework combining **CUDA-based parallel numerical solvers** and **quantum-inspired algorithms** to simulate nonlinear dynamics in **quantum field theory (QFT)** and **free-electron laser (FEL)** systems. |
| **Physical Scope**                        | Simulation of **Higgs field interactions**, **electroweak symmetry breaking**, and **relativistic charged-particle motion** in undulator magnetic fields (as in PSI FEL/Genesis systems).                                               |
| **Computational Components**              | GPU-accelerated solvers (CUDA, OpenMP, MPI), spectral time-evolution methods, lattice discretization for field equations, tensor contraction engines for gauge fields.                                                                  |
| **Quantum / Quantum-Inspired Components** | Variational Quantum Eigensolvers (VQE) for potential minimization; Quantum Phase Estimation (QPE) for particle mass spectra; Quantum Lattice Field Simulation via Trotter decomposition.                                                |
| **Key Theoretical Foundations**           | Quantum Electrodynamics (QED), Quantum Chromodynamics (QCD), Higgs mechanism, Yang–Mills gauge theory, and numerical relativity under curved spacetime metrics.                                                                         |
| **AI Integration**                        | Neural PDE solvers and physics-informed neural networks (PINNs) for approximating field evolution; reinforcement learning for adaptive mesh refinement and simulation control.                                                          |
| **Parallelization Strategy**              | Distributed GPU simulation of field lattices (10⁹+ grid points), real-time data exchange via CUDA-aware MPI; hybrid GPU + QPU loops for energy minimization and gradient sampling.                                                      |
| **Key Advantages**                        | • Accelerates large-scale QFT simulation via GPU + quantum co-processing<br>• Enables dynamic exploration of Higgs potential surfaces<br>• Reduces numerical instability via quantum feature maps                                       |
| **Experimental Relevance**                | Applicable to PSI and CERN FEL beamline simulations, Higgs potential parameter scanning, and plasma–beam interaction modeling in high-intensity accelerators.                                                                           |
| **Short-Term Goals (1–3 years)**          | Integrate CUDA-based QFT solvers with hybrid Qiskit / PennyLane modules; reproduce 1D–2D Higgs field evolution and compare with analytic symmetry-breaking solutions.                                                                   |
| **Mid-Term Goals (3–7 years)**            | Run hybrid GPU–QPU experiments on small-scale quantum processors; simulate multi-field coupling (Higgs + gauge fields) with partial quantum updates.                                                                                    |
| **Long-Term Goals (7+ years)**            | Full 3D–4D quantum lattice field simulation using exascale GPU clusters + fault-tolerant quantum processors for precision Higgs and dark-matter field modeling.                                                                         |
| **Collaborative Ecosystem**               | PSI (FEL beamline physics), CERN (QFT lattice benchmarking), ETH Zurich (Quantum Computing Hub), IBM Zurich (Qiskit runtime integration).                                                                                               |

<br>
