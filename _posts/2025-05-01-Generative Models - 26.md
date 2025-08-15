---
layout: post
title: Generative Models - 26
date: 2025-05-01
description: 🔹
categories: AI/ML
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---


Welcome,

Let's take a look at the history of Generative Models for Science<br><br><br><br>



# 1. References<br><br>

**1.1** 2024 [NeurlPS tutorial - Flow Matching for Generative Modeling](https://neurips.cc/virtual/2024/tutorial/99531) x [2024 Flow Matching Guide and Code](https://arxiv.org/abs/2412.06264)<br><br>

**1.2**  2023 [Generative Models: An Interdisciplinary Perspective](https://www.annualreviews.org/content/journals/10.1146/annurev-statistics-033121-110134)<br><br>

**1.3**  2021 [Deep Generative Modelling: A Comparative Review of VAEs, GANs, Normalizing Flows, Energy-Based and Autoregressive Models](https://ieeexplore.ieee.org/abstract/document/9555209)<br><br><br><br>



# 2. Optical Experiments Simulation by Diffusion Models<br><br>

**2.1** 2025 [Tunable Optimally-Coded Snapshot Hyperspectral Imaging for Scene Adaptation](https://onlinelibrary.wiley.com/doi/full/10.1002/lpor.202401921?casa_token=b1RPYQ5X85cAAAAA%3ArCeurTg2UnYi-G88T2esLaRmKlHEJdMUywn0UROqVcD1xfZ5jpQTUYlLrIVm97A2wojMePyxuO2fcLc)<br><br>

**2.2** 2023 [Binarized Spectral Compressive Imaging](https://proceedings.neurips.cc/paper_files/paper/2023/hash/788e086c07b8d6fa6b279df56e512312-Abstract-Conference.html)<br><br>

**2.3** 2022 [Mask-Guided Spectral-Wise Transformer for Efficient Hyperspectral Image Reconstruction](https://openaccess.thecvf.com/content/CVPR2022/html/Cai_Mask-Guided_Spectral-Wise_Transformer_for_Efficient_Hyperspectral_Image_Reconstruction_CVPR_2022_paper.html)<br><br><br><br>




# 3. Technical History of Today’s GenAI Models<br><br><br><br>




# 4. A Coding Sample from NeurlPS 2023 - Binarized Spectral Compressive Imaging<br><br>

**4.1 The Github Project** [A Toolbox for Binarized Spectral Compressive Imaging](https://github.com/caiyuanhao1998/BiSCI)<br><br><br><br>


## 5. Others


## Topics

<br>

**1. Multimodal Alignment**

   - `cross-attention`
   - `contrastive learning`
   - `CLIP - ViT + Transformer`

<br>

**2. Extreme Sparsity Self-Supervised Learning**

   - `Sparse Autoencoder`
   - `Masked Autoencoders - MAE` - [CVPR 2022 - Masked Autoencoders Are Scalable Vision Learners](https://openaccess.thecvf.com/content/CVPR2022/html/He_Masked_Autoencoders_Are_Scalable_Vision_Learners_CVPR_2022_paper)
   - `Extreme Sparsity`


<br>

```
Global Attention: O((H·W)²) - Every pixel talks to every pixel
Mamba Scans: O(H·W) - Linear recurrence per direction
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


 
<br><br><br><br>




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


<br><br><br><br>






