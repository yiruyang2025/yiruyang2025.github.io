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

## 2026

- [User Studies](https://juliachatain.com/)
- [The Synthetic Data Playbook - huggingface](https://huggingface.co/spaces/HuggingFaceFW/finephrase#introduction)


<br><br>

## 2025

- ETH3D
- Aria Gen 1/2
- [Human Mesh Modeling for Anny Body - NAVER LABS Europe](https://arxiv.org/pdf/2511.03589)
- [2025 - Kinematify: Open-Vocabulary Synthesis of High-DoF Articulated Objects](https://huggingface.co/papers/2511.01294)
- [2025 - Automatic analysis of three-dimensional cardiac tagged magnetic resonance images using neural networks trained on synthetic data](https://www.sciencedirect.com/science/article/pii/S1097664725000316?via%3Dihub)
- [2025 - CL-Splats-Dataset](https://huggingface.co/datasets/ackermannj/cl-splats-dataset)
- [SwissHeart Study](https://cmr.ethz.ch/swiss-heart-study.html)
- [Dec 2025 - Performance Guide](https://abseil.io/fast/)
- [2024 - Generative Zoo](https://genzoo.is.tue.mpg.de/)


<br>

- [2024 - GCD (GarmentCodeData)](https://igl.ethz.ch/projects/GarmentCodeData/)
- [GCD-MM (GarmentCodeData-MultiModal)](https://huggingface.co/georgeNakayama/AIpparel)
- [SewFactory - empty in 2025](https://huggingface.co/datasets/liulj/sewfactory)
- [POMELO Model Population Density Maps¶](https://gee-community-catalog.org/projects/pomelo/)
  - POMELO is a deep learning model addressing the need for fine-grained population maps in urban planning, environmental monitoring, public health, and humanitarian operations

<br>

## Notes

- [2025 - Recursive Language Models](https://arxiv.org/pdf/2512.24601)



<br>


## Medical

- [2025 - MC-MED](https://github.com/dkimlab/MCMED)

<br><br>


## Robots

- [2021 - Habitat - Matterport 3D Research Dataset](https://github.com/matterport/habitat-matterport-3dresearch)


<br><br>

## Audio Formats and Data Transfer Choices in ASR Datasets

| Component                   | Format / Command                                | Description                                                               | Why This Choice Is Common in AI / ML                                                                   |
| --------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Raw audio in distribution   | **FLAC (Free Lossless Audio Codec)**            | Lossless compressed waveform format that preserves exact signal fidelity  | Guarantees no acoustic information loss; ideal for reproducible research and feature extraction        |
| Compressed alternative      | **OPUS**                                        | High-efficiency lossy codec optimized for speech at low bitrates          | Strong compression–quality trade-off; reduces storage and transfer cost for large multilingual corpora |
| Internal segmentation       | **Short audio segments (≈10–20 s)**             | Audiobook recordings split into short utterances aligned with transcripts | Enables stable training, efficient batching, and reduced memory footprint in sequence models           |
| Common uncompressed format  | **WAV (PCM)**                                   | Raw pulse-code modulated waveform, typically 16-bit                       | Simple, universal, but storage-inefficient; often used internally after decoding                       |
| Legacy compressed format    | **MP3**                                         | Lossy audio compression designed for music playback                       | Rarely used in modern ASR due to artifacts and inconsistent decoding                                   |
| Broadcast / archival format | **AIFF**                                        | Uncompressed audio container similar to WAV                               | Occasionally used in speech corpora, but large in size                                                 |
| Research-friendly format    | **OGG Vorbis**                                  | Open-source lossy codec                                                   | Less common than OPUS; weaker speech-optimized performance                                             |
| Neural codec research       | **EnCodec / SoundStream**                       | Learned neural audio codecs                                               | Used in research on end-to-end audio modeling, not standard dataset storage                            |
| Dataset packaging           | **`.tar.gz` archive**                           | `tar` bundles files while preserving structure; `gzip` compresses them    | Standard for distributing large datasets with intact directory hierarchies                             |
| Data transfer tool          | **`rsync`**                                     | Incremental file transfer utility over SSH                                | Robust, resumable transfer of large datasets to HPC systems                                            |
| Transfer option             | **`-a` (archive)**                              | Preserves permissions, timestamps, and directory structure                | Ensures dataset integrity and reproducibility                                                          |
|                             | **`-v` (verbose)**                              | Prints detailed transfer progress                                         | Useful for monitoring long-running uploads                                                             |
|                             | **`-P` (progress + partial)**                   | Shows progress and keeps partial files if interrupted                     | Critical for multi-GB dataset transfers over unstable networks                                         |
| Typical workflow            | `rsync -avP *.tar.gz user@cluster:/scratch/...` | Upload compressed archives before extraction or streaming                 | Standard practice in large-scale ASR training pipelines                                                |



<br><br>

## 2026

```
- The Origin of 3D Computer Vision
```

## Coordinate Systems & Euclidean Transformations

| Concept                        | Who / When                     | Why Introduced                              | Mathematical Form                   | Mathematical Essence               |
| ------------------------------ | ------------------------------ | ------------------------------------------- | ----------------------------------- | ---------------------------------- |
| Euclidean Space $\mathbb{R}^n$ | Euclid (~300 BC)               | Describe geometry with distances and angles | $x \in \mathbb{R}^n$                | Metric space with inner product    |
| Rotation                       | Euler (18th c.)                | Model rigid motion preserving distances     | $x' = R x$, $R^T R = I$, $\det R=1$ | Linear isometry, group $SO(n)$     |
| Translation                    | Classical mechanics            | Describe displacement of objects            | $x' = x + t$                        | Affine (non-linear) transformation |
| Euclidean Transformation       | Klein (1872, Erlangen Program) | Classify geometry by invariants             | $x' = R x + t$                      | Group action of $SE(n)$            |

<br>


## Homogeneous (Extended) Coordinates

| Concept                                 | Who / When                | Why Introduced                        | Mathematical Form                                   | Mathematical Essence                         |
| --------------------------------------- | ------------------------- | ------------------------------------- | --------------------------------------------------- | -------------------------------------------- |
| Homogeneous Coordinates                 | Möbius, Plücker (19th c.) | Represent translation linearly        | $(x,y) \rightarrow (x,y,1)$                         | Embedding affine space into projective space |
| Projective Space $\mathbb{P}^n$         | Poncelet, Plücker         | Remove special cases (parallel lines) | $\mathbb{P}^n = (\mathbb{R}^{n+1}\setminus 0)/\sim$ | Equivalence classes up to scale              |
| Euclidean Transform in Homogeneous Form | Classical                 | Unified matrix representation         | $\begin{bmatrix} R & t \ 0 & 1 \end{bmatrix}$       | Linear action on $\mathbb{P}^n$              |


<br>

## 3D Projective Geometry

| Concept                        | Who / When       | Why Introduced      | Mathematical Form    | Mathematical Essence  |
| ------------------------------ | ---------------- | ------------------- | -------------------- | --------------------- |
| 3D Homogeneous Point           | Classical        | Unified 3D geometry | $X \in \mathbb{P}^3$ | Ray in $\mathbb{R}^4$ |
| Plane Representation           | Duality          | Incidence algebra   | $\pi^T X = 0$        | Dual space            |
| Plane at Infinity $\pi_\infty$ | Projective geom. | Parallelism in 3D   | $(0,0,0,1)^T$        | Directions            |


<br>

## Camera Model (Pinhole)

| Concept           | Who / When     | Why Introduced      | Mathematical Form                                               | Mathematical Essence |                |
| ----------------- | -------------- | ------------------- | --------------------------------------------------------------- | -------------------- | -------------- |
| Pinhole Camera    | Kepler (1604)  | Ideal imaging model | $x \sim P X$                                                    | Central projection   |                |
| Projection Matrix | CV standard    | Unified model       | $P = K [R                                                       | t]$                  | Projective map |
| Intrinsics $K$    | Photogrammetry | Sensor parameters   | $\begin{bmatrix}f & s & c_x \ 0 & f & c_y \ 0&0&1\end{bmatrix}$ | Image metric         |                |
| Extrinsics        | Rigid motion   | Camera pose         | $[R                                                             | t]$                  | $SE(3)$        |


<br>

## Calibration & Estimation

| Concept            | Who / When            | Why Introduced        | Mathematical Form     | Mathematical Essence |
| ------------------ | --------------------- | --------------------- | --------------------- | -------------------- |
| DLT                | Faugeras, Hartley     | Linear estimation     | $Ah=0$                | Null-space problem   |
| Normalization      | Hartley (1997)        | Numerical stability   | Zero-mean, unit RMS   | Conditioning         |
| Reprojection Error | Photogrammetry        | ML optimality         | $\sum |x - \hat x|^2$ | Maximum likelihood   |
| Zhang Calibration  | Zhengyou Zhang (1999) | Practical calibration | Plane homographies    | Absolute conic       |


<br>

## Distortions & Non-Ideal Cameras

| Concept           | Who / When          | Why Introduced     | Mathematical Form              | Mathematical Essence     |
| ----------------- | ------------------- | ------------------ | ------------------------------ | ------------------------ |
| Radial Distortion | Brown (1966)        | Real lenses        | $x_d = x(1+k_1 r^2 + k_2 r^4)$ | Nonlinear mapping        |
| Rolling Shutter   | Modern sensors      | Line-wise exposure | Time-dependent pose            | Non-rigid projection     |
| Event Camera      | Neuromorphic vision | High-speed sensing | Asynchronous events            | Spatio-temporal geometry |




<br><br>











<br><br><br><br><br><br><br><br>




## Topics - 2025 to 2026

| **Conference**                                                        | **Primary Academic Focus**                                                                                                                                    |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ICML** (International Conference on Machine Learning)               | Emphasizes **learning theory, algorithms, statistical modeling, and optimization methods**.                                                                   |
| **NeurIPS** (Conference on Neural Information Processing Systems)     | Focuses on **neural networks, cognitive science, large-scale applications, and interdisciplinary systems research**.                                          |
| **ICLR** (International Conference on Learning Representations)       | Highlights **deep learning architectures, representation learning, interpretability, and empirical training practices**.                                      |
| **CVPR** (IEEE Conference on Computer Vision and Pattern Recognition) | Concentrates on **computer vision algorithms, image/video understanding, 3D perception, and applied AI for visual data**.                                     |
| **ECCV** (European Conference on Computer Vision)                     | Shares the same vision focus as CVPR but emphasizes **methodological novelty, geometry, and European research collaborations**.                               |
| **ICCV** (International Conference on Computer Vision)                | Serves as the **global flagship vision conference**, covering **fundamental theory, large-scale datasets, and emerging applications in vision and robotics**. |



<br><br><br>


