---
layout: page
title: 2026 - Master Thesis - Flow-matching, Robotics, Security
description: Prototype, UZH AI, PRS
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>


- [🎵 2026](https://music.youtube.com/watch?v=kRCnR0m_vBY&list=OLAK5uy_lU5_UbT2MLEJq7uSs5NU4f76VC6p6-ceU), it's perfect
- [2023 - Seeing a Rose in Five Thousand Ways](https://ai.stanford.edu/~yzzhang/projects/rose/)
- [2026 - VGGT-SLAM 2.0: Real-time Dense Feed-forward Scene Reconstruction](https://www.youtube.com/watch?v=GBdOvd6p4OU)
- [2026 - 🎵](https://www.youtube.com/channel/UCafVZzwtU8XUWbXGs4LYtdg)


<br>

## Topics

- 4D Semantic Indoor Map under `LiDAR Free`, from Home Robots, Airlines to All
- privacy, accuracy, and low-latency, under dark and adverse conditions
- ID Re-identification

<br>



## Cute Products

- [Nvidia GEAR](https://research.nvidia.com/labs/gear/#open-positions)
- [Matic Robots](https://www.youtube.com/watch?v=i_8CKdULXWg), home, level-5
- [Rovex Technologies](https://www.linkedin.com/company/gorovex/), hospital
- [Flow](https://flow-project.github.io/), city navigation
- [Taalas Inc.](https://x.com/taalas_inc?lang=en)

<br>


## Task Definition

```
The essence of LiDAR-free technology can be summarized as: transforming sparse measurements of the physical world into dense geometric inference.
```

- [📍 2020 - Convolutional Occupancy Networks](https://arxiv.org/pdf/2003.04618)
- [2022 - Scalable Diffusion Models with Transformers](https://www.wpeebles.com/DiT), William Peebles, DiT


<br>


## References


- [2026 - High-Dimensional Probability](https://www.math.uci.edu/~rvershyn/papers/HDP-book/HDP-2.pdf)
- [2025 - Visual Chronicles: Using Multimodal LLMs to Analyze Massive Collections of Images](https://arxiv.org/pdf/2504.08727)

<br>

<br><br><br><br>






## Missing Capabilities in Classical SLAM

| Capability                                                  | Classical SLAM / VIO | Neural Mapping (NeRF, GS-SLAM) | Action-Conditioned World Models |
| ----------------------------------------------------------- | -------------------- | ------------------------------ | ------------------------------- |
| Estimate robot pose (“Where am I?”)                         | ✓                    | ✓                              | ✓ (implicitly)                  |
| Represent scene geometry (“What does the world look like?”) | ✓                    | ✓✓                             | ✓                               |
| Model long-term spatial consistency                         | ✓                    | ✓✓                             | ✓                               |
| Predict future robot motion                                 | ✓ (locally, via IMU) | ✗                              | ✓                               |
| **Predict how actions change the world**                    | ✗                    | ✗                              | **✓**                           |
| Handle non-rigid, contact-rich rearrangements               | ✗                    | ✗                              | **✓**                           |
| Support action-level foresight and planning                 | ✗                    | ✗                              | **✓**                           |


<br>

## Key Evolution of LiDAR-Free 3D Perception

| Stage                                                            | Core Papers                                    | Key Innovation                                                                   | Problem Solved                                                                                              | Technical Essence                                                                                          |
| ---------------------------------------------------------------- | ---------------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Stage 1: From 2D to 3D (BEV Revolution)**                      | LSS (Lift, Splat, Shoot), ECCV 2020; BEVDet    | Lift 2D image features into 3D space and project them into Bird’s-Eye View (BEV) | Vision systems could not unify multi-camera 2D pixels into a consistent 3D coordinate system for navigation | Establishes the foundational BEV-based architecture used in modern camera-only autonomy systems            |
| **Stage 2: Global Association with Transformers**                | BEVFormer, ECCV 2022                           | Introduces temporal modeling with Transformer-based spatial-temporal attention   | Handles occlusion and improves scene consistency by aggregating information across multiple frames          | Enables memory over previous frames, improving robustness and dynamic scene understanding                  |
| **Stage 3: Occupancy-Based Scene Understanding (Occupancy Era)** | TPVFormer; Tesla Occupancy Network (2022–2023) | Predicts dense 3D occupancy instead of object bounding boxes                     | Moves beyond object detection to full spatial understanding of free space and obstacles                     | Represents the world as a semantic voxel grid, enabling fine-grained geometry and material-level reasoning |


<br>

## Tool Kits for LiDAR-Free

| Layer                         | Technical Components           | Functional Role and Research Application                                                                                                                                                                                                   |
| ----------------------------- | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Distributed Orchestration** | Ray (Ray Core, Ray Data)       | Acts as the distributed runtime engine for asynchronous multi-camera stream ingestion. Enables zero-copy data sharing via the Plasma object store and manages cross-node task scheduling for real-time multi-object tracking.                              |
| **Computational Framework**   | JAX / XLA                      | Provides the functional programming foundation for high-performance numerical computing. Leverages the XLA compiler to optimize 4D trajectory estimation, uncertainty-aware bundle adjustment, and spatiotemporal manifold operations on GPU/TPU clusters. |
| **Model Composition**         | dm-haiku                       | Serves as the neural network library for JAX. Used to implement the Cross-Modal Transformer, degradation-aware encoders, and memory modules for long-term Re-Identification with explicit parameter management and state handling.                         |
| **Distributed Sharding**      | Mezzanine                      | Enables fine-grained tensor partitioning across heterogeneous compute nodes. Critical for scaling large Bundle Adjustment Hessian matrices and handling dynamic sharding when the number of tracked targets varies over time.                              |
| **Structural Inspection**     | Penzai                         | Provides model inspection and structural modification tools for large foundation models. Used to analyze latent spatiotemporal representations and selectively modify attention heads within the transformer backbone.                                     |
| **3D Vision and Geometry**    | PyTorch3D / COLMAP             | Supports differentiable 3D geometry operations including PnP solvers, triangulation, reprojection error computation, and camera pose refinement. COLMAP supplies baseline structure-from-motion pose initialization for multi-view geometry.               |
| **Robotic Middleware**        | ROS2 / C++ / Rust              | Handles low-latency message passing between drone hardware and compute clusters. Rust and C++ are used for safety-critical and high-concurrency modules such as temporal synchronization, RocSync integration, and real-time control loops.                |
| **Simulation and Synthesis**  | Unreal Engine / SUMO / Blender | Generates high-fidelity digital twin environments with synchronized multi-modal ground truth including RGB, depth, trajectories, and timestamps. Supports training and evaluation under adverse weather and long-tail navigation scenarios.                |
| **Hardware Acceleration**     | CUDA / Linux                   | Provides low-level GPU acceleration and kernel-level resource management for O(T) transformer inference, real-time backend optimization, and parallelized geometric solvers.                             |

<br>


## Detection and Tracking Algorithms

| Layer                     | Technical Components                    | Application                                                                                                       |
| ------------------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Detection Backbone        | RT-DETR                                 | Transformer-based object detection producing spatially consistent bounding boxes and feature embeddings for downstream multi-view association. |
| Temporal Association      | Query-Based Tracking (e.g., MOTR-style) | Maintains persistent object identities across frames using learnable spatiotemporal queries instead of heuristic matching.                     |
| Multi-View Correspondence | Epipolar Geometry                       | Filters cross-camera matches using the Fundamental Matrix to enforce geometric consistency before triangulation.                               |
| 3D Reconstruction         | Triangulation + PnP                     | Recovers metric 3D positions from validated multi-view 2D detections and refines camera pose estimates.                                        |
| Global Optimization       | Bundle Adjustment                       | Minimizes reprojection error jointly over camera poses and object trajectories to achieve globally consistent 4D reconstruction.               |
| Dynamic Motion Modeling   | Motion Decomposition                    | Separates object motion from camera motion to stabilize optimization under dynamic scenes.                                                     |
| Spatiotemporal Refinement | Uncertainty-Aware Optimization          | Weighs correspondences by confidence scores to improve robustness under occlusion, noise, and adverse weather conditions.                      |
| Identity Persistence      | Cross-Camera Re-Identification          | Uses learned feature embeddings to maintain consistent object identities across disjoint camera views.                                         |


<br>





<br><br><br><br><br>
