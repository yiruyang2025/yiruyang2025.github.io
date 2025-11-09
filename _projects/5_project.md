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


## Attended Lectures

  - [27-Nov-2025, 17:00, lecture hall ETH G3 (HCI)](https://www.linkedin.com/posts/eth-d-chab_ruzickaprize2025-ruzickaprize-awardee-activity-7389586307217276928-clEV?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk)



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

  - Dark Matter Detection / Chemistry Simulation

## Formulations

Define the neural manifold evolution:

$$
\frac{d\mathcal{M}_t}{dt} = \mathcal{F}(\mathcal{M}_t, W_t, C_t)
$$

Define the topological stability functional:

$$
S(\mathcal{M}_t) = \int_{\mathcal{M}_t} \kappa(x, t) \, dx
$$

where \( \kappa(x, t) \) denotes local curvature or connectivity density.

Disease onset condition:

$$
\exists \, t_c \; \text{s.t.} \; \frac{dS(\mathcal{M}_t)}{dt}\bigg|_{t = t_c} < -\epsilon
$$



## Philosophical Abstraction

| **Concept** | **Intuitive Meaning** |
|--------------|------------------------|
| Topological invariance | Structural stability of the system |
| Random graph m-coloring | Randomization of connectivity with functional labels |
| Product equals zero | Local structural collapse (functional failure) |
| Loss of constraint (“no card”) | Global coupling and regulation breakdown |
| **→ Result** | Disease emergence as a topological phase transition — not a linear decay |



## Essence

- The onset of disease corresponds to a **topological phase transition** in the 4D neural manifold, where the proportion of non-functional subgraphs exceeds a critical threshold, and the global topological invariants $$(\chi, \beta_k)$$ undergo discontinuous change, signaling the **loss of structural coherence in neural connectivity**.



<br><br><br>
