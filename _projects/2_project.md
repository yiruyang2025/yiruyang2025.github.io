---
layout: page
title: 2025 - Master Thesis
description: igl
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---

<br><br>

## 3D Reconstruction

<br>

```
Mesh-VAE World                          Implicit Geometry World
═══════════════════════════════         ══════════════════════════════════
Mold Shape   →  Fill Cream  →           Pour Batter   → Let Shape Form →  
Keep Shape   →  Adjust Icing            Implicitly Shape via Function
(Topology)      (Latent Codes)          (SDF / NeRF Fields)
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


<br><br>


| Feature               | Mesh-VAE (Explicit Representation)                                   | Implicit Geometry (e.g., NeRF, SDF)                                                                    |
| --------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Core Idea             | Encodes and decodes fixed-topology meshes (e.g., triangle meshes)    | Learns a function $f(x) \rightarrow \mathbb{R}$ describing geometry per point (e.g., SDF or occupancy) |
| Data Structure        | Explicit meshes (vertices + faces)                                   | Continuous scalar fields (implicit functions)                                                          |
| Suitable For          | Bodies, faces, organs with consistent topology                       | Arbitrary topology, volumetric shapes (e.g., furniture, animals, organic forms)                        |
| Representative Models | Mesh-VAE, CoMA, SpiralVAE, MeshDiffusion                             | DeepSDF, Occupancy Networks, NeRF, SIREN                                                               |
| Advantages            | Controllable, interpretable, easy for interpolation and registration | No need for fixed mesh, can handle varying topology and finer geometry                                 |

<br><br>

| Framework Name             | Description                                                                                       |
| -------------------------- | ------------------------------------------------------------------------------------------------- |
| Latent Shape Prior NeRF    | Mesh-VAE encodes shape into latent space, which conditions NeRF for multi-shape rendering         |
| Mesh2ImplicitNet           | Latent vector from Mesh-VAE is used as a condition input to an implicit decoder like DeepSDF      |
| MedShape VAE → ImplicitNet | Mesh-VAE builds statistical shape space for medical organs; implicit model refines geometry       |
| Surface-to-Volume Flow     | Mesh is used to generate flow fields, which are converted to implicit fields for shape completion |


<br><br>

## Tasks Matching

<br>


| Task Description                        | Recommended Method       | Reason                                                                |
| --------------------------------------- | ------------------------ | --------------------------------------------------------------------- |
| Modeling same-topology objects          | Mesh-VAE                 | Mesh connectivity is fixed and suitable for morphable structures      |
| Generating arbitrary shapes or plants   | Implicit Geometry        | Better suited for freeform, non-uniform topology                      |
| Image-to-3D with high variation         | Hybrid (Mesh + Implicit) | Mesh gives structure; NeRF/SDF adds realism and detail                |
| Medical shape modeling with priors      | Mesh-VAE + SDF           | Prior modeling with explicit structure, refined via continuous fields |
| Rigging, animation, physical simulation | Mesh-VAE                 | Per-vertex manipulation is straightforward                            |













<br><br>

## Background Knowledge

<br>

[2025 - TetWeave](https://x.com/TheGraphicsFrog/status/1920360716097274059)


[C++ lib repo - toolkit](https://github.com/libigl)

<br>

[Algorithmic Simplicity](https://www.youtube.com/@algorithmicsimplicity)

[3D Reconstruction from Images](https://www.youtube.com/watch?v=tqBD6rxiul4)

[Andreas Geiger - Deep Models for 3D Reconstruction - 2020](https://www.youtube.com/watch?v=Rfb1J3fJMYA)

<br><br>

[2023 - AGILE3D](https://arxiv.org/abs/2306.00977)

<br><br><br><br>


## Benchmark

<br><br><br><br>


## Dataset


<br><br><br><br><br>


## Research

<br><br><br>


**Stage 1 – Cross-modal alignment**

`OpenScene, CLIP space, DINOv2 space, text-3D embedding`

<br>

**Goal**

The reconstructed 3D features are no longer purely geometric but instead contain semantic information and can be aligned with modalities such as text and images. This allows the model to:

  - Easier to understand the meaning of the reconstruction results

  - Cross-modal retrieval (text → point cloud, image → mesh)

  - Supports zero-shot labeling, classification, and querying


<br>

**Stage 2 – Shape the Semantic Space**

Geometric Consistency Filtering + `3D Hough Voting` + Contrastive Learning

<br>

**Goal**

  - Semantic grouping after filtering and voting (more general than standard segmentation)
  - A semantically shape-aware structure space that can be used as a priori for Stage 3

<br>

**Stage 3 – Expand from Local → Global Shape Priors & Static → Dynamic**

`D-NeRF`

<br>

**Goal**

  - [2021 - CVPR D-NeRF: Neural Radiance Fields for Dynamic Scenes](https://openaccess.thecvf.com/content/CVPR2021/html/Pumarola_D-NeRF_Neural_Radiance_Fields_for_Dynamic_Scenes_CVPR_2021_paper.html?ref=labelbox.ghost.io)
  - [2023 - DeepLS: Local Search for Network Optimization Based on Lightweight Deep Reinforcement Learning](https://ieeexplore.ieee.org/abstract/document/10155296?casa_token=b8l78Uv-H1AAAAAA:U4ZrGd_uM2HkYEzeatrRLNIU9RPKDnyzng3i874NdXPrGdVPLDsBJgBFLWb-26OwSrxwryK7NA)

<br><br><br>

**Stage 4 – Self-Distillation for Efficiency & Real-time Inference**


`DINOv2`


<br>

**Goal**

   - Low Inference Latency
   - On-device


<br><br><br><br>

## 3D motion Generation

Most existing motion research focuses on healthy adults, while studies and data on children with impaired gait are very limited.



<br><br><br><br>

## Robotics



<br><br><br><br>




## References

<br>

[CAT-3D]

[2018 - Learning Priors for Semantic 3D Reconstruction](https://openaccess.thecvf.com/content_ECCV_2018/html/Ian_Cherabier_Learning_Priors_for_ECCV_2018_paper.html)

[2017 - Semantically Informed Multi‑view Surface Refinement](https://openaccess.thecvf.com/content_iccv_2017/html/Blaha_Semantically_Informed_Multiview_ICCV_2017_paper.html)

[2020 - Learning 3D Semantic Scene Graphs from 3D Indoor Reconstructions](https://openaccess.thecvf.com/content_CVPR_2020/html/Wald_Learning_3D_Semantic_Scene_Graphs_From_3D_Indoor_Reconstructions_CVPR_2020_paper.html)

[📍 2025 - CrossOver: 3D Scene Cross-Modal Alignment](https://openaccess.thecvf.com/content/CVPR2025/html/Sarkar_CrossOver_3D_Scene_Cross-Modal_Alignment_CVPR_2025_paper.html)

[📍 2002 - From Images to 3D Models](https://cacm.acm.org/research/from-images-to-3d-models/)

[2022 - Advancing the foundations of mixed reality](https://www.microsoft.com/en-us/research/blog/eccv-2022-highlights-advancing-the-foundations-of-mixed-reality/?OCID=msr_blog_ECCVHighlights_Lab)





<br><br>

**Trustworthy**

[2025 - IAP: Invisible Adversarial Patch Attack through Perceptibility-Aware Localization and Perturbation Optimization](https://arxiv.org/abs/2507.06856)

<br><br>


**CV**



[📍 2025 - VisualSpeaker](https://arxiv.org/pdf/2507.06060)

[2023 - 3DiFACE: Diffusion-based Speech-driven 3D Facial Animation and Editing](https://arxiv.org/abs/2312.00870)

[2022 - Tech helps (hopefully) - AR transcription and translation](https://x.com/Google/status/1524464030668177409)

[2025 - Eye Tracking](https://acl2025-eyetracking-and-nlp.github.io/)


<br><br>

**3D Vision**


[📍 2025 - AnyCam: Learning to Recover Camera Poses and Intrinsics from Casual Videos](https://openaccess.thecvf.com/content/CVPR2025/html/Wimbauer_AnyCam_Learning_to_Recover_Camera_Poses_and_Intrinsics_from_Casual_CVPR_2025_paper.html)

[2025 - Oral - MaskControl: Spatio-Temporal Control for Masked Motion Synthesis](https://www.ekkasit.com/ControlMM-page/)


[2025 - EgoVLA: Learning Vision-Language-Action Models from Egocentric Human Videos](https://rchalyang.github.io/EgoVLA/)


<br>

📍 Large multimodal models [CLIP], [DALL·E], [ALIGN]

📍 Implicit 3D representations [NeRF], [DeepSDF]


<br>

[1] Cherabier, I., Schönberger, J.L., Oswald, M.R., Pollefeys, M., Geiger, A.: Learning Priors for Semantic 3D Reconstruction. In: Proceedings of Conference on Computer Vision and Pattern Recognition (CVPR) (2018)

[2] Wang, Y., Pan, L., Pollefeys, M., Larsson, V.: Structure‑from‑Motion with a Non‑Parametric Camera Model. In: Proceedings of Conference on Computer Vision and Pattern Recognition (CVPR) (2025)

[3] Wald, J., Dhamo, H., Navab, N., Tombari, F.: Learning 3D Semantic Scene Graphs from 3D Indoor Reconstructions. In: Proceedings of International Conference on 3D Vision (3DV) (2020)

[4] Tombari, F., Di Stefano, L.: Object Recognition in 3D Scenes with Occlusions and Clutter by 📍 Hough Voting. In: Proceedings of International Conference on Computer Vision (ICCV) (2010)

[5] Peng, S., Genova, K., Jiang, C. M., Tagliasacchi, A., Pollefeys, M., Funkhouser, T.: OpenScene: 3D Scene Understanding with Open Vocabularies. In: Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR) (2023)

[6] Song, S., Yu, F., Zeng, A., Chang, A.X., Savva, M., Funkhouser, T.: Semantic Scene Completion from a Single Depth Image. In: Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR) (2017)




<br><br><br>



 - [ZapBench - 2025](https://zapbench-release.storage.googleapis.com/landing.html)

 - [State Space Models](https://yiruyang2025.github.io/blog/2025/State-Spaces-Models-25/)

 - [On the Tradeoffs of SSMs and Transformers](https://goombalab.github.io/blog/2025/tradeoffs/#mamba-putting-it-all-together)

- [2025 - SnapMoGen](https://arxiv.org/abs/2507.09122)


<br><br><br>

## Topics

<br>

- Veo3 - Deepmind
- Gen-4 - Runway
- Movie Gen - Meta
- Flow Loss

<br>


- [2023 - Flow Matching in Latent Space](https://arxiv.org/abs/2307.08698)<br>

- [2025 - Generative modelling in latent space](https://sander.ai/2025/04/15/latents.html)<br>

- [2025 - Runway Gen-4 solves AI video’s biggest problem: character consistency across scenes](https://venturebeat.com/ai/runways-gen-4-ai-solves-the-character-consistency-challenge-making-ai-filmmaking-actually-useful/?utm_source=chatgpt.com)<br>
  - 2025 - New York is a Zoo
  - 2025 - The Retrieval
<br>
- [Sparse Autoencoders - 2024 - Scaling and evaluating sparse autoencoder](https://arxiv.org/abs/2406.04093)


<br>


<br><br>

## Modules

<br>

**[Compressive Transformer]**

[Mamba], [RWKV]

[Differentiable Neural Computer]

[Sparse Access Memory]

[AlphaDev]

[Scaling 4D Representations](https://arxiv.org/pdf/2412.15212)

[Ego4D](https://ego4d-data.org/)


<br>

Causal ViViT

VQ-VAE

MaskGIT

C-ViViT 

T5X Encoder

Transformer in Latent Space

<br><br>



<br><br>


## References


<br>

- EVA-CLIP (2023), OpenCLIP (2023), CLIP-ViP (2023)
- [Multimodal Nerons in NNs](https://distill.pub/2021/multimodal-neurons/)
- LiT - 2022
- ALIGN - 2021


<br>

 
- [PaliGemma 2 - 2024](https://arxiv.org/abs/2412.03555)

- [CLIP - ICML 2021 - Learning Transferable Visual Models From Natural Language Supervision](https://arxiv.org/abs/2103.00020)

- [Multi-Layer Sparse Autoencoders - ICLR 2025](https://github.com/tim-lawson/mlsae)

- [Alpha-CLIP - CVPR 2024 - A CLIP Model Focusing on `Wherever` You Want](https://openaccess.thecvf.com/content/CVPR2024/html/Sun_Alpha-CLIP_A_CLIP_Model_Focusing_on_Wherever_You_Want_CVPR_2024_paper.html)


<br>

<br>


**Flow Matching Loss**
<br>

**Purpose**  
Enforce temporal smoothness by aligning latent representations of adjacent frames

**Definition**

$$
\mathcal{L}_{\mathrm{flow}} = \bigl\lVert z_{t+1} - \mathrm{warp}(z_t, f_{t\to t+1}) \bigr\rVert_{1}
$$

- $z_t, z_{t+1}$: latent features of frame $t$ and frame $t+1$
- $\mathrm{warp}(z_t, f_{t \to t+1})$: features $z_t$ warped by the predicted flow field $f_{t \to t+1}$ 
- $f_{t \to t+1}$: optical flow field predicted by a lightweight network

<br>

- **Domain**  
  - Flow Matching applies to video frames (temporal consistency)

- **Alignment Target**  
  - Flow Matching aligns adjacent frames’ latent features 

- **Warping Operation**  
  - Flow Matching includes a warp based on optical flow

- **Goal**  
  - Flow Matching improves frame-to-frame coherence in generated video



<br>

**Total Loss**

$$
\mathcal{L}_{\mathrm{flow}} = \bigl\lVert z_{t+1} - \mathrm{warp}(z_t, f_{t\to t+1}) \bigr\rVert_{1}
$$

<br><br>

## References

<br>

**Frontiers in AI Research (2025)**

<br>

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

<br>

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


<br><br>

<br><br><br>



