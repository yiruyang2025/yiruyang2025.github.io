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


<br><br><br><br>

## Other Topics 


-  Unifying fermions and bosons
-  Incorporating Maxwell's Equations that describe the electromagnetic field into the Dirac Equation has been a long-term goal in physics to unify quantum electrodynamics (QED) and general relativity


<br><br><br><br><br><br>


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

<br>

**Observed Data / MHD**


- GOES / Geostationary Operational Environmental Satellites, NOAA energetic particle data
  - These data represent extremely limited, single-point real-world observations of highly nonlinear magnetohydrodynamic (MHD) systems in infinite-dimensional `Hilbert space`.
  - The 📍 input feature x(t) received by the model is a high-dimensional tensor containing the local energy spectrum and pitch angle distribution. Essentially, the model attempts to use an M-layer to inversely 📍 derive the global unitary flow map that produces these particles from this high-dimensional time series.



<br>


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


## High-Dimensional Constraints Induced by Scientific Laws

| Domain | Scientific Law / Equation | Formula | Physical Meaning | What M-Layer Can Verify or Learn |
|---|---|---|---|---|
| **Special Relativity** | Mass-energy equivalence | $E = mc^2$ | Mass and energy are equivalent; rest mass is a form of energy. | Verify whether generated particle or event data preserve relativistic energy relations. |
| **Special Relativity** | Relativistic energy-momentum relation | $E^2 = p^2c^2 + m^2c^4$ | Energy, momentum, and mass are constrained by spacetime geometry. | Check whether simulated high-energy particles lie on the relativistic mass shell. |
| **Special Relativity** | Lorentz factor | $\gamma = \frac{1}{\sqrt{1 - v^2/c^2}}$ | Time dilation and length contraction depend on velocity. | Detect impossible trajectories where $v > c$ or relativistic timing becomes inconsistent. |
| **Special Relativity** | Time dilation | $\Delta t' = \gamma \Delta t$ | Moving clocks are measured differently by different observers. | Verify relativistic time-series data, such as satellite timing or high-speed motion. |
| **Special Relativity** | Length contraction | $L = \frac{L_0}{\gamma}$ | Moving objects contract along the direction of motion. | Detect violations in generated relativistic geometry. |
| **Special Relativity** | Four-velocity normalization | $u^\mu u_\mu = -c^2$ | Physical worldlines have a fixed spacetime norm. | Learn the lawful manifold of admissible relativistic trajectories. |
| **General Relativity** | Einstein field equations | $G_{\mu\nu} + \Lambda g_{\mu\nu} = \frac{8\pi G}{c^4}T_{\mu\nu}$ | Matter-energy determines spacetime curvature, and curvature determines motion. | Verify whether a proposed metric $g_{\mu\nu}$ and stress-energy tensor $T_{\mu\nu}$ are mutually consistent. |
| **General Relativity** | Einstein tensor | $G_{\mu\nu} = R_{\mu\nu} - \frac{1}{2}Rg_{\mu\nu}$ | Curvature is summarized by the Einstein tensor. | Test whether learned geometric fields satisfy curvature consistency. |
| **General Relativity** | Vacuum Einstein equation | $R_{\mu\nu} = 0$ | Empty spacetime can still contain curvature, such as gravitational waves or black holes. | Verify whether simulated vacuum spacetime solutions are physically admissible. |
| **General Relativity** | Geodesic equation | $\frac{d^2x^\mu}{d\tau^2} + \Gamma^\mu_{\alpha\beta}\frac{dx^\alpha}{d\tau}\frac{dx^\beta}{d\tau} = 0$ | Free-falling objects follow geodesics in curved spacetime. | Verify whether trajectories are consistent with an inferred gravitational field. |
| **General Relativity** | Stress-energy conservation | $\nabla_\mu T^{\mu\nu} = 0$ | Energy and momentum are locally conserved in curved spacetime. | Verify whether field simulations preserve local conservation laws. |
| **General Relativity** | Bianchi identity | $\nabla_\mu G^{\mu\nu} = 0$ | Geometric consistency condition underlying energy-momentum conservation. | Test whether learned curvature fields obey internal geometric consistency. |
| **Cosmology** | Friedmann equation | $H^2 = \frac{8\pi G}{3}\rho - \frac{kc^2}{a^2} + \frac{\Lambda c^2}{3}$ | Describes the expansion rate of the universe. | Verify whether cosmological trajectories match GR-based expansion laws. |
| **Cosmology** | Acceleration equation | $\frac{\ddot a}{a} = -\frac{4\pi G}{3}\left(\rho + \frac{3p}{c^2}\right) + \frac{\Lambda c^2}{3}$ | Determines whether cosmic expansion accelerates or decelerates. | Detect whether observed expansion history implies dark energy, modified gravity, or inconsistent dynamics. |
| **Cosmology** | Critical density | $\rho_c = \frac{3H^2}{8\pi G}$ | Defines the density required for a spatially flat universe. | Verify whether inferred cosmological parameters lie in physically consistent regions. |
| **Gravitational Lensing** | Weak deflection angle | $\alpha \approx \frac{4GM}{c^2b}$ | Massive objects bend the path of light. | Verify whether lensing patterns are consistent with visible mass, dark matter, or modified gravity. |
| **Black Holes** | Schwarzschild radius | $r_s = \frac{2GM}{c^2}$ | Defines the event horizon radius of a non-rotating black hole. | Verify whether generated black-hole parameters are physically admissible. |
| **Black Holes** | Schwarzschild metric | $ds^2 = -\left(1-\frac{2GM}{rc^2}\right)c^2dt^2 + \left(1-\frac{2GM}{rc^2}\right)^{-1}dr^2 + r^2d\Omega^2$ | Exact GR solution for a spherical, non-rotating mass. | Test whether simulated or inferred spacetime geometry matches the Schwarzschild solution. |
| **Black Holes** | Kerr spin bound | $a = \frac{J}{Mc}, \quad a \leq \frac{GM}{c^2}$ | Rotating black holes have bounded angular momentum. | Detect generated rotating black holes that violate physical spin constraints. |
| **Gravitational Waves** | Linearized Einstein equation | $\Box \bar h_{\mu\nu} = -\frac{16\pi G}{c^4}T_{\mu\nu}$ | Weak gravitational waves are perturbations of spacetime. | Verify whether waveform data are consistent with GR wave propagation. |
| **Gravitational Waves** | Vacuum wave equation | $\Box \bar h_{\mu\nu} = 0$ | Gravitational waves propagate through vacuum at light speed. | Detect non-GR waveform deviations or unphysical wave speeds. |
| **Gravitational Waves** | Quadrupole radiation principle | $P \sim \frac{G}{5c^5}\left\langle \dddot Q_{ij}\dddot Q_{ij}\right\rangle$ | Gravitational waves are mainly emitted by changing mass quadrupoles. | Verify whether simulated binary systems radiate energy consistently. |
| **Electromagnetism / Field Theory** | Gauss law for electricity | $\nabla \cdot \mathbf{E} = \frac{\rho}{\varepsilon_0}$ | Electric charge is the source of electric fields. | Verify whether learned electric fields are consistent with charge distributions. |
| **Electromagnetism / Field Theory** | Gauss law for magnetism | $\nabla \cdot \mathbf{B} = 0$ | Magnetic monopoles are absent in classical Maxwell theory. | Detect unphysical magnetic fields with nonzero divergence. |
| **Electromagnetism / Field Theory** | Faraday induction law | $\nabla \times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t}$ | Time-varying magnetic fields induce electric fields. | Verify whether temporal field evolution obeys electromagnetic induction. |
| **Electromagnetism / Field Theory** | Ampere-Maxwell law | $\nabla \times \mathbf{B} = \mu_0\mathbf{J} + \mu_0\varepsilon_0\frac{\partial \mathbf{E}}{\partial t}$ | Currents and time-varying electric fields generate magnetic fields. | Learn whether electromagnetic field simulations preserve Maxwell dynamics. |
| **Electromagnetic Waves** | Wave equation in vacuum | $\Box A^\mu = 0$ | Light is a propagating electromagnetic field. | Verify whether generated wave fields propagate causally at speed $c$. |
| **Gauge Field Theory** | Electromagnetic field tensor | $F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu$ | Electromagnetic fields arise from a gauge potential. | Learn gauge-consistent field representations instead of only fitting raw fields. |
| **Quantum Mechanics** | Schrodinger equation | $i\hbar\frac{\partial}{\partial t}\psi = \hat H\psi$ | Quantum states evolve under the Hamiltonian operator. | Verify whether learned quantum-state trajectories obey unitary evolution. |
| **Quantum Mechanics** | Born rule | $P(x) = |\psi(x)|^2$ | Measurement probabilities are given by wave-function amplitudes. | Check whether generated quantum states produce valid probability distributions. |
| **Quantum Mechanics** | Canonical commutation relation | $[\hat x, \hat p] = i\hbar$ | Position and momentum cannot both be sharply determined. | Verify whether learned latent operators preserve quantum structure. |
| **Quantum Field Theory** | Klein-Gordon equation | $(\Box + m^2)\phi = 0$ | Relativistic scalar fields satisfy a wave-like mass-shell equation. | Verify whether generated scalar fields satisfy relativistic field constraints. |
| **Quantum Field Theory** | Dirac equation | $(i\gamma^\mu\partial_\mu - m)\psi = 0$ | Relativistic spin-1/2 particles are described by spinor fields. | Learn physically admissible fermionic field dynamics. |
| **Quantum Field Theory** | Yang-Mills field equation | $D_\mu F^{\mu\nu} = J^\nu$ | Non-Abelian gauge fields generalize electromagnetism. | Verify whether learned gauge fields obey local symmetry constraints. |
| **Standard Model** | Gauge symmetry structure | $SU(3)_C \times SU(2)_L \times U(1)_Y$ | The Standard Model is organized by local gauge symmetries. | Learn whether high-dimensional particle interaction data respect symmetry-induced constraints. |
| **Higgs Mechanism** | Higgs potential | $V(\phi) = \mu^2|\phi|^2 + \lambda|\phi|^4$ | Spontaneous symmetry breaking gives particles mass. | Verify whether learned particle-field configurations lie near physically meaningful vacuum structures. |
| **Statistical Physics** | Boltzmann distribution | $p(x) = \frac{1}{Z}e^{-E(x)/(k_BT)}$ | Equilibrium probabilities depend exponentially on energy. | Check whether generated molecular or thermodynamic states obey equilibrium statistics. |
| **Brownian Motion** | Einstein diffusion relation | $\langle x^2(t)\rangle = 2Dt$ | Microscopic random motion produces macroscopic diffusion. | Verify whether stochastic particle, cell, or molecular trajectories obey diffusion scaling. |
| **Statistical Physics** | Einstein mobility-diffusion relation | $D = \mu k_BT$ | Diffusion and mobility are linked by temperature. | Test whether noisy dynamics respect thermodynamic constraints. |
| **Photoelectric Effect** | Photon energy | $E = hf$ | Light energy is quantized into photons. | Verify whether photon-material interaction data obey quantum energy constraints. |
| **Photoelectric Effect** | Photoelectric equation | $K_{\max} = hf - \phi$ | Electron kinetic energy depends on light frequency and material work function. | Verify whether simulated photoelectric data obey quantum threshold behavior. |
| **Atomic Radiation** | Detailed balance condition | $N_1B_{12}\rho(\nu) = N_2B_{21}\rho(\nu) + N_2A_{21}$ | Radiation and matter reach equilibrium through balanced transitions. | Check whether learned atomic transition models preserve equilibrium physics. |




