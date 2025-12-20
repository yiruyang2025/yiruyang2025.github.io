---
layout: post
title: CV Data Sets
date: 2025-11-01
description: 🔹
categories: AI/ML
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---


<br>

## 2025

- ETH3D
- Aria Gen 1/2
- [Human Mesh Modeling for Anny Body - NAVER LABS Europe](https://arxiv.org/pdf/2511.03589)
- [2025 - Kinematify: Open-Vocabulary Synthesis of High-DoF Articulated Objects](https://huggingface.co/papers/2511.01294)
- [2025 - Automatic analysis of three-dimensional cardiac tagged magnetic resonance images using neural networks trained on synthetic data](https://www.sciencedirect.com/science/article/pii/S1097664725000316?via%3Dihub)
- [2025 - CL-Splats-Dataset](https://huggingface.co/datasets/ackermannj/cl-splats-dataset)
- [SwissHeart Study](https://cmr.ethz.ch/swiss-heart-study.html)


<br><br>


## Medical

- [2025 - MC-MED](https://github.com/dkimlab/MCMED)

<br><br>


## Robots

- [2021 - Habitat - Matterport 3D Research Dataset](https://github.com/matterport/habitat-matterport-3dresearch)


<br><br>



## 2026 - The Origin of 3D Computer Vision


## Coordinate Systems & Euclidean Transformations

| Concept                        | Who / When                     | Why Introduced                              | Mathematical Form                   | Mathematical Essence               |
| ------------------------------ | ------------------------------ | ------------------------------------------- | ----------------------------------- | ---------------------------------- |
| Euclidean Space $\mathbb{R}^n$ | Euclid (~300 BC)               | Describe geometry with distances and angles | $x \in \mathbb{R}^n$                | Metric space with inner product    |
| Rotation                       | Euler (18th c.)                | Model rigid motion preserving distances     | $x' = R x$, $R^T R = I$, $\det R=1$ | Linear isometry, group $SO(n)$     |
| Translation                    | Classical mechanics            | Describe displacement of objects            | $x' = x + t$                        | Affine (non-linear) transformation |
| Euclidean Transformation       | Klein (1872, Erlangen Program) | Classify geometry by invariants             | $x' = R x + t$                      | Group action of $SE(n)$            |


## Homogeneous (Extended) Coordinates

| Concept                                 | Who / When                | Why Introduced                        | Mathematical Form                                   | Mathematical Essence                         |
| --------------------------------------- | ------------------------- | ------------------------------------- | --------------------------------------------------- | -------------------------------------------- |
| Homogeneous Coordinates                 | Möbius, Plücker (19th c.) | Represent translation linearly        | $(x,y) \rightarrow (x,y,1)$                         | Embedding affine space into projective space |
| Projective Space $\mathbb{P}^n$         | Poncelet, Plücker         | Remove special cases (parallel lines) | $\mathbb{P}^n = (\mathbb{R}^{n+1}\setminus 0)/\sim$ | Equivalence classes up to scale              |
| Euclidean Transform in Homogeneous Form | Classical                 | Unified matrix representation         | $\begin{bmatrix} R & t \ 0 & 1 \end{bmatrix}$       | Linear action on $\mathbb{P}^n$              |


## 3D Projective Geometry

| Concept                        | Who / When       | Why Introduced      | Mathematical Form    | Mathematical Essence  |
| ------------------------------ | ---------------- | ------------------- | -------------------- | --------------------- |
| 3D Homogeneous Point           | Classical        | Unified 3D geometry | $X \in \mathbb{P}^3$ | Ray in $\mathbb{R}^4$ |
| Plane Representation           | Duality          | Incidence algebra   | $\pi^T X = 0$        | Dual space            |
| Plane at Infinity $\pi_\infty$ | Projective geom. | Parallelism in 3D   | $(0,0,0,1)^T$        | Directions            |


## Camera Model (Pinhole)

| Concept           | Who / When     | Why Introduced      | Mathematical Form                                               | Mathematical Essence |                |
| ----------------- | -------------- | ------------------- | --------------------------------------------------------------- | -------------------- | -------------- |
| Pinhole Camera    | Kepler (1604)  | Ideal imaging model | $x \sim P X$                                                    | Central projection   |                |
| Projection Matrix | CV standard    | Unified model       | $P = K [R                                                       | t]$                  | Projective map |
| Intrinsics $K$    | Photogrammetry | Sensor parameters   | $\begin{bmatrix}f & s & c_x \ 0 & f & c_y \ 0&0&1\end{bmatrix}$ | Image metric         |                |
| Extrinsics        | Rigid motion   | Camera pose         | $[R                                                             | t]$                  | $SE(3)$        |


## Calibration & Estimation

| Concept            | Who / When            | Why Introduced        | Mathematical Form     | Mathematical Essence |
| ------------------ | --------------------- | --------------------- | --------------------- | -------------------- |
| DLT                | Faugeras, Hartley     | Linear estimation     | $Ah=0$                | Null-space problem   |
| Normalization      | Hartley (1997)        | Numerical stability   | Zero-mean, unit RMS   | Conditioning         |
| Reprojection Error | Photogrammetry        | ML optimality         | $\sum |x - \hat x|^2$ | Maximum likelihood   |
| Zhang Calibration  | Zhengyou Zhang (1999) | Practical calibration | Plane homographies    | Absolute conic       |


## Distortions & Non-Ideal Cameras

| Concept           | Who / When          | Why Introduced     | Mathematical Form              | Mathematical Essence     |
| ----------------- | ------------------- | ------------------ | ------------------------------ | ------------------------ |
| Radial Distortion | Brown (1966)        | Real lenses        | $x_d = x(1+k_1 r^2 + k_2 r^4)$ | Nonlinear mapping        |
| Rolling Shutter   | Modern sensors      | Line-wise exposure | Time-dependent pose            | Non-rigid projection     |
| Event Camera      | Neuromorphic vision | High-speed sensing | Asynchronous events            | Spatio-temporal geometry |




<br><br>











<br><br><br><br>



## Topics

| **Conference**                                                        | **Primary Academic Focus**                                                                                                                                    |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ICML** (International Conference on Machine Learning)               | Emphasizes **learning theory, algorithms, statistical modeling, and optimization methods**.                                                                   |
| **NeurIPS** (Conference on Neural Information Processing Systems)     | Focuses on **neural networks, cognitive science, large-scale applications, and interdisciplinary systems research**.                                          |
| **ICLR** (International Conference on Learning Representations)       | Highlights **deep learning architectures, representation learning, interpretability, and empirical training practices**.                                      |
| **CVPR** (IEEE Conference on Computer Vision and Pattern Recognition) | Concentrates on **computer vision algorithms, image/video understanding, 3D perception, and applied AI for visual data**.                                     |
| **ECCV** (European Conference on Computer Vision)                     | Shares the same vision focus as CVPR but emphasizes **methodological novelty, geometry, and European research collaborations**.                               |
| **ICCV** (International Conference on Computer Vision)                | Serves as the **global flagship vision conference**, covering **fundamental theory, large-scale datasets, and emerging applications in vision and robotics**. |



<br><br><br><br><br><br>


