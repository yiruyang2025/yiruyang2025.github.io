---
layout: page
title: 2026 - Important Thesis - M-Layer on Scientific Law Verification
description: Thomas, Jyrki, Lab
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---



<br><br>


## End Goals




```
Original experiment test:
  - Can the model determine whether X=(q,v,a) is physical?

Extended experiment test:
  - Can the model learn the nonlinear Hamiltonian flow as a linear operator in observable space?

End goals:
  - Finding linear symmetry representations of nonlinear dynamic systems in infinite-dimensional Hilbert space (Linear Representation of Symmetries)

Paths:
  - Use the M-Layer neural network to parameterize a Lie algebra generator (Lie Operator) to learn a strictly energy-preserving and volume-preserving evolutionary group (Unitary Flow Map) in the infinite-dimensional Hilbert space, so as to accurately predict complex nonlinear Hamiltonian physical systems.
```


<br>

- A machine-learning framework for discovering and verifying the constraint manifolds `induced by scientific laws` in high-dimensional `observation` space.


<br>

## What Else Can be Verified?

| Frontier Problem                   | Core Open Question                                                                  | Why It Is Nobel-Level                                                                                                                           | AI / M-Layer Direction                                                                                                                                                    |
| ---------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Quantum Gravity**                | How can general relativity and quantum mechanics be unified?                        | It asks what spacetime is at the Planck scale.                                                                                                  | Learn whether observed dynamics lie on hidden constraint manifolds consistent with classical, semiclassical, or beyond-GR regimes.                                        |
| **Dark Matter**                    | Is dark matter a particle, a field, primordial black holes, or modified gravity?    | Most matter in the universe is gravitationally visible but physically unidentified.                                                             | Use high-dimensional classifiers to distinguish Newtonian gravity, dark matter halos, and modified-gravity trajectories from lensing and galaxy dynamics.                 |
| **Dark Energy**                    | Is cosmic acceleration caused by a cosmological constant or evolving dark energy?   | Recent DESI results strengthen hints that dark energy may evolve over time. ([DESI][1])                                                         | Learn deviations from ΛCDM as geometric constraints in cosmological trajectory space.                                                                                     |
| **Black Hole Information Problem** | Does black hole evaporation preserve quantum information?                           | It tests the consistency of quantum mechanics, thermodynamics, and gravity.                                                                     | Use AI as a verifier for whether simulated black-hole dynamics obey conservation, entropy, and causal constraints.                                                        |
| **Testing General Relativity**     | Does Einstein gravity remain exact in strong-field regimes?                         | Gravitational waves allow direct tests near merging black holes. Current LIGO-Virgo-KAGRA analyses remain consistent with GR. ([aei.mpg.de][2]) | Train physical-law verifiers on waveform manifolds to detect subtle beyond-GR deviations.                                                                                 |
| **Gravitational-Wave Discovery**   | Can we extract weak, noisy, rare signals from detector data?                        | It opens a new observational channel for black holes, neutron stars, and early-universe physics.                                                | AI is already used for denoising, waveform modeling, and parameter estimation in gravitational-wave pipelines. ([Hep Journals][3])                                        |
| **Cosmic Structure Formation**     | How did galaxies, halos, filaments, and voids emerge from early fluctuations?       | It connects gravity, dark matter, baryons, and cosmology across billions of years.                                                              | Learn compact latent laws from simulations and surveys; explainable ML has already found interpretable structure in dark-matter halo profiles. ([mpa-garching.mpg.de][4]) |
| **Weak Lensing and Hidden Mass**   | Can we reconstruct invisible matter from distorted galaxy images?                   | Lensing is one of the cleanest probes of dark matter and dark energy.                                                                           | Use AI-assisted simulation-based inference and constraint learning to map hidden mass fields from sparse observations. ([Imperial College London][5])                     |
| **Modified Gravity**               | Are cosmic anomalies caused by unseen matter or by a failure of GR at large scales? | It challenges the foundation of modern cosmology.                                                                                               | Build contrastive datasets: GR-valid trajectories vs modified-gravity trajectories, then learn the separating physical manifold.                                          |
| **From Galaxies to Cells**         | Can one learning principle discover lawful dynamics across scales?                  | It would unify scientific ML beyond domain-specific prediction.                                                                                 | M-Layer can be framed as a high-dimensional physical constraint learner: not predicting one trajectory, but verifying whether a system belongs to the lawful manifold.    |

[1]: https://www.desi.lbl.gov/?utm_source=chatgpt.com "Dark Energy Spectroscopic Instrument (DESI)"
[2]: https://www.aei.mpg.de/1442601/testing-general-relativity-with-new-gravitational-wave-observations?utm_source=chatgpt.com "Testing general relativity with new gravitational-wave ..."
[3]: https://journal.hep.com.cn/fop/EN/10.15302/frontphys.2025.045301?utm_source=chatgpt.com "Dawning of a new era in gravitational wave data analysis"
[4]: https://www.mpa-garching.mpg.de/1098943/hl202407?utm_source=chatgpt.com "Explaining the density profiles of dark matter halos with neural ..."
[5]: https://www.imperial.ac.uk/news/articles/natural-sciences/physics/2026/ai-and-physics-combine-to-deliver-the-sharpest-weak-lensing-view-of-the-dark-universe/?utm_source=chatgpt.com "AI and physics combine to deliver the sharpest weak ..."







