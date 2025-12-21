---
layout: page
title: 2026 - Thesis - Brain Mapping / Camera
description: SSL, Learning-based, ()
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
- [2025 - 📍 Unsupervised Joint Learning of Optical Flow and Intensity with Event Cameras](https://iccv.thecvf.com/virtual/2025/poster/278)


<br>

## An (Online Self-calibrated) Camera with Signal Fusion / Space


- The important thing is not the formula, but `multi-sensor = multiple observations constraining the same latent state`


- [📍 2013 - Self-Calibration and Visual SLAM with a Multi-Camera System on a
Micro Aerial Vehicle](https://people.inf.ethz.ch/pomarc/pubs/HengAURO15.pdf) and its references
- [2019 - Calibration Wizard: A Guidance System for Camera Calibration Based on Modelling Geometric and Corner Uncertainty](https://openaccess.thecvf.com/content_ICCV_2019/papers/Peng_Calibration_Wizard_A_Guidance_System_for_Camera_Calibration_Based_on_ICCV_2019_paper.pdf)
- [2025 - Aria Gen 2 Documentation](https://facebookresearch.github.io/projectaria_tools/gen2/)
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
- [2003 - Using many cameras as one](https://ieeexplore.ieee.org/document/1211520)


<br>

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

## 📍 Explicit (vs. Implicit) Modeling of Temporal Inconsistency

| Dimension                         | Explicit Modeling                                                                         | Implicit Modeling                                                               |
| --------------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Core idea                         | Temporal inconsistency is modeled as structured uncertainty and explicitly reasoned about | Temporal inconsistency is absorbed by the model through representation learning |
| Time representation               | Timestamps, exposure intervals, offsets, and drift are explicit variables                 | Time is encoded as features or implicitly handled by network layers             |
| Treatment of uncertainty          | Different sources of uncertainty are explicitly separated and modeled                     | All uncertainty is merged into a generic latent representation                  |
| Physical meaning                  | Each temporal variable has a clear physical or statistical interpretation                 | Temporal effects lack explicit physical interpretation                          |
| Interpretability                  | High, temporal conflicts can be inspected and analyzed                                    | Low, behavior emerges without clear explanation                                 |
| Handling heterogeneous sensors    | Naturally supports different frame rates, shutter types, and modalities                   | Requires large datasets to implicitly learn heterogeneity                       |
| Long-term stability               | Robust to clock drift and long-duration recordings                                        | Sensitive to distribution shift and temporal drift                              |
| Downstream propagation            | Temporal uncertainty can be propagated to perception and decision modules                 | Downstream modules are unaware of temporal uncertainty                          |
| Data efficiency                   | Moderate, constraints guide learning                                                      | High, relies on extensive data coverage                                         |
| Engineering complexity            | Higher, requires modeling, inference, and optimization                                    | Lower, simpler end-to-end training                                              |
| Scalability                       | Scales well across heterogeneous systems with known structure                             | Scalability depends on dataset diversity                                        |
| Failure diagnosis                 | Failures can be attributed to specific temporal factors                                   | Failure modes are difficult to diagnose                                         |
| Alignment with theory             | Strongly aligned with probabilistic and state-space models                                | Weak theoretical grounding                                                      |
| Suitability for CVPR-style papers | Medium, may be perceived as theoretical                                                   | High, fits empirical optimization culture                                       |
| Long-term research value          | High, addresses structural modeling gaps                                                  | Medium, provides empirical robustness                                           |
| Typical failure mode              | Incorrect assumptions in the explicit model                                               | Overfitting temporal correlations                                               |
| Best use case                     | When temporal inconsistency is a core modeling concern                                    | When temporal inconsistency is minor or data is abundant                        |


<br>


## Core Formulation: Bayesian Multi-Modal Sensor Fusion

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

- where $\theta$ is treated as a time-invariant latent variable, $p(\theta)$ enforces temporal consistency of calibration parameters.


**Interpretation**
- Fusion thus corresponds to Bayesian state estimation under uncertainty, where heterogeneous sensor observations impose probabilistic constraints on a shared latent state evolving over time. Calibration parameters are inferred jointly with pose and user states, enabling online self-calibration.


**Sensor Models**

- $z_t^{imu} = h_{imu}(T_{t-1}, T_t) + \epsilon_{imu}$
- $z_t^{cam} = h_{cam}(T_t, \theta) + \epsilon_{cam}$
- $z_t^{eye} = h_{eye}(T_t, \psi_t) + \epsilon_{eye}$


**Filtering Approximation**

For online inference, we approximate the posterior using Bayesian filtering.
- Prediction: $p(x_t \mid z_{1:t-1}) = \int p(x_t \mid x_{t-1}) p(x_{t-1} \mid z_{1:t-1}) dx_{t-1}$
- Update: $p(x_t \mid z_{1:t}) \propto p(z_t \mid x_t) p(x_t \mid z_{1:t-1})$



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





<br>


## Why Gaussian

- For Closure Under Bayesian Operations
- Bayesian filtering requires two fundamental operations that are applied recursively over time.

- **Prediction**
- The prediction step propagates the belief forward in time using the system dynamics:

$p(x_t \mid z_{1:t-1}) = \int p(x_t \mid x_{t-1}) p(x_{t-1} \mid z_{1:t-1}) dx_{t-1}$

- **Update**
- The update step incorporates the new observation into the predicted belief:

$p(x_t \mid z_{1:t})
\propto
p(z_t \mid x_t)\,
p(x_t \mid z_{1:t-1})$

----

- Gaussian distributions possess a crucial closure property under these Bayesian operations:
  - The product of two Gaussian distributions is Gaussian.
  - The marginalization of a joint Gaussian distribution is Gaussian.

- As a consequence:
  - The prediction step preserves Gaussianity.
  - The update step preserves Gaussianity.

- Without this closure property, the posterior distribution does not remain in a tractable functional family, and Bayesian filtering becomes analytically intractable.




<br>

## Bayesian Filter、Kalman Filter, Gaussian Distribution

```
┌───────────────────────────────────────────────┐
│               Bayesian Filtering              │
│                                               │
│  p(x_t | z_{1:t}) ∝ p(z_t | x_t) p(x_t | z_{1:t-1}) │
│                                               │
│  • General probabilistic inference framework  │
│  • Arbitrary distributions                    │
│  • Arbitrary nonlinear dynamics               │
│  • Arbitrary observation models               │
│                                               │
│        (Intractable in general)               │
└───────────────────────┬───────────────────────┘
                        │
                        │  Gaussian assumption
                        ▼
┌───────────────────────────────────────────────┐
│            Kalman-style Filtering             │
│                                               │
│  Assumption:                                  │
│  p(x_t | z_{1:t}) ≈ 𝒩(μ_t, Σ_t)              │
│                                               │
│  • Posterior represented only by mean + cov   │
│  • Recursive closed-form updates              │
│  • Efficient and online                       │
│                                               │
│  Includes:                                    │
│   - Kalman Filter (linear)                    │
│   - EKF (local linearization)                 │
│   - UKF (sigma-point)                         │
└───────────────────────┬───────────────────────┘
                        │
                        │  Linear model + Gaussian noise
                        ▼
┌───────────────────────────────────────────────┐
│               Kalman Filter                   │
│                                               │
│  x_t = A x_{t-1} + w_t ,   w_t ~ 𝒩(0, Q)     │
│  z_t = H x_t     + v_t ,   v_t ~ 𝒩(0, R)     │
│                                               │
│  • Exact Bayesian inference                   │
│  • Optimal under linear-Gaussian assumptions  │
└───────────────────────────────────────────────┘
```

<br>

## For 📍 Each Time Step

```
Time t-1 belief                    Prediction                    Update
(posterior at t-1)                 (motion model)               (sensor fusion)

   p(x_{t-1}|z_{1:t-1})             p(x_t|z_{1:t-1})             p(x_t|z_{1:t})
     ~ 𝒩(μ_{t-1}, Σ_{t-1})     →       ~ 𝒩(μ_t^-, Σ_t^-)     →       ~ 𝒩(μ_t, Σ_t)
                │                              │                              │
                │                              │                              │
                ▼                              ▼                              ▼
        Gaussian belief              Gaussian prediction            Gaussian posterior
```

<br>

## Multiple sensors = multiple Gaussian 📍 constraints on the same state

```
                    z_t^cam
                 (camera likelihood)
                        │
                        ▼
                   ┌────────┐
z_t^imu ───────▶   │  x_t   │   ◀────── z_t^eye
(IMU likelihood)   │ latent │   (eye-tracking likelihood)
                   │ state  │
                   └────────┘
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


<br>

## Event Camera, Dynamic Camera, Generalized Camera

| Camera Model       | Who proposed it                                                                       | When                                               | Why it was proposed                                                                                                   | Core idea                                                                                      | What it is used for in practice                                                                                                        | Canonical mathematical formulation                                                                                                           |
| ------------------ | ------------------------------------------------------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Event Camera       | Tobi Delbrück and the neuromorphic vision community                                   | Early 2000s (concept); practical devices 2008–2014 | To overcome motion blur, low temporal resolution, high latency, and redundancy of frame-based cameras                 | Pixels asynchronously report changes in log intensity instead of recording frames              | High-speed motion estimation, optical flow, visual odometry, SLAM, robotics, autonomous driving in extreme lighting, low-power sensing | Event is triggered when:  \n$\Delta L(x,y,t)=\log I(x,y,t)-\log I(x,y,t-\Delta t) \ge C$  \nEvent representation:  \n$e_k=(x_k,y_k,t_k,p_k)$ |
| Dynamic Camera     | Gennady Medioni, Yi Ma, Stefano Soatto (dynamic vision / dynamic scene modeling line) | Late 1990s – early 2000s                           | To model cameras observing **time-varying scenes** and **camera motion** jointly rather than assuming static geometry | Camera measurements are functions of both spatial projection and temporal evolution            | Dynamic scene reconstruction, structure-from-motion with motion, video-based 3D reconstruction, non-rigid SLAM                         | Time-dependent projection model:  \n$x(t)=\pi(P(t),X(t))$  \nwhere camera pose $P(t)$ and scene point $X(t)$ evolve over time                |
| Generalized Camera | Thijs K. Schoenemann, Richard Hartley, later formalized by Geyer and Daniilidis       | Early 2000s (2000–2001)                            | To unify pinhole, multi-camera rigs, catadioptric, and non-central cameras in a single geometric model                | A camera is modeled as a set of rays in space, not necessarily passing through a single center | Multi-camera calibration, omnidirectional vision, panoramic systems, camera rigs in robotics and autonomous driving                    | Ray-based model:  \n$r_i = (o_i, d_i)$  \nwith projection constraint:  \n$X \in \{ o_i + \lambda d_i \mid \lambda > 0 \}$                    |


- Event camera: designed for when something changes.
- Dynamic camera: designed for how scenes and cameras evolve over time.
- Generalized camera: designed for how rays are formed, regardless of camera hardware.


<br>


## An Event Camera

| Aspect                            | Description                                                                                                                                                                                                                          |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Core idea (essence)               | An event camera is an **asynchronous, pixel-wise change detector** that outputs events whenever the **logarithmic intensity change** at a pixel exceeds a threshold, instead of recording full image frames at fixed time intervals. |
| What it outputs                   | A stream of events $e_k = (x_k, y_k, t_k, p_k)$, where $(x_k, y_k)$ is the pixel location, $t_k$ is the timestamp (microsecond resolution), and $p_k \in {+1, -1}$ is the polarity (brightness increase or decrease).                |
| Fundamental measurement principle | An event is triggered when the change in log intensity satisfies:  \n$\Delta L(x, y, t) = \log I(x, y, t) - \log I(x, y, t - \Delta t) \geq C$  \nwhere $C$ is a contrast threshold.                                                 |
| Data representation               | Sparse, asynchronous, temporally continuous event stream (no frames, no fixed FPS).                                                                                                                                                  |
| Who proposed it                   | First proposed conceptually and experimentally by **Tobi Delbrück** and collaborators in the neuromorphic vision community.                                                                                                          |
| When                              | Early 2000s (around 2001–2004 for initial silicon retina designs); practical modern devices emerged around 2008–2014.                                                                                                                |
| Why it was proposed               | To overcome limitations of frame-based cameras: motion blur, low temporal resolution, high latency, and redundant data in static scenes.                                                                                             |
| Biological inspiration            | Inspired by the **human retina**, where neurons respond to **changes** in brightness rather than absolute intensity.                                                                                                                 |
| Key advantages                    | Ultra-high temporal resolution (microseconds), high dynamic range (often >120 dB), low latency, low power consumption, and no motion blur.                                                                                           |
| Key limitations                   | No absolute intensity information, sparse data difficult to process, noise under low contrast, requires new algorithms.                                                                                                              |
| Contrast with frame cameras       | Frame cameras sample intensity: $I(x,y,t)$ at discrete times; event cameras sample changes: $\frac{d}{dt} \log I(x,y,t)$.                                                                                                            |
| Typical applications              | High-speed motion estimation, visual odometry, SLAM, optical flow, robotics, autonomous driving, high-speed tracking, and low-power vision.                                                                                          |
| Conceptual summary                | **Event cameras measure “when something changes,” not “what the scene looks like at a fixed time.”**                                                                                                                                 |

<br><br>


## A. Unresolved Core Problems in Modern CVPR (Post-Deep Learning Era)

| Problem Area                    | What the Problem Really Is                                                    | Why It Is Still Unsolved                                                                                     | How CVPR Papers Currently Cope                                      | Why Best Papers Still Miss It                                                        |
| ------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Continuous-time modeling        | Vision models are fundamentally discrete, but the world is continuous in time | Continuous-time inference is mathematically harder; requires differential equations and observability theory | Discretization, frame aggregation, splines, heuristic interpolation | Best papers optimize within discretized assumptions instead of fixing the time model |
| Temporal causality              | Models confuse correlation across frames with causal structure                | Causality requires intervention and counterfactual reasoning, not passive data                               | Self-supervision, temporal contrastive losses                       | These methods improve prediction, not causal understanding                           |
| Identifiability                 | Whether the true scene/state is uniquely recoverable from data                | Identifiability depends on geometry, noise, and sensor configuration                                         | Overparameterization hides non-identifiability                      | Best papers report accuracy, not whether the solution is meaningful                  |
| Geometry–learning consistency   | Learned representations often violate geometric invariants                    | Neural networks lack built-in structure preservation                                                         | Add geometry as loss terms or regularizers                          | Geometry is treated as decoration, not a first-class constraint                      |
| Probabilistic correctness       | Most “uncertainty” estimates are not valid probabilities                      | Proper probabilistic modeling is expensive and restrictive                                                   | Softmax scores, Monte Carlo dropout                                 | Best papers optimize calibration metrics without true probabilistic guarantees       |
| Sensor modeling                 | Real sensors are nonlinear, asynchronous, and imperfect                       | Accurate sensor models complicate learning pipelines                                                         | Synthetic data, simplified sensor assumptions                       | Papers assume idealized sensors to keep benchmarks manageable                        |
| Scale vs. meaning               | Scaling improves performance without improving understanding                  | Optimization rewards accuracy, not interpretability                                                          | Larger models, more data                                            | Best papers often demonstrate scale, not conceptual progress                         |
| Benchmark validity              | Benchmarks measure proxies, not the intended task                             | Ground truth is often ill-defined or biased                                                                  | Dataset curation and metric tuning                                  | Best papers win benchmarks without questioning what they measure                     |
| Failure characterization        | Knowing *when* and *why* a model fails                                        | Requires negative results and adversarial analysis                                                           | Ignore rare or hard cases                                           | Best papers are structurally biased against failure analysis                         |
| Generalization guarantees       | Performance outside training distribution                                     | Distribution shift is unavoidable in vision                                                                  | Domain adaptation, augmentation                                     | These mitigate but do not solve the theoretical problem                              |
| Multi-sensor fusion theory      | How heterogeneous sensors should be fused optimally                           | Requires unified state-space and noise models                                                                | Late fusion, learned fusion                                         | Fusion is learned empirically, not derived                                           |
| Inverse problems under learning | Whether learned inverses are stable and well-posed                            | Inverse problems are often ill-posed by nature                                                               | Implicit regularization via networks                                | Best papers rely on empirical stability, not proofs                                  |
| Long-horizon reasoning          | Understanding scenes over long time spans                                     | Error accumulation and memory limits                                                                         | Sliding windows, recurrent modules                                  | Best papers focus on short-term tasks                                                |
| Physical consistency            | Ensuring predictions obey physical laws                                       | Physics constraints are hard to encode differentiably                                                        | Physics-informed losses                                             | Usually approximate and task-specific                                                |
| Evaluation under ambiguity      | Multiple valid interpretations of the same scene                              | Ground truth often assumes a single answer                                                                   | Pick one label or average                                           | Best papers collapse ambiguity instead of modeling it                                |


## B. Key Meta-Observation (Critical)

| Observation                                      | Explanation                                     |
| ------------------------------------------------ | ----------------------------------------------- |
| These are not “missing tricks”                   | They are structural modeling problems           |
| They predate deep learning                       | Many come from 1950–2000 math/physics           |
| Best papers optimize *within* broken assumptions | They rarely question the assumptions themselves |
| Solving them reduces leaderboard gains           | Which is why incentives avoid them              |
| They require saying “this task is ill-posed”     | CVPR culture discourages this                   |



<br><br><br><br>



