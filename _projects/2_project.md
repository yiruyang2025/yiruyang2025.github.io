---
layout: page
title: 2025 - Master Thesis
description: 3D Recontruction / Robotics Navigation
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---



<br><br><br>

[CAT-3D]

[2018 - Learning Priors for Semantic 3D Reconstruction](https://openaccess.thecvf.com/content_ECCV_2018/html/Ian_Cherabier_Learning_Priors_for_ECCV_2018_paper.html)

[2017 - Semantically Informed Multi‑view Surface Refinement](https://openaccess.thecvf.com/content_iccv_2017/html/Blaha_Semantically_Informed_Multiview_ICCV_2017_paper.html)

[2020 - Learning 3D Semantic Scene Graphs from 3D Indoor Reconstructions](https://openaccess.thecvf.com/content_CVPR_2020/html/Wald_Learning_3D_Semantic_Scene_Graphs_From_3D_Indoor_Reconstructions_CVPR_2020_paper.html)



<br><br>

**Bio Singal**

[2025 - LSM-2: Learning from Incomplete Wearable Sensor Data](https://research.google/blog/lsm-2-learning-from-incomplete-wearable-sensor-data/)




<br><br>

**Trustworthy**

[2025 - IAP: Invisible Adversarial Patch Attack through Perceptibility-Aware Localization and Perturbation Optimization](https://arxiv.org/abs/2507.06856)

<br><br>


**CV**



[2025 - VisualSpeaker](https://arxiv.org/pdf/2507.06060)

[2023 - 3DiFACE: Diffusion-based Speech-driven 3D Facial Animation and Editing](https://arxiv.org/abs/2312.00870)

[2022 - Tech helps (hopefully) - AR transcription and translation](https://x.com/Google/status/1524464030668177409)

[2025 - Eye Tracking](https://acl2025-eyetracking-and-nlp.github.io/)


<br><br>

**3D Vision**

[2025 - Oral - MaskControl: Spatio-Temporal Control for Masked Motion Synthesis](https://www.ekkasit.com/ControlMM-page/)


[2025 - EgoVLA: Learning Vision-Language-Action Models from Egocentric Human Videos](https://rchalyang.github.io/EgoVLA/)




<br><br><br>

 - [ZapBench - 2025](https://zapbench-release.storage.googleapis.com/landing.html)

 - [State Space Models](https://yiruyang2025.github.io/blog/2025/State-Spaces-Models-25/)

 - [On the Tradeoffs of SSMs and Transformers](https://goombalab.github.io/blog/2025/tradeoffs/#mamba-putting-it-all-together)

- [2025 - SnapMoGen](https://arxiv.org/abs/2507.09122)


<br><br><br>

## Topics

<br>

[Aria](https://facebookresearch.github.io/projectaria_tools/docs/tech_spec/hardware_spec)

[LEMMA - 2020](https://link.springer.com/chapter/10.1007/978-3-030-58574-7_46)

- Egocentric Vision, Intent Prediction, Anticipation, Multimodal Learning

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