<br><br><br><br><br><br><br>






## Toolkit

**1. ODE**


- [2025 - Life at the boundary of chemical kinetics and program execution](https://arxiv.org/pdf/2503.19177), physical constraints
- 1931 - Hamiltonian Systems and Transformation in Hilbert Space
  - nonlinear dynamics can be represented as linear transformations on a Hilbert space of observables.
  - [2024 - Soliton dynamics and multistability analysis of the Hamiltonian amplitude model](https://www.sciencedirect.com/science/article/pii/S2211379724005631)
- [2026 - Paving the way for agents in biology](https://www.anthropic.com/research/agents-in-biology)

<br><br><br><br><br><br><br><br>


**2.Hamiltonian Systems and Operators**


- Hamiltonian system
- Hilbert space: Transition from state point to function space
- Weierstrass Approximation Theorem
  - Universal Approximation Theorem, Bézier Curve
- Lie operator, Unitary operator
- Flow map

<br>

<br><br><br><br><br><br><br><br>



**3. Topological Defect**



- The data manifold is extremely distorted, dimensionally reduced, or has broken connectivity in this region.

<br>

<br><br><br><br><br><br><br><br>


**4. PDE / MHD, or Benchmark paper**


```
learning hidden physical fields from sparse multimodal observations
```



- [2026 - A study confirms the role of magnetic fields in early stages of star formation](https://ice.csic.es/news/news-press-releases?view=article&id=951:a-study-confirms-the-role-of-magnetic-fields-in-early-stages-of-star-formation&catid=8)


```
multimodal observation
magnetic-field inference
streamer reconstruction
MHD-constrained dynamics
future disk prediction

ALMA / MHD simulation infers hidden protostellar dynamics
→ export magnetic fields, streamers, and gas-flow trajectories
→ CesiumJS / Three.js visualizes magnetogravitational accretion beautifully
```



<br><br><br><br><br><br><br><br><br><br>



**5. Activation Functions and Field Theories**






<br><br><br><br><br><br><br><br><br><br>



## Simulation


1. 📍 NASA GMAT
   - [link](https://github.com/nasa/GMAT?utm_source=chatgpt.com)
  
2. [Raindrops](https://www.linkedin.com/posts/hamidnaderiyeganeh_i-drew-this-view-of-raindrops-falling-into-share-7460704798078840832-hu-M/?utm_source=social_share_send&utm_medium=ios_app&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk&utm_campaign=copy_link)

```
trajectory generation
mission scenario
orbit propagation
lunar / deep-space transfer
navigation analysis

GMAT / Basilisk generates trajectory
→ export trajectory points
→ CesiumJS / Three.js visualizes it beautifully
```


<br><br>


## Visualization

1. NASA Eyes / Eyes on the Solar System
   - [link](https://eyes.nasa.gov/apps/solar-system/#/home)

```
3D scene
+ time controller
+ camera fly-through
+ mission trajectory
+ object labels
+ information panel
```

<br><br>


## Web Interaction

1. NASA/mission-viz
   - [link](https://github.com/nasa/mission-viz)
   - CesiumJS / Three.js
  



<br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>





## References


- [2019 - SO(8) Supergravity and the Magic of Machine Learning]()
- [2023 - On backpropagating Hessians through ODEs](https://arxiv.org/pdf/2301.08085)
- [2007 - A systematic approach to multiphysics extensions of finite-element-based micromagnetic simulations: Nmag](https://eprints.soton.ac.uk/46725/1/Fisc_07.pdf), Operator-based Abstraction
- []




<br><br>


## Lie Group, ODE, and Chaos

- [1] Georgi, Howard. Lie Algebras in Particle Physics. 2nd ed. Boca Raton: CRC Press, 2018.
- 📍 [2] Hairer, Ernst, and Gerhard Wanner. Solving Ordinary Differential Equations II: Stiff and Differential-Algebraic Problems. 2nd rev. ed. Berlin: Springer, 2010.
- [3] Sussman, Gerald Jay, and Jack Wisdom. Structure and Interpretation of Classical Mechanics. 2nd ed. Cambridge, MA: MIT Press, 2015.
- 📍 [4] Strogatz, Steven H. Nonlinear Dynamics and Chaos: With Applications to Physics, Biology, Chemistry, and Engineering. 2nd ed. Boulder: Westview Press, 2018. (Nonlinear Dynamics / Benchmark ODE)
- [5] Hall, Brian C. Lie Groups, Lie Algebras, and Representations: An Elementary Introduction. 2nd ed. Cham: Springer, 2015.



<br><br>


## References 2


- []
- [2026 - High-Dimensional Probability](https://www.math.uci.edu/~rvershyn/papers/HDP-book/HDP-2.pdf)
- [2023 - Seeing a Rose in Five Thousand Ways](https://ai.stanford.edu/~yzzhang/projects/rose/)
- [2025 - Visual Chronicles: Using Multimodal LLMs to Analyze Massive Collections of Images](https://arxiv.org/pdf/2504.08727)
- [2026 - Reward-Conditioned Reinforcement Learning](https://arxiv.org/pdf/2603.05066)

<br>

<br><br><br><br>







<br><br><br><br><br>
