---
layout: page
title: 2026 - M-Layer ML for Science Learning
description: Thomas, Jyrki, Lab
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---




<br><br>


## End Goals

- [Pretty visuals](https://valhovey.github.io/gaia-mary/)
- M-Layer for verifying symmetries induced by scientific laws in `high-dimensional observation` space.
- What might be missed in current Theoretical Laws?

**Experiment test**
- Can the model determine whether X=(q,v,a) is a valid physical state?

<br>

## Other Topics 


-  📍 `Unifying fermions and bosons`
-  `new gravitational-wave`
-  Incorporating Maxwell's Equations that describe the electromagnetic field into the Dirac Equation has been a long-term goal in physics to unify quantum electrodynamics (QED) and general relativity


<br>



<br><br><br><br><br>


## Path to M²-Layer

**Core Concept:** `M²-Layer = exp(Mb) * exp(Ma)`

1. **Observe and define the physical state.**
   In the current experiment, each observation is a Lorentz-state pair $x = (v, E)$. The physical manifold is defined by:
   $$
   E^2(1 - v^2) = 1
   $$
   with $y = 0$ denoting physical samples and $y = 1$ denoting non-physical samples. The model therefore acts as a physical-law verifier rather than a full dynamical simulator.

2. **Learn the original M-Layer generator.**
   The current M-Layer constructs a state-dependent matrix:
   $$
   M_\theta(x) = \sum_i x_i T_i
   $$
   and evaluates a matrix-exponential score:
   $$
   r_\theta(x) = \mathrm{Tr}(\exp(M_\theta(x))S)
   $$
   The physical law is represented as an implicit zero set $r_\theta(x) = 0$. Thus, the current model is an algebraic physical-law verifier, not yet a one-step ODE/PDE flow map.

3. **Upgrade to a composed M²-Layer.**
   The next architecture should not square the matrix literally as $\exp(M^2)$. Instead, it should compose two learned M-Layer flows:
   $$
   g_\theta(x) = \exp(M_b(x))\exp(M_a(x))
   $$
   By the Baker–Campbell–Hausdorff expansion:
   $$
   \exp(M_b)\exp(M_a) = \exp\left(M_a + M_b + \frac{1}{2}[M_b, M_a] + \dots\right)
   $$
   where:
   $$
   [M_b, M_a] = M_b M_a - M_a M_b
   $$
   The commutator term introduces curvature and non-commutative interactions that a single exponential generator cannot express. This is the natural next step suggested by the hard-negative failure in the current ablation.

   <br>

**Three Key Metrics**

  - ROC-AUC
    - Does the learned score separate physical from unphysical samples across thresholds?
  - Poincaré section consistency
    - 📍 Recover the same phase-space section geometry as the true dynamical system.
  - Zero-shot / Systematic Generalization / (Out-of-Distribution (OOD) Generalization Ability)



<br><br>


## Lorentz data

- 1D

```
gamma / energy
   ^
   |                              /
   |                            /
   |                         /
   |                      /
   |                  /
   |             __/
   |        __/
   |______/________________________> beta = v/c
        0        0.5       0.9   1
```

<br>

- 2D

```
beta_y
  ^
  |        high gamma near boundary
  |       ***********************
  |     ***                     ***
  |    **       low gamma         **
  |    **        near center      **
  |     ***                     ***
  |       ***********************
  +-------------------------------> beta_x
```



<br>


## When Choose Which Structure

| Space Type                 | Example                                | Original M-Layer |    M²-Layer |
| -------------------------- | -------------------------------------- | ---------------: | ----------: |
| Algebraic constraint space | ((v,E)), ((p,E))                       |           Enough |    Optional |
| Simple state space         | ((q,v,a)) one law                      |     Often enough |    Optional |
| Phase space                | ((q,p)) with multiple invariants       |         May fail |      Useful |
| Function space             | (u(t,x)) PDE field                     |          Limited |      Useful |
| Operator / Hilbert space   | quantum (H_a,H_b)                      |          Limited | Very useful |
| Gauge / curvature space    | field connection, commutator curvature |       Not enough |      Needed |




<br>

## What Else Can be Verified?

| Frontier Problem                   | Core Open Question                                                                  | Why                                                                                                                           | AI / M-Layer Direction                                                                                                                                                    |
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


<br>




<br>


## Physical Spaces

| Layer | Physical / Mathematical Theory | Proposed by / Historical Origin | Year / Period | Representative Space | Representative Dimension | Core State Variable | Core Law / Object | Relevance to GOES / NOAA Energetic-Particle Data | Meaning for M-Layer / Stage III |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Euclidean physical space | Euclid | c. 300 BCE | Classical geometric space | 3D | Position $(\mathbf{x}\in\mathbb{R}^3)$ | Distance, angle, straight line | The basic spatial background for satellite position, Earth-centered coordinates, and magnetospheric geometry | The lowest-level space in which GOES occupies a point on a geostationary orbit |
| 2 | Newtonian absolute space and time | Isaac Newton | 1687 | Absolute space plus absolute time | (3+1)D | $(\mathbf{x},t)$ | $\mathbf{F}=m\mathbf{a}$, inverse-square gravity | Provides the classical orbital description of GOES around Earth | Useful for satellite ephemeris, but not sufficient for plasma-field reconstruction |
| 3 | Keplerian orbital geometry | Johannes Kepler | 1609–1619 | Conic-section orbital space | 2D orbital plane embedded in 3D | Orbital elements $(a,e,i,\Omega,\omega,M)$ | Elliptic motion, area law, harmonic law | Describes idealized satellite/planetary motion before perturbations | Gives a controlled synthetic benchmark, but not the real MHD field |
| 4 | Lagrangian mechanics | Joseph-Louis Lagrange | 1788 | Configuration manifold and tangent bundle | $n$-D configuration; $2n$-D tangent state | $(q,\dot{q})$ | Euler–Lagrange equations | Useful for formulating particles moving under electromagnetic fields | Connects observed particle motion to hidden variational structure |
| 5 | Hamiltonian mechanics | William Rowan Hamilton | 1833–1835 | Phase space | $2n$-D for $n$ degrees of freedom | $(q,p)$ | Hamiltonian flow $(\dot{q}=\partial H/\partial p, \dot{p}=-\partial H/\partial q)$ | Charged-particle motion in magnetic fields is naturally Hamiltonian or nearly Hamiltonian | M-Layer can be interpreted as learning a generator of flow rather than a static classifier |
| 6 | Symplectic geometry | Hamilton, Jacobi, Poincaré; modern formalization by Hermann Weyl and others | 19th–20th century | Symplectic manifold | | | | | |





<br><br>


## ODE

| Person / period | Year | Problem they cared about | Equation style | Essence |
|---|---:|---|---|---|
| Newton / Leibniz | 1660s–1670s | Motion, curves, and rates of change | $\frac{dy}{dx}=f(x,y)$ | Differential equations emerge from calculus |
| Newton | 1687 | Planetary motion and mechanics | $m\ddot{q}=F(q)$ | Physical motion as time evolution |
| Jacob Bernoulli / Leibniz | 1695–1696 | Solvable nonlinear first-order equations | $y' + P(x)y = Q(x)y^n$ | Early named ODE family |
| Euler | 1700s, especially 1730s–1760s | Mechanics, astronomy, fluids, and variational problems | Systematic ODE methods | ODEs become a general mathematical tool |
| Cauchy | Early 1800s | Existence, uniqueness, and initial-value problems | $y(t_0)=y_0$ | Foundation of modern rigorous ODE theory |

<br>

## PDE

| Person / period | Year | Problem they cared about | Equation style | Essence |
|---|---:|---|---|---|
| d’Alembert | 1747 | Vibrating strings | $u_{tt}=c^2u_{xx}$ | Wave propagation |
| Euler / Daniel Bernoulli | 1740s–1750s | Strings, fluids, and continuum mechanics | Early PDE models | Motion of continuous media |
| Laplace | Late 1700s | Gravitational and electrostatic potential | $\Delta \phi=0$ | Equilibrium fields |
| Fourier | 1807 / 1822 | Heat conduction | $u_t=\kappa u_{xx}$ | Diffusion of a temperature field |
| Poisson | 1810s | Potential fields with sources | $\Delta \phi=f$ | Fields generated by matter or sources |
| Navier / Stokes | 1822 / 1845 | Viscous fluid flow | Navier–Stokes equations | Evolution of fluid velocity fields |
| Maxwell | 1861–1865 | Electricity and magnetism | Coupled PDEs for $\mathbf{E}$ and $\mathbf{B}$ fields | Electromagnetic field theory |
| Einstein | 1915 | Gravity as spacetime geometry | Einstein field equations | Dynamics of the spacetime metric field |



<br><br>



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


2. Houdini


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
  



<br><br><br><br><br><br><br><br><br><br>



<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>


## References


- [2019 - SO(8) Supergravity and the Magic of Machine Learning]()
- [2023 - On backpropagating Hessians through ODEs](https://arxiv.org/pdf/2301.08085)
- [2007 - A systematic approach to multiphysics extensions of finite-element-based micromagnetic simulations: Nmag](https://eprints.soton.ac.uk/46725/1/Fisc_07.pdf), Operator-based Abstraction




<br><br>


## Bio process

- [1](https://books.google.ch/books/about/Analysis_Synthesis_and_Design_of_Chemica.html?id=f6sbYJuFSycC&redir_esc=y) 2012, Analysis, Synthesis, and Design of Chemical Processes. 



<br><br>


## Lie Group, ODE, and Chaos

- [1] Georgi, Howard. Lie Algebras in Particle Physics. 2nd ed. Boca Raton: CRC Press, 2018.
- 📍 [2] Hairer, Ernst, and Gerhard Wanner. Solving Ordinary Differential Equations II: Stiff and Differential-Algebraic Problems. 2nd rev. ed. Berlin: Springer, 2010.
- [3] Sussman, Gerald Jay, and Jack Wisdom. Structure and Interpretation of Classical Mechanics. 2nd ed. Cambridge, MA: MIT Press, 2015.
- 📍 [4] Strogatz, Steven H. Nonlinear Dynamics and Chaos: With Applications to Physics, Biology, Chemistry, and Engineering. 2nd ed. Boulder: Westview Press, 2018. (Nonlinear Dynamics / Benchmark ODE)
- [5] Hall, Brian C. Lie Groups, Lie Algebras, and Representations: An Elementary Introduction. 2nd ed. Cham: Springer, 2015.



<br><br>


## References 2


- [2026 - High-Dimensional Probability](https://www.math.uci.edu/~rvershyn/papers/HDP-book/HDP-2.pdf)

<br>

**1. ODE**

- [2025 - Life at the boundary of chemical kinetics and program execution](https://arxiv.org/pdf/2503.19177), physical constraints
- 1931 - Hamiltonian Systems and Transformation in Hilbert Space
  - nonlinear dynamics can be represented as linear transformations on a Hilbert space of observables.
  - [2024 - Soliton dynamics and multistability analysis of the Hamiltonian amplitude model](https://www.sciencedirect.com/science/article/pii/S2211379724005631)
- [2026 - Paving the way for agents in biology](https://www.anthropic.com/research/agents-in-biology)

<br>


**2.Hamiltonian Systems and Operators**


- Hamiltonian system
- Hilbert space: Transition from state point to function space
- Weierstrass Approximation Theorem
- Lie operator, Unitary operator
- Flow map


<br>


**3. Topological Defect**


- The data manifold is extremely distorted, dimensionally reduced, or has broken connectivity in this region.

<br>


**4. Activation Functions and Field Theories**



<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>



## Other Topics

- [2026 - Geometric Signatures of Reasoning: A Spectral Perspective on Task Hardness](https://arxiv.org/abs/2406.19108)
- [2023 - Seeing a Rose in Five Thousand Ways](https://ai.stanford.edu/~yzzhang/projects/rose/)




<br><br><br><br><br><br><br><br>



<br><br><br><br><br>
