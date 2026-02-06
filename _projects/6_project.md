---
layout: page
title: 2026 - Master Thesis - Space
description: LiDAR Free, PRS
img: assets/img/4.jpg
importance: 6
category: work
related_publications: true
---

<br>

## Topics

- [2026 - SpaceX](https://x.com/Starlink/status/2017064797125410863?s=20)


<br>

## References

- [CVPR](https://cvpr.thecvf.com/Conferences/2025/AcceptedPapers)
- [Earthdata Plugin](https://plugins.qgis.org/plugins/nasa_earthdata/)

- `If a team / mentor can tolerate you saying "This has no information" and listen carefully to the rest of your sentence, then it is a very good peer / team.`

- [DiffusionDrive](https://openreview.net/revisions?id=sh7vDLo5EY), CVPR highlight 2025.
- [Disentangling Monocular 3D Object Detection](https://openaccess.thecvf.com/content_ICCV_2019/papers/Simonelli_Disentangling_Monocular_3D_Object_Detection_ICCV_2019_paper.pdf), ICCV 2019.
  - The core method of 3D perception that `does not rely on LiDAR` laid the foundation for many subsequent 3D Tracking and 3D MOT vision methods.
- [Monocular 3D Object Detection Leveraging Accurate Proposals and Shape Reconstruction](https://openaccess.thecvf.com/content_CVPR_2019/papers/Ku_Monocular_3D_Object_Detection_Leveraging_Accurate_Proposals_and_Shape_Reconstruction_CVPR_2019_paper.pdf), CVPR 2019.
- [Monocular Quasi-Dense 3D Object Tracking](https://ieeexplore.ieee.org/document/9760217), 2021.
- [Multi-Level Fusion based 3D Object Detection from Monocular Images](https://openaccess.thecvf.com/content_cvpr_2018/papers/Xu_Multi-Level_Fusion_Based_CVPR_2018_paper.pdf), CVPR 2018.
- [Development of the Nervous System](https://www.mls.uzh.ch/en/research/hajnal/teaching.html), [Prof. Dr. Stoeckli Esther](https://www.mls.uzh.ch/en/research/stoeckli/research.html)

<br>

## Multi-sensor Input Fusion From Space, Safety Detection

- [1960 - A New Approach to Linear Filtering and Prediction Problems](https://www.unitedthc.com/DSP/Kalman1960.pdf), Kalman
- [2005 - Probabilistic Robotics](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=zj6FavAAAAAJ&citation_for_view=zj6FavAAAAAJ:cSdaV2aYdYsC), Multi-sensor Input Fusion
- [2025 - ACDC Dataset](https://acdc.vision.ee.ethz.ch/overview), training and testing semantic perception on adverse visual conditions
- [📍 2019 - Calibration Wizard: A Guidance System for Camera Calibration Based on Modelling Geometric and Corner Uncertainty](https://openaccess.thecvf.com/content_ICCV_2019/papers/Peng_Calibration_Wizard_A_Guidance_System_for_Camera_Calibration_Based_on_ICCV_2019_paper.pdf)

<br>

## Topics


**0. Sensor Modalities and Data Types**

| Modality | Sensor Type                 | Data Representation                  |
|----------|----------------------------|--------------------------------------|
| Optical  | Visible-light satellite camera | 3-channel RGB image (8-bit)        |
| SAR      | Synthetic Aperture Radar     | 1-channel SAR image (32-bit float)   |


<br>

## 1. Maritime Search and Rescue

```
Optical satellite images
+ SAR satellite images
→ Ship Detection
→ Ship Re-Identification (ReID)
→ Trajectory generation & route prediction
```


| Platform          | Strength                                | Fundamental Limitation             |
| ----------------- | --------------------------------------- | ---------------------------------- |
| GEO satellites    | Wide coverage, high temporal resolution | Low spatial resolution             |
| Video satellites  | High spatial & temporal resolution      | Short duration, small coverage     |
| AIS-based systems | Accurate identity info                  | Only works for cooperative targets |


| Axis    | Examples                           |
| ------- | ---------------------------------- |
| Sensors | Optical, SAR, LiDAR, multispectral |
| Tasks   | Detection, ReID, tracking, mapping |
| Scale   | Local → Global                     |
| Time    | Snapshot → Long-term monitoring    |

<br>

## 2. Input Data Type

| Modality | Data Type           | Format                                       |
| -------- | ------------------- | -------------------------------------------- |
| Optical  | RGB image           | 3-channel, 8-bit TIF                         |
| SAR      | Radar backscatter   | 1-channel, 32-bit float TIF                  |
| Geometry | Ship size (derived) | Numeric vector (length, width, aspect ratio) |

<br>

## 3. Fusion Space

```
Optical image ─┐
               ├─ Dual-head tokenizer → Shared Transformer Encoder → Unified embedding
SAR image     ─┘
```

<br>

## 4. Output Data

| Stage      | Output Used                   |
| ---------- | ----------------------------- |
| ReID       | Feature distance matrix       |
| Tracking   | Identity association          |
| Trajectory | Time-ordered identity matches |


<br>

## A Dynamic Camera with Multi-modal Input Signal Fusion


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

## Multiple sensors = multiple Gaussian constraints on the same state

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

<br>


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

<br>

## B. Key Meta-Observation (Critical)

| Observation                                      | Explanation                                     |
| ------------------------------------------------ | ----------------------------------------------- |
| These are not “missing tricks”                   | They are structural modeling problems           |
| They predate deep learning                       | Many come from 1950–2000 math/physics           |
| Best papers optimize *within* broken assumptions | They rarely question the assumptions themselves |
| Solving them reduces leaderboard gains           | Which is why incentives avoid them              |
| They require saying “this task is ill-posed”     | CVPR culture discourages this                   |


<br>

