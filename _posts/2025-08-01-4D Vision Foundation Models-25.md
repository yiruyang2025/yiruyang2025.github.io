---
layout: post
title: 4D Vision Foundation Models - 25
date: 2025-08-01
description: ⛺️
categories: Research
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---

<br>

## Topics

<br>

`Artificial Neural Networks`

<br>

[Colah's Blog](https://colah.github.io/)


<br><br>

`3D Vision & Multi-modality x Foundation Models`

<br>

## References

<br><br>

[2025 - FAM-HRI: Foundation-Model Assisted Multi-Modal Human-Robot Interaction Combining Gaze and Speech](https://arxiv.org/pdf/2503.16492)




<br><br><br>




| Model                          | Input Data Type   | Domain     | Extendable to 3D?                                                     |
| ------------------------------ | ----------------- | ---------- | --------------------------------------------------------------------- |
| `DINOv2`                     | 2D image          | 2D CV      | Yes — Can serve as a visual token encoder for NeRF or 3D Transformers |
| **Grounding DINO**             | 2D image + text   | 2D CV      | No — Not natively designed for 3D bounding boxes                      |
| `SAM2`(Segment Anything 2)  | 2D image          | 2D CV      | Yes — Extendable to video segmentation and can integrate depth        |
| Segment Anything 3D | Point cloud + RGB | 3D Vision  | Yes — Native 3D segmentation model                                    |
| `OpenScene / OpenMask3D`     | RGB + depth       | 3D + 2D CV | Yes — Multimodal cross-domain visual perception                       |


<br><br>


| Application Task                              | Model Type          | Recommended Models                                            |
| --------------------------------------------- | ------------------- | ------------------------------------------------------------- |
| `Eye Gaze + Image Analysis (e.g., FAM-HRI)`     | **2D CV**           | DINOv2 / SAM2 / Grounding DINO                                |
| Pick-and-Place Robot Manipulation             | **2D → 3D Hybrid**  | CV-based 2D mask projected into 3D (e.g., SAM2 + RGB-D depth) |
| 3D Reconstruction / Point Cloud Segmentation  | **3DV**             | PointNeXt, Point-BERT, OpenScene                              |
| `AR Glasses + Real-Time Semantic Understanding` | **Primarily 2D CV** | SAM2 + DINOv2 + GPT (e.g., FAM-HRI stack)                     |
| SLAM / Robot Navigation                       | **Strictly 3DV**    | ORB-SLAM3, MapTR, NeRF, MVSNet                                |



<br><br><br><br>


## References

<br><br>




**1. Collatz Conjecture / 3n + 1 problem / hailstone problem**

<br>

[1950 - Lothar Collatz “Über die Differenzengleichung xₙ₊₁ = aₙ xₙ + bₙ”, Mathematische Nachrichten, Bd. 3 (1950).](https://www.digizeitschriften.de/search?filter%5BZeitschriften%5D%5B1%5D=245319514%7Clog1&filter%5BObjekttyp%5D%5B1%5D=volume)

[2003 - The 3x+1 problem: An annotated bibliography (1963--1999) (sorted by author)](https://arxiv.org/abs/math/0309224)

[2017 - Collatz Conjecture in Color - Numberphile](https://www.youtube.com/watch?v=LqKpkdRRLZw)

<br><br>

**2.📍📍 Erwin: A Tree-based Hierarchical Transformer for Large-scale Physical Systems [ICML'25]**

[repo](https://github.com/maxxxzdn/erwin)




<br><br>

**3. Self-Distillation Loss + Diffusion Loss**

```
Representation Robustness  ←─── TRADE‑OFF ───→  Training Efficiency & Reuse
          ▲                                         ▲
          │                                         │
  Self‑Distillation Loss                 Pretrained Priors (Stable Diffusion, DINOv2)
  • Enforces invariance across           • Inject rich 2D visual semantics
    views/augmentations                  • Accelerate convergence, improve transfer
  • Stabilizes training dynamics
          │                                         │
          ▼                                         ▼
                  Diffusion Loss (Denoising Objective)
        • Learn to reverse a noise process on 3D data (e.g., point clouds)
        • Yields generative and noise‑robust latent features
          │                                               │
          └──────────── PROPOSED INTEGRATION ─────────────┘
                               │
                               ▼
                 Unified, High‑Quality 3D Latent Space
     → Better downstream performance (classification, segmentation, reconstruction)
     → Strong generalization from 2D/3D synergy
```


<br><br>

**3**

<br><br>

**4**

<br><br>

**5**



<br><br><br><br>




`Articles`

<br>

[2024 - nGPT: Normalized Transformer with Representation Learning on the Hypersphere](https://arxiv.org/abs/2410.01131)

[2021 - Multimodal Neurons in Artificial NNs](https://distill.pub/2021/multimodal-neurons/)

[2018 - The Building Blocks of Interpretability](https://distill.pub/2018/building-blocks/)

[2008 - Kernel methods in machine learning](https://projecteuclid.org/journals/annals-of-statistics/volume-36/issue-3/Kernel-methods-in-machine-learning/10.1214/009053607000000677.full)



<br><br><br>






## References


**1. Contrastive Loss**

[1993 NIPS - Signature Verification using a “Siamese” Time Delay Neural Network](https://proceedings.neurips.cc/paper/1993/hash/288cc0ff022877bd3df94bc9360b9c5d-Abstract.html)

[2006 CVPR - Dimensionality Reduction by Learning an Invariant Mapping](https://ieeexplore.ieee.org/document/1640964)




**Implementations**

[CLIP]  
[DALL·E 3]


<br><br>


**2. Fusion**


[2011 - Multimodal Deep Learning](https://d1wqtxts1xzle7.cloudfront.net/74090107/icml11-MultimodalDeepLearning-libre.pdf?1635868597=&response-content-disposition=inline%3B+filename%3DMultimodal_deep_learning.pdf&Expires=1752407377&Signature=Oq6xDECIppt4tyqVPOPbxUz2Tp6hPlMk7oSIG4~iwiJ6pONeoF6RzJgaLcquZ14DamAru-WXhiwiuOyeRaQtbzcohkXJBlxW1MEyJH7vinRGVk8otM2Arv0j00DWw3jv~lcZ1m5VkMhPMNZC69dxrzKYF94I8TsLiQZhuMeJ9K0v1fC6yy5vxpo2y0TB0Xy1AEc~YX2vLqEAEWYmJCdhi16UH1v0T38etc12g1I-olQvpcevbh-IW9jwpxzdnLbJgXh-~Fs2kKr31G-q~1XsDrK302ywvQicxDKDxDmFg-xKLXrCrYfkwwZ4z~wQDaCmFDJrUvCCkrvFgbJk4hT9sQ__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA)


[2019 - ViLBERT: Pretraining Task-Agnostic Visiolinguistic Representations](https://arxiv.org/abs/1908.02265)


[2019 - UNITER: UNiversal Image-TExt Representation Learning](https://arxiv.org/abs/1909.11740)


<br><br><br><br>


## The Topic

<br>


```
**Self-Distillation + Diffusion**
    ↓
[ 3D Diffusion Network ]
    ←— combine point‑cloud denoising loss with DINOv2‑style self‑distillation loss
    ↓
Enhanced 3D features

**2D → 3D Distillation**
    ↓
[ Multi‑View 2D Encoder (Stable Diffusion / DINOv2) ]
    ↓
[ Feature Projection & Distillation ]
    ←— align 2D features to 3D points via multi‑view correspondences
    ↓
3D backbone embeddings

**Overall Goal**
    ↓
[ Unified 3D Representation ]
    ←— fuses high‑fidelity geometry (diffusion) + strong discriminative cues (distillation)
```


<br>

`Explore 3D Representation Learning by -> Combining Self-Distillation Loss + Diffusion Loss`


<br>

**DINOv2**

- **Hybrid discriminative objective based on DINO + iBOT**
  - Image-level (DINO) - Two networks (student, teacher) process different strong/weak enhancements of the same image, similar to the "prototype classification" cross entropy loss on the [CLS] token
  - Patch-level (iBOT) - The student inputs a masked patch to predict the corresponding unmasked patch of the teacher. Similar to Masked Image Modeling (MIM), it also uses classification-based prototype alignment

 <br>
 
- **KoLeo regularization**
  - The logarithmic penalty of the minimum adjacent distance within the batch encourages features to be evenly spread on the sphere

<br>

- **Training a large model and then distilling**
  - First, use ViT‑g/14 (student–teacher architecture) with 1B parameters to self-supervise a large number of iterations on 142M images
  - Then distill the small models (ViT‑L, ViT‑B, ViT‑S) from the large model - use the same DINO objective, but replace the teacher with a frozen large ViT‑g, and train the student from scratch, which is fast and low-cost

<br>

-> Relying solely on self-supervised pre-training, can obtain general, out-of-the-box visual features that are on par with or better than large-scale weak supervision (such as CLIP)

<br>

**Goals**


- **Why pre-train 3D representations?**
  - `Goal` - Before 3D downstream tasks (such as segmentation, classification, and registration), let the model be trained on large-scale unlabeled point clouds to obtain universal and robust feature representations.

  - `Challenges` - Point clouds do not have natural pixel grids like images, but are more sparse and disordered, requiring special network structures (PointNet, Point Transformer...) and task design.

<br>

- **Self-Distillation's "Representation Learning" Advantages**
  - Principle - Let the model act as both a "teacher" and a "student" at the same time, aligning features with each other through different augmented views (or different model branches)
  - Effect - Methods such as DINOv2 can learn very discriminative features for downstream segmentation/classification, and do not rely on labels
 
<br>

- **Diffusion Loss' "Generative" Advantages**
  - Principle - Gradually add noise to the unlabeled point cloud during the training phase, and then let the network learn to denoise at each noise level. The loss is generally the mean square error between the predicted noise and the real noise
  - Effect - The network learns both global and local "generative capabilities" and can capture high-fidelity distribution details

<br>

**Improve 3D Pretraining Strategies by Combining Self-Distillation & Diffusion Losses**

- Combine the representation learning strengths of self-distillation models—such as DINOv2, which excels at segmentation and classification—with the high-fidelity feature capabilities of current generative diffusion models
- Begin by fine-tuning a 3D point cloud diffusion model (e.g., PointDif) and integrating self-distillation losses inspired by DINOv2, or contrastive-like regularizers as introduced in Diffuse and Disperse
- Then analyze the impact of these representation-enhancing losses on downstream tasks such as 3D segmentation and 3D classification



<br><br>


## Possible Improvements


[2025 - Efficient Distillation of Classifier-Free Guidance using Adapters](https://arxiv.org/abs/2503.07274)

- `1. A More Efficient Self-Distillation`
  - Freeze the backbone: keep the original diffusion model (or self-distillation model) parameter θ unchanged
  - Insert lightweight adapter: add a small trainable module ψ after the key layer (such as Transformer's attention block, PointNet's MLP block, etc.)
  - Single forward simulated self-distillation: Adapter learns to approximate the "teacher model + guidance mechanism" (in AGD, it simulates Classifier-Free Guidance), so that reasoning only needs one forward pass, which can simultaneously retain the generation function and distillation signal

<br>

 [2022 - Flow Matching for Generative Modeling](https://arxiv.org/abs/2210.02747)
 
- `2. Flow Matching Loss` vs. Diffusion Loss
  - **Advantages**
  - More stable convergence and fewer iterations: No longer fighting against noise randomness, FlowMatching often converges faster than ScoreMatching/DDPM
  - Fast sampling: Especially if you choose the OT path, you can generate samples with dozens of forward passes, which can theoretically reduce the number of inference steps by half or more
  - **Challenges**
  - Complexity of velocity field design: To achieve accurate mapping and ODE integration on unordered point clouds, additional engineering is required
  - Existing library support: Most 3D diffusion frameworks only implement random diffusion. To change to ODE, you need to connect to torchdiffeq or similar components yourself


<br><br>


## References 1


<br>

[2025 - How I Understand Flow Matching](https://www.youtube.com/watch?v=DDq_pIfHqLs)

[Flow Matching - GIF](https://x.com/mathusmassias/status/1935246909473521829?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ)


[2015 - U-Net](https://link.springer.com/chapter/10.1007/978-3-319-24574-4_28)

[1] DINOv2: Learning robust visual features without supervision, Oquab et al. TMLR 2023

[2] High-resolution image synthesis with latent diffusion models, Rombach et al. CVPR 2022

[3] Point Cloud Pre-training with Diffusion Models, Zheng et al. CVPR 2024

[4] Diffuse and Disperse, Wang et al. ArXiv 2025

[5] A Tale of Two Features: Stable Diffusion Complements DINO for Zero-Shot Semantic Correspondence, Zhang et al. NeurIPS 2023

[6] 3D Scene Understanding with Open Vocabularies, Peng at al. CVPR 2023

[7] Harnessing Text-to-Image Diffusion Models for Point Cloud Self-Supervised Learning, Chen et al. ArXiv 2025


<br><br>


## References 2

<br><br>

[2015 - U-Net: Convolutional Networks for Biomedical Image Segmentation](https://arxiv.org/abs/1505.04597)

[2016 - V-Net: Fully Convolutional Neural Networks for Volumetric Medical Image Segmentation](https://arxiv.org/abs/1606.04797)

[2020 - nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation](https://www.nature.com/articles/s41592-020-01008-z)

[2021 - TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation](https://arxiv.org/abs/2102.04306)

[2021 - UNETR: Transformers for 3D Medical Image Segmentation](https://arxiv.org/abs/2103.10504)


<br><br>




<br><br><br><br><br><br><br>



## Some other topics

Masked Flow Matching for Real-Time Signal Processing

[2010 - Meta-learning for time series forecasting and forecast combination](https://www.sciencedirect.com/science/article/pii/S0925231210001074?casa_token=eu0V3jGb8eIAAAAA:haVDZz9weP60Wt5smAtoHOmf0YEq8r8PPyf7BPNNaf6wLATzcWteTR6Vaqdda_6ipjyELg1YLs23)


**Backbone: Masked Flow Matching + Bayesian Layers**  
– Variational analogs of convolutional/fully-connected layers (e.g. `DenseVariational`, `BayesianLinear`)  
– Weights modeled by variational distribution $q(w)$  

<br>

**ELBO Loss**  
Minimize the negative Evidence Lower Bound:  

$$
\mathcal{L}_{\mathrm{ELBO}}(\theta, \phi)
=
\underbrace{\mathbb{E}_{w\sim q_\phi(w)}\bigl[\ell\bigl(f_w(x),\,y\bigr)\bigr]}_{\displaystyle\text{（1）Expected data loss}}
\;+\;
\underbrace{\lambda\;\mathrm{KL}\bigl(q_\phi(w)\,\|\,p(w)\bigr)}_{\displaystyle\text{（2）Variational Regularization}}
$$

<br>

**Inference via Weight Sampling**  
Perform $T$ stochastic forward passes with $w_t \sim q(w)$, then compute:  
$$
\mu(x) \;=\; \frac{1}{T}\sum_{t=1}^T f_{w_t}(x),
\quad
\sigma^2(x) \;=\; \frac{1}{T}\sum_{t=1}^T\bigl(f_{w_t}(x) - \mu(x)\bigr)^2
$$  

<br><br>

**Decision Making**  
If $\sigma(x) > \tau$, trigger a fallback or alert


<br><br>

## References

- Bayesian Neural Nets / BNN


<br><br><br><br>

`Study Notes`

<br>

**nGPT vs. Mamba**

```
Deep Learning Training Challenge
─────────────────────────────────────────────────────────────────
Training Efficiency (Steps)  ←──── TRADEOFF ────→  Architecture Complexity
        │                                                      │
        ▼                                                      ▼
Simple architectures:                              Complex architectures:
Fast convergence but                               Slow convergence, needs
limited performance                                warmup, weight decay, etc.
        │                                                      │
        └─────────────── nGPT SOLUTION ────────────────────────┘
                                    │
                                    ▼
                        Hypersphere Geometry
                    4-20x faster training + architectural elegance
```


```
Sequence Processing Challenge  
───────────────────────────────────────────────────────────────
Computational Efficiency     ←──── TRADEOFF ────→    Context Understanding
        │                                                    │
        ▼                                                    ▼
RNNs: O(n) complexity                              Transformers: O(n²) complexity
Sequential processing                               Parallel processing
Limited context window                             Global attention
        │                                                     │
        └──────────────── MAMBA SOLUTION ─────────────────────┘
                                    │
                                    ▼
                          Selective State Space
                    O(n) complexity + global understanding
```


<br>






**nGPT - Training Optimization**

```
Solution: Mathematical reinterpretation
├── Transformer = Hypersphere optimizer
├── Normalization = Geometric constraints
└── Updates = Spherical interpolation
```



<br>


**Mamba - Inference Efficiency**

```
Solution: Architectural paradigm shift
├── Attention mechanism → State space model
├── Parallel computation → Selective recursion
└── Global perception → Compressed memory
```


<br><br>

## "2020 - System Design Interview An Insider’s Guide" - Alex Xu - Ver_1.0

<br>

[2024 - A Beginner’s Guide to System Design](https://medium.com/@sentalkssane/a-beginners-guide-to-system-design-76d64689788b)

<br>

**Common Data Capacity Units (Power-of-Two Table)**

```
| Unit Symbol | Name     | Definition                          | Exact Bytes         | Decimal Approximation |
| ----------- | -------- | ----------------------------------- | ------------------- | --------------------- |
| bit         | bit      | a single binary digit               | 1 bit               | —                     |
| B           | byte     | 8 bits                              | 8 bits              | —                     |
| KiB         | kibibyte | 2¹⁰ bytes = 1 024 bytes             | 1 024 B             | ≈ 1.02 KB (10³)       |
| MiB         | mebibyte | 2²⁰ bytes = 1 048 576 bytes         | 1 048 576 B         | ≈ 1.05 MB (10⁶)       |
| GiB         | gibibyte | 2³⁰ bytes = 1 073 741 824 bytes     | 1 073 741 824 B     | ≈ 1.07 GB (10⁹)       |
| TiB         | tebibyte | 2⁴⁰ bytes = 1 099 511 627 776 bytes | 1 099 511 627 776 B | ≈ 1.10 TB (10¹²)      |
```



<br><br><br>


<img width="468" height="645" alt="image" src="https://github.com/user-attachments/assets/0b781de2-7e00-4695-9b64-ef0b4b6ea62e" />