<br><br><br><br><br><br>



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

| Person / period           |                    Year | Problem they cared about                           | Equation style         | Essence                                     |
| ------------------------- | ----------------------: | -------------------------------------------------- | ---------------------- | ------------------------------------------- |
| Newton / Leibniz          |             1660s–1670s | motion, curves, rates of change                    | (\frac{dy}{dx}=f(x,y)) | Differential equations emerge from calculus |
| Newton                    |                    1687 | planetary motion and mechanics                     | (m\ddot q = F(q))      | physical motion as time evolution           |
| Jacob Bernoulli / Leibniz |               1695–1696 | solvable nonlinear first-order equations           | (y'+P(x)y=Q(x)y^n)     | early named ODE family                      |
| Euler                     | 1700s, esp. 1730s–1760s | mechanics, astronomy, fluids, variational problems | systematic ODE methods | ODE becomes a general mathematical tool     |
| Cauchy                    |             early 1800s | existence, uniqueness, initial-value problems      | (y(t_0)=y_0)           | modern rigorous ODE theory                  |


<br><br>


## PDE


| Person / period          |        Year | Problem they cared about             | Equation style                | Essence                          |
| ------------------------ | ----------: | ------------------------------------ | ----------------------------- | -------------------------------- |
| d’Alembert               |        1747 | vibrating string                     | (u_{tt}=c^2u_{xx})            | wave propagation                 |
| Euler / Daniel Bernoulli | 1740s–1750s | strings, fluids, continuum mechanics | early PDE models              | motion of continuous media       |
| Laplace                  |  late 1700s | gravity/electrostatic potential      | (\Delta \phi=0)               | equilibrium field                |
| Fourier                  | 1807 / 1822 | heat conduction                      | (u_t=\kappa u_{xx})           | diffusion of temperature field   |
| Poisson                  |       1810s | potential with sources               | (\Delta \phi=f)               | field generated by matter/source |
| Navier / Stokes          | 1822 / 1845 | viscous fluid flow                   | Navier–Stokes equations       | fluid velocity field evolution   |
| Maxwell                  |   1861–1865 | electricity and magnetism            | coupled PDEs for (E,B) fields | electromagnetic field theory     |
| Einstein                 |        1915 | gravity as spacetime geometry        | Einstein field equations      | spacetime metric field dynamics  |



<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>



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

<br><br><br><br>

## Toolkit


- npzviewer




**1. ODE**


- [2025 - Life at the boundary of chemical kinetics and program execution](https://arxiv.org/pdf/2503.19177), physical constraints
- 1931 - Hamiltonian Systems and Transformation in Hilbert Space
  - nonlinear dynamics can be represented as linear transformations on a Hilbert space of observables.
  - [2024 - Soliton dynamics and multistability analysis of the Hamiltonian amplitude model](https://www.sciencedirect.com/science/article/pii/S2211379724005631)
- [2026 - Paving the way for agents in biology](https://www.anthropic.com/research/agents-in-biology)

<br><br><br>


**2.Hamiltonian Systems and Operators**


- Hamiltonian system
- Hilbert space: Transition from state point to function space
- Weierstrass Approximation Theorem
  - Universal Approximation Theorem, Bézier Curve
- Lie operator, Unitary operator
- Flow map


<br><br><br>



**3. Topological Defect**



- The data manifold is extremely distorted, dimensionally reduced, or has broken connectivity in this region.



<br><br><br>


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


<br><br><br>



**5. Activation Functions and Field Theories**

<br><br><br><br><br><br><br><br>



## Other Topics

- [2026 - Geometric Signatures of Reasoning: A Spectral Perspective on Task Hardness](https://arxiv.org/abs/2406.19108)
- [2023 - Seeing a Rose in Five Thousand Ways](https://ai.stanford.edu/~yzzhang/projects/rose/)




<br><br><br><br><br><br><br><br>



<br><br><br><br><br>
