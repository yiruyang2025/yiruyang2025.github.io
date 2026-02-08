---
layout: page
title: 2026 - Master Thesis - Connectomics
description: 4D Brain Mapping, Alzheimer's Disease, PRS, UniBE
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>

## Pending


- The model will focus on `optimizing specific neural circuits` (such as the hippocampus region)
 
- Non-invasive alternative: Provides a new pathway for AD diagnosis without the need for radioactive tracers
- Voxel-level quantization: Elevates diagnosis from traditional "regional mean" to 3D whole-brain voxel-level "distribution mapping"
- Multi-scale alignment: Successfully unifies microscopic histology (IHC), macroscopic molecular imaging (PET), and physical imaging (MRI) within a deep learning framework




<br>

## Topics

  - [EU Open Research Repository](https://zenodo.org/), [AiiDA.net](https://www.aiida.net/)
  - [CERN](https://home.cern/), [PSI](https://www.psi.ch/en)

  
  - [2025 - 📍 ZapBench](https://github.com/google-research/zapbench), [PathFinder](https://www.biorxiv.org/content/10.1101/2025.05.16.654254v1)
  - [2024  - Next-generation AI for 📍 Connectomics](https://www.nature.com/articles/s41592-024-02336-0)
  - [2023 - 📍 SegCLR: Multi-layered maps of neuropil with segmentation-guided contrastive learning, Nature Methods.](https://www.nature.com/articles/s41592-023-02059-8)


- [2025 - Siglip 2: Multilingual vision-language encoders with improved semantic understanding, localization, and 📍 dense features](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=8gruapYAAAAJ&sortby=pubdate&citation_for_view=8gruapYAAAAJ:D_sINldO8mEC)


- [2026 - A generalizable foundation model for analysis of human brain MRI](https://www.nature.com/articles/s41593-026-02202-6)
- [2026 - How the brain’s wiring changes](https://www.nature.com/articles/d44151-026-00013-z)
- [2026 - SpaceX](https://x.com/Starlink/status/2017064797125410863?s=20)

<br>

## Coding

  - [2026 - Let your training 8hrs -> 📍 13mins](https://x.com/MaxWBuckley/status/2016998645631947148?s=20)
  - [📍 Armadillo](https://github.com/conradsnicta/armadillo-code)

<br>

## Alzheimer’s Disease Neuroimaging Initiative (ADNI)

- A large-scale longitudinal multi-center study initiated in 2004. The dataset includes 3D brain MRI and PET images with associated diagnostic labels and clinical metadata, and is publicly available via the ADNI Image and Data Archive under a data use agreement
- [ADNI Database](https://adni.loni.usc.edu/)
- The essence of Alzheimer's disease (AD) is the breakdown of neuronal connections caused by the deposition of amyloid plaques at the microscopic level, PATHFINDER (bioRxiv 2025) addresses how to precisely reconstruct damaged neurons, QSM/MRI Framework (Arxiv 2503) addresses how to quantify plaque burden in vivo using imaging
- Data alignment: Microscopic data (PATHFINDER) and MRI data (ADNI) differ in spatial scale by several orders of magnitude. Instead of directly feeding them into the same model, you need to learn their representation mapping, 3D U-Net or `A Medical GAN`
- Python + PyTorch (deep learning) + ANTs (image registration) + MEDI (QSM reconstruction)
- Based on 3D deep learning, `Spatial Mapping Reconstruction` from QSM magnetic signals to Amyloid pathological signals is achieved, `Why`:
  - `PET scan`: Can directly visualize amyloid plaques in the brain, but it is expensive, involves radiation, and is not available in many hospitals
  - `QSM MRI (Input)`: A newer MRI technique, highly sensitive to magnetic materials in the brain (such as iron deposits and plaques). It is inexpensive and safe
  - `Thesis task`: Use AI to find patterns between QSM signals and PET plaque distribution.


<br>

```
ADNI Cohort
│
├── QSM MRI (in vivo)
│     ├── QSM reconstruction & normalization
│     ├── Spatial registration to PET space
│     └── 3D volume cropping / resampling
│
├── Amyloid PET (reference standard)
│     ├── ADNI-standard preprocessing
│     ├── Intensity normalization
│     └── Co-registration with QSM
│
▼
3D QSM Volume
│
▼
Encoder: BrainIAC-Pretrained 3D Vision Transformer
│   (global contextual representation learning)
│
▼
Latent Cross-Modal Representation
│
▼
Alignment Module
│   (Conditional Diffusion or GAN-based refinement)
│
▼
Decoder
│
▼
Predicted Amyloid Burden Map
(continuous voxel-wise 3D estimate)
│
▼
Loss Optimization
│   ├── Structural Similarity (SSIM)
│   ├── Perceptual Loss (VGG-based)
│   └── Intensity Consistency Loss
│
▼
Voxel-wise Quantification of Cerebral Amyloid Plaque Burden
```


<br>

## Generalization

| Method                                 | Core Idea                                                                      | Effect on Optimization                                               | Importance in This Thesis                                                                                                                                                                                                |
| -------------------------------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **SAM (Sharpness-Aware Minimization)** | Explicitly searches for flat minima that are robust to parameter perturbations | Reduces sensitivity to small weight changes and avoids sharp valleys | **Critical**: Medical imaging models are prone to overfitting sharp minima that perform well on ADNI but fail under real-world, out-of-distribution clinical data. SAM significantly improves generalization robustness. |
| **Weight Decay**                       | Penalizes large parameter magnitudes                                           | Prevents memorization and controls model capacity                    | Essential for stabilizing training and avoiding overfitting, especially when only a small subset of parameters (e.g., projection and LoRA modules) is trainable.                                                         |


<br>

## Algorithmic Methods Used in This Study

| Algorithm / Method                                       | Used for in this study                                                            | Core principle (essence)                                                                                                           | Originally proposed by                                                                   |
| -------------------------------------------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **Median Filtering**                                     | Noise reduction in each z-plane before aggregate detection                        | Non-linear filtering that replaces each pixel with the median of its neighborhood, preserving edges while removing impulsive noise | John Tukey (1977, exploratory data analysis)                                             |
| **Gaussian Smoothing (Gaussian Convolution)**            | Spatial smoothing of log-transformed intensity images                             | Convolution with a Gaussian kernel to suppress high-frequency noise and approximate scale-space representation                     | Carl Friedrich Gauss (19th century); formalized in image processing by Witkin (1983)     |
| **Log-Intensity Transformation**                         | Enhance contrast of faint α-syn aggregates                                        | Nonlinear intensity compression that expands low-intensity differences and stabilizes variance                                     | Classical image processing; widely used in microscopy (no single originator)             |
| **Local Maxima Detection**                               | Initial detection of candidate α-syn aggregates                                   | Identifies pixels that are locally maximal compared to neighbors, approximating blob centers                                       | Early computer vision methods; formalized in blob detection literature (Lindeberg, 1998) |
| **3D Connected Component Grouping**                      | Group detections across adjacent z-slices into 3D aggregates                      | Spatial adjacency-based clustering to form volumetric objects                                                                      | Classical 3D image analysis (Rosenfeld & Pfaltz, 1966)                                   |
| **Bounding Box Extraction (3D)**                         | Define spatial extent and center of each aggregate                                | Axis-aligned bounding boxes around connected components                                                                            | Computational geometry (Preparata & Shamos, 1985)                                        |
| **Support Vector Machine (Nonlinear SVM)**               | Morphological filtering to exclude non-aggregate structures (e.g., blood vessels) | Maximum-margin classifier in kernel-induced feature space                                                                          | Vladimir Vapnik & Alexey Chervonenkis (1963–1995)                                        |
| **Feature-based Morphological Classification**           | Separate true aggregates from artifacts                                           | Shape, size, and intensity descriptors fed into a classifier                                                                       | Classical pattern recognition (Haralick et al., 1973)                                    |
| **Rigid Image Registration**                             | Initial alignment of LSM brain volumes to atlas                                   | Global transformation (translation + rotation) minimizing intensity mismatch                                                       | Arun et al. (1987); applied to medical imaging by Hill et al.                            |
| **Affine Image Registration**                            | Correct scaling and shearing differences                                          | Linear transformation preserving parallelism                                                                                       | Medical image registration literature (Brown, 1992)                                      |
| **B-spline Non-rigid Registration**                      | Fine anatomical alignment to mouse brain atlas                                    | Smooth, local deformation model using spline control points                                                                        | Rueckert et al., 1999                                                                    |
| **Elastix Registration Framework**                       | Combined rigid + affine + nonrigid registration                                   | Multi-resolution, intensity-based optimization framework                                                                           | Klein et al., IEEE TMI, 2010                                                             |
| **Voxelization of Point Events**                         | Assign each detected aggregate to a 3D grid                                       | Discretization of continuous space into volumetric bins                                                                            | Computer graphics & volumetric imaging (Foley et al.)                                    |
| **Local Density Estimation (3D Neighborhood Summation)** | Generate α-syn spreading heatmaps                                                 | Counts neighboring events within a fixed-radius cube (5×5×5 voxels)                                                                | Kernel density estimation concepts (Parzen, 1962)                                        |
| **Maximum Intensity Projection (MIP)**                   | Visualization of aggregates and TH signal                                         | Projects maximum voxel intensity along viewing axis                                                                                | Medical imaging standard (radiology, microscopy)                                         |
| **Full Width at Half Maximum (FWHM)**                    | Quantify spatial sharpness of aggregates                                          | Width of Gaussian fit at half-maximum amplitude                                                                                    | Spectroscopy & optics (Rayleigh criterion era)                                           |
| **Manual ROI / VOI-based Quantification**                | TH+ neuron counting and striatal signal analysis                                  | Region-based intensity or object counting                                                                                          | Stereology & quantitative histology (Gundersen, 1986)                                    |
| **Mann–Whitney U Test**                                  | Statistical comparison between ipsi/contra sides                                  | Non-parametric rank-based hypothesis test                                                                                          | Henry Mann & Donald Whitney (1947)                                                       |


<br>

## 1. Overview of the ADNI Dataset

| Item          | Description                                                     |
| ------------- | --------------------------------------------------------------- |
| Study Name    | Alzheimer’s Disease Neuroimaging Initiative (ADNI)              |
| Start Year    | 2004                                                            |
| Current Phase | ADNI4                                                           |
| Phases        | ADNI1, ADNIGO, ADNI2, ADNI3, ADNI4                              |
| Study Type    | Longitudinal, multi-center, multi-modal                         |
| Primary Goal  | Early detection and progression modeling of Alzheimer’s disease |
| Access        | IDA portal (login + Data Use Agreement required)                |


<br>

## 2. Participant Identifiers and Longitudinal Indexing

| Field                         | Description                          | Usage                                        |
| ----------------------------- | ------------------------------------ | -------------------------------------------- |
| PTID                          | Participant ID (format: XXX_S_XXXXX) | Primary key across all tables                |
| RID                           | Numeric subject ID derived from PTID | Easier joins and indexing                    |
| VISDATE / EXAMDATE / SCANDATE | Visit / exam / scan date             | Temporal alignment for longitudinal analysis |
| Phase Indicator               | ADNI1 / GO / 2 / 3 / 4               | Cohort and protocol stratification           |

<br>

## 3. Diagnostic Group Distribution

| Group          | Description                     | Number of Subjects |
| -------------- | ------------------------------- | ------------------ |
| CN             | Cognitively Normal              | 1,272              |
| SMC            | Significant Memory Concern      | 97                 |
| EMCI           | Early Mild Cognitive Impairment | 315                |
| LMCI           | Late Mild Cognitive Impairment  | 180                |
| MCI (total)    | EMCI + LMCI                     | 1,006              |
| AD             | Alzheimer’s Disease             | 523                |
| Total Patients | All non-CN subjects             | 141                |

<br>

## 4. Neuroimaging Data (Raw and Processed)

| Modality         | Access Path           | Format             | Dimensionality | Typical Use                    |
| ---------------- | --------------------- | ------------------ | -------------- | ------------------------------ |
| Structural MRI   | Advanced Image Search | DICOM / NIfTI      | 3D             | Brain atrophy analysis, 3D CNN |
| Functional MRI   | Advanced Image Search | NIfTI              | 4D             | Functional connectivity        |
| Amyloid PET      | Advanced Image Search | DICOM / NIfTI      | 3D             | Amyloid burden estimation      |
| FDG-PET          | Advanced Image Search | DICOM / NIfTI      | 3D             | Glucose metabolism analysis    |
| Pathology Slides | Advanced Image Search | Whole-slide images | 2D/3D          | Neuropathological validation   |


<br>


## Brain Signals (Why Median + MAD)


| **Property**                  | **Meaning**                                       | **Impact**                                     |
| ----------------------------- | ------------------------------------------------- | ---------------------------------------------- |
| **Non-stationary**            | The mean varies across time and sessions          | Mean and standard deviation become unstable    |
| **Heavy-tailed distribution** | Strong artifacts or high-amplitude spikes         | Standard deviation is inflated by outliers     |
| **Weak signal + mixed noise** | High-frequency oscillations + low-frequency drift | Large mean variation, clear skewness           |
| **Inter-channel variation**   | Each sensor has different sensitivity             | Requires independent per-channel normalization |


<br><br>

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



## 4D and LiDAR Free

  - [2024 - Interactive4D: Interactive 4D LiDAR Segmentation](https://arxiv.org/abs/2410.08206)
  - [4D Lidar L1 Application Scenarios - Robots - Unitree](https://www.unitree.com/cn/LiDAR)
  - [Aeva – 4DLiDAR for Autonomous Navigation - Auto Driving - beyond Beam](https://www.aeva.com/)
  - [A Digital Geneva / Zurich](https://carla.readthedocs.io/en/latest/adv_digital_twin/)








<br>
