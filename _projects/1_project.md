---
layout: page
title: 2025 - Thesis - Deep Learning
description: nGPT, AI Center
img: assets/img/4.jpg
importance: 1
category: work
related_publications: true
---

<br>

## 📍 Main Goal - Learning by Training

<br>

 - [1/2] Stabilizing the Training, Hidden Space Alignment via Feature Map
   - [2024 - nGPT](https://arxiv.org/html/2410.01131v1)
   - [📍 2025 - Why Stacking Sliding Windows Can't See Very Far](https://guangxuanx.com/blog/stacking-swa.html)

<br>

 - [2/2] Training Loss with different training set amounts
    - [TAID](https://iclr.cc/virtual/2025/poster/29025)
    - [What a real loss curve for 70B looks like (with y-axis labels)](https://x.com/haeggee/status/1962933627584413721)
    - [ASR SOTA](https://huggingface.co/spaces/hf-audio/open_asr_leaderboard)



<br>

## RiemannianProjector, Geodesic Loss, 

```
class RiemannianProjector(nn.Module):
    def __init__(self, in_dim=768, out_dim=1280):
        ...
    def forward(self, x):
        x = self.map(x)
        return F.normalize(x, dim=-1)

cos_sim = (x*y).sum(-1)
loss = acos(cos_sim)


Teacher (Whisper-large-v2, frozen)
        │
        ▼
Student (distil-small + LoRA adapters)
        │
        ├── CE loss (labels supervision)
        │       ↑
        │       └── Hard labels = ground truth text
        │           (e.g. “Hello world” from dataset)
        │
        ├── KL loss (soft logits distillation)
        │       ↑
        │       └── Soft labels = teacher’s predicted probabilities
        │           (e.g. P(“hello”)=0.62, P(“hey”)=0.31, P(“halo”)=0.07)
        │
        └── Geo loss (Riemannian alignment)
                ↑
                └── Aligns latent embeddings on a curved manifold
                    (ensures student follows teacher’s geometry)
        ↓
   Optimizer (AdamW + Cosine LR)
        ↓
  LoRA Adapter Checkpoint (Google Drive)
        ↓
Evaluation (WER / RTF / Memory)


s_hid = student_proj(s_out.encoder_last_hidden_state)
t_hid = normalize(t_out.encoder_last_hidden_state)
geo = geodesic_distance_on_sphere(s_hid, t_hid)
```

<br>


## Background Knowledge

| Topic                                           | Content                                                                                                                                                             | Focus                                                                                                                         |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Bias–Variance Trade-off**                     | Understand the decomposition of prediction error into bias², variance, and irreducible noise; analyze how model capacity and regularization (L1/L2, dropout, early stopping) govern generalization. | Derive and visualize bias–variance curves; compare polynomial regression vs. linear regression on synthetic data to quantify overfitting.                     |
| **Loss Functions**                              | Master the mathematical formulation and gradients of MSE, Cross-Entropy, Hinge, KL-divergence, and CTC losses; relate them to likelihood maximization and task-specific objectives.                 | Construct mappings between task types (classification, ranking, sequence modeling) and optimal loss design; contrast probabilistic vs. margin-based criteria. |
| **Optimization Fundamentals**                   | Deeply understand SGD and its momentum variants (RMSProp, Adam, AdamW); analyze convergence, stability, and implicit regularization; study learning-rate schedules and curvature effects.           | Derive update equations for each optimizer; simulate optimization trajectories on convex and non-convex surfaces to interpret convergence behavior.           |
| **Regularization Strategies**                   | Examine explicit (L1/L2, weight decay) and implicit (dropout, data augmentation, early stopping) regularizers; interpret their influence on gradient dynamics and parameter sparsity.               | Compare gradient magnitudes under different penalties; evaluate the effect of augmentation on effective data entropy.                                         |
| **Evaluation Metrics**                          | Formalize metrics such as Precision, Recall, F1, ROC-AUC, BLEU, and WER; understand trade-offs under class imbalance and probabilistic calibration.                                                 | Compute full confusion matrices; explore threshold tuning and visualize ROC/PR curves to interpret metric behavior.                                           |
| **Neural Network Fundamentals**                 | Analyze forward and backward propagation through multilayer perceptrons; compute gradients via chain rule; interpret vanishing/exploding gradient phenomena.                                        | Manually derive partial derivatives for a one-hidden-layer MLP; validate gradients numerically using finite differences.                                      |
| **Convolutional Neural Networks (CNNs)**        | Explore convolution as parameter sharing and local connectivity; examine receptive fields, stride, padding, pooling, and feature hierarchy formation.                                               | Implement a miniature convolution example by hand; compute output dimensions and receptive-field growth analytically.                                         |
| **Recurrent / Gated Networks (RNN, LSTM, GRU)** | Model temporal dependencies and long-term gradient propagation; dissect gating mechanisms and compare architectures’ ability to mitigate vanishing gradients.                                       | Trace gradient flow across time steps; contrast SRN → LSTM → Transformer evolution in sequential modeling.                                                    |
| **Transformer and Attention Mechanisms**        | Master Q-K-V formulation, scaled dot-product attention, multi-head operations, positional encodings, normalization layers, and their computational complexity.                                      | Derive softmax(QKᵀ / √d) attentional weighting; visualize attention maps to interpret self-attention versus convolution locality.                             |
| **Graph Neural Networks (GNNs)**                | Understand message-passing frameworks (GCN, GAT, GraphSAGE) and hierarchical pooling; analyze how convolution generalizes to irregular domains.                                                     | Illustrate neighborhood aggregation with small graph examples; derive one-hop and multi-hop update equations.                                                 |
| **Data Pipeline Engineering**                   | Design robust data-handling pipelines: cleaning, stratified splitting, shuffling, augmentation, and normalization while avoiding data leakage.                                                      | Build a pipeline diagram showing data flow and random-state control; test reproducibility under resampling.                                                   |
| **Model Lifecycle Management**                  | Cover end-to-end ML workflow—training, validation, deployment, and monitoring—with emphasis on reproducibility and CI/CD integration.                                                               | Reconstruct your own project pipeline (e.g., DQLoRA) and annotate control points for data, code, and configuration versioning.                                |
| **Debugging Machine Learning Systems**          | Identify root causes of non-convergence (poor initialization, LR instability, label noise, normalization errors); apply gradient clipping and adaptive schedulers.                                  | Perform systematic ablations varying LR and batch size; log gradient norms to detect exploding gradients.                                                     |
| **Experiment Tracking and Reproducibility**     | Employ experiment-management frameworks for logging, checkpointing, and hyperparameter optimization; ensure deterministic training via controlled seeds.                                            | Configure a reproducible run with Weights & Biases or MLflow; record hyperparameter sweeps and validation curves.                                             |
| **Model Deployment and Efficiency**             | Implement post-training compression—quantization, pruning, distillation, LoRA adapters—for low-resource inference; design efficient serving pipelines.                                              | Benchmark inference latency and memory footprint on constrained hardware; reproduce deployment from your hearing-aid ASR system.                              |









<br>

| Trend                                  | Description                                     | Representative Systems                |
| -------------------------------------- | ----------------------------------------------- | ------------------------------------- |
| **Cosine + Warmup → Standard Default** | Most stable across architectures.               | ViT, GPT-J, Whisper, Stable Diffusion |
| **Adaptive + Restart Hybrids**         | Combine SGDR + ReduceLROnPlateau.               | DeepSpeed, Megatron-LM, PaLM 2        |
| **Optimizer-Integrated Scheduling**    | Scheduler coupled with optimizer (AdamW, LAMB). | GPT-4, Gemini 1.5, Claude 3           |
| **Noisy / Stochastic Schedules**       | Inject noise to encourage flat minima.          | Google Brain NAS, RL-based training   |
| **Dynamic Data-Aware LR Control**      | LR adapted by validation loss or gradient norm. | Reinforcement fine-tuning (RLHF, PPO) |


<br>

| **Year** | **Model**                         | **Number of Layers** | **Parameter Count** | **FLOPs (per inference)** | **Activations (per forward pass)** | **Typical Memory Footprint**          |
| -------- | --------------------------------- | -------------------- | ------------------- | ------------------------- | ---------------------------------- | ------------------------------------- |
| **1998** | **LeNet**                         | 5                    | ~0.1 M              | ~0.001 GFLOPs             | < 1 MB                             | < 10 MB                               |
| **2012** | **AlexNet**                       | 8                    | 60 M                | ~1.5 GFLOPs               | ~100 MB                            | ~1 GB                                 |
| **2015** | **VGG-16**                        | 16                   | 138 M               | ~15 GFLOPs                | ~200 MB                            | ~2–4 GB                               |
| **2016** | **ResNet-152**                    | 152                  | 60 M                | ~11 GFLOPs                | ~250 MB                            | ~4–6 GB                               |
| **2018** | **BERT-Large**                    | 24                   | 340 M               | ~180 GFLOPs               | ~1 GB                              | ~10–12 GB                             |
| **2020** | **GPT-3**                         | 96                   | 175 B               | ~3.1 × 10¹² FLOPs         | ~20 GB                             | ~350 GB (weights) / > 1 TB (training) |
| **2024** | **GPT-4 / Gemini 1.5 / Claude 3** | ~120 – 200           | > 1 T (trillion)    | ~10¹³ – 10¹⁴ FLOPs        | > 50 GB (activations)              | Multiple TB (large-scale training)    |



<br>

```
Underfitting:     Overfitting:        Good Embedding:
 • • • • •        ●●●  ○○○  ▲▲▲       ● ●   ○ ○   ▲ ▲
 ○ ○ ○ ○ ○        (tight) (tight)      (clear but smooth)
 ▲ ▲ ▲ ▲ ▲        val points outside   val & train overlap
```

| Principle                                                                            | Intuition |
| ------------------------------------------------------------------------------------ | --------- |
| **Regularization** = adding controlled noise or constraints to prevent memorization. |           |
| **Overfitting** = perfect fit on training data, poor generalization.                 |           |
| **Goal** = flatter minima + smoother decision boundaries.                            |           |


<br>


## CNN

```
[Input  D×E  (image or signal)]
      │
      ▼
[Convolution  U×V  (kernel/filter)]
      │  learns local spatial patterns
      │  parameters ≪ fully-connected layers
      ▼
[Zero-Padding / Stride Control]
      │
      ├─ Padding → keeps size (same)
      └─ Stride  → downsamples (D−U)/S+1
      ▼
[Feature Map  K×M  (activation before nonlinearity)]
      │
      ▼
[Activation  g(a)  → ReLU / Sigmoid / Tanh]
      │
      ▼
[Pooling  R×R  window (Avg / Max / Global)]
      │
      ├─ replaces stride for down-sampling
      ├─ reduces spatial size, increases receptive field
      └─ enhances translation invariance
      ▼
[Stacked Conv + Pooling Layers]
      │
      ├─ small kernels (3×3) + pooling ⇒ large receptive field
      ├─ more layers > larger kernels (prefer depth)
      └─ weights grow linearly w/ layers
      ▼
[Flatten or Global Pooling]
      │
      ├─ flatten:  A ∈ ℝ^{Q×K×M} → a ∈ ℝ^{Q·K·M}
      └─ global pooling:  spatial avg → a ∈ ℝ^{Q}
      ▼
[Fully-Connected Layer + Loss]
      │
      ├─ Regression → J_L2
      ├─ Binary → J_BCE
      └─ Categorical → Softmax + J_CCE
      ▼
[Output Prediction y  / Class Probabilities]
```

## Forward Pass

```
Input (32×32×3)
      ↓
Conv (3×3 kernel, 16 filters)
      ↓
ReLU activation
      ↓
Max Pooling (2×2)
      ↓
Conv (3×3 kernel, 32 filters)
      ↓
ReLU
      ↓
Global Avg Pooling
      ↓
Flatten → Dense (Fully-connected)
      ↓
Softmax → [Cat, Dog, Car, …]
```





<br>

| Stage                   | **Method**                                  | **Purpose / Effect**                                        |
| --------------------------- | ------------------------------------------- | ----------------------------------------------------------- |
| **Initialization Stage**    | Xavier / He initialization                  | Avoid falling into poor regions at the start                |
| **Early Exploration Stage** | Large learning rate + Momentum              | Maintain global exploration ability                         |
| **Mid Convergence Stage**   | Adam / RMSProp + Cosine Annealing           | Ensure smooth descent and curvature adaptation              |
| **Late Fine-tuning Stage**  | SAM / Entropy-SGD / Weight Decay            | Locate flat minima and enhance generalization               |
| **During Training**         | Mini-batch noise + Dropout                  | Prevent getting stuck at saddle points                      |
| **Architectural Level**     | Residual connections / Normalization layers | Improve gradient flow and smooth the optimization landscape |


<br>

| Model Example          | **Normalization**                                                                                                           | **Regularization**                                                                                                           | **Essence & How It Works**                                                                                                            |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **CNN (e.g., ResNet)** | **Batch Normalization** — normalizes activations within a mini-batch to stabilize gradients and speed up convergence.       | **Weight Decay + Dropout** — penalizes large weights and randomly drops neurons to reduce overfitting.                       | *Normalization* equalizes feature scales during training, while *Regularization* constrains model capacity to improve generalization. |
| **Transformer / LLM**  | **Layer Normalization** — normalizes hidden states across features to maintain stable activations in deep attention layers. | **Attention Dropout + L2 Regularization** — randomly masks attention links and adds weight penalties to prevent overfitting. | Normalization stabilizes internal representations; regularization prevents memorization of training data.                             |
| **MLP**                | **Input Standardization** — rescales each input feature to zero mean and unit variance.                                     | **L2 Regularization (Ridge)** — discourages large parameter magnitudes for smoother mappings.                                | Normalization improves numerical stability; regularization enforces simpler models with better generalization.                        |


<br>


| Item              | **L1 Regularization**                                 | **L2 Regularization**                                |
| ----------------- | ----------------------------------------------------- | ---------------------------------------------------- |
| **Shape**         | Diamond-shaped constraint                             | Circular constraint                                  |
| **Optimum Point** | Usually lies on the coordinate axes (sparse solution) | Usually lies on the circle (continuous shrinkage)    |
| **Result**        | Some weights are “cut” to exactly 0                   | All weights are smoothly reduced but remain non-zero |


<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project1_5.jpg" alt="Project 1 Visualization" width="75%">
</p>


<br>

## Optimized Decoding

```
Classical Decoding (Without KV Cache)             Optimized Decoding (With KV Cache)

 ┌───────────────┐                                ┌────────────────────────┐
 │   Decoder     │                                │   Decoder + KV Cache   │
 │  (Self-Attn)  │                                │  (Self-Attn + Storage) │
 └───────┬───────┘                                └──────────┬─────────────┘
         │                                                   │
         ▼                                                   ▼
 ┌───────────────┐                                ┌─────────────────────────┐
 │ Recompute all │   O(n²) per step               │  Reuse stored K/V       │
 │ past tokens   │ -----------------------------> │  Only new Q calculated  │
 │ at every step │                                │  O(n) per step          │
 └───────────────┘                                └─────────────────────────┘
         │                                                     │
         ▼                                                     ▼
     ┌─────────┐                                       ┌───────────────┐
     │ Latency │                                       │  Low Latency  │
     │  High   │                                       │  On-Device OK │
     └─────────┘                                       └───────────────┘

   - Redundant computation                           - No recomputation
   - High memory bandwidth                           - Lower memory & power
   - Slow inference                                  - Faster inference
```

<br>

```
Training Loop
    ↓
[ Forward pass ]
    ↓
[ Compute loss ]
    ↓
[ Backward pass: compute gradients ]
    ↓
[ **Gradient Clipping** ]       ←— `clip_grad_norm_(model.params, max_norm)`
    ↓
[ **AdamW Update** ]            ←— `optimizer = AdamW(lr=…, weight_decay=…)`
    ↓
[ Zero Gradients ]          ←— `optimizer.zero_grad()`
    ↓
[ **Cosine LR Annealing** ]     ←— `scheduler = CosineAnnealingLR(optimizer, T_max, eta_min)`
    ↓
[ Next batch ]
```



<br>


**Key Improvements**

1. LoRA + Lightweight Decoders + non-linear Projection to Guide the Student in the Hidden State -> similar WER with `lower inference Latency`
2. `INT8` - Inference - Post-Training [`Quantization`](https://www.youtube.com/watch?v=t509sv5MT0w) -> can try Quantization-Aware Training by yourself
3. Write a script to test the choice of your Surface

<br>

```
%load_ext tensorboard
%tensorboard --logdir /content/drive/MyDrive/distil_run_cell2.x/tb
```

<br>


By modifying `cfg.taid_power` at runtime, the shape of TAID's interpolation curve can be "dynamically" changed without affecting the original function and structure -> Turned out results not good for our model structure

"We found that **4 layers** was the minimum required to get reasonable WER performance for distil-small.en, where it performs to within 3% WER of Whisper large-v2 while being **5.6x faster**"

"While distil-medium.en and distil-large-v2 use **2 layers of decoders** layers each, distil-small.en uses 4. Using more decoder layers improves the WER performance of the model, at the expense of **slower inference speed**"

<br>

`Single card peak ~ 13–15 GB VRAM -> Start your Experiment with FP16 + AMP`

Whisper large-v3 has the same architecture as the previous large and large-v2 models, except for the following minor differences:

1. The spectrogram input uses 128 Mel frequency bins instead of 80
2. A new language token for Cantonese


<br>


**`Teacher`**  
- **Model**: [`whisper-large-v3-turbo`](https://huggingface.co/openai/whisper-large-v3-turbo) - 📍 ≈ 809 M parameters (FP16)
- **Input**: `128-channel log-Mel` (mono, 16 kHz)
- **Encoder**  
  - Hidden size: 1 280
  - Layers: 32  
  - Sequence length: ~ 1 500 frames  
  - **All parameters frozen**  
- **Decoder**  
  - Auto-regressive transformer LM  
  - Hidden size: 1 280  
  - Layers: `4` 
  - Output: `token logits over vocabulary`  
  - **No parameters updated**
  - (ASR) and speech translation. Trained on `1 million hours` of weakly labeled audio and `4 million hours` of pseudo-labeled audio collected using Whisper large-v2


`Input Audio → Encoder → Decoder (Auto-Regressive) → Transcript Tokens`


<br>

**`Benchmark Student`**  

- **Backbone Model**: [distil-whisper/distil-small.en](https://huggingface.co/distil-whisper/distil-small.en) - 📍 ≈166 M parameters (FP16)  
- **Hidden size**: 768  
- **Encoder**  
  - `80-channel log-Mel input` 
  - Layers: 12 (inherited from Whisper-small)  
  - **All parameters frozen**  
- **Decoder**  
  - Layers: 4 (pre-distilled)
  - Auto-regressive transformer LM  
  - **LoRA injection** into every decoder layer:
      1. Decoder (Self-Attn) `self_attn.q_proj`, `self_attn.k_proj`, `self_attn.v_proj`, `self_attn.out_proj`
      2. Decoder（Encoder-Decoder Attn）`encoder_attn.q_proj`, `encoder_attn.k_proj`, `encoder_attn.v_proj`, `encoder_attn.out_proj`
      3. Decoder（Feed-Forward）`fc1`, `fc2`

<br>

**`Our Student`** 

- **Hidden size**: 768  
- **Encoder**  
  - `Same 128-channel log-Mel input` 
  - Layers: 12 (inherited from Whisper-large-v3)  
  - **All parameters frozen**  
- **Decoder**  -> CE Loss - the decoder’s final softmax outputs + KL Loss - logits before the decoder’s final softmax
  - Layers: `4`
  - Auto-regressive transformer LM  
  - **LoRA injection** into every decoder layer - **r = 64**
      1. Decoder (Self-Attn) `self_attn.q_proj`, `self_attn.k_proj`, `self_attn.v_proj`, `self_attn.out_proj`
      2. Decoder（Encoder-Decoder Attn）`encoder_attn.q_proj`, `encoder_attn.k_proj`, `encoder_attn.v_proj`, `encoder_attn.out_proj`
      3. Decoder（Feed-Forward）`fc1`, `fc2`
  - For ASR Distillation, higher T at the begining and then cooler down - `**Cosine Annealing**`

<br>

- simple **80/10/10** split for val/test, Do not touch your Test Set, **SEED = 42**
- **INT8** - Inference - **Post-Training Quantization**
- 4 layers was the minimum required to get reasonable WER performance for distil-small.en, where it performs to `within 3% WER of Whisper large-v2 while being 5.6x faster`
- training samples `≈ 22 000 hrs`

<br>


`check points` of Sample Student Models

**distil-large-v3** (≈756 M parameters) is the **best-performing** distilled checkpoint, performing to within 1.5% WER of Whisper large-v3 on out-of-distribution short-form audio and within 1% WER on long-form decoding

**distil-medium.en** (≈394 M params) provides a balanced trade-off between performance and efficiency, and is recommended for most applications along with distil-large-v2

**distil-small.en** (≈166 M params) is the most compact option and performs to within 3% WER of Whisper large-v2 while being 5.6x faster, making it ideal for `memory-constrained applications (e.g. on-device)`

<br>

**Each token output by `Attention carries global context information`, while `FFN applies "fine-tuning" or "feature combination" to each token` to improve the feature quality at each position**

<br>

```
Transformer = Non-Sugar Donut Factory Assembly Line  
═══════════════════════════════════════════════════════
Raw Donuts → Community Check → Solo Decoration → Finished Donuts  
(Input)       (Attention)       (FFN)            (Output)
    ↓             ↓                ↓               ↓
┌─────────┐  ┌──────────────┐  ┌──────────────┐    ┌─────────┐
│ Plain   │→ │  Community   │→ │   Solo       │ →  │Gourmet  │
│ Donuts  │  │  Analysis    │  │ Decoration   │    │Donuts   │
└─────────┘  └──────────────┘  └──────────────┘    └─────────┘
   ↓                ↓                 ↓                 ↓
   X₀          X₁ = Attention     X₂ = FFN            Output

 1. X₁ᵢ = Σⱼ αᵢⱼ × V_j               (Global Linear)  
 2. X₂ᵢ = W₂·ReLU(W₁·X₁ᵢ + b₁) + b₂  (Local Nonlinear)

Attention: Convex combination → Stays within input space
FFN: Nonlinear transformation → Can transcend input space
```

<br>


```
Activation Function Characteristics Comparison:
═════════════════════════════════════════════════
┌──────────┬────────────┬───────────────┬──────────────┬─────────────┐
│Function  │ Smoothness │ Computational │ Gradient     │ Performance │
│          │            │ Complexity    │ Properties   │             │
├──────────┼────────────┼───────────────┼──────────────┼─────────────┤
│ ReLU     │ Non-smooth │ Minimal       │ Sparse       │ Baseline    │
│ GELU     │ Smooth     │ Moderate      │ Dense        │ Better      │
│ SwiGLU   │ Smooth     │ High          │ Gated        │ Best        │
│ Mish     │ Very Smooth│ High          │ Adaptive     │ Very Good   │
│ Swish    │ Smooth     │ Moderate      │ Self-gated   │ Good        │
│ ELU      │ Smooth     │ Moderate      │ Negative-safe│ Good        │
└──────────┴────────────┴───────────────┴──────────────┴─────────────┘
```

<br>

`Input Features` From Whisper

- [librosa.feature.melspectrogram](https://librosa.org/doc/main/generated/librosa.feature.melspectrogram.html)

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project1_3.jpg" alt="Project 1 Visualization" width="40%">
</p>

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project1_4.jpg" alt="Project 1 Visualization" width="50%">
</p>

<br>

## [Fourier Transform](https://www.linkedin.com/posts/imarpit_ai-machinelearning-deeplearning-activity-7367542558693937152-28w2?utm_source=share&utm_medium=member_desktop&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk)


```
        ┌───────────────────────────────┐
        │        Original Domain        │
        │  - Pixels (Images)            │
        │  - Samples (Audio, Signals)   │
        │  - Tokens (Text)              │
        └───────────────────────────────┘
                       │
                       ▼  Fourier Transform
        ┌───────────────────────────────┐
        │        Frequency Domain       │
        │  - Low frequencies → smooth   │
        │  - High frequencies → edges   │
        │  - Harmonics → fine details   │
        └───────────────────────────────┘
                       │
        ┌──────────────┼────────────────────┐
        ▼              ▼                    ▼
   ┌───────────┐  ┌────────────┐       ┌─────────────┐
   │   CNNs    │  │ Transformers│      │ Speech/Image│
   └───────────┘  └────────────┘       └─────────────┘
   - Edges = HF   - Sinusoidal pos.    - STFT / spectrogram
   - Smooth = LF    encoding           - Highlight textures
   - Convolutions   (frequency basis)  - Recognize phonemes
     simplified                        - Detect fine image details
     in frequency
     space
```


<br><br>

## Distillation Ice Factory

```
Raw Material (Input) → Processing (Distill) → Packaging (Loss) → Finished Product (Student)
    ↓                       ↓                       ↓                    ↓
X₀ (Teacher Output)    X₁ (Distillation)    X₂ (Loss Computation)     Student
```


| Distillation Type   | Factory Analogy                                                                      | Time Complexity     | Space Complexity    |
| ------------------- | ------------------------------------------------------------------------------------ | ------------------- | ------------------- |
| **Logit-based**     | 🧊 **Taste Test Ice**<br>Chef tastes logits → balances flavor (KL) → packages      | $O(B \times C)$     | $O(B \times C)$     |
|                     | - Input: $C$ class logits from the teacher<br>- Loss: KL divergence over classes     | (batch × #classes)  | (batch × #classes)  |
| **Feature-based**   | 🧊 **Texture Match Ice**<br>Dough texture (hidden) → aligns texture (MSE) → packages | $O(B \times D)$     | $O(B \times D)$     |
|                     | - Input: hidden-state vector of dimension $D$<br>- Loss: MSE over each feature dimension | (batch × feature dim) | (batch × feature dim) |
| **Attention-based** | 🧊 **Sprinkle Alignment Ice**<br>Sprinkle pattern (attention map) → aligns → packages | $O(B \times n^2)$   | $O(B \times n^2)$   |
|                     | - Input: attention matrix of size $n \times n$ (heads × seq²)<br>- Loss: MSE/KL on maps | (batch × seq length²) | (batch × seq length²) |
| **Relation-based**  | 🧊 **Community Graph Ice**<br>Community relations (Gram matrix) → aligns → packages | $O(B \times n^2)$   | $O(B \times n^2)$   |
|                     | - Input: similarity matrix among samples or tokens<br>- Loss: MSE/InfoNCE on Gram matrix | (batch × nodes²)    | (batch × nodes²)    |

<br>
```
**B** = batch size
**C** = number of classes
**D** = hidden feature dimension
**n** = sequence length or number of nodes
```


1. **Logit-based “Taste Test”**: Only aligns final class probabilities, linear cost in #classes → lightest overhead
2. **Feature-based “Texture Match”**: Aligns internal feature vectors, linear cost in feature dimension → moderate overhead
3. **Attention-based “Sprinkle Alignment”**: Aligns every sprinkle in the attention map, quadratic cost in sequence length → heavy overhead
4. **Relation-based “Community Graph”**: Aligns all pairwise relations among samples/tokens, also quadratic cost → highest overhead



<br>

## TAID

**Initial training (step=0): λ=0.1**
intermediate = 0.9 * student_probs + 0.1 * teacher_probs

→ Mainly learn the student's own distribution

**Mid-training (step=400): λ≈0.5**
intermediate = 0.5 * student_probs + 0.5 * teacher_probs

→ Balanced learning

**Late training (step=800): λ=0.9**
intermediate = 0.1 * student_probs + 0.9 * teacher_probs

→ Mainly learn the teacher's distribution



<br>

Add a projection layer to ensure dimension alignment, and the projected student hidden state is aligned with the teacher hidden state by **MSE for Hidden-State / Encoder Alignment Loss**

Even `without a decoder`, the `student encoder` can internalize the teacher’s linguistic knowledge by `Mimicking its Output Distributions` and `Hidden‐State Representations` --> 📍 `KL Loss + CE / CTC Loss` 

<br>

**Add Projection Layer - For The Distillation**

- Student (whisper-small): 768 dimensions
- Teacher (whisper-large-v2): 1280 dimensions
- **`Projection Layer`** - Linear(768 → 1280) to align student and teacher hidden dimensions

<br>

```
Teacher (Whisper-large-v2)                     Student (distil-small.en + LoRA + Hidden Align)
─────────────────────────────                  ──────────────────────────────────────────────────

Audio Input                                     Audio Input  
1 × T samples                                   1 × T samples
     │                                               │
     ▼                                               ▼
Whisper Encoder                                 Whisper Encoder
1280-d hidden, T~1500 frames                    768-d hidden, T~499 frames
(32 layers, FROZEN)                            (12 layers, FROZEN)
     │                                               │
     │                                               │
     ├─────── Hidden States ──────────────────────── ├─── Projection Layer ───┐
     │        (B,1500,1280)                          │    (768→1280)          │
     │                                               │                        │
     ▼                                               ▼                        ▼
Whisper Decoder                                 Whisper Decoder              Aligned Hidden
(32 layers, FROZEN)                            (4 layers +/ LoRA)            (B,1500,1280)
     │                                               │                        │
     │                                               │                        │
     ▼                                               ▼                        │
Teacher Logits ────── Soft Targets ─────────▶ Student Logits                  │
(B,seq,vocab)         (KL Loss)               (B,seq,vocab)                   │
     │                 T=temperature              │                           │
     │                                            │                           │
     │                                            ▼                           │
     │                                      Hard Labels ◀── Ground Truth      │
     │                                      (CTC Loss)                        │
     │                                            │                           │
     │                                            │                           │
     │                                            ▼                           │
     │                                       Student Loss ◀─── MSE Loss ──────┘
     │                                            │         (Hidden Align)
     │                                            │
     ▼                                            ▼
No parameter updates                        (LoRA) + Projection parameters
(Inference only)                             ONLY these are trained
```

<br>

```
Teacher Encoder Output (t_h)
┌─────────────────────────────────────────┐
│  t_h: shape = (B, T≈1500, 1280)         │
│                                         │
│  ┌─────┐ ┌─────────────┐ ┌─────────────┐│
│  │ B   │ │  T_frames   │ │ Hidden_dim  ││
│  │     ├─│ ≈1500       ├─│ 1280        ││
│  └─────┘ └─────────────┘ └─────────────┘│
└─────────────────────────────────────────┘

Student Encoder Output (s_h)
┌──────────────────────────────────────────┐
│  s_h: shape = (B, T≈499, 768)            │
│                                          │
│  ┌─────┐ ┌─────────────┐ ┌─────────────┐ │
│  │ B   │ │  T_frames   │ │ Hidden_dim  │ │
│  │     ├─│  ≈499       ├─│ 768         │ │
│  └─────┘ └─────────────┘ └─────────────┘ │
└──────────────────────────────────────────┘
```

<br>


```
↓↓  Student Model: LoRA Injection Points for Encoder & Decoder  ↓↓

           ┌───────────────────────┐
           │   Whisper Encoder     │   ← 12 frozen transformer layers
           │   (layer i)           │
           │                       │
           │  ┌───────────────┐    │    ← If i ∈ {top-4 layers}, 
           │  │ Self-Attn     │◀───┼───┐      inject LoRA into:
           │  │  ┌───┬───┬───┬───┐ │   │      • self_attn.q_proj
           │  │  │ Q │ K │ V │ Out││   │      • self_attn.k_proj
           │  └──┴───┴───┴───┴───┘ │   │      • self_attn.v_proj
           │  ┌───────────────┐    │   │      • self_attn.out_proj
           │  │ Feed-Forward  │    │   │      • fc1, fc2
           │  │  ┌────┐  ┌─────┐│  │   └───────┘
           │  │  │fc1 │  │ fc2 ││  │
           │  └──┴────┴──┴─────┴┘  │
           └───────────────────────┘

                    ↓  (pass projected hidden to Decoder)

           ┌───────────────────────┐
           │  Whisper Decoder      │   ← 4 frozen transformer layers
           │  (layer j)            │
           │                       │
           │  ┌───────────────┐    │    ← inject LoRA into every
           │  │ Self-Attn     │◀───┼───┐      • self_attn.q_proj
           │  │  ┌───┬───┬───┬───┐ │   │      • self_attn.k_proj
           │  │  │ Q │ K │ V │ Out││   │      • self_attn.v_proj
           │  └──┴───┴───┴───┴───┘ │   │      • self_attn.out_proj
           │  ┌───────────────┐    │   │
           │  │ Cross-Attn    │◀───┼───┐      • encoder_attn.q_proj
           │  │  ┌───┬───┬───┬───┐ │   │      • encoder_attn.k_proj
           │  │  │ Q │ K │ V │ Out││   │      • encoder_attn.v_proj
           │  └──┴───┴───┴───┴───┘ │   │      • encoder_attn.out_proj
           │  ┌───────────────┐    │   └───────┘
           │  │ Feed-Forward  │◀───┼───┐      • fc1, fc2
           │  │  ┌────┐  ┌─────┐│  │   └───────┘
           │  │  │fc1 │  │ fc2 ││  │
           │  └──┴────┴──┴─────┴┘  │
           └───────────────────────┘

(All adapters B·A learnable; original weights frozen)
```




<br>

**Why T≈499**

- Whisper feature extractor
- The original audio (30 s) generates about 3000 frames of 80-dimensional log-Mel features at a granularity of 10 ms per frame
  - Whisper first divides the original mono audio (30 seconds, 16 kHz) into several short segments
  - Generate an 80-dimensional log-Mel feature every 10 ms
  - 30 s / 0.01 s = 3000 frames
  - These 3000 frames are still very dense. If Transformer processes them directly, the computational workload and memory requirements will be too high
- Before being fed into the Transformer encoder, these 3000 frames are first downsampled through a convolutional layer (stride=2), and then continuously merged or downsampled in the multi-layer Transformer block
- The final output length is about 3000 / 2 / 3 = 500 frames (actually 499 frames)

```
30 s audio
    ⇓ (extract 80-dim log-Mel every 10 ms)
3000 frames
    ⇓ (convolutional layer with stride=2)
1500 frames
    ⇓ (further down-sampling/merging inside the Transformer encoder ≈×3)
    ⇓ (Pooling or Conv1d: kernel_size=3, stride=3)
≈500 frames  (actually 499 frames)
```

<br>


Audio Signal Characteristics - `Redundancy` -> why can be **compressed** to T~499 frames

```
1. Audio frame rate is typically high
sample_rate = 16000      # 16 kHz sampling rate
frame_rate = 100         # 100 frames per second
frame_duration = 10      # 10 ms per frame

2. 30 seconds of audio
total_frames = 30 * frame_rate  # 3000 frames

3. Adjacent frames are highly correlated
correlation_coefficient ≈ 0.9  # typical inter-frame correlation
```


<br>


- Always remember to do **Automatic checkpoint saving**
- !pip install -U bitsandbytes>=0.41.0
- Put Your Teacher model on CPU
- MIN_DURATION = 1.0
- MAX_DURATION = 30.0 # Same as **Whispe maximum acceptance length**


<br>

| Paper           | Venue                                | Data Size                             |
|-----------------|--------------------------------------|---------------------------------------|
| DistilBERT      | NeurIPS 2019                         | 800 M words + 2.5 B words             |
| TinyBERT        | EMNLP 2020                           | 800 M words + 2.5 B words             |
| MobileBERT      | ICLR 2020                            | 800 M words + 2.5 B words             |
| distil-small.en  |                                     | ≈ 22 000 hours of pseudo-labelled audio across 10 domains (>18 000 speakers)               |
| Our Work        | No Target Venue                      | ≈ **22 000** hours                    |


<br>

<p align="left">
  <img src="/assets/img/project1_2.jpg" alt="Knowledge Map" width="45%">
</p>

<br>

In the design of LoRA, choosing which modules and with what rank 𝑟 to insert the adapter is essentially a trade-off between `Parameter Overhead` and `Adaptability`

**Orignial LoRA Paper**

```
ΔW = A · B -> only low-rank increments are made to W_q and W_v in the attention
```

<br>

`3 Choices of LoRA Injection`

```
decoder.layers.*.encoder_attn.q_proj
decoder.layers.*.encoder_attn.v_proj
decoder.layers.*.self_attn.q_proj
decoder.layers.*.self_attn.v_proj
```


```
decoder.layers.*.encoder_attn.q_proj, encoder_attn.k_proj, encoder_attn.v_proj
decoder.layers.*.self_attn.q_proj, self_attn.k_proj, self_attn.v_proj
decoder.layers.*.fc2
```

```
decoder.layers.*.encoder_attn.q_proj, encoder_attn.k_proj, encoder_attn.v_proj, encoder_attn.out_proj
decoder.layers.*.self_attn.q_proj, self_attn.k_proj, self_attn.v_proj, self_attn.out_proj
decoder.layers.*.fc1, fc2
```

<br>

**`Features - LoRA`**

- **End-to-end alignment**: No extra alignment mechanism; the model learns acoustic-to-text alignment during training
- **Scalable functionality**: Supports ASR, speech translation, and multi-language recognition
- **High decoding overhead**: Requires decoder and beam search at each step, resulting in higher latency
- Balance: r = 8 is generally the most stable between effect and cost
- Pursuing the limit: r = 16 / 32 has the best expressiveness, but requires more video memory and gradients


<br>

**`Temperature`**

- **Initial pilot temperature**: `T =  `  
- **Search range**: `[ ]`  
- **Optuna hyperparameter**: include `temp` as a tunable parameter  
- **Guidance**: prevent over-smoothing (i.e. avoid `T > 5`)


<br>


**`Hard vs. Soft Labels in Knowledge Distillation`**

- **Hard Labels**: one-hot vectors from ground truth  
  `y = [0, …, 1, …, 0]`  
  • Strong supervision → binary certainty  
  • Forces correct classification

- **Soft Labels**: teacher’s softmax outputs  
  `p_teacher = [0.6, 0.3, 0.1]`  
  • Confidence & uncertainty  
  • Encodes inter-class similarity


<br>

`Why num_workers Affects GPU Performance`

The num_workers parameter in PyTorch DataLoader controls the number of CPU processes responsible for data loading and preprocessing. This directly impacts GPU utilization through data pipeline optimization

<br>

`Performance Comparison`

**Single-threaded (num_workers=0)**

- CPU: Load→Preprocess→Transfer, GPU idle, Load→Preprocess→Transfer
- GPU: Idle, Compute, Idle
  
**Multi-threaded (num_workers=4)**

- CPU: Continuous data preparation (4 parallel threads)
- GPU: Continuous computation (minimal idle time)

**Key Insight**

- Increasing num_workers enhances "CUDA kernel parallelism" not by adding GPU parallelism, but by eliminating GPU starvation. Multiple CPU workers ensure the GPU receives a steady stream of preprocessed data, maximizing hardware utilization and reducing training time
- The optimal num_workers typically ranges from 2-4 per GPU, depending on CPU core count and I/O bottlenecks

<br>

**CTC Loss - Hard Supervision** - Here `Cross-Entropy (CE) Loss` since Whisper is `Seq2Seq with Decoders`


Since Whisper is a Seq2Seq model with Decoder, cross-entropy loss is employed here.

The decoder generates hidden state sequences at step $u$:
$$\{\mathbf{d}_u\}_{u=1}^U$$

mapping to the target text sequence:
$$\{y_u\}_{u=1}^U$$

using token-by-token one-to-one supervision:

- **Token-to-Token Alignment** Each step has a clear "correct" next token, requiring no implicit alignment
- **One-Step Supervision** Cross-entropy is directly applied to the prediction distribution at each position $u$  
- **Direct Gradient** Backpropagated from the output layer, enabling stable convergence

**Cross-Entropy Loss Formula**
$$\mathcal{L}_{\mathrm{CE}} = -\sum_{u=1}^U \log P_\theta\bigl(y_u \mid y_{<u}, \mathbf{h}_{1:T}\bigr)$$

where:
- $\mathbf{h}_{1:T}$ represents the audio representation output by the encoder  
- $y_{<u}=(y_1,\dots,y_{u-1})$ are the previously generated tokens
- $U$ is the target sequence length

Following the encoder's output audio frame sequence:
$$\{\mathbf{h}_t\}_{t=1}^T$$

mapping to transcript tokens:
$$\{y_u\}_{u=1}^U$$

without explicit frame-level labels:

- **Frame-to-Token Alignment** Automatic alignment from audio frames to text tokens
- **Marginalizing Paths** Marginalizing over all possible alignment paths
- **Gradient Signal** Gradient signals propagate to all relevant audio frames through attention mechanisms

<br><br>

**KL Distillation Loss - Soft Supervision**

KL Distillation Loss compares the teacher’s and student’s posterior distributions over labels at each time-step in latent space
<br>

  - Soft Distribution Matching
  - Preference Transfer
  - Capturing Uncertainty

<br>

Since the softmax outputs retain probabilities for all tokens, the KL term transfers the teacher’s uncertainty patterns—e.g., when the teacher is unsure between two phonemes, the student learns to mirror that ambiguity

<br><br>

**Total Loss**

$$
L_{\text{total}}
= L_{\mathrm{CE}}
+ 0.xx\,T^{2}\,L_{\mathrm{KD}}
+ \alpha\,L_{\mathrm{hidden\_align}}
$$


<br>

where

$$
\begin{aligned}
& L_{\mathrm{CE}}
   &&\text{is the hard CE loss}\\
& L_{\mathrm{KD}}
   = \mathrm{KL}\bigl(p_{\rm teacher}^{T}\;\|\;p_{\rm student}^{T}\bigr)
   &&\text{is the softened KL-divergence loss with temperature }T\text{ and weight }\0.8 (*the same as student backbone)\\
& L_{\mathrm{hidden\_align}}
   &&\text{is the projected hidden-state MSE loss with weight }\alpha
\end{aligned}
$$  


<br><br>

**Hyperparameter Optimization**

<br>

With 15hrs dataset experiment, we used 50 rounds to run a "warm-up" for no problem. If you want to perform large-scale tuning in a production environment, it is recommended to `increase n_trials to 50-100`

```
import optuna
from optuna.pruners import MedianPruner
from optuna.samplers import TPESampler

def objective(trial):
    # Distillation loss weights
    alpha = trial.suggest_loguniform("alpha", 1e-3, 1e1)
    beta  = trial.suggest_loguniform("beta",  1e-3, 1e1)
    # Optimization hyperparameters
    lr        = trial.suggest_loguniform("lr",        1e-5, 1e-3)
    batch_size= trial.suggest_categorical("batch_size", [4, 8, 16, 32])
    dropout   = trial.suggest_float("dropout", 0.0, 0.5)
    
    # Train & evaluate with these settings (implement train_and_evaluate accordingly)
    wer = train_and_evaluate(
        alpha=alpha,
        beta=beta,
        learning_rate=lr,
        batch_size=batch_size,
        dropout=dropout,
        pruner=trial  # for early stopping
    )
    return wer

# Pruner to stop unpromising trials early
pruner  = MedianPruner(n_startup_trials=5, n_warmup_steps=100)
sampler = TPESampler()

study = optuna.create_study(
    direction="minimize",
    sampler=sampler,
    pruner=pruner
)
study.optimize(objective, n_trials=100)

print("Best hyperparameters:", study.best_params)
```


```
**Gradient Underflow**
feats = b["input_features"].half().to(device) <- FP32 to 16

self.scaler = **GradScaler()**
...
with autocast():
    loss = model(input)  # loss = float16
self.scaler.scale(loss).backward() 
self.scaler.step(optimizer)  
self.scaler.update()
```

<br><br>


## PCA vs. t-SNE vs. UMAP vs. DTW

<br>

<p align="center">
  <img src="https://yiruyang2025.github.io/assets/img/project1_1.jpg" alt="Project 1 Visualization" width="75%">
</p>

<br>

```
- Local weights
w_ij = exp(−(d(x_i, x_j) − ρ_i) / σ_i)  
w_ji = exp(−(d(x_j, x_i) − ρ_j) / σ_j)

- Fuse into a single “strength” score
μ_ij = w_ij + w_ji − w_ij * w_ji
```

<br><br><br>


## References


**Connectionist Temporal Classification (CTC) in Knowledge Distillation**  - No need since Encoder-Decoder Seq2Seq Model here 

- **Proposer & Year**: Alex Graves et al. (2006 ICML)  
- **Motivation**:  
  Frame–label alignment unavailable in speech/handwriting tasks 
- **Mechanism**:  
  1. Automatic alignment of variable‐length audio to text  
  2. Marginalization over all valid alignment paths  
  3. Blank token to handle repeats and separations  
- **Role in Distillation**:  
  Provides hard supervision—ensures correct sequence output without frame-level labels

<br>

**Kullback–Leibler (KL) Distillation Loss**  

- **Proposer & Year**: Hinton et al. (2015 NIPS)  
- **Motivation**:  
  Transfer “dark knowledge” (inter-class similarity and uncertainty) from teacher to student.  
- **Mechanism**:  
  1. Compute teacher and student softmax distributions at each time step  
  2. Apply temperature \(T\) to smooth distributions  
  3. Minimize KL divergence between them  
- **Role in Distillation**:  
  Provides soft supervision—guides student to match teacher’s probability patterns and improve generalization.

<br>

**Rectification Loss (Representation-Level Supervision)**  

- **Proposer & Year**: Romero et al. (2014 ICLR “FitNets”)  
- **Motivation**:  
  Teacher’s internal feature representations carry structural and reasoning cues beyond output labels.  
- **Mechanism**:  
  1. Extract corresponding hidden-layer activations from teacher and student  
  2. Minimize feature‐map discrepancy via L2 or similar loss  
- **Role in Distillation**:  
  Provides intermediate supervision—aligns student’s internal representations with teacher’s, stabilizing training and preserving network–level knowledge.


<br>

**Basic + Advanced Parallel**
  - First use linear projection + MSE as the basic alignment (to ensure training feasibility)
  - At the same time, design a Group-wise Cross-Attention Projector (refer to ACCV2022) to capture more expressive mappings

**Progressive Distillation Scheduling**
  - In the early stage of training, only output distribution distillation + projection MSE is used;
  - Then gradually "unfreeze" the intermediate layer alignment loss, or add a blank frame / non-blank frame factorization strategy (refer to CTC-ASR).

**Multi-stage Intermediary**
  - If the teacher-student difference is too large, an auxiliary teacher with a more similar structure can be introduced to complete the alignment **in two steps**



<br>

## Background Knowledge 2

```
[Training Neural Network]
      │
      ▼
[Problem: Overfitting]
      │  model performs well on train set
      └─ poor generalization on unseen data
      ▼
[Regularization Strategies]
      │
      ├─ L1 Regularization → add |w| penalty
      │     encourages sparsity, feature selection
      │
      ├─ L2 Regularization (Weight Decay)
      │     adds w² penalty, smooths weights
      │     reduces variance, stabilizes gradients
      │
      ├─ Early Stopping
      │     monitor validation loss → stop early
      │
      ├─ Data Augmentation
      │     enlarge dataset (flip, crop, color jitter)
      │     improves robustness & invariance
      │
      └─ Dropout
            randomly deactivate neurons (mask m)
            prevents co-adaptation
            during inference: scale activations by p
      ▼
[Normalization Layers]
      │
      ├─ Batch Normalization (BN)
      │     normalize activations per mini-batch
      │     μ_B, σ_B computed over batch samples
      │     then apply γ (scale) + β (shift)
      │     allows larger learning rate & faster training
      │
      ├─ Layer Normalization (LN)
      │     normalize across features, not batch
      │     used in Transformers (batch-size independent)
      │
      └─ Effect:
            stabilizes gradient flow
            reduces internal covariate shift
            improves convergence speed
      ▼
[Residual Connections]
      │
      └─ skip connection y = F(x) + x
            eases gradient propagation
            enables very deep CNNs (ResNet)
      ▼
[Combined Strategy]
      │
      ├─ Regularization (L1/L2)
      ├─ Dropout
      ├─ Batch Normalization
      └─ Data Augmentation
      ▼
[Result]
      │
      └─ High generalization, stable training,
         smoother optimization landscape,
         reduced overfitting risk
```

```
[Closed-Set Classification]
      │
      └─ assumes all test classes are known
         model outputs one of O fixed labels
      ▼
[Open-Set Problem]
      │
      ├─ real-world contains unknown categories
      ├─ standard SoftMax → overconfident wrong predictions
      └─ need to reject unseen (unknown) samples
      ▼
[Goal: Open-Set Recognition]
      │
      ├─ recognize known classes correctly
      └─ detect / reject unknown classes (OOD)
      ▼
[Two Main Paradigms]
      │
      ├─ Two-Stage OSR
      │     Stage 1: detect unknowns (OOD)
      │     Stage 2: classify known samples
      │
      └─ Integrated OSR
            single model learns known + reject class
            adds “unknown” logits or rejection threshold
      ▼
[Core Approaches]
      │
      ├─ OSDN (Open-Set Deep Network)
      │     compute Mean Activation Vector (MAV)
      │     distance D_o = ||ϕ - μ_o||
      │     fit EVT (Extreme Value Theory) model to tails
      │
      ├─ GHOST (Gaussian Hypothesis OSR)
      │     per-class Gaussian modeling in feature space
      │     normalize logits by (μ_o, σ_o)
      │     provides calibrated confidence
      │
      ├─ Garbage / Background Class
      │     add class y₀ for “none of the above”
      │     weighted loss: λ_τ = N / ((O+1)N_τ)
      │
      ├─ Entropic Open-Set Loss
      │     for unknowns, enforce uniform SoftMax
      │     target: t_o = 1/O for all o
      │     equalizes logits → high entropy
      │
      └─ Confidence Thresholding
            use ζ threshold on SoftMax
            accept if max(ŷ_o) > ζ, else reject
      ▼
[Training]
      │
      ├─ Known samples: one-hot targets
      ├─ Unknown samples: uniform targets
      └─ Loss combines CE + Entropic term
      ▼
[Evaluation Metrics]
      │
      ├─ CCR (Correct Classification Rate)
      │     true positives among known samples
      │
      ├─ FPR (False Positive Rate)
      │     unknowns misclassified as knowns
      │
      └─ OSCR Curve (CCR vs FPR)
            area under curve (AUOSCR) = performance
      ▼
[Modern Implementations]
      │
      ├─ ImageNet-based OSR protocols (P1–P3)
      ├─ Feature-space Gaussian models (GHOST)
      ├─ Entropic loss + background class hybrid
      └─ Evaluation by AIML UZH / WACV 2023
      ▼
[Outcome]
      │
      └─ OSR enables reliable recognition under uncertainty:
         “I know what I know — and I know what I don’t.”
```



<br>

## NeurlPS 2026 Submission Quick Check

<br>

 | Focus Area                 | **ICML**                                           | **ICLR**                                             | **NeurIPS**                                                  |
| -------------------------- | -------------------------------------------------- | ---------------------------------------------------- | ------------------------------------------------------------ |
| **Core Identity**          | Theory & Algorithms                                | Representation & Deep Learning                       | Broad AI & Computational Science                             |
| **Theoretical Work**       | Optimization, convergence, learning theory         | Representation learning theory                       | Mathematical + computational perspectives (theory + applied) |
| **Architecture**           | Classical ML (kernels, boosting, graphical models) | Neural architectures (Transformers, Diffusion, GNNs) | Novel architectures with interdisciplinary impact            |
| **Reinforcement Learning** | Algorithmic + theoretical RL                       | Representation-based RL, world models                | RL + neuroscience + multi-agent + cognitive links            |
| **Generative Models**      | Probabilistic & Bayesian models                    | Neural generative models (GANs, VAEs, Diffusion)     | Foundation models, multimodal, scaling laws                  |
| **Applications**           | Applied ML (health, econ, systems, social science) | Deep-learning apps (CV, NLP, multimodal)             | Cross-domain (AI + physics, bio, climate, neuroscience)      |
| **Experiment Style**       | Balanced theory & experiments                      | Large-scale empirical results                        | Technically deep + interdisciplinary demos                   |

<br>

## References



[UK Biobank](https://www.ukbiobank.ac.uk/)

[SCAI](https://scai.ethz.ch/)

[2025 - MC-MED](https://github.com/dkimlab/MCMED)

[2020 - Topological Autoencoders](https://proceedings.mlr.press/v119/moor20a.html?ref=https://githubhelp.com)


[2025 - Development of a multimodal vision transformer model for predicting traumatic versus degenerative rotator cuff tears on magnetic resonance imaging: A single-centre retrospective study](https://esskajournals.onlinelibrary.wiley.com/doi/10.1002/ksa.70000)

<br>


## Toolkit


[2025 - Brainchop: In-browser 3D MRI rendering and segmentation](https://github.com/neuroneural/brainchop)


<br><br>


## Organ / Liver Preservation

  
[USZ - Department of Visceral Surgery and Transplantation](https://www.usz.ch/en/department/visceral-and-transplantation/)

[2025 - Predicting Rejection Risk in Heart Transplantation: An Integrated Clinical–Histopathologic Framework for Personalized Post-Transplant Care](https://www.linkedin.com/posts/anant-madabhushi-9a75a21_hearttransplant-ai-digitalpathology-activity-7372616055581585408-x86I?utm_source=share&utm_medium=member_desktop&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk)


[2025 - MC-MED, multimodal clinical monitoring in the emergency department](https://www.nature.com/articles/s41597-025-05419-5)


[2025 - USZ + ETHz - Regenerative Heart Repair](https://www.linkedin.com/posts/omer-dzemali-prof-dr-med-dr-h-c-2702b9104_from-lab-to-beating-hearts-activity-7358452392071262208-bPba?utm_medium=ios_app&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk&utm_source=social_share_send&utm_campaign=copy_link)

[Department of Thoracic Surgery](https://www.usz.ch/team/sami-hosari/)



<br>

## End-to-End Real-World Data Flow - [USZ](https://www.usz.ch/en/department/diagnostic-and-interventional-radiology/)



```
Hospital CT / MRI
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

**Temporal Alignment Leakage**

```
┌─────────────────────────────────────────┐
│  Temporal Downsampling Effect           │
│                                         │
│  Teacher Sequence (1500 frames)         │
│  ┌─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┐  │
│  │▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│▓│  │
│  └─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┘  │
│          ↓ 3:1 compression              │
│  Student Sequence (499 frames)          │
│  ┌─────┬─────┬─────┬─────┬─────┬─────┐  │
│  │ ▓▓▓ │ ▓▓▓ │ ▓▓▓ │ ▓▓▓ │ ▓▓▓ │ ▓▓▓ │  │
│  └─────┴─────┴─────┴─────┴─────┴─────┘  │
│     ↑                                   │
│  Information "leaks" to adjacent windows│
└─────────────────────────────────────────┘
```


<br>

| Method              | Memory Usage                    | Training Speed                    |
| ------------------- | ------------------------------- | --------------------------------- |
| **Normal Training** | High (store all activations)    | Fast (no recomputation needed)    |
| **Checkpointing**   | Low (store partial activations) | Slow (extra recomputation needed) |


<br>


## Gradient Checkpointing


```
Forward Pass:
Input → [Layer1: store] → [Layer2: recompute later] → [Layer3: recompute later] → Output

Backward Pass:
Recompute Layer2 & Layer3 forward
Use recomputed activations → compute gradient
Use Layer1 activation → compute gradient
```


<br><br>


## References

- [FitNets]
- [1991 - Adaptive Mixtures of Local Experts](https://ieeexplore.ieee.org/abstract/document/6797059)
- [2022 - Knowledge Distillation via Hypersphere Features Distribution Transfer](https://dl.acm.org/doi/abs/10.1145/3511808.3557621?casa_token=5zxwbIg9Lp8AAAAA:LqsNXD0NVGJIFJqlulaWKhSG8kp69U673xQL0Jr2vauz2MlxmVoTq0rlxXzyKdR0IRthPyemq9_t)
- [2025 - An Intuitive Overview of Few-Step Diffusion Distillation](https://ronaldyu.substack.com/p/an-intuitive-overview-of-few-step)
- [2025 - TAID]
- [Polyscope - Toolkit for demos]
- [2025 - Efficient Distillation of Classifier-Free Guidance using Adapters](https://arxiv.org/abs/2503.07274)
- [2025 - AXLearn: Modular Large Model Training on Heterogeneous Infrastructure](https://arxiv.org/abs/2507.05411)
- [2013 - Efficient Estimation of Word Representations in Vector Space](https://arxiv.org/abs/1301.3781)
- [2014 - Adam: A Method for Stochastic Optimization](https://arxiv.org/abs/1412.6980)
- [2016 - Information Geometry and Its Applications](https://link.springer.com/book/10.1007/978-4-431-55978-8)
- [2015 - Matrix Backpropagation for Deep Networks With Structured Layers](https://openaccess.thecvf.com/content_iccv_2015/html/Ionescu_Matrix_Backpropagation_for_ICCV_2015_paper.html)
- [2019 - Auxiliary teacher - Improved Knowledge Distillation via Teacher Assistant](https://arxiv.org/abs/1902.03393?utm_source=chatgpt.com)
- [2023 - Sub-sentence encoder: Contrastive learning of propositional semantic representations](https://arxiv.org/pdf/2311.04335)
- [2023 - Accelerating Large Language Model Decoding with Speculative Sampling](https://arxiv.org/pdf/2302.01318)
- [ASR WER + Latency](https://huggingface.co/spaces/hf-audio/open_asr_leaderboard)
- [2021 - 1-bit Adam: Communication Efficient Large-Scale Training with Adam’s Convergence Speed](https://proceedings.mlr.press/v139/tang21a.html)
- [2024 - SqueezeAttention: 2D Management of KV-Cache in LLM Inference via Layer-wise Optimal Budget](https://arxiv.org/abs/2404.04793)
- [2025 - Qwen/Qwen3-235B-A22B-Instruct-2507](https://huggingface.co/Qwen/Qwen3-235B-A22B-Instruct-2507)

<br><br>



