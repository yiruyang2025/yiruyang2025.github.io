---
layout: page
title: 2026 - Thesis - Reasoning
description: warp
img: assets/img/4.jpg
importance: 6
category: work
related_publications: true
---

<br>

## References 1


- [📍 Demos](https://www.linkedin.com/posts/lou-kohler-voinov-9956a5236_ever-wondered-what-happens-to-an-rnn-during-ugcPost-7440301117588180993-uiPt?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk)
- [📍 2019 - Point-Voxel CNN for Efficient 3D Deep Learning](https://proceedings.neurips.cc/paper/2019/hash/5737034557ef5b8c02c0e46513b98f90-Abstract.html), NIPS
- [2020 - Searching efficient 3d architectures with sparse point-voxel convolution](https://arxiv.org/pdf/2007.16100)
- [2026 - nvidia/NV-Generate-MR-Brain](https://huggingface.co/nvidia/NV-Generate-MR-Brain)

<br><br>

## References 2

- [2026 - Unlocking the Working Memory of Large Language Models for Latent Reasoning](https://arxiv.org/pdf/2605.30343)


<br><br><br><br><br><br><br><br><br><br>

## 1. Comparison between Conventional Structural MRI and Quantitative Susceptibility Mapping (QSM MRI)


| **Property**                     | **Conventional Structural MRI (e.g., T1/T2)**                                                                           | **Quantitative Susceptibility Mapping (QSM MRI)**                                                                                                   |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Signal origin**                | Measures proton relaxation properties (T1 and T2 relaxation times) following RF excitation.                             | Measures phase shifts induced by local variations in the proton Larmor precession frequency.                                                        |
| **Primary contrast mechanism**   | Differences in longitudinal and transverse relaxation of hydrogen protons.                                              | Local magnetic field perturbations caused by tissue magnetic susceptibility.                                                                        |
| **What it depicts**              | Macroscopic anatomical structures (e.g., gray matter–white matter boundaries, cortical thickness).                      | The absolute magnetic susceptibility (χ) distribution of tissue.                                                                                    |
| **Physical nature**              | Qualitative or semi-quantitative signal intensity (relative brightness or darkness).                                    | Quantitative physical parameter expressed in parts per million (ppm).                                                                               |
| **Biophysical interpretability** | Indirect and non-specific; contrast reflects multiple tissue properties simultaneously.                                 | Directly linked to underlying biophysical sources of magnetism in tissue.                                                                           |
| **Sensitivity to pathology**     | Sensitive to gross structural changes such as atrophy or lesions, but largely insensitive to early molecular pathology. | Highly sensitive to **paramagnetic substances (e.g., iron deposition)** and **diamagnetic components (e.g., calcification or protein aggregates)**. |



<br>


## 2. Model Structures

```
- Comparison of Contributions under Medical Saliency Perspective (ADNI, Amyloid Mapping)
- The core model is a voxel-wise mapping fθ: X → Y, where learning implicitly assigns region-aware
saliency weights over 3D brain structures to disentangle amyloid-related signals from QSM inputs.
```


| **Medical Fact / Aspect**                                                | **Modeling Requirement**                    |
| ------------------------------------------------------------------------ | ------------------------------------------ |
| Amyloid deposition is regionally distributed (e.g., cortex, hippocampus) | Must incorporate region-level context      |
| Dense 2D feature descriptors per pixel                                  | Limited usefulness for 3D brain modeling   |
| Designed for 2D images                                                  | Not suitable for volumetric data           |
| Local implicit saliency (pixel-level peaks)                             | Only partially useful                      |
| No anatomical structure modeling                                        | Not useful for medical interpretation      |
| Local neighborhood only                                                 | Insufficient for global brain structure    |
| No region-level context                                                 | Not useful for AD modeling                 |
| Local feature correspondence                                            | Moderately useful                          |
| Image matching / retrieval objective                                    | Poor fit for medical regression tasks      |
| No disentanglement of mixed signals                                     | Not useful                                 |
| Not scalable to 3D brain volumes                                        | Not usable                                 |
| Local feature inspiration only                                          | Minor contribution                         |
| Pixel importance (local saliency)                                       | Weak interpretability                      |
| 3D voxel-based representation                                           | Highly useful for brain modeling           |
| Native 3D modeling                                                     | Fully aligned with volumetric data         |
| Region-aware implicit saliency                                          | Critical for amyloid prediction            |
| Encodes spatial brain structure                                         | Essential for medical interpretation       |
| Captures 3D spatial dependencies                                        | Essential                                 |
| Supports region-level aggregation                                       | Highly useful                              |
| Voxel-wise mapping function fθ(X)                                       | Core modeling requirement                  |
| 3D regression / field prediction                                        | Strong fit for ADNI task                   |
| Implicit signal separation via structure                                | Useful                                     |
| Efficient volumetric processing                                         | Highly useful                              |
| Direct voxel-wise amyloid prediction                                    | Major contribution                         |
| Region-aware voxel importance                                           | Critical for interpretability              |




<br>




## 3. Medical Principles for Amyloid Prediction


| **Medical Fact**                                                         | **Modeling Requirement**              |
| ------------------------------------------------------------------------ | ------------------------------------- |
| Amyloid deposition is regionally distributed (e.g., cortex, hippocampus) | Must incorporate region-level context |
| QSM signals are mixed (iron + amyloid)                                   | Must perform signal disentanglement   |
| PET provides voxel-wise ground truth                                     | Must support voxel-wise prediction    |
| Alzheimer’s disease progression is network-level                         | Must capture cross-voxel dependencies |




<br><br><br>


## 4. Coding

  - [2026 - Let your training 8hrs -> 📍 13mins](https://x.com/MaxWBuckley/status/2016998645631947148?s=20)
  - [📍 Armadillo](https://github.com/conradsnicta/armadillo-code)
  - [Differentiable Physics with Nvidia - Warp 1.11.1](https://nvidia.github.io/warp/)

<br>

## 5. Alzheimer’s Disease Neuroimaging Initiative (ADNI)

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

## Overview of the ADNI Dataset

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

## Participant Identifiers and Longitudinal Indexing

| Field                         | Description                          | Usage                                        |
| ----------------------------- | ------------------------------------ | -------------------------------------------- |
| PTID                          | Participant ID (format: XXX_S_XXXXX) | Primary key across all tables                |
| RID                           | Numeric subject ID derived from PTID | Easier joins and indexing                    |
| VISDATE / EXAMDATE / SCANDATE | Visit / exam / scan date             | Temporal alignment for longitudinal analysis |
| Phase Indicator               | ADNI1 / GO / 2 / 3 / 4               | Cohort and protocol stratification           |

<br>

## Diagnostic Group Distribution

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

## Neuroimaging Data (Raw and Processed)

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




<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

<br><br><br><br><br><br><br><br>



## References

- [Earthdata Plugin](https://plugins.qgis.org/plugins/nasa_earthdata/)
- [DiffusionDrive](https://openreview.net/revisions?id=sh7vDLo5EY), CVPR highlight 2025.
- [Development of the Nervous System](https://www.mls.uzh.ch/en/research/hajnal/teaching.html), [Prof. Dr. Stoeckli Esther](https://www.mls.uzh.ch/en/research/stoeckli/research.html)

<br>






<br><br><br><br><br><br><br><br>

