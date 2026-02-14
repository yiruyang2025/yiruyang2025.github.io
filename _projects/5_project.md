---
layout: page
title: 2026 - Master Thesis - Airlines and House Robots
description: End-to-End, PRS
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>

## Topics

- 4D Semantic Indoor Map under `LiDAR Free`, from Home Robots, Airlines to All
- the sensors weren’t really converging into intelligence, robots didn’t really understand which part of the home
- privacy, accuracy, and low-latency, under dark and adverse conditions

<br>

## Cute Products


- [Matic Robots](https://www.youtube.com/watch?v=i_8CKdULXWg), home
- [Rovex Technologies](https://www.linkedin.com/company/gorovex/), hospital


<br><br><br><br><br><br>


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
