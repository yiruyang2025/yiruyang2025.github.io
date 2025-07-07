---
layout: page
title: 2025 - Master Thesis
description: Spatiotemporal Modeling + On-device
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---

<br>


A Lightweight Pre-trained Model

Spatiotemporal Modeling / Neural Activity Prediciton via Extreme Sparse Modeling

<br>


 - [ZapBench - 2025](https://zapbench-release.storage.googleapis.com/landing.html)

 - [State Space Models](https://yiruyang2025.github.io/blog/2025/State-Spaces-Models-25/)


<br>

**Hypothesis**

Sometimes `Geometric dimensionality reduction` may help more than compression / sparsity

<br>

```
Short-term memory ──▶ Attention ──▶ Hidden activation h
│
▼
Manifold mapping (Hypersphere)
│
▼
Riemann P-PCA dimensionality reduction (R-PCA)
│
▼
Compressed memory ←— Quantization (Sphere PQ)
```



<br>

Sometimes Geometry is so elegant in the AI domain

<br><br>

`[Compressive Transformer]`

[Differentiable Neural Computer]

[Sparse Access Memory]

[AlphaDev]

[Ego4D](https://ego4d-data.org/)

[realtime track, e.g. locate your pet](https://docs.xreal.com/Sample%20Code)


<br><br>



## References

<br>

[1 - 2014 - Neural Networks, Manifolds, and Topology](https://colah.github.io/posts/2014-03-NN-Manifolds-Topology/)

[2 - 2015 - Understanding LSTM Networks](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)

<br>

- EVA-CLIP (2023), OpenCLIP (2023), CLIP-ViP (2023)
- [Multimodal Nerons in NNs](https://distill.pub/2021/multimodal-neurons/)
- LiT - 2022
- ALIGN - 2021


<br>


## Topics

1. Multimodal Alignment

   - `cross-attention`
   - `contrastive learning`
   - `CLIP - ViT + Transformer`

2. Extreme Sparsity Self-Supervised Learning

   - `Sparse Autoencoder`
   - `Masked Autoencoders - MAE` - [CVPR 2022 - Masked Autoencoders Are Scalable Vision Learners](https://openaccess.thecvf.com/content/CVPR2022/html/He_Masked_Autoencoders_Are_Scalable_Vision_Learners_CVPR_2022_paper)
   - `Extreme Sparsity`


<br>

```
┌─────────────────────────────────────────┐
│ 🏝️ Each position is an isolated island  │
│                                         │
│  [·] [·] [·] [·]  ← Only sees itself    │
│  [·] [X] [·] [·]  ← No spatial context  │
│  [·] [·] [·] [·]  ← Pure local view     │
│  [·] [·] [·] [·]                        │
│                                         │
│  output[i,j] = X[i,j]                   │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────┐
│ 🌊 Information flows like rivers in all directions              │
│                                                                 │
│    ←←←← LR Flow (Left→Right)                                    │
│    ↑ ┌─→─→─→─→─┐ ↑                                              │
│    ↑ │ 🌊 [X] 🌊 │ ↑  ← Center aggregates from ALL directions    │
│    ↑ └─←─←─←─←─┘ ↑                                              │
│    ↑     ↓↓↓↓     ↑                                             │
│    TB Flow    BT Flow                                           │
│  (Top→Bot)  (Bot→Top)                                           │
│              ↓                                                  │
│  LR[i,j] = scan_LR(X)[i,j]    # ←←← Accumulate left history     │
│  RL[i,j] = scan_RL(X)[i,j]    # →→→ Accumulate right history    │
│  TB[i,j] = scan_TB(X)[i,j]    # ↑↑↑ Accumulate top history      │
│  BT[i,j] = scan_BT(X)[i,j]    # ↓↓↓ Accumulate bottom history   │
│                                                                 │
│  output[i,j] = LR + RL + TB + BT  # 🌊 River confluence         │
└─────────────────────────────────────────────────────────────────┘

🐌 Global Attention: O((H·W)²) - Every pixel talks to every pixel
   ┌──────────────────────────────────────────────────────────┐
   │ 💬 Chatty pixels: 64×64 = 4,096 → 16,777,216 connections │
   └──────────────────────────────────────────────────────────┘

🚀 Mamba Scans: O(H·W) - Linear recurrence per direction
   ┌─────────────────────────────────────────────────────────┐
   │ 🌊 River flows: 64×64 = 4,096 → 4,096 × 4 = 16,384 ops  │
   └─────────────────────────────────────────────────────────┘

🌊 Four Rivers Converge into One Mighty Stream:

     ←←←LR←←←
        ↑
    ↑   |   ↓
    TB [🎯] BT  → Full Spatial Awareness
    ↑   |   ↓
        ↓
     →→→RL→→→

Each position becomes a confluence point where all directional 
information streams meet, creating complete spatial understanding
with linear computational cost! 🌊⚡
```







<br><br>

## References

`1. Spatiotemporal Video Encoding`

- Feichtenhofer, C., Fan, H., Malik, J., & `He, K`. “SlowFast Networks for Video Recognition.” CVPR 2019.

- Capture both spatial detail (handshape, body posture) and temporal dynamics (movement trajectories)
- Common backbones include ViViT- or TimeSformer-style vision Transformers and 3D CNNs such as SlowFast or MViT

`2. Pose & Keypoint Extraction`

- Cao, Z., Hidalgo Martinez, G., Simon, T., Wei, S.-E., & Sheikh, Y. “OpenPose: Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields.” CVPR 2017.

- Real-time sign recognition often begins by detecting hand and body keypoints with tools like MediaPipe or OpenPose
- These skeletal sequences are then encoded by Graph Convolutional Networks (GCNs) or lightweight Transformers, reducing raw‐pixel complexity

📍 `3. Multimodal Alignment & Fusion` 

- Transformer, ViLBERT

- Aligning visual signals (hand motion, appearance) with text tokens relies on robust cross-attention mechanisms
- Architectures employ encoder–decoder attention, co-attention blocks, and both early- and late-fusion strategies to integrate vision and language features

`4. Low-Latency Decoding` - `CTC + RNN-Transducer`📍 

- Graves, A., Fernández, S., Gomez, F., & Schmidhuber, J. “Connectionist Temporal Classification: Labelling Unsegmented Sequence Data with Recurrent Neural Networks.” ICML 2006. - **CTC**

- Graves, A. “Sequence Transduction with Recurrent Neural Networks.” ICASSP 2012. - **RNN-T**

- For interactive translation, non-autoregressive decoders such as CTC or RNN-Transducer enable single-pass inference
- Understanding the trade-offs between greedy decoding and beam search is essential for minimizing latency under resource constraints

`5. Adapter & Distillation Methods` 
- The Gemma family uses adapter modules to fine-tune large models with minimal overhead. Techniques like LoRA, prefix-tuning, and adapter fusion inject low-rank updates into fixed backbones
- Cross-modal distillation—combining KL divergence on output distributions with hidden-state alignment—transfers knowledge from teacher to student efficiently

`6. Quantization & On-Device Compression`  
- SignGemma targets mobile and edge deployment, requiring post-training quantization (8-bit, 4-bit), mixed-precision (FP16/BF16), and optimized transformer kernels (e.g., FlashAttention)
- Mastery of these methods ensures model size and compute footprint fit constrained hardware

`7. Multilingual & 📍 Zero-Shot Transfer` 

- mBERT（Multilingual BERT），Devlin et al. “BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding.” NAACL 2019.

- Supporting multiple sign languages (e.g., ASL, BSL) demands domain adaptation strategies
- Key approaches include multilingual pre-training, adapter-based language extension, and contrastive video–text learning to enable zero-shot transfer across language variants


<br>

- [2025 - Simplifying DINO via Coding Rate Regularization](https://arxiv.org/abs/2502.10385)

- [**Text-to-Image Diffusion Models** are Zero-Shot Video Generators](https://github.com/Picsart-AI-Research/Text2Video-Zero)
   - Latent Memory Module

<br>
 
- [PaliGemma 2 - 2024](https://arxiv.org/abs/2412.03555)

- [📍 CLIP - ICML 2021 - Learning Transferable Visual Models From Natural Language Supervision](https://arxiv.org/abs/2103.00020)

- [Multi-Layer Sparse Autoencoders - ICLR 2025](https://github.com/tim-lawson/mlsae)

- [📍 Alpha-CLIP - CVPR 2024 - A CLIP Model Focusing on `Wherever` You Want](https://openaccess.thecvf.com/content/CVPR2024/html/Sun_Alpha-CLIP_A_CLIP_Model_Focusing_on_Wherever_You_Want_CVPR_2024_paper.html)



<br>

- Veo3 - Deepmind
- Gen-4 - Runway
- Movie Gen - Meta
- Flow Loss


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
  - `SparseMAE (ICCV ’23): masked autoencoding with <0.1 % tokens` 📍 
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

`CLIP`

```
[Input Image (224×224×3)] → [Vision Encoder: ViT-B/32 or RN50] → [Image Features (512)]
         ↓                                                              ↓
[Resize + CenterCrop]                                        [Layer Normalization]
         ↓                                                              ↓
[ToTensor + Normalize]                                       [Linear Projection Matrix]
         ↓                                                              ↓
[CLIP Transform Pipeline]                                    [L2 Normalization]
                                                                       ↓
                                          [InfoNCE Loss with Learnable Temperature]
                                                    ↑           ↓
                                        [torch.matmul(I_f, T_f.T) * exp(τ)]
                                                    ↑
[Input Text (max 77 tokens)] → [Text Encoder: Transformer] → [Text Features (512)]
         ↓                                                              ↓
[ftfy.fix_text() + html.unescape()]                         [Layer Normalization]
         ↓                                                              ↓
[BPE Tokenization (49152 vocab)]                            [Linear Projection Matrix]
         ↓                                                              ↓
[Add [SOS]/[EOS] tokens + Pad]                             [L2 Normalization]
```






<br><br>

`High-Level Topics`


```
Cross-Modal Alignment
├── Core Architectures
│   ├── Dual-Encoder Model
│   │   └─ CLIP (Contrastive Language–Image Pre-training)  
│   ├── Multimodal Transformers
│   │   └─ ViLBERT, UNITER, FLAVA, Florence  
│   ├── Co-Attention Networks
│   │   └─ VisualBERT, LXMERT  
│   └── Graph-Based Alignment
│       └─ MMG (Multimodal Graph), VLP-GNN  
│
├── Pretraining & Losses
│   ├── Contrastive Learning  
│   │   └─ InfoNCE, LoCL, SLiC (Hard Negative Mining)  
│   ├── Masked Multimodal Modeling  
│   │   └─ VideoMAE+Text, MM-BEiT  
│   ├── Image–Text Matching (ITM) 
│   │   └─ alignment head + triplet loss  
│   └── Cross-Modal Distillation  
│       └─ CLIP Distill, Florence→TinyFlorence  
│
├── Attention Mechanisms
│   ├── Cross-Attention 
│   ├── Co-Attention 
│   ├── Hierarchical Attention 
│   └── Efficient Attention 
│       └─ Performer, Linformer, FlashAttention  
│
├── Advanced Techniques
│   ├── Adapter & Prefix-Tuning
│   │   └─ LoRA, AdapterFusion  
│   ├── Prompt-Based Alignment 
│   │   └─ CoOp, MaPLe  
│   ├── Multimodal Fusion Strategies
│   │   └─ Early-Fusion / Late-Fusion / Joint-Fusion  
│   └── Self-Supervised Alignmen  
│       └─ SLIP, CLIP-style Vision–Speech, VideoCLIP  
│
└── Optimization & Deployment
    ├── Model Compression
    │   └─ Quantization, Pruning, Knowledge Distillation  
    ├── Hardware Acceleratio  
    │   └─ TensorRT, ONNX-Runtime, FlashAttention  
    ├── Real-time Inference  
    │   └─ Streamable Cross-Attention, Low-Latency Decoding  
    └── Edge & On-Device 
        └─ TFLite, PyTorch Mobile, CoreML
```

<br>

```
Spatiotemporal Modeling
├── Core Architectures
│   ├── 3D CNNs
│   ├── Video Transformers
│   ├── Graph Neural Networks
│   └── Hybrid Models
├── Attention Mechanisms 
│   ├── Temporal Attention 
│   ├── Spatial Attention 
│   ├── Cross-Modal Attention
│   └── Efficient Attention
├── Advanced Techniques 
│   ├── Neural Radiance Fields 
│   ├── Flow-based Methods 
│   ├── Memory Networks
│   └── State Space Models
└── Optimization & Deployment 
    ├── Model Compression 
    ├── Hardware Acceleration
    ├── Real-time Processing 
    └── Edge Computing
```

<br><br>

- [2023 - Flow Matching in Latent Space](https://arxiv.org/abs/2307.08698)<br>

- [2025 - Generative modelling in latent space](https://sander.ai/2025/04/15/latents.html)<br>

- [2025 - Runway Gen-4 solves AI video’s biggest problem: character consistency across scenes](https://venturebeat.com/ai/runways-gen-4-ai-solves-the-character-consistency-challenge-making-ai-filmmaking-actually-useful/?utm_source=chatgpt.com)<br>
  - 2025 - New York is a Zoo
  - 2025 - The Retrieval
 
- [Sparse Autoencoders - 2024 - Scaling and evaluating sparse autoencoder](https://arxiv.org/abs/2406.04093)



<br><br>



<br><br><br>

