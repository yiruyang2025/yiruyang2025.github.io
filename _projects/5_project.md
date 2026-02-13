---
layout: page
title: 2026 - Master Thesis - Airlines
description: UZH AI, PRS
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>

## Topics

- Multi Object Tracking under LiDAR Free, from Airlines to All

<br>


## Tool Kits for LiDAR-Free Multi-Object Tracking

| Layer                         | Technical Components           | Functional Role and Research Application                                                                                                                                                                                                                   |
| ----------------------------- | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Distributed Orchestration** | Ray (Ray Core, Ray Data)       | Acts as the distributed runtime engine for asynchronous multi-camera stream ingestion. Enables zero-copy data sharing via the Plasma object store and manages cross-node task scheduling for real-time multi-object tracking.                              |
| **Computational Framework**   | JAX / XLA                      | Provides the functional programming foundation for high-performance numerical computing. Leverages the XLA compiler to optimize 4D trajectory estimation, uncertainty-aware bundle adjustment, and spatiotemporal manifold operations on GPU/TPU clusters. |
| **Model Composition**         | dm-haiku                       | Serves as the neural network library for JAX. Used to implement the Cross-Modal Transformer, degradation-aware encoders, and memory modules for long-term Re-Identification with explicit parameter management and state handling.                         |
| **Distributed Sharding**      | Mezzanine                      | Enables fine-grained tensor partitioning across heterogeneous compute nodes. Critical for scaling large Bundle Adjustment Hessian matrices and handling dynamic sharding when the number of tracked targets varies over time.                              |
| **Structural Inspection**     | Penzai                         | Provides model inspection and structural modification tools for large foundation models. Used to analyze latent spatiotemporal representations and selectively modify attention heads within the transformer backbone.                                     |
| **3D Vision and Geometry**    | PyTorch3D / COLMAP             | Supports differentiable 3D geometry operations including PnP solvers, triangulation, reprojection error computation, and camera pose refinement. COLMAP supplies baseline structure-from-motion pose initialization for multi-view geometry.               |
| **Robotic Middleware**        | ROS2 / C++ / Rust              | Handles low-latency message passing between drone hardware and compute clusters. Rust and C++ are used for safety-critical and high-concurrency modules such as temporal synchronization, RocSync integration, and real-time control loops.                |
| **Simulation and Synthesis**  | Unreal Engine / SUMO / Blender | Generates high-fidelity digital twin environments with synchronized multi-modal ground truth including RGB, depth, trajectories, and timestamps. Supports training and evaluation under adverse weather and long-tail navigation scenarios.                |
| **Hardware Acceleration**     | CUDA / Linux                   | Provides low-level GPU acceleration and kernel-level resource management for O(T) transformer inference, real-time backend optimization, and parallelized geometric solvers.                                                                               |




<br><br><br><br><br>
