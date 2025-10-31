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

  - [📍 Click Here](https://zenodo.org/), [AiiDA.net](https://www.aiida.net/)
  - [Thesis](https://sirop.org/app/013a8549-281d-475b-bc42-1a63fff75d98?_k=D4wOn3UvPzaQuIzU)

  
  - [Physiology or Medicine](https://www.nobelprize.org/prizes/lists/all-nobel-laureates-in-physiology-or-medicine/), [Physics](https://www.nobelprize.org/prizes/lists/all-nobel-prizes-in-physics/)
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


- In the brain connectivity matrix, random matrix theory helps us identify which connectivity patterns are `functional (signal)` and which are just random noise (noise)

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

## Dark Matter Detection / Chemistry Simulation



<br><br><br>
