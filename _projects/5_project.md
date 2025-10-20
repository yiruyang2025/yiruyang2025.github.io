---
layout: page
title: 2026 - Thesis - AI Simulation
description: Scientific Research
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>

## Topics

  - [📍 Click Here](https://zenodo.org/)
  - [Physiology or Medicine](https://www.nobelprize.org/prizes/lists/all-nobel-laureates-in-physiology-or-medicine/)
  - [Physics](https://www.nobelprize.org/prizes/lists/all-nobel-prizes-in-physics/)
  - [2025 - 12](https://www.uzh.ch/en/researchinnovation/excellence/nobelprize.html), [2025 - 22](https://ethz.ch/en/the-eth-zurich/portrait/awards/nobel-prize-laureates.html)

  - [CERN](https://home.cern/), [PSI](https://www.psi.ch/en)

<br>


## References

  - [2025 - ZapBench](https://github.com/google-research/zapbench)
  - [2025 - DeepSomatic](https://www.nature.com/articles/s41587-025-02839-x)
  - [Development of the Nervous System](https://www.mls.uzh.ch/en/research/hajnal/teaching.html)
    - [Stoeckli Esther](https://www.mls.uzh.ch/en/research/stoeckli/research.html)
  - [2025 - some others - Discovering Symbolic Cognitive Models from Human and Animal Behavior](https://www.biorxiv.org/content/10.1101/2025.02.05.636732v1)


<br>

## [1/2] Physiology or Medicine



| Core Principle                                              | Description                                                                                                                                                     | Mathematical Framework                                               |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| **High-dimensional dynamic modeling of structural systems** | Whether in neuronal networks, molecular structures, or protein folding, all study the state evolution of complex network systems.                               | Graph Theory, Dynamical Systems, Tensor / PDE Simulation             |
| **Energy optimization over probability distributions**      | All aim to find the lowest-energy, most stable, or most probable configurations.                                                                                | Energy-based Models, Free Energy Minimization, Statistical Mechanics |
| **Modeling information flow in continuous space**           | Whether synaptic signaling, electron wave functions, or chemical bonding, all involve solving evolution equations of probability densities in continuous space. | Schrödinger Equation, Fokker–Planck Equation, Diffusion Equation     |
| **Topological and graph embedding problems**                | Both connectomes and molecular bond structures can be abstracted as graphs of nodes, edges, and weights.                                                        | Graph Laplacian, Spectral Graph Theory, Graph Neural Networks (GNNs) |
| **Approximation of many-body interactions**                 | Both electron cloud interactions and synaptic electrical signals represent nonlinear coupling in many-body systems.                                             | Mean-field Approximation, Monte Carlo Simulation, Neural PDE Solver  |

<br>

## Chemistry Simulation

| Field                    | Core Problem                                                                                                      | Computability                                                                         | Tools / Methods                                                        |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **Chemistry Simulation** | Predict the most stable molecular geometry and electron distribution from a known formula (minimum energy state). | Solvable but complex (requires approximation).                                        | DFT, QM/MM, Diffusion-based molecular generative models                |
| **Connectomics**         | Reconstruct the brain’s complete neural topology and functional coupling.                                         | Extremely large-scale (≈10¹⁴ synapses).                                               | FFN, SENSE, SHAPE, GNN, Transformer                                    |
| **Alzheimer’s Disease**  | Explain how structural degeneration leads to cognitive decline.                                                   | Highly complex and non-deterministic (biological variability and temporal evolution). | Graph Diffusion Models, Protein Misfolding Simulation, Causal Modeling |


<br>

```
┌─────────────────────────────────┐
│  Chemistry Simulation (DFT, QM) │ ← Microscopic Level
│  → Computes atomic interactions │
└──────────────┬──────────────────┘
               ↓
┌────────────────────────────────┐
│  Connectomics                  │ ← Mesoscopic Level
│  → Maps neuron-to-neuron graph │
└──────────────┬─────────────────┘
               ↓
┌───────────────────────────────┐
│  Alzheimer’s Disease Modeling │ ← Macroscopic Level
│  → Studies functional decline │
└───────────────────────────────┘
```

<br>


## [2/2] Connectomics - 4D Reconstruction

## Dark Matter Detection


| **Dimension**                             | **Description**                                                                                                                                                                                                                                                                                                 |
| ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Project Title**                         | Hybrid Quantum–Classical Simulation for Dark Matter Detection and Cosmological Field Evolution                                                                                                                                                                                                                  |
| **Objective**                             | Develop a scalable hybrid framework that combines **GPU-accelerated particle simulations** and **quantum-inspired inference algorithms** to model the nonlinear interactions, propagation, and detection signatures of **dark matter candidates** in astrophysical and laboratory environments.                 |
| **Physical Scope**                        | Simulation of **dark matter–baryon scattering**, **weakly interacting massive particles (WIMPs)**, and **axion-like field dynamics** across galactic and detector-scale domains; includes modeling of gravitational lensing effects and cosmic microwave background (CMB) perturbations induced by dark matter. |
| **Computational Components**              | GPU-based Monte Carlo event generators, lattice discretization of scalar fields, OpenMP/MPI-based parallel solvers for N-body cosmological evolution, and tensor-contraction engines for simulating dark-matter–nucleus interactions.                                                                           |
| **Quantum / Quantum-Inspired Components** | Quantum Boltzmann solvers for stochastic field evolution, **Variational Quantum Eigensolvers (VQE)** for potential landscape estimation, **Quantum Phase Estimation (QPE)** for particle mass spectrum inference, and **Quantum Annealing** for detector event reconstruction.                                  |
| **Key Theoretical Foundations**           | Cosmological ΛCDM model, Quantum Field Theory (QFT) for dark-sector interactions, Supersymmetry (SUSY) and Axion frameworks, Gauge symmetry extensions (U(1)′, SU(2)×U(1)), and General Relativity for large-scale gravitational coupling.                                                                      |
| **AI Integration**                        | Application of **Physics-Informed Neural Networks (PINNs)** for solving Boltzmann transport equations, **Graph Neural Networks (GNNs)** for detector event topology analysis, and **reinforcement learning** for adaptive parameter search in cosmological simulations.                                         |
| **Parallelization Strategy**              | Distributed **GPU + QPU** co-simulation of dark-matter fields with up to 10⁹ spatial nodes; real-time data exchange via **CUDA-aware MPI**, enabling hybrid training of AI surrogates for potential mapping and likelihood estimation.                                                                          |
| **Key Advantages**                        | • Bridges particle-scale interactions and cosmological observables via hybrid quantum–classical modeling<br>• Accelerates search for dark-matter particle properties using AI-guided simulation<br>• Reduces statistical noise through quantum-enhanced sampling and feature mapping                            |
| **Experimental Relevance**                | Applicable to **XENONnT, LUX-ZEPLIN, PandaX**, and **CERN Dark Sector** experiments; enables synthetic event generation for detector calibration and statistical inference of dark-matter mass and cross-section limits.                                                                                        |
| **Short-Term Goals (1–3 years)**          | Integrate GPU-based N-body solvers with quantum-inspired inference modules; reproduce dark-matter halo evolution and direct detection recoil spectra consistent with experimental sensitivity thresholds.                                                                                                       |
| **Mid-Term Goals (3–5 years)**            | Execute hybrid GPU–QPU co-simulations of WIMP and axion interactions; test AI-accelerated reconstruction pipelines for dark-matter–nucleus scattering signatures in underground detectors.                                                                                                                      |
| **Long-Term Goals (5+ years)**            | Perform **4D quantum lattice simulations** of coupled dark-sector fields using exascale GPU clusters and emerging fault-tolerant quantum processors; refine cosmological constraints on dark-matter composition and distribution.                                                                               |
| **Collaborative Ecosystem**               | **CERN** (Dark Sector & ATLAS groups), **ETH Zurich Quantum Computing Hub**, **PSI** (Astroparticle Physics), **Gran Sasso Laboratory** (XENONnT collaboration), and **IBM Zurich** (Qiskit Runtime Integration).                                                                                               |

<br>
