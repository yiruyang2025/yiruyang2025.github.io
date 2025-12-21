---
layout: page
title: 2026 - Thesis - Brain Mapping / Camera
description: SSL
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>

## Topics

  - [EU Open Research Repository](https://zenodo.org/), [AiiDA.net](https://www.aiida.net/)
  - [Thesis](https://sirop.org/app/013a8549-281d-475b-bc42-1a63fff75d98?_k=D4wOn3UvPzaQuIzU)
  - [CERN](https://home.cern/), [PSI](https://www.psi.ch/en)


<br>


## References

- [2025 - 📍 ZapBench](https://github.com/google-research/zapbench)
- [Development of the Nervous System](https://www.mls.uzh.ch/en/research/hajnal/teaching.html)
    - [Stoeckli Esther](https://www.mls.uzh.ch/en/research/stoeckli/research.html)
- [Topological Deep Learning](https://decisive-stomach-548.notion.site/Topological-Deep-Learning-2a1425ccedaa800782f5ca86486c5080?showMoveTo=true&saveParent=true)
- [2025 - TopoBench: A Framework for Benchmarking Topological Deep Learning](https://arxiv.org/pdf/2406.06642)


<br>

## A (Online Self-calibrated) Camera with Signal Fusion / Space


- The important thing is not the formula, but `multi-sensor = multiple observations constraining the same latent state`


- [📍 2013 - Self-Calibration and Visual SLAM with a Multi-Camera System on a
Micro Aerial Vehicle](https://people.inf.ethz.ch/pomarc/pubs/HengAURO15.pdf) and its references, CVG
- [2025 - Aria Gen 2 Documentation](https://facebookresearch.github.io/projectaria_tools/gen2/), CVG
- [1960 - A New Approach to Linear 📍 Filtering and Prediction Problems](https://www.unitedthc.com/DSP/Kalman1960.pdf), Kalman
  - The essence of Kalman Filtering is to make an optimal estimate of the state of a system that evolves over time, in the presence of noise
  - It defines a state-space model, breaking down the problem into:
    - How the state changes over time (prediction)
    - How observations arise from the state (update)
  - Kalman Filtering As The Mathematical Origin of Sensor Fusion, the key ideas introduced in this paper includes:
    - `Latent state`
    - A hidden variable that represents the true system state we care about (e.g., position, orientation, velocity), which cannot be observed directly
    - `Observation model`
    - A probabilistic mapping from the latent state to sensor measurements, explicitly modeling noise and uncertainty
    - `Recursive Bayesian update`
    - A principled way to update the belief over the latent state over time, combining prior knowledge with new observations in a sequential and efficient manner

- [2005 - Probabilistic Robotics](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=zj6FavAAAAAJ&citation_for_view=zj6FavAAAAAJ:cSdaV2aYdYsC), Multi-sensor Input Fusion
- [2025 - ACDC Dataset](https://acdc.vision.ee.ethz.ch/overview), training and testing semantic perception on adverse visual conditions
- [2003 - Generalized Multi-Camera Scene Reconstruction Using Graph Cuts](https://link.springer.com/chapter/10.1007/978-3-540-45063-4_32)
- [2003 - Using many cameras as one](https://ieeexplore.ieee.org/document/1211520)



<br>


**Core Formulation: Bayesian Multi-Modal Sensor Fusion**

**Latent State Definition**

- At time step t, the latent state is defined as:
$x_t = \{ T_t, \theta, \psi_t \}$

- where $T_t$ denotes the device pose, $\theta$ represents the calibration parameters shared across time, and $\psi_t$ denotes user-centric latent variables.

**Multi-Modal Observations**

- Given heterogeneous sensor measurements at time t:
$z_t = \{ z_t^{cam}, z_t^{imu}, z_t^{eye} \}$

- where observations are obtained from the camera, IMU, and eye-tracking modalities.

**Bayesian Fusion Objective**

- Multi-modal fusion is defined as inference over the joint posterior:
$p(x_{1:T} \mid z_{1:T})$

- Using the Markov assumption and conditional independence of observations, the posterior factorizes as:
$p(x_{1:T} \mid z_{1:T}) \propto \prod_{t=1}^{T} p(z_t \mid x_t)\, p(x_t \mid x_{t-1})$

**Multi-Modal Likelihood Factorization**

- Assuming conditional independence between sensor modalities given the latent state:
$p(z_t \mid x_t)
= p(z_t^{cam} \mid x_t)\, p(z_t^{imu} \mid x_t)\, p(z_t^{eye} \mid x_t)$

**State Transition Model**

- The temporal evolution of the latent state is modeled as:
$p(x_t \mid x_{t-1})
= p(T_t \mid T_{t-1})\, p(\psi_t \mid \psi_{t-1})\, p(\theta)$

- where $\theta$ is treated as a time-invariant latent variable.

**Interpretation**
- Fusion thus corresponds to Bayesian state estimation under uncertainty, where heterogeneous sensor observations impose probabilistic constraints on a shared latent state evolving over time. Calibration parameters are inferred jointly with pose and user states, enabling online self-calibration.



<br>


## Practical Filtering Choices under XR Self-Calibrated Camera Constraints

| Method                            | Inference Principle                             | Handles High-Dimensional State | Real-Time / Online | Geometric Interpretability | Typical Failure Mode  | Suitability for Your Pipeline |
| --------------------------------- | ----------------------------------------------- | ------------------------------ | ------------------ | -------------------------- | --------------------- | ----------------------------- |
| **Full Bayesian Filtering**       | Exact posterior inference $p(x_t \mid y_{1:t})$ | No (intractable)               | No                 | Theoretically yes          | Intractable integrals | ✗ (theoretical only)          |
| **Particle Filter**               | Sampling-based Bayesian inference               | Poor (curse of dimensionality) | No                 | Weak (implicit geometry)   | Sample degeneracy     | ✗                             |
| `Kalman Filter (KF)`            | Linear-Gaussian Bayesian inference              | Moderate                       | Yes                | Strong (explicit states)   | Model mismatch        | ✓ (baseline)                  |
| **Extended Kalman Filter (EKF)**  | Local linearization of nonlinear models         | Moderate–High                  | Yes                | Strong                     | Linearization error   | ✓✓                            |
| **Unscented Kalman Filter (UKF)** | Sigma-point approximation                       | Moderate                       | Borderline         | Strong                     | Computational cost    | △                             |
| **Information Filter**            | KF in information (precision) form              | High                           | Yes                | Strong                     | Numerical instability | ✓                             |
| **Factor Graph / Smoothing**      | MAP estimation over state graph                 | High                           | Semi-online        | Very strong                | Latency / memory      | ✓✓ (geometry modules)         |
| **Continuous-Time Filters**       | Trajectory as continuous function               | High                           | Yes                | Strong                     | Model complexity      | ✓✓                            |
| **Variational Bayesian Filters**  | Approximate posterior optimization              | High                           | No                 | Weak–Moderate              | Approximation bias    | ✗                             |
| **Neural / Learned Filters**      | Learned belief update                           | High                           | Yes                | Weak (opaque)              | Geometry drift        | ✗ (as core filter)            |


<br>


## Method Selection Is Constraint-Driven, Not Aesthetic


| Hard Constraint                             | Practical Interpretation                                                                                                                                                                | Technical Implication                                                                                                                                                       |
| ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Online, real-time, low latency**          | The system runs on an XR device worn by a human user. End-to-end latency above tens of milliseconds leads to motion sickness and unacceptable user experience.                          | Any method that is offline, batch-only, or exhibits unstable latency is infeasible and must be excluded.                                                                    |
| **High-dimensional continuous state space** | The system state includes not only camera pose but also velocity, IMU biases, camera intrinsics and extrinsics, and temporal offsets between sensors.                                   | The resulting state space is high-dimensional, continuous, and strongly nonlinear, making general inference methods computationally intractable.                            |
| **Geometric honesty and interpretability**  | Solutions must be physically and geometrically valid, not merely visually plausible. Calibration parameters must correspond to real camera models and be diagnosable when errors occur. | Methods that produce visually convincing but geometrically inconsistent results are unacceptable. Explicit state representation and interpretable uncertainty are required. |



<br>


## Kalman-Style Filtering in the Feasible Regime

| Aspect                          | Trade-Off Made                                         | Practical Consequence                                             |
| ------------------------------- | ------------------------------------------------------ | ----------------------------------------------------------------- |
| **Distribution expressiveness** | Discards multi-modal posteriors and non-Gaussian tails | Enables closed-form or efficiently approximated inference         |
| **Uncertainty representation**  | Sacrifices global uncertainty expressiveness           | Retains explicit covariance for local uncertainty and diagnostics |
| **State representation**        | Enforces explicit, physically meaningful states        | Each variable corresponds to a real system quantity               |
| **Computational cost**          | Avoids sampling-based or variational inference         | Supports real-time, bounded-latency operation                     |
| **Failure behavior**            | Accepts approximation error                            | Provides diagnosable and predictable failure modes                |
| **Geometric compatibility**     | Restricts inference to interpretable state spaces      | Integrates naturally with geometry-aware constraints              |





<br><br>



## A Dynamic Camera with Multi-modal Input Signal 📍 Fusion


```
          Human perception
        ┌──────────────────┐
        │  Vestibular      │
        │  Vision          │
        └──────────────────┘
                 ▲
                 │
    ┌────────────┴────────────────┐
    │ Wearable System Estimation  │
    └────────────┬────────────────┘
                 │
 ┌───────┬────────┬────────┬────────┬────────┐
 │ Camera│  IMU   │ Eye    │ Depth  │ Others │
 │       │        │ tracker│ / ToF  │        │
 └───────┴────────┴────────┴────────┴────────┘
```



<br>


## 3D/4D Non-Rigid Reconstruction vs. Series Elastic Actuators (SEA)

- Both problems replace impossible exact control or exact reconstruction with explicit structural priors that guarantee stability, coherence, and robustness under uncertainty

| Aspect                    | 3D / 4D Non-Rigid Reconstruction                                                              | Series Elastic Actuators (SEA)                                                                                            |
| ------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| One-sentence essence      | Recover a time-varying continuous geometry from incomplete, noisy, and indirect observations. | Design a physical actuation system that remains stable, controllable, and predictable under uncertainty and non-rigidity. |
| Nature of the system      | Perceptual and representational                                                               | Physical and mechanical                                                                                                   |
| Objects involved          | Humans, animals, cloth, hair, soft bodies                                                     | Motors, gears, springs, loads, environment                                                                                |
| Type of non-rigidity      | Geometric deformation and topology change                                                     | Mechanical compliance and elasticity                                                                                      |
| Source of difficulty      | Incomplete observations and ill-posed inference                                               | Unknown contacts, shocks, delays, and model mismatch                                                                      |
| Observations / inputs     | 2D images, videos, sparse points, patch-level features                                        | Motor states, force sensing, spring deformation                                                                           |
| True target               | 3D / 4D geometry with spatiotemporal consistency                                              | Stable force / impedance interaction with the environment                                                                 |
| Local–global coupling     | Local deformation affects global shape                                                        | Local elastic deformation affects global stability                                                                        |
| Failure mode if untreated | Drift, collapse of correspondence, inconsistent geometry                                      | Instability, shocks, damage, unsafe interaction                                                                           |
| Core strategy             | Introduce structural priors to regularize an ill-posed inverse problem                        | Introduce mechanical structure to regularize an uncontrollable system                                                     |
| Role of structure         | Geometry, smoothness, correspondence, temporal coherence                                      | Passive elasticity, impedance, energy storage                                                                             |
| What structure replaces   | Impossible exact reconstruction from data alone                                               | Impossible exact control of rigid, high-gain actuators                                                                    |
| Problem class             | “Structural degeneration + ill-posed inverse problem”                                         | “Physical interaction + uncertainty problem”                                                                              |


<br>



## Tool Kits


- [Project MONAI](https://github.com/Project-MONAI)



<br>


## Best Normalization

| **Data Distribution Characteristics**       | **Method**                              | **Formula**                                      | **Core Assumption**                                                                 |
| ------------------------------------------- | --------------------------------------- | ------------------------------------------------ | ----------------------------------------------------------------------------------- |
| **Gaussian-like Distribution**              | Standard z-score normalization          | $z = \dfrac{x - \mu}{\sigma}$                    | Most data points are concentrated near the mean; few outliers exist.                |
| **Skewed or Heavy-Tailed Distribution**     | Robust z-score (Median + MAD)           | $z = \dfrac{x - \mathrm{median}}{\mathrm{MAD}}$  | Extreme values exist; the median provides a more stable estimate.                   |
| **Bounded Values (0–1, Ratio-type Data)**   | Min–Max normalization                   | $x' = \dfrac{x - x_{\min}}{x_{\max} - x_{\min}}$ | Data lies within a fixed range; preserving proportional relationships is important. |
| **Log-Normal or Multiplicative Noise Data** | Log transform + z-score                 | $\log(x)$ or $\log(1 + x);\rightarrow;$ z-score  | Noise varies multiplicatively; log transformation linearizes it.                    |
| **Mixed Noise or Asymmetric Distributions** | Quantile normalization / Rank transform | $x \mapsto \mathrm{rank}(x)$ or quantile mapping | Exact values are less important; relative ordering matters.                         |



<br>

## Brain Signals (Why Median + MAD)


| **Property**                  | **Meaning**                                       | **Impact**                                     |
| ----------------------------- | ------------------------------------------------- | ---------------------------------------------- |
| **Non-stationary**            | The mean varies across time and sessions          | Mean and standard deviation become unstable    |
| **Heavy-tailed distribution** | Strong artifacts or high-amplitude spikes         | Standard deviation is inflated by outliers     |
| **Weak signal + mixed noise** | High-frequency oscillations + low-frequency drift | Large mean variation, clear skewness           |
| **Inter-channel variation**   | Each sensor has different sensitivity             | Requires independent per-channel normalization |


<br><br><br>





