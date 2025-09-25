---
layout: page
title: 2025 - Master Thesis and Project
description: Multi-view 4D Reconstruction, CVG
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---

<br>

## Supervisors


Dr. Ulrike Wissen

Dr. Jonas Egeler



<br>

## Topics

<br>

**Related Coursework** - Learnt background knowledge


- ViT, DINOv3, SAM2, Diffusion, Flow-matching, Clip, RL


- [2025 - 3D Vision](https://cvg.ethz.ch/lectures/3D-vision/)
- [2025 - Seminar in Visual Computing](https://cvg.ethz.ch/lectures/Doctoral-Seminar/)
- [2025 - Mixed Reality](https://cvg.ethz.ch/lectures/Mixed-Reality/)
- ([2025 - Advanced Topics in Embodied Intelligence](https://www.vvz.ethz.ch/Vorlesungsverzeichnis/lerneinheit.view?lerneinheitId=197038&semkez=2025W&ansicht=LEHRVERANSTALTUNGEN&lang=en))


<br>

## Reading List / References

<br>

Toolkit - [2025 - PartPacker: Efficient Part-level 3D Object Generation via Dual Volume Packing](https://github.com/NVlabs/PartPacker)


<br>


📍 Two-View Geometry Scoring 📍 Without Correspondences

Zero-1-to-3: Zero-shot One Image to 3D Object

CAST: Component-Aligned 3D Scene Reconstruction from an RGB Image (SIGGRAPH 25 TOG)

📍 Hydra: A real-time spatial perception system for 3D scene graph construction and optimization

Incremental Translation Averaging

Revisiting Rotation Averaging: Uncertainties and Robust Losses

Vggt: Visual geometry grounded transformer

Open X-Embodiment: Robotic Learning Datasets and RT-X

📍 Semantic-SAM: Segment and Recognize Anything at Any Granularity

<br>

[2025 - MonST3R](https://monst3r-project.github.io) - Feed forward, Estimating geometry from videos of dynamic scenes
  - [codebase](https://colab.research.google.com/drive/1-fc8uBxaXC2gbgBJQF-Jf_f0BVmJ-uTP?usp=drive_link)


[2024 - DUSt3R: Geometric 3D Vision Made Easy](https://europe.naverlabs.com/research/publications/dust3r-geometric-3d-vision-made-easy/)

<br>

[📍 T-PAMI 2025 DiffMVS & CasDiffMVS](https://www.linkedin.com/posts/fangjinhua-wang-4ba2aa150_computervision-3dvision-3dreconstruction-ugcPost-7369084868091170816-ZdVh?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk)


  - [codebase](https://colab.research.google.com/drive/1krSH8BB3EcN5ISZuHwaGF4i4FGOzg63i?usp=sharing)

<br>

[2023 - 3D Line Mapping Revisited](https://openaccess.thecvf.com/content/CVPR2023/papers/Liu_3D_Line_Mapping_Revisited_CVPR_2023_paper.pdf)


<br>

[2025 - TAPNext: Tracking Any Point (TAP) as Next Token Prediction](https://tap-next.github.io/)

[2022 - NeSF: Neural Semantic Fields for Generalizable Semantic Segmentation of 3D Scenes](https://research.google/pubs/nesf-neural-semantic-fields-for-generalizable-semantic-segmentation-of-3d-scenes/)

[2025 - LSD-3D: Large-Scale 3D Driving Scene Generation with Geometry Grounding](https://princeton-computational-imaging.github.io/LSD-3D/)

<br><br>

**Attended Master Thesis Project Defense at cvg**

  - 01 Sep 2025 - 📍 Reconstructing Complete Garments with Foundation Models
    - Pattern Prediction on Fabric Recognition
    - 'Garments are both cultural artifacts and engineered products, but most generative models produce visuals that cannot be manufactured. This thesis introduces a foundation model for pattern-centric garment generation, where outputs are sewing patterns—panels, seams, and annotations—ready for CAD and simulation. A new tokenizer and multimodal dataset enable structured decoding from text or image inputs in a unified framework. In parallel, we investigate fabric recognition from large-scale product data, underscoring the challenge of linking garment shape to material behavior. Experiments show state-of-the-art pattern prediction, strong generalization, and predictable scaling. Together, these contributions move digital fashion toward simulation-ready, fabrication-oriented design.'
    - [2025 - AIpparel: A Multimodal Foundation Model for Digital Garments](https://igl.ethz.ch/projects/aipparel/aipparel_paper.pdf)
    - [2025 - Single View Garment Reconstruction Using Diffusion Mapping Via Pattern Coordinates](https://arxiv.org/html/2504.08353v1)

<br>

  - 10 Sep 2025 - An Interactive, Foundation-Model-Empowered Video Annotation Interface for Constructing a Challenging Video Object Segmentation Dataset
    - SAM 2, DINOv2, GPT-4o, 📍 `real-time Annotation`
    - demo - nutsh


<br>


```
   +-------------------+
   |   Canonical Mesh  |
   |  (reference shape)|
   +-------------------+
             |
             |  (apply warp function: motion / pose / deformation)
             v
   +-------------------+
   | Deformation Warp  |
   |  (maps canonical  |
   |   → target space) |
   +-------------------+
             |
             |  (query points in deformed space)
             v
   +--------------------+
   |  Implicit Field    |
   | (SDF / occupancy / |
   | density / radiance)|
   +--------------------+
             |
             v
   +-------------------+
   |  Final Geometry / |
   |   Appearance      |
   +-------------------+
```






<br><br>

## Semester Project / Independent Study / Thesis

<br>

`Medical Organ Data Formats`

| Format           | Typical Source (Hospital / Research)                             | Advantages                                                                                | Limitations                                                                    | Role in Your Pipeline (3D → 2D SVG → Annotation → Deformation → 3D)                          |
| ---------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------- |
| **DICOM**        | Standard format for CT / MRI scans (hospital PACS systems)       | Contains complete volumetric data + metadata (patient, scan parameters); widely supported | Very large size; slice-based (requires reconstruction); no direct surface mesh | Start point in hospitals. Requires segmentation + surface reconstruction before projection.  |
| **NIfTI / NRRD** | Research imaging formats (MRI/CT studies, segmentation masks)    | Compact single-file volume storage; standardized for research                             | Not directly a surface mesh; still requires segmentation + reconstruction      | Similar to DICOM: used as intermediate research data before extracting surface mesh.         |
| **STL**          | 3D printing, surgical simulation models                          | Simple structure (triangular mesh only); lightweight; widely supported                    | No colors or textures; no rich metadata                                        | Very suitable for 3D → 2D projection; ideal for shape-only tasks (cutting, deforming).       |
| **OBJ**          | Converted CT/MRI meshes; 3D modeling software (Blender, MeshLab) | Supports vertices, normals, textures, materials; flexible for visualization               | Larger file sizes; redundant texture data if unused                            | Excellent for your pipeline (interactive 2D SVG projection, deform, 3D rendering).           |
| **PLY**          | 3D scanning, point clouds + surface meshes                       | Stores vertex attributes (color, normals, custom fields); good for scientific use         | Larger size; less universal web support                                        | Works like OBJ; useful if additional attributes (e.g., CT intensity) are mapped to vertices. |
| **VTK**          | Scientific visualization, research datasets (e.g. IRCAD meshes)  | Rich topology support; integrates with visualization pipelines                            | Less common in web apps; conversion to OBJ/STL often needed                    | Intermediate format (research to web). Can be converted into OBJ/STL for your web app.       |

<br>

## End-to-End Real-World Data Flow - [USZ](https://www.usz.ch/en/department/diagnostic-and-interventional-radiology/)

<br>

### Standard Surgical Workflow

```
Hospital CT / MRI 🏥
        ↓

DICOM (raw slices + metadata)
        ↓ Segmentation + Reconstruction

Surface Mesh (OBJ / STL / PLY / VTK)
        ↓ Projection

2D SVG (interactive) / PNG (static)
        ↓ Annotation

Surgeon marks points / lines on SVG
        ↓ Mapping

Handles mapped back to 3D mesh
        ↓ Deformation

FastAPI /deform → ARAP deformation applied
        ↓ Visualization

Updated 3D mesh rendered in LiverViewer (three.js)
        ↓ Export

Surgical plan → PDF / PNG / QR for clinical workflow
```

<br>

### Extended Research / Printing Workflow

```
Hospital CT / MRI ✅
        ↓

DICOM (raw slices + metadata)
        ↓ Segmentation (3D Slicer / nnUNet)

NIfTI mask (segmentation labels)
        ↓ Mesh Extraction

Surface Mesh Export:
   • GLB → Web visualization (three.js, with color/texture)
   • PLY → Research (point cloud + RGB/labels)
   • STL → 3D printing (geometry only)
        ↓ Projection

2D SVG (interactive) / PNG (static)
        ↓ Annotation

Surgeon marks points / lines on SVG
        ↓ Mapping

Handles mapped back to 3D mesh
        ↓ Deformation

FastAPI /deform → Laplacian / ARAP deformation applied
        ↓ Visualization

Updated 3D mesh rendered in LiverViewer (three.js)
        ↓ Export

Surgical plan → PDF / PNG / QR + optional STL for printing
```


<br>

| Comparison 🔍              | Standard Workflow 🏥                          | Extended Research / Printing Workflow 🚀                        |
| -------------------------- | --------------------------------------------- | --------------------------------------------------------------- |
| **Input** 📥               | DICOM → Mesh (OBJ/STL)                        | DICOM → NIfTI mask → Mesh                                       |
| **Intermediate Result** 🔄 | Mesh (OBJ/STL/PLY)                            | NIfTI segmentation (with labels 🏷️)                            |
| **Output Formats** 📂      | OBJ / STL / PLY / VTK                         | GLB (Web 🌐), PLY (Research 📊), STL (3D Printing 🖨️)          |
| **Frontend Display** 🖥️   | SVG + three.js (OBJ)                          | SVG + three.js (GLB ⚡ faster, with colors 🎨)                   |
| **Export** 📑              | PDF / PNG / QR                                | PDF / PNG / QR + STL for printing 🖨️                           |
| **Main Application** 🎯    | Clinical documentation & surgical planning 🩺 | Research, AI analysis 🤖, Web visualization 🌐, 3D printing 🖨️ |





<br><br>

## Feature Extractor vs Physics-Informed 4D Representation

| Dimension         | Vision Feature Extractor (4D)                                                                         | Physics-Informed 4D Representation                                                                                  |
| ----------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **Essence**       | Extracts **spatio-temporal features** from video/image sequences (data-driven embedding)              | Introduces **physical constraints** in the 4D representation space (physics-driven regularization)                  |
| **Input**         | Raw perceptual data (RGB, Depth, Point Cloud, Sewing Patterns, Motion Sequences)                      | Output of the Feature Extractor (latent 4D features)                                                                |
| **Learning Goal** | Learn rich spatio-temporal dynamics representations                                                   | Ensure that the dynamics obey real physical laws (gravity, tension, friction, energy conservation)                  |
| **Methodology**   | Relies on large-scale data + foundation backbones (MAE, DINOv2, VideoMAE, LLaVA-Video)                | Adds physical constraints in the loss/latent space (PINN-style, energy-based loss, differentiable cloth simulation) |
| **Strengths**     | Strong generalization, adaptable to multiple tasks (segmentation, dynamics prediction, editing)       | Physically plausible outputs, avoids “fake motions” or unstable 4D dynamics                                         |
| **Limitations**   | May generate physically inconsistent predictions (e.g., cloth floating unnaturally, body penetration) | Requires explicit modeling or approximating physical laws, higher computational cost                                |
| **Relation**      | Perception Layer: extracts data-driven 4D embeddings                                                  | Consistency Layer: injects physical inductive biases into embeddings                                                |
| **Applications**  | 4D instance segmentation, video-based garment generation, non-rigid tracking                          | Cloth folding simulation, garment draping, robotic manipulation with physics-consistent prediction                  |




<br><br>


`Build A 4D Vision Feature Extractor, test on Semantic Head / Heads`

<br>

```
             Input Data (4D sequence)
                 (clothes, etc.)
                        │
                        ▼
           **Vision Feature Extractor**
                 (Non-Rigid ViT)
                        │
         High-level spatiotemporal features
                        │
                        ▼
             ┌──────────────────────────┐
             │    **Semantic Head**     │
             │ - Semantic Keypoints     │
             │ - Segmentation Maps      │
             │ - Space-Time Transformer │
             │ - (Optional) VLM Module  │
             └──────────────────────────┘
                        │
     Sparse keypoints + region maps + temporal cues + optional language embeddings
                        │
                        ▼
             Downstream Controller / Robot
             - Folding sequences
             - Grasp planning
             - Task sequencing (fold / hang / place)
```

<br>

## Semantic Heads

<br>

| **Semantic Head Type**            | **Core Function**                                                        | **Industrial Frontier Applications**                                                                      | **Representative Companies / Labs**                             |
| --------------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **Part Segmentation Head**        | Pixel-wise or region-wise segmentation of object parts                   | **Garment industry**: sleeve/neck/hem segmentation for folding and robotic manipulation                   | Meta (FAIR, Garment Manipulation), Amazon Robotics              |
| **Instance Segmentation Head**    | Distinguishes individual objects of the same class                       | **Agriculture**: detecting individual crops vs weeds for precision spraying                               | John Deere, Blue River Technology                               |
| **Region Classification Head**    | Assigns semantic labels to regions or masks                              | **Healthcare / Surgery**: organ or tumor classification for robotic surgery guidance                      | Intuitive Surgical, Siemens Healthineers                        |
| **Surface Parsing Head**          | Extracts continuous surface boundaries                                   | **Surgical robots**: organ surface modeling, surgical field tracking                                      | Philips, ETH Zurich + Intuitive collaborations                  |
| **Affordance Head**               | Predicts functional regions (grasp points, fold lines, cut regions)      | **Robotics**: folding clothes, grasping tools, space robotics                                             | Boston Dynamics Spot, TRI (Toyota Research Institute), NASA JPL |
| **3D/4D Spatio-Temporal Head**    | Learns semantic labels over time sequences (video/4D input)              | **Space**: satellite/space debris tracking, multi-frame segmentation for robotic arms                     | NASA, SpaceX, ESA AI programs                                   |
| **Multi-Modal Fusion Head**       | Combines visual semantics with other modalities (depth, language, force) | **AR/VR & Human-Robot Interaction**: wearable AR (HoloLens, Aria) semantic mapping for manipulation tasks | Microsoft HoloLens, Meta Reality Labs, Apple Vision Pro         |
| **Self-Supervised Semantic Head** | Uses pseudo-labels or consistency for training                           | **Scalable Robotics & Industry 4.0**: training robots without full annotations                            | Covariant.ai, Intrinsic (Alphabet)                              |



<br><br>


**References**

[📍 2008 - Anatomy of high-performance matrix multiplication](https://dl.acm.org/doi/10.1145/1356052.1356053)


<br><br><br>


**Some Products**

[2025 - LeFranX](https://www.linkedin.com/posts/zkweng_lerobot-robotics-robotlearning-activity-7368317883715604481-nD8m?utm_source=share&utm_medium=member_desktop&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk) - High-performance VR-based teleoperation


<br><br><br>


**Topics**

Zero-shot, Co-training, better Generalization, a Feature Extractor


<br><br><br>


## Representation Learning for 'object-level', Action Tokenization for 'control-level'

<br>

**A 4D tokenization For VLA in Production**

```
          ┌───────────────────────────┐
          │   4D Perception Module    │
          │   (FFN-based Segmentation)│
          └───────────┬───────────────┘
                      │
   Input (video/point cloud) 
   x,y,z,t → 4D Instance Masks
                      │
                      ▼
          ┌───────────────────────────┐
          │   Representation Layer    │
          │   (Tokens / Scene Graph)  │
          └───────────┬───────────────┘
                      │
      Object IDs, Trajectories, 
      Relations (cup on table, 
      human holding phone, etc.)
                      │
                      ▼
          ┌───────────────────────────┐
          │  VLA (π0 / π0.5 style)    │
          │ Vision-Language-Action FM │
          └───────────┬───────────────┘
                      │
     Language: "Clean up the table"
     Visual: scene tokens
     Action: robot skill library
                      │
                      ▼
          ┌───────────────────────────┐
          │   Robot Execution Layer   │
          │  (Household / Navigation) │
          └───────────────────────────┘
               │                  │
       ┌───────┘                  └────────┐
       ▼                                   ▼
┌───────────────┐                  ┌─────────────────┐
│ Household     │                  │ Navigation      │
│ Tasks         │                  │ Tasks           │
│ - Clean table │                  │ - Dynamic SLAM  │
│ - Pick objects│                  │ - Avoid humans  │
│ - Sort laundry│                  │ - Reach target  │
└───────────────┘                  └─────────────────┘
```

<br>

```
         ┌────────────────────────────┐
         │       4D Input Data        │
         │   (x, y, z, t sequences)   │
         │  Video / Dynamic PointCloud│
         └─────────────┬──────────────┘
                       │
                       ▼
         ┌───────────────────────────┐
         │   Vision Feature Extractor│
         │  CNN / ViT / 3D CNN / GNN │
         └─────────────┬─────────────┘
                       │  feature embeddings
                       ▼
         ┌────────────────────────────┐
         │ Representation Learning    │
         │  + Scaling Laws            │
         │  (learn semantic space)    │
         └─────────────┬──────────────┘
                       │
                       ▼
         ┌────────────────────────────┐
         │   4D Instance Segmentation │
         │  Instance masks + tracking │
         │  (object IDs over time)    │
         └────────────────────────────┘
```


<br>

| **Research Theme (Abbeel)**                       | **Key Works**                                                                                      | **Core Idea**                                                                            | **Relation to Physical Intelligence (π)**                                                                                                          |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Reinforcement Learning & Policy Optimization**  | TRPO, GAE, Soft Actor-Critic (SAC)                                                                 | Stable training in high-dimensional continuous control spaces                            | **FAST action tokenization** tackles the same challenge of efficient control in high-dimensional spaces, extending RL efficiency with tokenization |
| **Representation Learning & Generative Modeling** | InfoGAN, DDPM, Decision Transformer                                                                | Interpretable representation learning; diffusion models; framing RL as sequence modeling | **π0 / π0.5 VLA** adopt the same idea: treating robot actions as sequences, aligning with the Decision Transformer paradigm                        |
| **Robotics & Imitation Learning**                 | Apprenticeship Learning via IRL, End-to-end visuomotor policies, Domain Randomization for Sim2Real | Learning from human demonstrations; transferring policies from simulation to real robots | **π0.5 open-world generalization** extends this line of work by ensuring VLA policies can adapt to unseen real-world environments                  |
| **General Policies & Scalability**                | Hindsight Experience Replay (HER), Multi-agent actor-critic, DeepMimic                             | Scaling up RL to more tasks and agents; learning versatile and robust skills             | **π series** (π0, π0.5) represent scaling towards generalist robot policies, trained across multiple robots and tasks                              |




<br><br><br><br>


## Some Related Art works

<br>

[2025 - VGGT](https://vgg-t.github.io/) - `Convert the` geometric `problem into` a sequence modeling problem of Transformer

[📍 2023 - OpenScene](https://openaccess.thecvf.com/content/CVPR2023/papers/Peng_OpenScene_3D_Scene_Understanding_With_Open_Vocabularies_CVPR_2023_paper.pdf) - Open set


[2018 - GQN](https://deepmind.google/discover/blog/neural-scene-representation-and-rendering/) - SSL, Neural scene representation



<br><br><br><br>


## Key Contributions


<br>

A FFN for 4d Segmentation - Semantic -> Instance, for real-time Inference


Hierarchical, 

<br><br><br>



## Benchmarks and SOTAs

<br>

## 1. 4D




<br>

## Why FFN

<br>


| Category                               | Representative Works / Applications                                                                                                                                                                                                                                                                                                                 |
| -------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **FFN in 3D/4D Segmentation**          | **PointNet / PointNet++** (CVPR’17, FFN-style MLP, 3D semantic & instance segmentation) <br> **Flood-Filling Networks** (NeurIPS’17, large-scale neuron segmentation) <br> **Spatio-temporal FFNs** (MICCAI’19, biomedical 4D segmentation)                                                                                                         |
| **Transformers in 3D/4D Segmentation** | **DINOv3** (Meta, 2025 – open-vocabulary semantic features) <br> **VGGT** (CVPR’25 – geometry + segmentation backbone) <br> **PanSt3R** (CVPR’25, ETH – 4D panoptic segmentation) <br> **MonST3R** (CVPR’25, Meta+ETH – motion-aware segmentation) <br> **Shape of Motion** (CVPR’25, Meta Reality Labs – dynamic 4D reconstruction & segmentation) |
| **Frameworks (DeepMind / Google)**     | **TensorFlow 3D (TF3D)** – Google/DeepMind 3D segmentation library <br> **TensorFlow 4D (TF4D)** – experimental library for spatio-temporal 4D segmentation                                                                                                                                                                                         |
| **Industry Applications**              | **Meta Reality Labs** – AR/VR semantic & instance segmentation (Project Aria) <br> **DeepMind** – scene segmentation research (TF3D/TF4D) <br> **NVIDIA Isaac** – 4D obstacle segmentation for robotics <br> **Apple ARKit** – semantic scene segmentation for AR                                                                                   |

<br><br>




📍 `4d Scene Modeling - Hierarchies`

<br>

```
        Projective
  (collinearity, cross-ratio)
                 ↓
          Affine
   (parallelism, ratios of areas)
                 ↓
          Similarity
   (ratios of distances, angles)
                 ↓
   Tekin et al. (2018): CNN + PnP
   ---> Upgrade metric → Euclidean
                 ↓
          Euclidean (SE(3))
   (absolute distances, 6D pose)
                 ↓
          4D Spatio-temporal
   (geometry + temporal coherence)
```

<br>


## Pipeline

<br>

```
                ┌──────────────────────────────┐
                │   Local Object Dynamics      │
                │ (SO(3) Forecasting, ICCV’25) │
                │  - Neural CDE + SG filter    │
                │  - Robust to noise & forces  │
                └─────────────┬────────────────┘
                              │
            Pose / Rotation Trajectories (SO(3)) 
                              │
      ┌───────────────────────▼──────────────────────────┐
      │           Global 4D Scene Modeling               │
      │────────────────────────────────────────────────  │
      │ MonST3R (CVPR’25)  → Geometry in motion          │
      │ Shape of Motion (CVPR’25) → Shape + motion priors│
      │ 4DNeX (CVPR’25)   → End-to-end 4D generation     │
      └─────────────┬───────────────────────┬────────────┘
                    │                       │
     ┌──────────────▼─────────────┐   ┌─────▼──────────────┐
     │ Geometric Backbone         │   │ Semantic Backbone  │
     │ VGGT (CVPR’25)             │   │ OpenScene (2023)   │
     │ - Camera intrinsics/extr.  │   │ - Open-vocab 3D    │
     │ - Depth, 3D tracks         │   │ - Semantic labels  │
     └────────────────────────────┘   └────────────────────┘
```



<br><br><br><br>


## 2. 3D

<br>

[2025 - MonST3R: A Simple Approach for Estimating Geometry in the Presence of Motion](https://monst3r-project.github.io/)


[2024 - AGILE3D](https://ywyue.github.io/AGILE3D/)

[2016 - COLMAP 1](https://github.com/colmap/colmap) - baseline 1

[2025 - COLMAP 2](https://developer.nvidia.com/blog/how-to-instantly-render-real-world-scenes-in-interactive-simulation/) - baseline 2

<br>

## 📍 Evolution for 3D Vision

<br>

| Level              | Traditional Methods | Frontier Alternatives                                                                             | Applications                                   |
| ------------------ | ------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| **2D**             | Euclidean / Affine  | Homography + Optical Flow                                                                         | Image stitching, registration                  |
| **3D Rigid**       | SE(3) rigid motion  | Lie group / Lie algebra optimization (Bundle Adjustment)                                          | SfM, SLAM                                      |
| **Non-Rigid**      | —                   | Deformation Fields, Dynamic NeRF                                                                  | Human motion, dynamic scene modeling           |
| **General Scene**  | —                   | NeRF, Gaussian Splatting, **VGGT (Geometry → Transformer)**, TetWeave                             | Full 3D reconstruction                         |
| **Learning Layer** | —                   | Equivariant GNNs (SE(3)-equivariant nets), **DINOv3 (universal self-supervised visual backbone)** | Representation learning, cross-modal alignment |



<br>

```
[2000s] Classical 2D Stitching
   - Euclidean / Affine / Homography
   - Used in panoramas, satellite mosaics, medical imaging
   - Fast, lightweight, real-time

   Euclidean (3 DOF)
   ▢ → ▢
   Rigid rotation + shift
        |
        v
   Affine (6 DOF)
   ▢ → ⬠
   Parallel preserved (shear, scaling)
        |
        v
   Projective (8 DOF)
   ▢ → ⬳
   Perspective distortion (vanishing point)
-------------------------------------------------
        |
        v
[2010s] Multi-View Geometry
   - SfM (Structure from Motion), SLAM
   - SE(3) rigid motion + Bundle Adjustment
   - Full 3D scene reconstruction (static environments)
        |
        v
[2020s] Neural Implicit Representations
   - NeRF (Neural Radiance Fields)
   - Gaussian Splatting, Dynamic NeRF
   - Rich photorealistic 3D, supports dynamics
        |
        v
[2025 → ] Transformer & Foundation Models
   - VGGT (Geometry → Transformer sequence modeling)
   - DINOv3 (7B SSL backbone, dense visual features)
   - Replaces manual geometry → universal representations
   - Powers Pixel 10 AI (Gemini Nano + Tensor G5)
```




<br>

## CUT3R

<br>

Navigation-level Scene Semantics


```
Sparse RGB / Depth / LiDAR (stream)
   ↓
Surface Fitting Module (Point cloud → implicit SDF)
   ↓
Continuous LOD generation
   ↓
4D Human Profile (geometry + temporal motion)
   ↓
Navigation / Control Integration
   - dynamic path planning
   - human-aware motion prediction
```


<br><br>


## Shape Modeling

<br>

  - Output → Spatiotemporally consistent, topologically correct 4D instance segmentation
  - The directional SDF formulation and fairness regularization of `TetWeave` can provide topology-safe and smoothly consistent support for the 4D segmentation

<br>

[📍 2025 - TetSphere Splatting: Representing High-Quality Geometry with Lagrangian Volumetric Meshes](https://github.com/gmh14/tssplat)


[2025 - VertexRegen: Mesh Generation with Continuous Level of Detail](https://vertexregen.github.io/)

<br>

```
On-the-fly Delaunay Triangulation
(unstructured tetrahedral grid; dynamic connectivity)
Mathematics: Delaunay(T) → max-min angle, avoids skinny simplices
                 ↓
Directional Signed Distance (d-SDF)
(finer control along edges; spherical harmonics expansion)
Formula: d(p, θ, φ) = Σ_{l=0}^L Σ_{m=-l}^l c_{lm}(p) Y_{lm}(θ, φ)
                 ↓
Marching Tetrahedra Extraction
(guaranteed watertight, 2-manifold, intersection-free)
Isosurface: {x ∈ ℝ³ | f(x) = 0}, f from d-SDF over tetrahedral edges
                 ↓
Gradient-based Mesh Optimization
(optimize positions p and coefficients c_{lm})
Update rule: p ← p - η ∇ₚ L ,   c_{lm} ← c_{lm} - η ∇_{c_{lm}} L
                 ↓
Fairness Regularization + Resampling
(ODT energy + fairness loss; adaptive refinement)
Fairness loss: L_fair = Σ_T (aspect_ratio(T) - 1)²
                 ↓
High-quality Adaptive Mesh
(memory ~ O(N), scalable to complex 3D shapes)
```


<br><br>


## Models

<br>

`1. Geometry-Centric 3D Models`

DUSt3R (CVPR 2024)
  - 2D Images → Feature Matching → 3D Structure

MASt3R (ECCV 2024)
  - Images → 3D-Aware Matching → Precise Geometry

VGGT (CVPR 2025)
  - Image Sequences → Geometry-Grounded Attention → 3D Pose & Structure

<br>

`2. Semantic + Geometry Joint Models`


SAM (ICCV 2023, Meta AI) / SAM 2 (2024, Meta AI)
  - Video / 3D Stream → SAM 2 Engine → Consistent 2D/3D/4D Segmentation

PanSt3R (ICCV 2025)
  - Multi-View Images → Fuse Masks → 3D Segmented Scene

4D Panoptic Extensions (CVPR 2024, Ego-Exo4D)
  - Video → 3D Panoptic + Time → 4D Reconstruction


<br>


## 3D Reconstruction Methods

<br>

```
Classical Geometry         →   CAD / Mapping / Robotics
Delaunay / Voronoi

Smooth Surfaces            →   3D Scanning / Medical Imaging
Poisson / α-shapes

Volumetric                 →   Real-time AR / Autonomous Navigation
TSDF / KinectFusion

Implicit Functions         →   AR/VR / VFX / Self-driving
DeepSDF / NeRF

Neural Rendering           →   Real-time XR / Digital Humans / Digital Twins
3D Gaussian Splatting

Foundation Models          →   📹 4D Scene Modeling / Metaverse / Robotics & AI Agents
Transformers (VGGT / MonST3R / Shape of Motion)
```




<br>

```
Delaunay/Voronoi → Classical geometry

Poisson/α-shapes → Smooth geometric reconstruction

Volumetric/TSDF → Dense volumes

Implicit (SDF/NeRF) → Continuous function surfaces

Modern neural methods (GS, Transformers) → End-to-end, dynamic scenes

-

Points → Delaunay Triangulation (Triangles)
      ○         ○───────○
       \       / \     /
        ○─────○───○───○
       / \     \ /     \
      ○   ○─────○──────○


Points → Voronoi Diagram (Cells)
      ○     │     ○
     ┌┼─────┼─────┼┐
     │ Cell │ Cell │
  ○──┼──────┼──────┼──○
     │ Cell │ Cell │
     └┼─────┼─────┼┘
      ○     │     ○


Points → Poisson / α-shapes (Smooth Surface)
        ●──────────●
      ╱              ╲
    ●                  ●
    ╲                  ╱
      ●──────────────●


Points → Volumetric / TSDF (Voxel Grid)
   ▓▓▓▓▓
   ▓███▓    Each cube = voxel
   ▓▓▓▓▓


Points → Implicit Fields (SDF / NeRF)
   f(x,y,z) = 0  → Surface
   Continuous function learned by NN
   "Shape emerges from equations"


Points → Modern Neural Models (GS / Transformer)
   ● Gaussian Splatting → soft blobs in 3D
   ● VGGT / MonST3R / PanSt3R → End-to-end feed-forward 3D/4D
   ● NeRF → Radiance fields, view-dependent rendering
```







<br>


<br><br><br>



<br><br>


## 3. 2D

<br>

[2025 - DINOv3 - checkpoints](https://huggingface.co/collections/facebook/dinov3-68924841bd6b561778e31009)

<br>


<br>

| Method                          | Core Task                       | Revolutionary Idea + Solved Problem                                                                             |
| ------------------------------- | ------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| **SAM / SAM2** (Meta 2023–2024) | Image / Video Segmentation      | Promptable segmentation; class-agnostic masks; temporal consistency; solved dataset-locked segmentation         |
| **CLIP** (OpenAI 2021)          | Vision–Language Alignment       | Contrastive learning; shared embedding space; open-vocabulary recognition; solved classifier retraining problem |
| **DINOv3** (Meta 2024)          | Universal Visual Backbone (SSL) | Large-scale self-supervised training (7B params, 1.7B images); dense features; solved annotation dependence     |






<br><br><br><br>



## Some Other topics

<br>

[2024 - soft MOE](https://arxiv.org/pdf/2308.00951)


[2025 - Probabilistic Methods for Monocular 3D Human Reconstruction](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Probabilistic+Methods+for+Monocular+3D+Human+Reconstruction&btnG=)

[2025 - minFM: Minimal Flow Matching](https://github.com/Kai-46/minFM)

[NanoGPT (124M) in 3 minutes](https://github.com/KellerJordan/modded-nanogpt)


[Aug 2025 - Proxies Could Be The Key To Interacting With Physical Objects In Mixed Reality](https://www.uploadvr.com/research-proxies-mixed-reality/)


<br><br>



## World Models / [Reality Proxy](https://www.arxiv.org/pdf/2507.17248)

<br>

[Mahcine Learning Street Talk](https://x.com/MLStreetTalk/status/1952743787454668931)

[3d gaussian](https://shivangi-aneja.github.io/projects/scaffoldavatar/)

<br>


## Topics


<br>

[Implicit 3D Representations]


[2021 - D-NeRF](https://github.com/albertpumarola/D-NeRF)


[2025 - TetWeave](https://x.com/TheGraphicsFrog/status/1920360716097274059)


[C++ lib repo - toolkit](https://github.com/libigl)


<br><br>



```
Mesh-VAE World                          Implicit Geometry World
═══════════════════════════════         ══════════════════════════════════
Mold Shape  →  Fill Cream  →           Pour Batter → Let Shape Form →  
Keep Shape  →  Adjust Icing            Implicitly Shape via Function
(Topology)     (Latent Codes)          (SDF / NeRF Fields)
     ↓                ↓                         ↓
┌────────────┐  ┌────────────┐           ┌────────────┐  ┌────────────────┐
│ Cake Mold  │→ │ Cream Code │    vs.    │  Batter    │→ │ Shape Function │
│ (Mesh Topo)│  │ (Latent z) │           │ (No Mesh)  │  │ f(x) → Geometry│
└────────────┘  └────────────┘           └────────────┘  └────────────────┘
     ↓                ↓                         ↓               ↓
Consistent Shape   Editable Details         Any Shape      Learned Surface
Fixed Faces        Vertex Offsets           Continuous     Surface = f(x)=0


Hybrid models:
1. Use Mesh-VAE to encode coarse shape → condition NeRF/SDF to model fine detail
2. Combine structural control (mesh) with detail realism (fields)

🍨 NeRF = Gelato Machine with View-Conditioned Flavor Control
🏗️ SDF = Invisible Sculptor Guided by Distance and Space Curvature
```


<br>

📍 `🍰 3D Representation Worlds`

<br>

| **Representation**        | **Analogy**            | **How it works**                                            | **Strengths**                                 | **Limitations**                           |
| ------------------------- | ---------------------- | ----------------------------------------------------------- | --------------------------------------------- | ----------------------------------------- |
| **Point Cloud**           | ✨ “Sprinkle Sugar”     | Just scatter points in space                                | Light & simple, straight from sensors         | No structure, no surface continuity       |
| **Mesh**                  | 🎂 “Cake Mold”         | Fixed mold (vertices + faces) holds the shape               | Precise surface, easy to render               | Topology fixed, hard to deform            |
| **Volumetric**            | 🧊 “Ice Cube Tray”     | Fill a voxel grid with occupancy/distance values            | Full space captured, physics-friendly         | Memory explodes with resolution           |
| **Convex 3D**             | 🥟 “Dumpling Wrappers” | Wrap shape in convex shells (convex hulls or decomposition) | Fast optimization, strong geometry guarantees | Concave details hard to capture           |
| **Implicit (SDF / NeRF)** | 🍨 “Gelato Machine”    | Function defines the surface/appearance continuously        | Infinite resolution, learns fine detail       | Needs heavy sampling, less direct control |



<br><br>

## 📍 Structure-from-Motion (SfM) Pipeline

<br>


```
Input: Multiple images (Image Sequence)
   ↓
1️⃣ Feature Extraction  
   - Detect keypoints and compute descriptors  
   - Methods: SIFT, ORB, SuperPoint, D2-Net  
   ↓
2️⃣ Feature Matching  
   - Find correspondences across images  
   - Techniques: Nearest Neighbor, RANSAC, StereoGlue  
   ↓
3️⃣ Camera Motion Estimation  
   - Estimate relative poses using Essential / Fundamental Matrix  
   - Recover camera extrinsics (Rotation R, Translation t)  
   ↓
4️⃣ Triangulation  
   - Back-project matched points  
   - Compute 3D scene points (sparse point cloud)  
   ↓
5️⃣ Bundle Adjustment (BA)  
   - Global non-linear optimization  
   - Refine camera poses and 3D points  
   - Minimize reprojection error  
   ↓
6️⃣ Output  
   - Optimized 3D point cloud (sparse or dense)  
   - Camera trajectory (motion path)  
```




<br>

## Visual SLAM Pipeline

<br>

```
Input Images (RGB / RGB-D / Stereo)
        ↓
Front-End Tracking
   - Feature Extraction (ORB, SuperPoint)
   - Feature Matching (KLT, StereoGlue)
   - Motion Estimation (PnP, Essential Matrix)
        ↓
Back-End Optimization
   - Bundle Adjustment (BA)
   - Sliding Window Optimization
        ↓
Loop Closure
   - Place Recognition
   - Pose Graph Optimization
        ↓
Mapping
   - Sparse Map (Point Cloud)
   - Dense Map (Depth / Voxel / Mesh)
   - Semantic Map (Object / Scene Labels)
        ↓
Output: Robust Trajectory + Map
```


<br><br>

## Visual Computing


<br>

`3d Segmentation`

<br>

```
2D → 3D Projection World                     Multi-View Segmentation World
═══════════════════════════════              ══════════════════════════════════
Pixel Point  →  Camera Intrinsics →          Multi-View Image →  Camera Extrinsics →
Corrected by Distortion → Project to 2D      Align Views Consistently → Back-Project to 3D
    ↓                   ↓                          ↓                       ↓
┌────────────┐   ┌────────────┐              ┌────────────┐   ┌────────────────┐
│ Pixel Coord│ → │ Metric Ray │      vs.     │ Seg. Mask  │ → │ 3D Point Cloud │
│ (u,v)      │   │ (K Matrix) │              │ (2D Image) │   │  or Voxels     │
└────────────┘   └────────────┘              └────────────┘   └────────────────┘
    ↓                   ↓                          ↓                 ↓
Distortion-Free    Accurate Geometry           Consistent 3D     Semantic Labels
Projection         Pixel → Metric Space        Reconstruction   in 3D Space


Summary:
1. Intrinsics: Ensure pixels map to correct metric coordinates
2. Extrinsics: Align multi-view cameras consistently
3. Distortion Params: Correct lens errors
4. Projection: World point → Image point
5. Back-Projection: Pixel + depth → World point
6. Goal: Lift 2D segmentation masks into 3D semantic segmentation

📸 Camera = Projector (2D Screen View)
🗺️ Extrinsics = GPS for Camera Pose
🎭 Segmentation = Paint Mask that Becomes 3D Object
```



<br>

## Classical SfM vs. VGGT

<br>

```
 Classical SfM / MVS World                   VGGT World
═══════════════════════════════════         ════════════════════════════════════
Find Keypoints → Match Pairs →              Drop Images → Transformer Thinks →
Estimate Pose → Triangulate →               One Forward Pass → Geometry Pops Out
Optimize BA → Wait Forever                  (Pose, Depth, Points, Tracks in ms)
     ↓                   ↓                          ↓
┌─────────────┐   ┌──────────────┐           ┌───────────────┐   ┌────────────────┐
│ Feature     │ → │ Epipolar     │    vs.    │ Transformer   │ → │ Unified Outputs│
│ Matching    │   │ Geometry     │           │ Global Context│   │ (Pose+Depth+3D)│
└─────────────┘   └──────────────┘           └───────────────┘   └────────────────┘
     ↓                   ↓                          ↓                    ↓
Fragile Matches     Heavy Optimization         Robust Priors        Instant Geometry
(SIFT/SuperPoint)   (Bundle Adjustment)        Learned Attention    Feed-forward Only

Hybrid approaches:
1. Use classical SfM to bootstrap intrinsics → fine-tune with VGGT outputs
2. Combine hand-crafted geometry checks (epipolar) with learned global priors

📸 Classical SfM = Puzzle Builder with Thousands of Pieces (slow, error-prone)
🧠 VGGT = Instant Polaroid Printer that Prints 3D (fast, all-in-one)
```


<br>

`Classical SfM (Geometry-driven)`

<br>

```
Calibration
   ↓
K = [[fx, 0, px], [0, fy, py], [0,0,1]]
[R | t]
   ↓
Feature Matching (2D–2D)
   ↓
Epipolar Constraint: xᵢᵀ F xⱼ = 0
   ↓
Projection
   λ [x, y, 1]ᵀ = K [R | t] [X, Y, Z, 1]ᵀ
   ↓
Optimization (Bundle Adjustment)
   min {R,t,X} Σ ‖x − π(K,R,t,X)‖²
   ↓
Output
   • Camera poses
   • Sparse/Dense 3D point cloud
```

<br>

`VGGT (Learning-driven)`

<br>

```
Input Images
   ↓
Patch Embedding (DINO)
   ↓
Camera Tokens + Self-Attention
   ↓
Feed-forward Transformer
   ↓
Outputs (Direct Prediction)
   • Intrinsics K
   • Extrinsics [R | t]
   • Depth Maps
   • Point Maps
   • 3D Tracks
```



<br>

## Visual Computing - Coursework


<br>


| Tuesday (Topic)                                                                                                  | Thursday (Topic)                                                                               |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **Introduction to SfM** <br> Overview of Structure-from-Motion, applications in photogrammetry, robotics, AR/VR. | **The Multi-View Problem** <br> From 2D images to 3D geometry, role of camera models.          |
| **Image Features I** <br> Feature detection (SIFT, ORB).                                                         | **Image Features II** <br> Feature description and matching.                                   |
| **Epipolar Geometry** <br> Essential matrix, Fundamental matrix.                                                 | **RANSAC & Robust Estimation** <br> Outlier rejection in correspondences.                      |
| **Camera Pose Estimation I** <br> PnP problem, intrinsics vs extrinsics.                                         | **Camera Pose Estimation II** <br> Homography, motion from two views.                          |
| **Triangulation I** <br> Linear triangulation methods.                                                           | **Triangulation II** <br> Non-linear triangulation and uncertainty.                            |
| **Incremental SfM** <br> Sequential addition of cameras, growing reconstruction.                                 | **Global SfM** <br> Joint optimization across all cameras.                                     |
| **Bundle Adjustment I** <br> Definition and reprojection error.                                                  | **Bundle Adjustment II** <br> Nonlinear least squares, Levenberg–Marquardt optimization.       |
| **Sparse vs Dense Reconstruction** <br> Difference between sparse SfM and dense MVS.                             | **Multi-View Stereo (MVS)** <br> PatchMatch, depth map fusion.                                 |
| **Structure Representation** <br> Point clouds, meshes, voxel grids.                                             | **Surface Reconstruction** <br> Poisson surface reconstruction and variants.                   |
| **SfM in Practice I** <br> COLMAP basics: input images, output formats.                                          | **SfM in Practice II** <br> COLMAP visualization and debugging reconstruction.                 |
| **Limitations of Traditional SfM** <br> Drift, loop closure, scalability issues.                                 | **Robustness & Failures** <br> Low-texture scenes, repetitive patterns, robustness strategies. |
| **Extensions I: Dynamic Scenes** <br> Non-rigid SfM, motion segmentation.                                        | **Extensions II: Large-Scale SfM** <br> City-scale and aerial 3D reconstruction.               |
| **Learning-based SfM I** <br> Deep feature matching (SuperGlue, LoFTR).                                          | **Learning-based SfM II** <br> Neural reconstruction pipelines (DUSt3R, VGGT).                 |
| **Future of SfM** <br> From optimization-based to transformer-based methods.                                     | **SfM vs VGGT** <br> COLMAP vs VGGT, comparison of pros and cons.                              |


<br><br><br><br>


## References 1

<br>

**Frontiers in AI Research (2025)**


1. Efficient Multimodal Alignment & Generation  
- **Key Results**:  
  - CLIPDraw++ (NeurIPS ’24): unified vision–language alignment  
  - Video-LLaMA (ICLR ’25): zero-shot text-to-video generation  
- **Challenges**: real-time deployment, fine-grained controllability, safety/robustness

📍 2. Long-Term Temporal & Structural Consistency  
- **Key Results**:  
  - FlowFormer (CVPR ’25): flow-matching for video coherence
  - VideoMamba (25)
  - MemoryNeRF (NeurIPS ’24): implicit scene memory across seconds  
- **Opportunities**:  
  - scalable frame-level memory modules  
  - layered geometric+semantic caching  
  - dynamic scene understanding

📍 3. Self-Supervised Learning from Extreme Sparsity  
- **Key Results**:  
  - `SparseMAE (ICCV ’23): masked autoencoding with <0.1 % tokens`
  - Contrastive-Sparse (ICLR ’24): adaptive masking focus on high-entropy regions  
- **Goals**:  
  - near-fully-supervised performance with ‰-level labels  
  - unified multi-task pretraining (classification, detection, generation)

4. Differentiable Physics & Hybrid Simulation  
- **Key Results**:  
  - DiffPhys (NeurIPS ’24): end-to-end differentiable physics engine  
  - FluidNeRF (CVPR ’25): fluid simulation within NeRF framework  
- **Directions**:  
  - trainable raytracing and material modules  
  - learned+classical simulator hybrids  
  - transferable “physical basis” representations

5. Verifiable Robustness & Explainable Security  
- **Key Results**:  
  - Certified Diffusion Robustness (ICLR ’25)  
  - Provable Transformer Defenses (NeurIPS ’24)  
- **Imperatives**:  
  - certified adversarial bounds  
  - causal traceability in generation/decision chains  
  - end-to-end system-level trust guarantees

📍 **1. DiT (Diffusion Transformer)**
- **Overview**: Combines Transformer context modeling with diffusion denoising  
- **Examples**  
  1. **KeyFace** – speech-driven face animation via stepwise denoising  
  2. **DiffLocks** – high-fidelity hair generation  
  3. **Pippo** – multi-view rendering with geometric and texture coherence  
- **Benefit**: Maintains character appearance/style across shots and supports conditional, coherent animation

📍 **2. Diadic Models**
- **Concept**: Model both speaking and listening behaviors for interactive avatars  
- **Examples**  
  - **INFP** / **DualTalk**: dual-branch networks for speaker lip sync and listener micro‐expressions  
- **Insight**: Ensures consistent identity/style in extended dialogues by modeling two-way interaction

**3. Priors**
- **Synthetic Priors (GASP, SynShot)**  
  - Generate “pseudo-real” head avatars (poses, expressions, lighting) to enrich training data  
  - Improves generalization to extreme poses and rare expressions  
- **Diffusion-based Priors (CAP4D, GAF)**  
  - Use pretrained diffusion models to produce high-quality 3D avatars or dynamic sequences  
  - Accelerates multi-view/multi-expression data generation and boosts video consistency

**4. Implications**
- **Architecture**: Adopt DiT’s diffusion-Transformer for cross-scene realface rendering  
- **Interaction Consistency**: Integrate diadic modeling to handle speaking and listening coherently  
- **Memory Extension**: Add a latent memory module to preserve character traits across sessions



<br><br><br><br>


## References 2 / Reading List

<br>


[2024 - Robust Symmetry Detection via Riemannian Langevin Dynamics](https://symmetry-langevin.github.io/)


[BERT], [Wav2Vec2] - SSL, masked reconstruction, contrastive loss


<br>

## 4D

<br>

[2025 - MonST3R: A Simple Approach for Estimating Geometry in the Presence of Motion](https://monst3r-project.github.io/)


[2025 - Shape of Motion](https://shape-of-motion.github.io/)


[2025 - 4DNex](https://x.com/janusch_patas/status/1957697411591336114?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ) - 4d scene understanding


<br>


[2024 - CAT4D](https://cat-4d.github.io/) - 4d Reconstruction from video


<br><br>


## 3D

<br>


## Surgery 3D Scene

<br>

[2025 - MICCAI 2025 - SurgTPGS: Semantic 3D Surgical Scene Understanding with Text Promptable Gaussian Splatting](https://lastbasket.github.io/MICCAI-2025-SurgTPGS/)




<br>


## 3D Understanding ( / Reconstruction)

<br>

[2025 - VGGT](https://vgg-t.github.io/)

[📍 2023 - OpenScene](https://openaccess.thecvf.com/content/CVPR2023/papers/Peng_OpenScene_3D_Scene_Understanding_With_Open_Vocabularies_CVPR_2023_paper.pdf)

[📍 2024 - Segment3D](https://link.springer.com/chapter/10.1007/978-3-031-72754-2_16)

[2023 - AGILE3D](https://ywyue.github.io/AGILE3D/)

[COLMAP], [GLOMAP]


<br>


[1. Align3R: Aligned Monocular Depth Estimation for Dynamic Videos](https://openaccess.thecvf.com/content/CVPR2025/html/Lu_Align3R_Aligned_Monocular_Depth_Estimation_for_Dynamic_Videos_CVPR_2025_paper.html)


[2. Stereo4D: Learning How Things Move in 3D from Internet Stereo Videos](https://arxiv.org/abs/2412.09621)



<br><br>


## 2D

<br>

[DINOv3]

[SAM 2]


<br><br>


## Some Products

<br>

[2025 - RealityScan](https://x.com/RealityCapture_/status/1932422430967922793)

[3DV projects 2024](https://cvg.ethz.ch/lectures/3D-vision/assets/3DV_Projects_2024.pdf)

[3DV projects 2025]


<br><br><br>



