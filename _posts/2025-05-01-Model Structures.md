---
layout: post
title: Model Structures
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

<br>

```
Let's take a look at the history of the Model Structures we're using today.
```


- All our models today are intentionally designed to be differentiable but `without a closed-form`. This is because once a closed form is present, the model becomes linear and simple, with weak expressive power, unable to learn Mozart's harmonic progressions. Only by creating multiple layers of non-linear nesting can a model achieve both differentiability and the inability to solve for a closed-form, thus possessing powerful expressive power.


```
However, the cost is the necessity for 📍 iterative training.
```

<br>

## macOS on Apple Silicon: Package and Environment Management

Apple Silicon uses the **ARM64** instruction set, also called **AArch64**. Most current macOS software is available as native ARM64 or universal binaries. Older Intel-only software may still require **Rosetta 2**.

<br>

## DL after Classic ML

| **Component**      | **Description**                                                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Origin**         | Deep Learning was formalized in **1986** by **Rumelhart, Hinton, and Williams** with the invention of **Backpropagation**.                  |
| **Key Idea**       | Learn hierarchical representations — from low-level edges to high-level concepts — through multiple neural layers.                          |
| **Representation** | Automatically extracts features from raw data (images, audio, text) instead of manual feature engineering.                                  |
| **Optimization**   | Trains large neural networks using **gradient descent** and **backpropagation** to minimize a defined loss.                                 |
| **Architecture**   | Stacks multiple nonlinear transformations (e.g., CNNs, RNNs, Transformers) to form deep computational graphs.                               |
| **Generalization** | Learns robust patterns that transfer to unseen data, aided by large datasets, GPUs, and regularization methods.                             |
| **Impact / Use**   | Powers modern AI systems in **vision (CNNs)**, **language (Transformers)**, **speech (RNNs)**, and **generative models (Diffusion, GANs)**. |

<br>

## Deep Learning, Training, and Knowledge Distillation

| Dimension | Deep Learning | Training | Knowledge Distillation |
| ---------- | -------------- | ---------- | ------------------------ |
| **Objective** | Learn multi-layer nonlinear function `f(x; θ)` to represent complex patterns. | Optimize a loss function from data. | Make the student model mimic the teacher’s output distribution and internal representations. |
| **Input Information** | Raw data `(x)` | `(x, y)` | `(x, y, T(x))` |
| **Loss Function** | Any differentiable objective. | Task loss `𝓛(f(x), y)` | `α 𝓛(f(x), y) + (1−α) KL(f(x) ∥ T(x))` |
| **Supervision Source** | Data itself. | Hard labels `(y)`. | Teacher outputs `(T(x))` + true labels `(y)`. |
| **Entropy Characteristic** | May be high or low depending on task. | Low-entropy one-hot supervision. | High-entropy soft targets (smoothed teacher outputs). |
| **Optimization Process** | BP + GD *(Backpropagation + Gradient Descent)*. | BP + GD. | BP + GD with temperature scaling `τ`. |
| **Application Goal** | General representation learning. | Task-specific model fitting. | Model compression, knowledge transfer, or performance enhancement. |
| **Output Features** | Deep hierarchical representations. | Task predictions. | Balanced task accuracy and teacher–student alignment. |

<br>

```
Deep Learning World                             Classical ML World
═══════════════════════════════════             ════════════════════════════════════
Raw Data → Multi-layer Network →                Handcrafted Features → Shallow Model →
Learn Representations → Optimize by Gradient    Manual Design → Limited Adaptability
     ↓                     ↓                           ↓                     ↓
┌───────────────┐   ┌─────────────────┐           ┌─────────────────┐   ┌───────────────────────┐
│ Raw Inputs    │ → │ Neural Layers   │    vs.    │ Engineered Feats│ → │ Classifier (SVM/Tree) │
│ (Image/Text)  │   │ (CNN/RNN/Trans.)│           │ (HOG/SIFT/MFCC) │   │ (Fixed Decision Rules) │
└───────────────┘   └─────────────────┘           └─────────────────┘   └───────────────────────┘
     ↓                     ↓                           ↓                     ↓
End-to-End Learning     Automatic Feature Hierarchy   Manual Tuning Needed   Poor Transferability
(Backprop + Gradient)   (Low→Mid→High Abstractions)   (Domain-Specific)      (Retrain for New Task)

Hybrid approaches:
1. Use pretrained deep features + classical models for fast adaptation  
2. Fine-tune deep backbones with task-specific heads for efficiency  

Deep Learning = Student who learns concepts from examples (automatic understanding)  
Classical ML  = Student who uses fixed formulas (must be told what features matter)
```

<br>

## Generalization Ability

```
Unsupervised World                              Zero-Shot World
═══════════════════════════════════             ════════════════════════════════════
No Labels → Discover Patterns →                 Pretrained Knowledge → New Task →
Cluster / Reduce Dim → Build Representations    Direct Prediction → Works Instantly
     ↓                     ↓                           ↓                     ↓
┌───────────────┐   ┌─────────────────┐           ┌─────────────────┐   ┌───────────────────────┐
│ Data Patterns │ → │ Learned Embeds  │    vs.    │ Language / Text │ → │ Recognize Unseen Task │
│ (Raw Inputs)  │   │ (Structure Only)│           │ Semantic Priors │   │ (Zero Examples)       │
└───────────────┘   └─────────────────┘           └─────────────────┘   └───────────────────────┘
     ↓                     ↓                           ↓                     ↓
Unclear for Tasks      Needs Extra Step            Direct Generalization   Immediate Usability
(PCA/K-means/SimCLR)   (Downstream Fine-tune)      (CLIP, GPT)             (Zero-shot QA/CLS)

Hybrid approaches:
1. Learn unsupervised embeddings → map to semantic space for zero-shot transfer
2. Combine raw pattern discovery with pretrained knowledge for stronger generalization

Unsupervised = Tourist wandering a city with no map (discover zones by yourself)  
Zero-Shot   = Tourist with a guidebook (instantly spot city hall & cathedral)
```

<br>

## Why Deep Structure
  - Compared with the original machine learning models:
  - **Linear Regression / SVM / Shallow Decision Trees**
  - Deep structures refer to neural networks with **Multiple Layers of Nonlinear Transformations**
  - how to find some other temporal modeling way for the Non-linear Transformation?
<br>

## Content

- Transformer
- Mamba
- GPT
- Tokenization
- ARIMA
- RNN, LSTM, GRU
- Diffusion Models
- Flow Matching
- Quantization / Adapter Guided - LoRA + QLoRA


  - These deep models are capable of `Learning Hierarchical Features`, where each layer captures increasingly abstract representations of the data.

<br>

## Local Minimal vs. Saddle Point
<br>

<p align="left">
  <img src="/assets/img/deep_1.jpg" alt="Knowledge Map" width="75%">
</p>

<br>

In practice, "Deep" means:

- More than 3–4 layers in fully connected networks
- 10+ layers in convolutional networks
- Or even hundreds of layers in modern transformers like GPT


<br>


## Key Structures

- **MLP**
  - Multilayer Perceptron
  - Feedforward fully connected networks
  - Used in classification, regression, or small-scale tabular/audio tasks
  - 1989 - Universal Approximation Theorem / Still used as light head in multimodal systems<br>

- 📍 **RNN -> LSTM**
  - When inputs are sequences<br>
  - [Hochreiter & Schmidhuber 1997 - LSTM](https://ieeexplore.ieee.org/abstract/document/6795963)<br>

- **Some Other 📍 Temporal Modeling**
  - GRU
  - ConvGRU
  - DynamicLSTM
  - GatedGRU

- **CNN**
  - Convolutional Neural Networks
  - When inputs are images or grid-like data
  - Extracts spatial features, widely used in image/audio tasks
  - Fully Connected Layer -> Receptive Field -> Parameter Sharing -> Convolutional Layer
  - 1998 - LeNet / 2012 - AlexNet: ImageNet Classification with Deep Convolutional Neural Networks<br>

- **Transformer**
  - When inputs are sequences<br>
  - Self-attention + Parallel computation<br>
  - [2015 ICLR - Neural Machine Translation by Jointly Learning to Align and Translate - **Additive Attention**](https://arxiv.org/abs/1409.0473)<br>
  - [2017 NeuralPS - Attention Is All You Need - **Self-Attention / Scaled Dot-Product Attention**](https://arxiv.org/abs/1706.03762)<br>

- **Mamba**
  - Linear-Time Sequence Modeling<br>
  - State Space Model - SSM - with selective long-range memory<br>
  - [2023 - Mamba: Linear-Time Sequence Modeling with Selective State Spaces](https://arxiv.org/abs/2312.00752)

- **Conformer**
  - Convolution + Transformer = Conformer
  - Combines local - CNN - and Global Self-attention Features
  - Widely used in speech recognition tasks
  - [2020 - Conformer: Convolution-augmented Transformer for Speech Recognition](https://arxiv.org/abs/2005.08100)<br>

 - **GAN**
   - Generator vs Discriminator<br>
   - Generates Images, Audio<br>
   - Popular in TTS, audio enhancement, and image generation<br>
   - [2014 - Generative Adversarial Nets](https://proceedings.neurips.cc/paper_files/paper/2014/hash/f033ed80deb0234979a61f95710dbe25-Abstract.html)<br>

- **Diffusion Based**
  -  Gradual denoising process to generate samples from noise<br>
  -  Currently SoTA in image and speech generation<br>
  -  Training is stable, generation is slow<br>
  -  **In Diffusion**
     - The model learns to reverse noise through a pre-defined noise schedule
     - It does not evaluate or penalize each intermediate step
     - There is no "fitness score" like in genetic algorithms
  - **In genetic algorithms - GA**
     - Every candidate (individual) is evaluated using a fitness function
     - Poor candidates are penalized or discarded<br>
     - 2020 - Denoising Diffusion Probabilistic Models

- **📍 SSL**
  - Learns from unlabeled data by solving pretext tasks<br>
  - Strong performance in low-resource and zero-shot setups<br>

- **Memory - Transformers vs. RNN / LSTM**
  - Add Reflection - 2024 - You Only Cache Once: Decoder-Decoder Architectures for Language Models

- **Flow Matching**
  - [An Introduction to Flow Matching](https://mlg.eng.cam.ac.uk/2024/01/20/flow-matching.html)

<br>


## 1. Gradient Noise


<p align="left">
  <img src="/assets/img/deep_5.jpg" alt="Knowledge Map" width="50%">
</p>


<br>

## 2. What is Gradient Noise


| Source                          | Explanation                                                                                          |
| ------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Sampling noise                  | Each batch only samples part of the data, so the gradient is an approximation of the true mean.      |
| Reward noise (RL-specific)      | Rewards from the environment vary greatly across trajectories.                                       |
| Numerical noise (hardware)      | Floating-point rounding errors, limited bfloat16 precision, or non-deterministic accumulation order. |
| Communication noise (multi-GPU) | Random order of all-reduce operations causes slight variations in summed gradients.                  |
| Regularization noise            | Dropout and mixed-precision scaling introduce artificial randomness.                                 |

<br>

$$
\nabla L(\theta) = \frac{\partial L}{\partial \theta}
$$

  - Compute the exact gradient of the loss function (ideal case)

$$
\tilde{\nabla} L(\theta) = \nabla L(\theta) + \varepsilon
$$

  - Represent the noisy gradient observed in practice (with noise term \( \varepsilon \))


<br>

## 3. Why Gradient Noise is Especially Large in RL

$$
J(\theta) = \mathbb{E}_{\tau \sim \pi_\theta}[R(\tau)]
$$

  - Expected future reward objective in reinforcement learning

$$
\nabla_\theta J(\theta) = \mathbb{E}_{\tau} \left[ \nabla_\theta \log \pi_\theta(a_t \mid s_t) \cdot R(\tau) \right]
$$


  - Policy gradient estimating how parameters affect expected reward


$$
Var(\nabla_\theta J) = Var\left(R \cdot \nabla_\theta \log \pi_\theta \right)
$$

  - High variance of rewards and log-probabilities amplifies gradient noise


<br>

## 4. Learning Rates - Theoretically

  - [2025 - A Proof of Learning Rate Transfer under µP](https://arxiv.org/pdf/2511.01734)


<br>


## 5. Historical Development of Kernel Functions

| Year            | Person / School                  | Contribution                                                                                                                                                   |
| --------------- | -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1909**        | **James Mercer**                 | Proposed **Mercer’s Theorem** — the mathematical relationship between symmetric positive-definite kernel functions and inner-product spaces of high dimension. |
| **1930 – 1950** | Integral-Equation School         | The term *kernel* originally referred to the weighting function of an integral operator, $K(x, y)$.                                                            |
| **1960s**       | **Vapnik & Chervonenkis (USSR)** | Developed **statistical learning theory** and introduced the idea of **implicit feature mapping**.                                                             |
| **1992 – 1995** | **Vapnik, Boser, Guyon, Cortes** | Formally applied kernel functions in **Support Vector Machines (SVM)** using the **kernel trick** to avoid explicit high-dimensional mapping.                  |


<br>

## 6. Common Kernel Functions

| **Kernel Name**                   | **Formula**                                              | **Feature**                                       |
| ---------------------------------- | -------------------------------------------------------- | ------------------------------------------------- |
| **Linear Kernel**                  | $K(x, y) = x^{T}y$                                       | Original linear inner product                     |
| **Polynomial Kernel**              | $K(x, y) = (x^{T}y + c)^{d}$                             | Polynomial non-linear mapping                     |
| **RBF / Gaussian Kernel**          | $K(x, y) = \exp\!\big(-\|x - y\|^{2} / (2\sigma^{2})\big)$ | Infinite-dimensional mapping; most commonly used  |
| **Sigmoid Kernel**                 | $K(x, y) = \tanh(\alpha\, x^{T}y + c)$                   | Similar to a neural-network activation function   |
| **Laplacian / Exponential Kernel** | $K(x, y) = \exp\!\big(-\|x - y\| / \sigma\big)$          | More sensitive to sparse features                 |

<br>


## 7. Evolution of 3D Scene Representations

| **Period**     | **Method**                       | **Representation**                                                                                   | **Advantages / Limitations**                                                                                                          |
| -------------- | -------------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **1980–2010s** | SfM / MVS / Mesh                 | Explicit point clouds or polygonal meshes                                                            | Accurate but discrete; cannot represent complex appearance or soft surfaces                                                           |
| **1990–2010s** | IBR / Light Field                | Sampled light rays or image interpolation                                                            | Highly photorealistic but lacks true 3D geometry; strong view dependence                                                              |
| **2015–2019**  | Deep Implicit Fields             | Implicit functions (Occupancy / Signed Distance Field)                                               | Continuous and smooth geometry; no explicit color or reflectance modeling                                                             |
| **2020–2022**  | **NeRF family**                  | Neural radiance fields (density + color)                                                             | Unified geometry and appearance; high fidelity but slow to train and render                                                           |
| **2023–Now**   | **3D Gaussian Splatting (3DGS)** | Explicit point-based volumetric primitives (Gaussian ellipsoids with color, opacity, and anisotropy) | Extremely fast rendering and editing; preserves view consistency; but lacks strong geometry regularization and semantic understanding |


<br>

## Convolution and CNN as Structured DNN

- [1989 - Backpropagation applied to handwritten zip code recognition](https://ieeexplore.ieee.org/abstract/document/6795724/)
- [1998 - LeNet5 - Gradient-Based Learning Applied to Document Recognition](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=726791)
- NeuroBio Fudanmental
  - 1959–1962 David Hubel & Torsten Wiesel
  - [1980 - Neocognitron: A self-organizing neural network model for a mechanism of pattern recognition unaffected by shift in position](https://link.springer.com/article/10.1007/BF00344251)


<br>


| Aspect                  | Mathematical Convolution                                                 | CNN Convolution Layer                                | Fully Connected DNN (MLP)          | Intuitive Explanation                   |
| ----------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------- | ---------------------------------- | --------------------------------------- |
| First appearance        | 18–19th century (Fourier analysis, signal processing)                    | 1989                                                 | 1950s–60s                          | Convolution long predates deep learning |
| Key proposer            | —                                                                        | Yann LeCun                                           | Rosenblatt, Widrow, others         | CNN formalized for vision tasks         |
| Original motivation     | Analyze signals & systems                                                | Model visual pattern recognition                     | Generic function approximation     | CNN was built *for images*              |
| Core formula            | $(f * g)(x)=\int f(\tau)g(x-\tau),d\tau$; $(f * g)[i]=\sum_k f[k]g[i-k]$ | Same discrete form (kernel flip ignored in practice) | $y=Wx+b$                           | All are linear mappings                 |
| What it actually does   | Sliding weighted sum                                                     | Sliding weighted sum                                 | One-shot global weighted sum       | CNN looks locally, MLP looks everywhere |
| How weights behave      | One kernel reused everywhere                                             | Same filter reused across space                      | Each connection has its own weight | CNN “reuses the same eye”               |
| Connectivity pattern    | Local                                                                    | Local                                                | Dense                              | CNN ignores far-away pixels             |
| Weight matrix view      | Toeplitz / structured operator                                           | Sparse, tied $W$                                     | Dense $W$                          | CNN = heavily constrained $W$           |
| Translation behavior    | Translation equivariant                                                  | Translation equivariant                              | Not equivariant                    | Shift image → shift features            |
| Layer equation          | —                                                                        | $y_i=\sum_{j\in\mathcal{N}(i)} w_{j-i}x_j$           | $y=Wx+b$                           | CNN is a restricted linear layer        |
| Parameters              | Few (kernel-sized)                                                       | Few                                                  | Many                               | CNN saves parameters massively          |
| Inductive bias          | Built-in locality & symmetry                                             | Built-in locality & symmetry                         | None                               | CNN encodes assumptions about the world |
| Function class          | —                                                                        | Subset of DNN                                        | Superset                           | CNN $\subset$ DNN                       |
| What is *not* different | —                                                                        | Expressive power in principle                        | Expressive power in principle      | Difference is learning efficiency       |
| Final takeaway          | A mathematical operator                                                  | A structured linear layer                            | A generic linear layer             | CNN is a **structured DNN**             |


<br>

## Concepts From CNN

| Concept                                 | What it is                                                     | Who formalized / popularized it   | What problem it solves                       | Why it matters                            |
| --------------------------------------- | -------------------------------------------------------------- | --------------------------------- | -------------------------------------------- | ----------------------------------------- |
| **Equivariance to translation**         | Convolution commutes with spatial translation: $f(Tx)=T(f(x))$ | LeCun et al. (CNNs, 1990s)        | Detects features regardless of location      | Encodes translation symmetry              |
| **Patch processing**                    | Applies the same local operator to overlapping spatial patches | Hubel & Wiesel (biology); CNNs    | Exploits local spatial correlations          | Enforces locality bias                    |
| **Image filtering**                     | Linear filtering with learnable kernels                        | Classical signal processing; CNNs | Extracts edges, textures, patterns           | Bridges signal processing and learning    |
| **Parameter sharing**                   | Same kernel weights reused across spatial locations            | LeCun et al.                      | Reduces parameter count                      | Improves data efficiency                  |
| **Variable-sized input processing**     | Convolution independent of absolute input size                 | CNN framework design              | Handles arbitrary image resolutions          | Enables dense prediction                  |
| **Multi-channel convolution**           | Each output channel sums convolutions over all input channels  | Early CNNs                        | Combines multiple feature maps               | Enables cross-channel feature composition |
| **Local receptive field**               | Each neuron depends only on a local neighborhood               | Fukushima (Neocognitron), CNNs    | Limits interaction range                     | Defines spatial inductive bias            |
| **Hierarchical feature composition**    | Deeper layers compose simpler features into complex ones       | Deep CNNs (AlexNet onward)        | Models high-level structure                  | Explains the role of depth                |
| **Nonlinearity**                        | Pointwise nonlinear functions (e.g., ReLU)                     | Modern neural networks            | Prevents collapse to linear filters          | Enables expressive function classes       |
| **Pooling / downsampling**              | Spatial aggregation (max, average, strided conv)               | LeCun et al.                      | Introduces robustness to small shifts        | Produces approximate invariance           |
| **Equivariance vs. invariance**         | Convolution is equivariant; pooling induces invariance         | CNN theory                        | Clarifies preserved vs discarded information | Central to representation design          |
| **Fully convolutional operator**        | Defines a mapping on spatial fields, not fixed vectors         | FCNs (Long et al.)                | Enables per-pixel prediction                 | Treats CNNs as operators on grids         |
| **Implicit regularization**             | Architectural constraints bias learning                        | Empirical deep learning theory    | Improves generalization                      | Architecture acts as a prior              |
| **Boundary conditions / padding**       | How convolution handles image borders                          | Practical CNN design              | Controls artifacts and symmetry breaks       | Affects exact equivariance                |
| **Group equivariance (generalization)** | Convolution as a group-equivariant operator                    | Cohen & Welling (G-CNNs)          | Extends symmetry beyond translation          | Unifies CNNs with symmetry theory         |


<br><br>

## 🔎 Unified Pair-Problem Decision Table


| Input Structure                                      | Think As             | Best Data Structure        | Optimal Strategy                 | Time Complexity          | Typical Problem              |
| ---------------------------------------------------- | -------------------- | -------------------------- | -------------------------------- | ------------------------ | ---------------------------- |
| Two **unsorted** arrays, need all combinations       | Matrix (unordered)   | Max/Min Heap               | Push all or maintain size-K heap | O(NM log K)              | K largest/smallest pair sums |
| Two **sorted** arrays, need K smallest/largest pairs | Sorted Matrix        | Min Heap (multi-way merge) | Treat each row as sorted stream  | O(K log N)               | K smallest pairs             |
| Two **sorted** arrays, need exact target             | Two-pointer          | Two pointers               | Converging scan                  | O(N)                     | Two Sum II                   |
| Two arrays, need count of valid pairs                | Frequency model      | HashMap / Counter          | Count-based math                 | O(N + M)                 | Count pairs with sum K       |
| Dynamic "extract max repeatedly"                     | Priority queue model | Max Heap                   | Repeated pop + push              | O(N log N)               | Last Stone Weight            |
| State transitions between pairs                      | Graph                | BFS / DFS + visited set    | Layer-by-layer traversal         | O(V + E)                 | Word Ladder style problems   |
| Sliding window over pair condition                   | Window model         | Two pointers               | Expand / shrink window           | O(N)                     | Subarray / bounded sum       |
| Bitwise pair optimization (XOR)                      | Binary Trie          | Trie                       | Bit-level greedy                 | O(N * bit)               | Maximum XOR pair             |
| Need smallest distance among pairs                   | Value search         | Binary Search + counting   | Search on answer                 | O(N log W)               | K-th smallest pair distance  |
| N×M grid fully sorted by row & column                | Monotonic matrix     | Binary search or heap      | Matrix step expansion            | O(K log N) or O(N log W) | K-th smallest in matrix      |


<br><br>

## FP and AMP

| Precision strategy           | Historical origin                                                                                  | Mathematical / computational idea                                                                            | VRAM on 16GB GPU                         | Speed                       | Stability                   | Best use case                                     |
| ---------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ | ---------------------------------------- | --------------------------- | --------------------------- | ------------------------------------------------- |
| **FP32 full precision**      | IEEE 754 single precision, standardized in **1985**                                                | All major tensors and computations use 32-bit floating point.                                                | High, about **100%** baseline            | Baseline                    | Very high                   | Stable training when memory is not the bottleneck |
| **Pure FP16 half precision** | Modern IEEE binary16 standardized in **2008**; earlier graphics half formats appeared in the 1990s | All or most tensors use 16-bit floating point.                                                               | Low, about **50%** tensor storage        | Very fast on supported GPUs | Low without careful scaling | Memory saving, but risky for full training        |
| **Mixed precision training** | Deep-learning formulation by **Micikevicius et al., NVIDIA, 2017**                                 | Use FP16 for selected forward/backward operations, while preserving critical states or accumulation in FP32. | Medium-low, about **60–70%** in practice | Fast                        | High                        | Efficient training with near-FP32 accuracy        |
| **AMP**                      | Framework automation popularized by **NVIDIA Apex** and later native PyTorch/TensorFlow AMP        | Automatically casts safe operations to FP16 and keeps sensitive operations in FP32; applies loss scaling.    | Medium-low, about **60–70%** in practice | Fast                        | High                        | Recommended default for 16GB GPU training         |


<br>

## Jax vs. Numpy

| Feature            | NumPy                          | Pandas                          | JAX                                     |
| ------------------ | ------------------------------ | ------------------------------- | --------------------------------------- |
| **Core Role**      | Numerical computing            | Tabular data analysis           | Differentiable accelerated computing    |
| **Data Structure** | `ndarray`                      | `DataFrame`, `Series`           | `jax.Array`                             |
| **Best For**       | Linear algebra, simulation     | Cleaning, statistics, CSV/Excel | ML, physics models, GPU/TPU             |
| **Main Strength**  | Fast, stable, widely supported | Easy labeled-data operations    | Autograd, JIT, `vmap`                   |
| **Project Use**    | Solve dynamical equations      | Organize results and metadata   | Train M-Layer and run large simulations |



<br>



## Layer 0 — CPU Architecture and Binary Compatibility

| Property                   | Native Apple Silicon    | Intel Compatibility Mode               |
| -------------------------- | ----------------------- | -------------------------------------- |
| Architecture               | ARM64 / AArch64         | x86_64 / AMD64                         |
| Native on M-series         | Yes                     | No                                     |
| Execution                  | Direct                  | Rosetta 2 translation                  |
| Homebrew prefix            | `/opt/homebrew`         | `/usr/local`                           |
| Check process architecture | `arch` → `arm64`        | `arch` → `i386`                        |
| Check machine architecture | `uname -m` → `arm64`    | Physical machine still reports `arm64` |
| Force execution            | `arch -arm64 <command>` | `arch -x86_64 <command>`               |
| Typical use                | Modern software         | Legacy Intel-only software             |

Install Rosetta 2 only when required:

```bash
softwareupdate --install-rosetta --agree-to-license
```

**Rule:** Prefer native ARM64 software.

<br>

## Layer 1 — Apple-Provided System Tools

| Tool                         | Location                              | Purpose                            | Rule                                  |
| ---------------------------- | ------------------------------------- | ---------------------------------- | ------------------------------------- |
| Apple Python                 | `/usr/bin/python3`                    | macOS and developer-tool workflows | Do not install project packages there |
| Apple Ruby and Perl          | `/usr/bin/*`                          | System scripts                     | Do not replace them                   |
| Apple `curl`, `ssh`, and CLI | `/usr/bin/*`                          | Core system utilities              | Install separate versions if needed   |
| Xcode Command Line Tools     | `/Library/Developer/CommandLineTools` | Compilers, headers, `git`, `make`  | Install before native development     |
| Full Xcode                   | `/Applications/Xcode.app`             | Apple-platform and Metal workflows | Install only when required            |

Install the Xcode Command Line Tools:

```bash
xcode-select --install
```

**Rule:** Treat `/usr/bin`, `/bin`, `/sbin`, and `/System` as read-only. Never use `sudo pip install` or `sudo brew`.

<br>

## Layer 2 — Machine-Level Package Managers

| Manager                | Handles                                    | Default location              | Best use                        |
| ---------------------- | ------------------------------------------ | ----------------------------- | ------------------------------- |
| Homebrew               | CLI tools, libraries, services, GUI apps   | `/opt/homebrew`               | Default choice for most users   |
| MacPorts               | Unix tools and native libraries            | `/opt/local`                  | Packages better supported there |
| Nix with `nix-darwin`  | Declarative packages and system settings   | `/nix/store`                  | Reproducible machine setups     |
| Mac App Store          | Apple-distributed GUI applications         | `/Applications`               | Xcode and Store-managed apps    |
| Vendor `.dmg` / `.pkg` | GUI apps, drivers, and system integrations | `/Applications` or `/Library` | Vendor-required installation    |

### Essential Homebrew Commands

| Command                            | Purpose                         |
| ---------------------------------- | ------------------------------- |
| `brew install <formula>`           | Install a CLI tool or library   |
| `brew install --cask <cask>`       | Install a GUI app or font       |
| `brew list`                        | List installed packages         |
| `brew leaves`                      | List explicitly installed tools |
| `brew outdated`                    | Show available updates          |
| `brew upgrade`                     | Upgrade packages                |
| `brew uninstall <package>`         | Remove a package                |
| `brew info <package>`              | Show package information        |
| `brew search <name>`               | Search packages                 |
| `brew bundle dump --file=Brewfile` | Export installed packages       |
| `brew bundle --file=Brewfile`      | Restore installed packages      |
| `brew doctor`                      | Diagnose configuration problems |
| `brew cleanup`                     | Remove old versions and caches  |
| `brew autoremove`                  | Remove unused dependencies      |

**Rule:** Use Homebrew as the primary package manager. Do not mix Homebrew and MacPorts on the same `PATH` unless carefully isolated.

<br>

## Layer 3 — Language Runtime Managers

| Tool     | Languages                                   | Project configuration                          | Recommended role                    |
| -------- | ------------------------------------------- | ---------------------------------------------- | ----------------------------------- |
| `mise`   | Python, Node.js, Ruby, Go, Java, and others | `.mise.toml` or `.tool-versions`               | Recommended general-purpose manager |
| `asdf`   | Multiple languages through plugins          | `.tool-versions`                               | Established team alternative        |
| `pyenv`  | Python                                      | `.python-version`                              | Specialised Python workflows        |
| `nvm`    | Node.js                                     | `.nvmrc`                                       | Common Node-only manager            |
| `fnm`    | Node.js                                     | `.nvmrc`                                       | Faster Node-only alternative        |
| `rbenv`  | Ruby                                        | `.ruby-version`                                | Existing Ruby workflows             |
| `rustup` | Rust                                        | `rust-toolchain.toml`                          | Official Rust toolchain manager     |
| `uv`     | Python runtime and dependencies             | `.python-version`, `pyproject.toml`, `uv.lock` | Python-only workflows               |

**Rule:** Choose one primary runtime manager, normally `mise` or `asdf`. Use `rustup` for Rust.

<br>

## Layer 4 — Python Environments and Dependency Management

| Tool              | Creates environments     | Installs dependencies          | Locking            | Recommended role                        |
| ----------------- | ------------------------ | ------------------------------ | ------------------ | --------------------------------------- |
| `venv`            | Yes                      | No                             | No                 | Minimal standard-library environment    |
| `virtualenv`      | Yes                      | No                             | No                 | Legacy compatibility                    |
| `pip`             | No                       | Yes                            | No                 | Basic package installer                 |
| `pip-tools`       | No                       | Yes                            | Requirements files | Lightweight dependency locking          |
| `uv`              | Yes                      | Yes                            | `uv.lock`          | Recommended default                     |
| Poetry            | Yes                      | Yes                            | `poetry.lock`      | Existing Poetry-based projects          |
| PDM               | Yes                      | Yes                            | Yes                | Standards-oriented alternative          |
| Hatch             | Yes                      | Yes                            | Environment-based  | Library development and testing         |
| Conda             | Yes                      | Yes, including native packages | Yes                | Scientific stacks with native libraries |
| Mamba             | Uses Conda environments  | Yes                            | Conda-compatible   | Faster Conda solver                     |
| `pipx`            | One environment per tool | Yes                            | No project lock    | Isolated global Python CLI tools        |
| `uv tool install` | One environment per tool | Yes                            | Tool-specific      | Preferred Python CLI installation       |

**Rule:** Use `uv` for Python projects and `uv tool install` for Python CLI tools. Use Conda or Mamba only when native scientific dependencies require them.


<br><br>

| Hierarchical Layer             | Concept / Component                          |                                     Historical Origin or Typical Era | Essential Meaning                                                                                                                | Primary Purpose                                                                 | Windows                                                    | Linux                                                   | macOS                                                     | Correct Practice / Key Insight                                                                                            |
| ------------------------------ | -------------------------------------------- | -------------------------------------------------------------------: | -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| 1. Operating System            | Operating system                             | Windows NT: 1993; Linux kernel: 1991; macOS Darwin/XNU lineage: 2001 | The lowest user-visible system layer controlling processes, files, memory, permissions, devices, networking, and native binaries | Provides the execution environment in which Python and all libraries run        | Windows NT kernel, drive-letter filesystem, PE executables | Linux kernel, single-root filesystem, ELF executables   | Darwin/XNU, POSIX-style filesystem, Mach-O executables    | Python code may be portable, but processes, paths, permissions, binary packages, and hardware backends remain OS-specific |
| 1. Operating System            | Kernel                                       |                                                         OS-dependent | The privileged core that manages hardware and system resources                                                                   | Process scheduling, memory management, device access, filesystems, system calls | Windows NT kernel                                          | Linux kernel                                            | XNU hybrid kernel                                         | A Python virtual environment does not isolate or replace the kernel                                                       |
| 1. Operating System            | Executable format                            |                                                    Platform-specific | Native binary layout understood by the operating system loader                                                                   | Allows compiled programs and extension modules to run                           | `.exe`, `.dll`, `.pyd`, PE format                          | ELF binaries and `.so` libraries                        | Mach-O binaries and `.dylib` / `.so` libraries            | A compiled package built for one OS cannot normally be copied to another OS                                               |
| 1. Operating System            | CPU architecture                             |                                                   Hardware-dependent | Instruction-set architecture used by binaries                                                                                    | Determines binary compatibility and performance                                 | Commonly x86-64; ARM64 also exists                         | x86-64, ARM64, and server architectures                 | Intel x86-64 or Apple Silicon ARM64                       | Record both OS and architecture in reproducibility reports                                                                |
| 2. User Interface              | Terminal host                                |                                                   Varies by platform | A graphical or textual application that displays a command-line session                                                          | Displays prompts, accepts keystrokes, and hosts shells                          | Windows Terminal, VS Code terminal, legacy console host    | GNOME Terminal, Konsole, xterm, VS Code terminal        | Terminal.app, iTerm2, VS Code terminal                    | A terminal is not a shell; it can host different shells                                                                   |
| 2. User Interface              | Shell                                        |                   cmd: 1987; PowerShell: 2006; Bash: 1989; Zsh: 1990 | A command language and process launcher                                                                                          | Parses commands, expands variables, resolves executables, and launches programs | PowerShell, cmd, Git Bash, WSL shells                      | Bash, Zsh, Fish, others                                 | Zsh by default; Bash also available                       | Command syntax is determined by the active shell, not by the terminal application                                         |
| 2. User Interface              | PowerShell                                   |                                                                 2006 | Object-oriented shell and automation language                                                                                    | System administration, scripting, structured pipelines                          | Native major shell                                         | Available as `pwsh`                                     | Available as `pwsh`                                       | Use PowerShell syntax only inside PowerShell                                                                              |
| 2. User Interface              | cmd.exe                                      |                                                                 1987 | Legacy Windows command interpreter                                                                                               | Batch files and compatibility workflows                                         | Native                                                     | Not native                                              | Not native                                                | Use mainly for legacy `.bat` or `.cmd` workflows                                                                          |
| 2. User Interface              | Bash                                         |                                                                 1989 | Unix shell compatible with Bourne-shell conventions                                                                              | Scripting, automation, Linux administration                                     | Available through Git Bash or WSL                          | Very common default shell                               | Available, but not the modern default                     | Bash scripts require Unix-style paths and syntax                                                                          |
| 2. User Interface              | Zsh                                          |                                                                 1990 | Unix shell with advanced interactive features                                                                                    | Interactive shell and scripting                                                 | Optional                                                   | Optional                                                | Default shell on modern macOS                             | Bash and Zsh are similar but not fully identical                                                                          |
| 2. User Interface              | Shell prompt                                 |                                                    Platform-specific | Visual representation of the active shell and current state                                                                      | Helps identify shell and active environment                                     | `PS C:\...>` or `C:\...>`                                  | `user@host:~$`                                          | `user@host ~ %` or `$`                                    | Prompt appearance is helpful but not authoritative evidence of interpreter identity                                       |
| 2. User Interface              | Script extension                             |                                                    Platform-specific | File extension convention indicating the intended interpreter                                                                    | Associates scripts with shells or programs                                      | `.ps1`, `.bat`, `.cmd`, `.py`                              | `.sh`, `.py`; extension may be optional                 | `.sh`, `.command`, `.py`                                  | Execute a script with the interpreter for which it was written                                                            |
| 2. User Interface              | Current-directory script prefix              |                                                       Shell-specific | Explicitly indicates that a script is located in the current directory                                                           | Prevents accidental command shadowing                                           | `.\script.ps1` in PowerShell                               | `./script.sh`                                           | `./script.sh`                                             | `.\` and `./` are shell path syntax, not Python syntax                                                                    |
| 3. Filesystem                  | Root structure                               |                                                          OS-specific | Top-level organization of storage paths                                                                                          | Determines how absolute paths are written                                       | Multiple roots such as `C:\`, `D:\`                        | One root `/`                                            | One root `/`, with volumes under `/Volumes`               | Avoid hard-coded absolute paths in portable code                                                                          |
| 3. Filesystem                  | Home directory                               |                                                          OS-specific | User-owned default working area                                                                                                  | Safe location for projects and environments                                     | `C:\Users\name`                                            | `/home/name`                                            | `/Users/name`                                             | Store projects under a user-writable development directory                                                                |
| 3. Filesystem                  | Path separator                               |                                                          OS-specific | Character separating directory components                                                                                        | Constructs file paths                                                           | `\` natively                                               | `/`                                                     | `/`                                                       | Use `pathlib.Path` instead of manually concatenating separators                                                           |
| 3. Filesystem                  | Case sensitivity                             |                                                 Filesystem-dependent | Whether `File.py` and `file.py` are considered different names                                                                   | Affects imports, paths, and portability                                         | Usually case-insensitive                                   | Usually case-sensitive                                  | Usually case-insensitive by default                       | Keep filename capitalization consistent even on case-insensitive systems                                                  |
| 3. Filesystem                  | Hidden files                                 |                                              Convention or attribute | Files not normally displayed                                                                                                     | Stores configuration and tooling data                                           | Hidden attribute; dotfiles also used                       | Leading dot, such as `.venv`                            | Leading dot                                               | `.venv` is a convention, not a required name                                                                              |
| 3. Filesystem                  | Line endings                                 |                                       Historical platform convention | Character sequence ending a text line                                                                                            | Affects scripts and Git diffs                                                   | CRLF common                                                | LF                                                      | LF                                                        | Configure Git line-ending normalization and use UTF-8                                                                     |
| 3. Filesystem                  | File locking                                 |                                                 OS-specific behavior | Rules governing files opened by processes                                                                                        | Affects deletion, replacement, and temporary files                              | Open files often block deletion or replacement             | Files may be unlinked while still open                  | Unix-like behavior                                        | Close file handles explicitly and test workflows on each OS                                                               |
| 4. Permissions                 | Permission model                             |                                                          OS-specific | Rules deciding who may read, write, or execute a file                                                                            | Protects system and user data                                                   | ACL-based security descriptors                             | POSIX mode bits, ACLs, capabilities                     | POSIX mode bits, ACLs, additional platform protections    | Do not treat every failure as a Python error; check filesystem permissions first                                          |
| 4. Permissions                 | Administrative elevation                     |                                                          OS-specific | Running with elevated privileges                                                                                                 | Allows protected system modifications                                           | Run as Administrator / UAC                                 | `sudo` or root                                          | `sudo`                                                    | Do not use elevation for normal project-level pip installation                                                            |
| 4. Permissions                 | Script execution control                     |                                                          OS-specific | Restriction on executing scripts                                                                                                 | Prevents unauthorized scripts from running                                      | PowerShell execution policy may block `.ps1` files         | Execute bit and mount options                           | Execute bit plus Gatekeeper/quarantine effects            | An activation-free workflow avoids changing PowerShell policy                                                             |
| 4. Permissions                 | Ownership tools                              |                                                          OS-specific | Commands for changing file ownership and access                                                                                  | Repairs incorrect ownership or permissions                                      | `takeown`, `icacls`                                        | `chown`, `chmod`, `setfacl`                             | `chown`, `chmod`, ACL tools                               | Correct ownership deliberately; do not use recursive privilege changes without understanding their scope                  |
| 5. Python Runtime              | Python language                              |                                                 Public release: 1991 | A programming language with defined syntax and semantics                                                                         | Expresses algorithms and applications                                           | Same language semantics                                    | Same language semantics                                 | Same language semantics                                   | The language is portable; its runtime environment and compiled packages may not be                                        |
| 5. Python Runtime              | Python interpreter                           |                                              Implementation-specific | Program that parses and executes Python code                                                                                     | Runs scripts, imports modules, and manages runtime state                        | Usually `python.exe`, sometimes selected through `py`      | Usually `python3`                                       | Usually `python3`                                         | Always verify the actual executable with `sys.executable`                                                                 |
| 5. Python Runtime              | `python` command                             |                                               Shell-resolved command | Name resolved through PATH                                                                                                       | Launches one selected Python interpreter                                        | Common, but may be intercepted by Store aliases            | May not exist; `python3` is common                      | `python3` is common                                       | Command spelling is less important than executable identity                                                               |
| 5. Python Runtime              | `py` launcher                                |                                                     Windows-specific | Version-selection launcher for installed Python versions                                                                         | Chooses a specific interpreter version                                          | Common on Python.org installations                         | Usually unavailable                                     | Usually unavailable                                       | Use `py -3.12` when multiple Windows Python versions coexist                                                              |
| 5. Python Runtime              | `sys.executable`                             |                                              Python runtime property | Absolute path to the running interpreter                                                                                         | Definitive interpreter identity                                                 | Returns `.exe` path                                        | Returns interpreter path                                | Returns interpreter path                                  | More reliable than checking the prompt prefix                                                                             |
| 5. Python Runtime              | `sys.path`                                   |                                                 Python import system | Ordered list of locations searched for imports                                                                                   | Determines which modules can be loaded                                          | Environment-dependent                                      | Environment-dependent                                   | Environment-dependent                                     | Diagnose `ModuleNotFoundError` by inspecting both `sys.executable` and `sys.path`                                         |
| 6. Module Execution            | `python -m`                                  |                            Long-standing Python command-line feature | Runs an importable module as a program                                                                                           | Binds module execution to a selected interpreter                                | Same semantics                                             | Same semantics                                          | Same semantics                                            | `-m` belongs to Python, not to pip                                                                                        |
| 6. Module Execution            | `python -m pip`                              |                                    Modern recommended pip invocation | Runs the pip module belonging to the selected Python interpreter                                                                 | Prevents interpreter-installer mismatch                                         | Strongly recommended                                       | Strongly recommended                                    | Strongly recommended                                      | Prefer this over an unqualified `pip` command                                                                             |
| 6. Module Execution            | `python -m venv`                             |                                                     Python 3.3, 2012 | Runs the standard-library virtual-environment creator                                                                            | Creates an isolated project environment                                         | Creates `Scripts` layout                                   | Creates `bin` layout                                    | Creates `bin` layout                                      | The selected base interpreter determines the environment's Python version                                                 |
| 6. Module Execution            | `python -m pytest`                           |                                                Module-launch pattern | Executes pytest inside the selected environment                                                                                  | Avoids calling a different global pytest executable                             | Same concept                                               | Same concept                                            | Same concept                                              | Use when executable PATH ambiguity is possible                                                                            |
| 7. Packaging                   | PyPI                                         |                                                                 2003 | Central index of Python distributions                                                                                            | Helps installers discover packages                                              | Same public service                                        | Same public service                                     | Same public service                                       | PyPI indexes packages; it does not perform installation itself                                                            |
| 7. Packaging                   | pip                                          |                                                                 2008 | Python package installer and dependency resolver                                                                                 | Downloads, resolves, builds, and installs distributions                         | Installs Windows-compatible artifacts                      | Installs Linux-compatible artifacts                     | Installs macOS-compatible artifacts                       | pip behavior is conceptually shared, but available binaries differ by OS and architecture                                 |
| 7. Packaging                   | Distribution                                 |                                                    Packaging concept | Installable project artifact plus metadata                                                                                       | Unit installed by pip                                                           | Wheel or source distribution                               | Wheel or source distribution                            | Wheel or source distribution                              | Distribution name may differ from import name                                                                             |
| 7. Packaging                   | Module                                       |                                                Python import concept | Single importable code unit                                                                                                      | Organizes executable Python code                                                | Same                                                       | Same                                                    | Same                                                      | `pip install Pillow` produces the import package `PIL`                                                                    |
| 7. Packaging                   | Package                                      |                                             Python namespace concept | Collection of modules and subpackages                                                                                            | Organizes reusable code                                                         | Same                                                       | Same                                                    | Same                                                      | Do not confuse an import package with a distribution package                                                              |
| 7. Packaging                   | Wheel                                        |                                                    PEP 427 era, 2012 | Prebuilt installable binary distribution                                                                                         | Avoids local compilation                                                        | Windows-tagged wheels                                      | `manylinux` or `musllinux` wheels                       | Intel, ARM64, or universal macOS wheels                   | A wheel must match Python version, OS, architecture, and ABI                                                              |
| 7. Packaging                   | Source distribution                          |                                          Historical packaging format | Archive containing source and build metadata                                                                                     | Enables installation when no compatible wheel exists                            | May require MSVC                                           | May require GCC/Clang and development headers           | May require Apple Clang and SDK tools                     | Source builds expose system-level dependencies                                                                            |
| 7. Packaging                   | Native extension                             |                                   Compiled module imported by Python | Accelerates numerical or system-level operations                                                                                 | Provides high performance                                                       | `.pyd` plus DLL dependencies                               | `.so` plus ELF dependencies                             | `.so` or Mach-O dependencies                              | Native extensions are not portable across operating systems                                                               |
| 7. Packaging                   | Build toolchain                              |                                                          OS-specific | Compiler, linker, headers, and SDK                                                                                               | Builds packages from source                                                     | MSVC Build Tools and Windows SDK                           | GCC/Clang and development packages                      | Xcode Command Line Tools / Apple Clang                    | Upgrade pip first to maximize the chance of finding a compatible wheel                                                    |
| 7. Packaging                   | TLS certificate validation                   |                                                   Security mechanism | Verifies package-server identity                                                                                                 | Protects downloads against interception                                         | Proxy and trust-store issues may occur                     | Proxy and CA package issues may occur                   | Proxy and Keychain/trust issues may occur                 | Do not use `--trusted-host` as a routine fix                                                                              |
| 8. Virtual Environments        | PEP 405                                      |                                    Proposed 2011; Python 3.3 in 2012 | Standard design for lightweight Python environments                                                                              | Separates project-specific package installations                                | `.venv\Scripts` and `Lib\site-packages`                    | `.venv/bin` and `lib/pythonX.Y/site-packages`           | `.venv/bin` and `lib/pythonX.Y/site-packages`             | A virtual environment is a Python-prefix isolation mechanism, not a full OS sandbox                                       |
| 8. Virtual Environments        | `.venv` directory                            |                                                   Project convention | Local generated environment folder                                                                                               | Holds environment interpreter entry points and installed packages               | Commonly `.venv\Scripts\python.exe`                        | Commonly `.venv/bin/python`                             | Commonly `.venv/bin/python`                               | Do not commit `.venv` to Git                                                                                              |
| 8. Virtual Environments        | `pyvenv.cfg`                                 |                                                              PEP 405 | Configuration linking environment to a base Python installation                                                                  | Identifies base interpreter and environment behavior                            | Present                                                    | Present                                                 | Present                                                   | A venv usually depends on the base Python installation                                                                    |
| 8. Virtual Environments        | Activation                                   |                                              Shell-level convenience | Temporarily modifies environment variables and PATH                                                                              | Makes environment commands resolve first                                        | `.\.venv\Scripts\Activate.ps1`                             | `source .venv/bin/activate`                             | `source .venv/bin/activate`                               | Activation is optional; isolation exists before activation                                                                |
| 8. Virtual Environments        | Activation-free execution                    |                                      Explicit interpreter invocation | Calls the environment Python directly                                                                                            | Avoids shell-state ambiguity                                                    | `.\.venv\Scripts\python.exe`                               | `./.venv/bin/python`                                    | `./.venv/bin/python`                                      | Best choice for scripts, CI, and reproducible automation                                                                  |
| 8. Virtual Environments        | Deactivation                                 |                                                         Shell helper | Restores the previous PATH and environment variables                                                                             | Ends activation convenience                                                     | `deactivate`                                               | `deactivate`                                            | `deactivate`                                              | Deactivation does not delete the environment                                                                              |
| 8. Virtual Environments        | Environment deletion                         |                                                 Filesystem operation | Removes generated environment files                                                                                              | Resets a broken environment                                                     | `Remove-Item -Recurse -Force .venv`                        | `rm -rf .venv`                                          | `rm -rf .venv`                                            | Safe when dependencies are declared reproducibly                                                                          |
| 8. Virtual Environments        | Portability                                  |                                                 Environment property | Degree to which an environment can move between machines                                                                         | Determines whether copying is safe                                              | Not portable to Linux/macOS                                | Not portable to Windows/macOS                           | Not portable to Windows/Linux                             | Recreate the environment independently on every OS                                                                        |
| 9. Reproducibility             | Isolation                                    |                                                 Environment property | Prevents projects from sharing the same installed package directory                                                              | Reduces dependency interference                                                 | venv                                                       | venv                                                    | venv                                                      | Isolation does not guarantee reproducibility                                                                              |
| 9. Reproducibility             | `requirements.txt`                           |                                                  Common pip workflow | Text list of dependencies or pinned versions                                                                                     | Reinstalls a package set                                                        | Same concept                                               | Same concept                                            | Same concept                                              | May not fully describe platform-specific resolution                                                                       |
| 9. Reproducibility             | `pip freeze`                                 |                                                          pip feature | Snapshot of installed distributions                                                                                              | Captures one current environment state                                          | Same                                                       | Same                                                    | Same                                                      | May include incidental or transitive dependencies                                                                         |
| 9. Reproducibility             | `pyproject.toml`                             |                           Modern packaging standard, PEP 518/621 era | Declarative project, build, and dependency specification                                                                         | Records project intent                                                          | Same                                                       | Same                                                    | Same                                                      | Prefer for reusable projects and formal packaging                                                                         |
| 9. Reproducibility             | Lock file                                    |                                                        Tool-specific | Concrete resolved dependency graph                                                                                               | Improves repeatable installation                                                | May contain Windows-specific artifacts                     | May contain Linux-specific artifacts                    | May contain macOS-specific artifacts                      | One universal lock may not work for every platform and accelerator                                                        |
| 9. Reproducibility             | Environment manifest                         |                                                    Research practice | Record of OS, Python, packages, hardware, and commands                                                                           | Enables experiment reconstruction                                               | Required                                                   | Required                                                | Required                                                  | Record code revision, package versions, data hashes, seeds, hardware, and exact commands                                  |
| 9. Reproducibility             | Container                                    |                                           OS-level userspace package | Captures application dependencies above the kernel                                                                               | Improves deployment consistency                                                 | Often Linux containers through WSL2 or a VM                | Native Linux container ecosystem                        | Linux containers run inside a VM                          | Containers do not capture the host kernel, physical GPU, or host driver completely                                        |
| 9. Reproducibility             | WSL2                                         |                                                        2019–2020 era | Linux environment integrated into Windows                                                                                        | Runs Linux-first development and ML stacks on Windows                           | Available                                                  | Not applicable                                          | Not applicable                                            | Useful when Linux package and CUDA workflows are better supported than native Windows paths                               |
| 10. Array Computing            | NumPy                                        |                                                                 2006 | Scientific Python foundation based on homogeneous multidimensional arrays                                                        | Efficient numerical computing                                                   | Same high-level API                                        | Same high-level API                                     | Same high-level API                                       | Numerical semantics are portable; low-level performance backends differ                                                   |
| 10. Array Computing            | `ndarray`                                    |                                                    NumPy core object | Homogeneous N-dimensional array with shape, dtype, and strides                                                                   | Represents vectors, matrices, images, signals, and tensors                      | CPU array                                                  | CPU array                                               | CPU array                                                 | All elements follow one dtype interpretation                                                                              |
| 10. Array Computing            | Shape                                        |                                              Universal array concept | Length of every array axis                                                                                                       | Defines structural compatibility                                                | Same                                                       | Same                                                    | Same                                                      | Explicitly document axis meaning, not only dimensions                                                                     |
| 10. Array Computing            | `ndim`                                       |                                              Universal array concept | Number of axes                                                                                                                   | Distinguishes scalar, vector, matrix, batch, and sequence                       | Same                                                       | Same                                                    | Same                                                      | Array rank is structural, not semantic                                                                                    |
| 10. Array Computing            | dtype                                        |                                              Universal array concept | Binary representation of array elements                                                                                          | Controls precision, memory, and hardware support                                | Same conceptual dtypes                                     | Same conceptual dtypes                                  | Same conceptual dtypes                                    | `float32`, `float64`, `complex64`, and integer types have different cost and precision                                    |
| 10. Array Computing            | Stride                                       |                                                Memory-layout concept | Byte step required to move along an axis                                                                                         | Supports views and transposes without copying                                   | Same abstraction                                           | Same abstraction                                        | Same abstraction                                          | Non-contiguous layouts may affect performance or interoperability                                                         |
| 10. Array Computing            | Broadcasting                                 |                                                 NumPy-era array rule | Combines compatible shapes without explicitly duplicating values                                                                 | Concise vectorized computation                                                  | Same                                                       | Same                                                    | Same                                                      | Successful broadcasting does not guarantee semantically correct axis alignment                                            |
| 10. Array Computing            | Vectorization                                |                                        Numerical-programming pattern | Applies array operations instead of Python element loops                                                                         | Improves speed and exposes parallelism                                          | Same                                                       | Same                                                    | Same                                                      | Use vectorization where it preserves clarity and correct axis semantics                                                   |
| 10. Array Computing            | Reduction                                    |                                                      Array operation | Collapses one or more axes                                                                                                       | Computes sums, means, norms, and losses                                         | Same                                                       | Same                                                    | Same                                                      | Always specify or verify the reduction axis                                                                               |
| 10. Array Computing            | BLAS / LAPACK backend                        |                                             Native numerical library | Implements optimized linear algebra kernels                                                                                      | Determines much of NumPy's performance                                          | Wheel-selected backend                                     | Wheel or system-linked backend                          | Wheel-selected backend, possibly Apple-specific libraries | Identical NumPy code can have different performance across systems                                                        |
| 11. Labeled Data               | pandas                                       |                                                                 2008 | Labeled data-analysis library built around Series and DataFrame                                                                  | Cleaning, joining, grouping, time series, reporting                             | Same high-level semantics                                  | Same high-level semantics                               | Same high-level semantics                                 | Use pandas when labels, schemas, missing data, or relational operations are central                                       |
| 11. Labeled Data               | Series                                       |                                                   pandas core object | One-dimensional labeled data                                                                                                     | Represents a named analytical variable                                          | Same                                                       | Same                                                    | Same                                                      | Values align by index labels                                                                                              |
| 11. Labeled Data               | DataFrame                                    |                                                   pandas core object | Two-dimensional labeled table with potentially heterogeneous columns                                                             | Represents structured datasets                                                  | Same                                                       | Same                                                    | Same                                                      | A DataFrame is not merely a two-dimensional NumPy array                                                                   |
| 11. Labeled Data               | Index                                        |                                             pandas axis-label object | Explicit labels for rows or columns                                                                                              | Enables selection and alignment                                                 | Same                                                       | Same                                                    | Same                                                      | Label-based alignment can introduce missing values when indexes differ                                                    |
| 11. Labeled Data               | Missing-data semantics                       |                                              Analytical data concept | Representation of absent or unknown values                                                                                       | Supports cleaning and imputation                                                | Same API                                                   | Same API                                                | Same API                                                  | Missing values interact with dtype and aggregation rules                                                                  |
| 11. Labeled Data               | GroupBy                                      |                                            Split-apply-combine model | Groups observations and applies aggregation or transformation                                                                    | Statistical summaries and feature engineering                                   | Same                                                       | Same                                                    | Same                                                      | Check whether grouped output preserves, removes, or reorders indexes                                                      |
| 11. Labeled Data               | Merge / join                                 |                                                 Relational operation | Combines tables using keys or indexes                                                                                            | Integrates multiple datasets                                                    | Same                                                       | Same                                                    | Same                                                      | Validate key uniqueness and join cardinality                                                                              |
| 11. Labeled Data               | File ingestion                               |                                                OS-sensitive boundary | Converts stored files into tables                                                                                                | Reads CSV, Parquet, JSON, and databases                                         | Path, CRLF, encoding, and locking issues                   | Path, LF, locale, and permissions issues                | Path, encoding, ARM package compatibility                 | Specify UTF-8, parse rules, and absolute resolved paths                                                                   |
| 12. Differentiable Programming | JAX                                          |                                         Public open-source era: 2018 | NumPy-like numerical system centered on function transformations                                                                 | Automatic differentiation, compilation, vectorization, accelerator execution    | CPU; accelerator support depends on current backend matrix | Strong CPU, CUDA, ROCm, and TPU-oriented workflows      | CPU and Apple-related backend/plugin paths; no CUDA       | JAX is not merely NumPy running on a GPU                                                                                  |
| 12. Differentiable Programming | `jax.Array`                                  |                                                      JAX core object | Array participating in tracing, transformation, and device execution                                                             | Represents differentiable numerical values                                      | Device-dependent                                           | Device-dependent                                        | Device-dependent                                          | JAX semantics emphasize functional transformations and explicit devices                                                   |
| 12. Differentiable Programming | `jax.grad`                                   |                                                   JAX transformation | Converts a scalar-output function into its gradient function                                                                     | Reverse-mode automatic differentiation                                          | Same API                                                   | Same API                                                | Same API                                                  | The differentiated function must satisfy JAX transformation requirements                                                  |
| 12. Differentiable Programming | `jax.value_and_grad`                         |                                                   JAX transformation | Returns both function value and gradient                                                                                         | Avoids duplicate forward evaluation                                             | Same                                                       | Same                                                    | Same                                                      | Useful for optimization steps                                                                                             |
| 12. Differentiable Programming | `jax.jit`                                    |                                                   JAX transformation | Compiles a compatible function for optimized execution                                                                           | Reduces repeated execution cost                                                 | Backend-dependent                                          | Backend-dependent                                       | Backend-dependent                                         | Compilation overhead may dominate small or one-off workloads                                                              |
| 12. Differentiable Programming | `jax.vmap`                                   |                                                   JAX transformation | Automatically vectorizes a single-example function                                                                               | Adds batching without manual loops                                              | Same                                                       | Same                                                    | Same                                                      | Batch axes remain semantic choices                                                                                        |
| 12. Differentiable Programming | JVP                                          |                                  Automatic differentiation primitive | Jacobian-vector product                                                                                                          | Efficient forward-mode differentiation                                          | Same                                                       | Same                                                    | Same                                                      | Useful when inputs are fewer than outputs                                                                                 |
| 12. Differentiable Programming | VJP                                          |                                  Automatic differentiation primitive | Vector-Jacobian product                                                                                                          | Reverse-mode differentiation building block                                     | Same                                                       | Same                                                    | Same                                                      | Forms the conceptual basis of backpropagation                                                                             |
| 12. Differentiable Programming | Functional update                            |                                                JAX programming model | Returns modified arrays rather than mutating them in place                                                                       | Makes transformations and compilation tractable                                 | Same                                                       | Same                                                    | Same                                                      | Hidden mutation can break tracing assumptions                                                                             |
| 12. Differentiable Programming | Explicit random keys                         |                                                           JAX design | Random state passed as ordinary values                                                                                           | Makes randomness explicit and transformable                                     | Same                                                       | Same                                                    | Same                                                      | Split and propagate keys deliberately                                                                                     |
| 12. Differentiable Programming | XLA compilation                              |                                               JAX backend technology | Lowers numerical programs into optimized device executables                                                                      | Enables CPU, GPU, and TPU execution                                             | Support depends on platform packages                       | Most mature accelerator workflows                       | Backend coverage differs from Linux CUDA                  | Record backend, compiler, and device details                                                                              |
| 13. Deep Learning              | PyTorch                                      |                                            Development began in 2016 | Tensor and automatic-differentiation framework with model-building tools                                                         | Deep-learning research and deployment                                           | CPU and CUDA; other paths vary                             | CPU, CUDA, ROCm, distributed clusters                   | CPU and Apple MPS                                         | PyTorch is broader than a neural-network layer collection                                                                 |
| 13. Deep Learning              | `torch.Tensor`                               |                                                  PyTorch core object | Multidimensional value with dtype, device, layout, and optional gradient history                                                 | Represents model inputs, parameters, outputs, and states                        | CPU or supported accelerator                               | CPU or supported accelerator                            | CPU or MPS                                                | Device and dtype are part of tensor semantics                                                                             |
| 13. Deep Learning              | Autograd graph                               |                                    Dynamic differentiation structure | Records differentiable operations executed during the forward pass                                                               | Computes gradients by reverse-mode differentiation                              | Same concept                                               | Same concept                                            | Same concept                                              | Graph structure follows the operations actually executed                                                                  |
| 13. Deep Learning              | `requires_grad`                              |                                                      Tensor property | Marks values whose gradients should be tracked                                                                                   | Enables parameter optimization                                                  | Same                                                       | Same                                                    | Same                                                      | Avoid tracking gradients for data or inference-only tensors                                                               |
| 13. Deep Learning              | `loss.backward()`                            |                                                   Autograd operation | Propagates gradients from a scalar loss                                                                                          | Computes parameter gradients                                                    | Same                                                       | Same                                                    | Same                                                      | Gradients accumulate unless explicitly cleared                                                                            |
| 13. Deep Learning              | `nn.Module`                                  |                                            PyTorch model abstraction | Registers parameters, buffers, and submodules                                                                                    | Organizes trainable model structures                                            | Same                                                       | Same                                                    | Same                                                      | Use `state_dict` for explicit parameter serialization                                                                     |
| 13. Deep Learning              | Optimizer                                    |                                                 Training abstraction | Updates parameters using gradients and optimizer state                                                                           | Performs learning steps                                                         | Same API                                                   | Same API                                                | Same API                                                  | Save optimizer state when resumable training is required                                                                  |
| 13. Deep Learning              | Dataset                                      |                                                       Data interface | Defines how one sample is retrieved                                                                                              | Connects stored data to model training                                          | Same concept                                               | Same concept                                            | Same concept                                              | Keep OS-specific file logic outside model code                                                                            |
| 13. Deep Learning              | DataLoader                                   |                             Batching and multiprocessing abstraction | Loads, batches, shuffles, and parallelizes samples                                                                               | Feeds models efficiently                                                        | Uses spawn-style multiprocessing                           | Often uses fork by default                              | Uses spawn on modern Python                               | Write DataLoader code that is safe under spawn semantics                                                                  |
| 13. Deep Learning              | `model.train()`                              |                                                 Module-state control | Enables training-specific behavior                                                                                               | Activates dropout and training-mode normalization                               | Same                                                       | Same                                                    | Same                                                      | Does not itself enable gradients                                                                                          |
| 13. Deep Learning              | `model.eval()`                               |                                                 Module-state control | Enables evaluation-specific behavior                                                                                             | Disables dropout and changes normalization behavior                             | Same                                                       | Same                                                    | Same                                                      | Does not itself disable gradient recording                                                                                |
| 13. Deep Learning              | `torch.no_grad()`                            |                                                     Autograd context | Disables gradient graph recording                                                                                                | Reduces inference memory and overhead                                           | Same                                                       | Same                                                    | Same                                                      | Separate from model training/evaluation mode                                                                              |
| 13. Deep Learning              | CUDA                                         |                                          NVIDIA accelerator platform | GPU runtime and programming ecosystem                                                                                            | High-performance model training and inference                                   | Supported with matching builds and drivers                 | Most mature research/server path                        | Not supported on modern macOS                             | CUDA code is not portable to Apple MPS or AMD ROCm without abstraction                                                    |
| 13. Deep Learning              | ROCm                                         |                                             AMD accelerator platform | AMD GPU compute stack                                                                                                            | GPU training on supported AMD systems                                           | Limited relative to Linux                                  | Supported on selected Linux hardware and distributions  | Unavailable                                               | Verify exact GPU and software compatibility                                                                               |
| 13. Deep Learning              | MPS                                          |                                      Apple Metal Performance Shaders | Apple GPU backend                                                                                                                | PyTorch acceleration on Apple Silicon                                           | Unavailable                                                | Unavailable                                             | Available on supported systems                            | Some operations and performance characteristics differ from CUDA                                                          |
| 13. Deep Learning              | Distributed training                         |                                Multi-process and multi-device system | Coordinates computation across accelerators or machines                                                                          | Scales model training                                                           | Possible, but less dominant                                | Primary cluster and cloud ecosystem                     | Limited mainly to local workflows                         | Linux remains the dominant large-scale ML deployment environment                                                          |
| 14. Multiprocessing            | `spawn`                                      |                                                 Process-start method | Launches a fresh interpreter and imports the main module                                                                         | Safe cross-platform process creation                                            | Default                                                    | Available, not always default                           | Default on modern Python                                  | Always protect process creation with a main guard                                                                         |
| 14. Multiprocessing            | `fork`                                       |                                            Unix process-start method | Copies the parent process state into a child                                                                                     | Fast process creation                                                           | Not normal native behavior                                 | Common default                                          | No longer the normal safe default for many workflows      | Fork can inherit unsafe accelerator or thread state                                                                       |
| 14. Multiprocessing            | Main guard                                   |                                             Python execution pattern | Ensures code runs only in the original process                                                                                   | Prevents recursive child-process creation                                       | Essential                                                  | Recommended                                             | Essential                                                 | Use `if __name__ == "__main__":` in portable scripts                                                                      |
| 14. Multiprocessing            | Pickling                                     |                                            Serialization requirement | Converts Python objects for transfer to child processes                                                                          | Enables spawn-based workers                                                     | Required                                                   | Required under spawn                                    | Required                                                  | Functions and objects sent to workers must be serializable                                                                |
| 15. Interoperability           | pandas to NumPy                              |                                             Data-boundary conversion | Removes labels and produces an array representation                                                                              | Feeds numerical kernels                                                         | `df.to_numpy()`                                            | Same                                                    | Same                                                      | Labels and heterogeneous dtypes may be lost                                                                               |
| 15. Interoperability           | NumPy to pandas                              |                                             Data-boundary conversion | Wraps array values with labels                                                                                                   | Produces analytical tables                                                      | `pd.DataFrame(...)`                                        | Same                                                    | Same                                                      | Supply semantic column and index labels explicitly                                                                        |
| 15. Interoperability           | NumPy to PyTorch                             |                                           Array-to-tensor conversion | Creates a tensor from an ndarray                                                                                                 | Moves preprocessing output into a model                                         | `torch.from_numpy`                                         | Same                                                    | Same                                                      | CPU memory may be shared; mutation and contiguity matter                                                                  |
| 15. Interoperability           | PyTorch to NumPy                             |                                           Tensor-to-array conversion | Converts a CPU tensor without gradient tracking                                                                                  | Enables analysis and reporting                                                  | `.detach().cpu().numpy()`                                  | Same                                                    | Same                                                      | Device transfer and synchronization may occur                                                                             |
| 15. Interoperability           | NumPy to JAX                                 |                                                     Array conversion | Creates a JAX array from NumPy-compatible data                                                                                   | Enters JAX computation                                                          | `jnp.asarray`                                              | Same                                                    | Same                                                      | May trigger memory copy or device transfer                                                                                |
| 15. Interoperability           | JAX to NumPy                                 |                                            Device-to-host conversion | Materializes a standard ndarray                                                                                                  | Enables external analysis                                                       | `np.asarray(...)`                                          | Same                                                    | Same                                                      | Can synchronize the device and transfer data to host memory                                                               |
| 15. Interoperability           | DLPack                                       |                                      Cross-framework tensor standard | Shares tensor memory between compatible frameworks                                                                               | Reduces copies between JAX, PyTorch, and others                                 | Device-dependent                                           | Device-dependent                                        | Device-dependent                                          | Respect ownership, synchronization, dtype, device, and lifetime rules                                                     |
| 16. Hardware Backends          | CPU                                          |                                                    General processor | Executes scalar and vector instructions                                                                                          | Universal fallback and preprocessing platform                                   | Supported                                                  | Supported                                               | Supported                                                 | Record CPU architecture and numerical-library threading                                                                   |
| 16. Hardware Backends          | NVIDIA GPU                                   |                                             CUDA-capable accelerator | Executes massively parallel tensor operations                                                                                    | Deep-learning training and inference                                            | Native CUDA or WSL2                                        | Primary ecosystem                                       | Not available on modern Macs                              | Linux is normally the strongest target for large NVIDIA workloads                                                         |
| 16. Hardware Backends          | AMD GPU                                      |                                             ROCm-capable accelerator | Executes parallel GPU workloads                                                                                                  | Alternative accelerator stack                                                   | Limited                                                    | Supported on selected systems                           | Unavailable                                               | ROCm compatibility is narrower than generic Python portability                                                            |
| 16. Hardware Backends          | Apple GPU                                    |                                   Metal-based integrated accelerator | Uses Apple Silicon unified-memory GPU                                                                                            | Local model training and inference                                              | Not applicable                                             | Not applicable                                          | PyTorch MPS and platform-specific tooling                 | Apple GPU behavior is not equivalent to CUDA                                                                              |
| 16. Hardware Backends          | TPU                                          |                                         Specialized tensor processor | Optimized accelerator for large matrix computations                                                                              | Large-scale JAX and ML workloads                                                | Usually remote/cloud                                       | Cloud or managed Linux environments                     | Usually remote/cloud                                      | Treat TPU as a separate execution backend                                                                                 |
| 17. Cross-Platform Coding      | `pathlib`                                    |                                Python 3 standard-library abstraction | Object-oriented path handling                                                                                                    | Writes portable filesystem code                                                 | Produces Windows paths                                     | Produces POSIX paths                                    | Produces POSIX paths                                      | Prefer `Path.home() / "dev" / "project"` over string concatenation                                                        |
| 17. Cross-Platform Coding      | Environment variables                        |                                     Process-level key-value settings | Configure runtime behavior and external libraries                                                                                | Controls paths, credentials, devices, and performance                           | `$env:NAME` in PowerShell                                  | `$NAME`, `export NAME=value`                            | `$NAME`, `export NAME=value`                              | Read variables from Python using `os.environ` when possible                                                               |
| 17. Cross-Platform Coding      | Encoding                                     |                                                  Text representation | Maps characters to bytes                                                                                                         | Affects files, logs, and datasets                                               | Locale may differ                                          | Locale may differ                                       | Locale may differ                                         | Use UTF-8 explicitly                                                                                                      |
| 17. Cross-Platform Coding      | Device selection                             |                                             Runtime capability check | Chooses an available accelerator                                                                                                 | Keeps model code portable                                                       | CUDA or CPU                                                | CUDA, ROCm, TPU, or CPU                                 | MPS or CPU                                                | Select by capability rather than by OS name alone                                                                         |
| 17. Cross-Platform Coding      | Shell wrappers                               |                                           Thin platform entry points | Translate OS-specific startup into portable Python execution                                                                     | Launches the same Python application                                            | `.ps1` or `.bat`                                           | `.sh`                                                   | `.sh`                                                     | Keep scientific logic inside Python, not duplicated across shell scripts                                                  |
| 18. Research Workflow          | Data preprocessing                           |                                       Pre-model transformation layer | Cleans, standardizes, validates, and converts data                                                                               | Produces model-ready inputs                                                     | pandas / NumPy                                             | pandas / NumPy                                          | pandas / NumPy                                            | Record preprocessing versions and data hashes                                                                             |
| 18. Research Workflow          | Metadata handling                            |                                                  Semantic data layer | Stores filenames, labels, splits, provenance, and configuration                                                                  | Controls experiment organization                                                | pandas                                                     | pandas                                                  | pandas                                                    | Keep metadata separate from dense tensor computation                                                                      |
| 18. Research Workflow          | Numerical kernels                            |                                       Mathematical computation layer | Applies array operations and signal-processing transforms                                                                        | Computes features and metrics                                                   | NumPy                                                      | NumPy                                                   | NumPy                                                     | Use NumPy when gradients and accelerators are not required                                                                |
| 18. Research Workflow          | Differentiable scientific computation        |                                        Transformable numerical layer | Computes gradients, vectorized programs, and compiled kernels                                                                    | Scientific ML and custom optimization                                           | JAX                                                        | JAX                                                     | JAX with backend limitations                              | Choose JAX when function transformation is the main abstraction                                                           |
| 18. Research Workflow          | Model training                               |                                               Trainable-system layer | Builds models, losses, optimizers, and data pipelines                                                                            | Deep-learning experiments                                                       | PyTorch                                                    | PyTorch                                                 | PyTorch with MPS or CPU                                   | Choose PyTorch when model-centric workflows and ecosystem integration dominate                                            |
| 18. Research Workflow          | Evaluation                                   |                                                    Measurement layer | Compares outputs with targets or reference distributions                                                                         | Produces quantitative conclusions                                               | NumPy, pandas, JAX, or PyTorch                             | Same                                                    | Same                                                      | Move results into a stable reporting format with explicit units and aggregation rules                                     |
| 18. Research Workflow          | Experiment orchestration                     |                                                Process-control layer | Launches independent runs and records status                                                                                     | Makes large experiments fault-tolerant                                          | PowerShell/Bash/WSL wrappers                               | Bash or workflow systems                                | Bash/Zsh wrappers                                         | Run each model independently, record logs and return codes, and continue after failures                                   |
| 18. Research Workflow          | Failure tolerance                            |                                                   Workflow invariant | Prevents one failed experiment from terminating all others                                                                       | Preserves compute time and partial results                                      | Avoid failure-chained launchers                            | Avoid unqualified `set -e` in multi-model orchestration | Same as Linux                                             | Each run should produce a log, return code, checkpoint state, and structured status file                                  |
| 18. Research Workflow          | Reproducibility record                       |                                            Final experiment artifact | Complete description of execution context                                                                                        | Enables independent verification                                                | OS, Python, packages, GPU, drivers                         | OS, Python, packages, GPU, drivers                      | OS, Python, packages, MPS/CPU details                     | Record everything needed to recreate both software and data conditions                                                    |
| 19. Error Diagnosis            | Command not found                            |                                             Shell-resolution failure | The shell cannot locate the requested executable                                                                                 | Indicates PATH or installation problem                                          | Check `Get-Command` and aliases                            | Check `command -v`                                      | Check `command -v`                                        | Diagnose shell resolution before changing Python packages                                                                 |
| 19. Error Diagnosis            | Wrong pip location                           |                                       Interpreter-installer mismatch | pip belongs to another Python installation                                                                                       | Causes packages to install into the wrong environment                           | Common with multiple installations                         | Common with system and user Python                      | Common with Homebrew, pyenv, and system paths             | Use the selected interpreter with `-m pip`                                                                                |
| 19. Error Diagnosis            | `ModuleNotFoundError`                        |                                            Import-resolution failure | Running interpreter cannot locate the module                                                                                     | Indicates wrong environment, wrong import name, or missing installation         | Same diagnosis                                             | Same diagnosis                                          | Same diagnosis                                            | Check `sys.executable`, `pip show`, and the actual import name                                                            |
| 19. Error Diagnosis            | Permission denied                            |                                      Filesystem or ownership failure | Process cannot write or execute the target                                                                                       | Blocks environment creation or package installation                             | Check ACLs and protected paths                             | Check mode bits and ownership                           | Check mode bits, ownership, and security controls         | Do not solve a permission problem by blindly using administrator/root pip                                                 |
| 19. Error Diagnosis            | Compiler required                            |                                             Missing compatible wheel | pip is attempting a source build                                                                                                 | Requires native development tools                                               | Install MSVC tooling                                       | Install compiler and development packages               | Install Xcode Command Line Tools                          | First verify whether a compatible binary wheel should exist                                                               |
| 19. Error Diagnosis            | SSL verification failure                     |                                         Trust-chain or proxy failure | HTTPS certificate validation cannot complete                                                                                     | Blocks secure package download                                                  | Corporate proxy or trust-store issue                       | CA certificates, proxy, or clock issue                  | Keychain, proxy, or clock issue                           | Correct the trust environment rather than disabling verification                                                          |
| 19. Error Diagnosis            | GPU unavailable                              |                                           Backend or driver mismatch | Framework cannot access the expected accelerator                                                                                 | Causes CPU fallback or failure                                                  | CUDA build, driver, WSL, or device issue                   | CUDA/ROCm/container visibility issue                    | MPS support or operator availability issue                | Print framework device lists and backend versions                                                                         |
| 19. Error Diagnosis            | DataLoader recursion or hang                 |                                         Multiprocessing design error | Child processes re-import or inherit unsafe state                                                                                | Blocks training data delivery                                                   | Common without main guard                                  | Fork-related deadlocks or worker crashes                | Spawn and pickling issues                                 | Test with zero workers, then add workers gradually                                                                        |
| 19. Error Diagnosis            | Different numerical results                  |                                    Backend and determinism variation | Different kernels, compilers, hardware, or process scheduling alter output                                                       | Affects reproducibility                                                         | CUDA/CPU/build variation                                   | CUDA/ROCm/BLAS/cluster variation                        | MPS/CPU/ARM variation                                     | Record precision, seeds, deterministic settings, hardware, and backend                                                    |
| 20. Library Selection          | Choose NumPy                                 |                                            Problem-centered decision | Use when numerical arrays and scientific kernels are central                                                                     | Signal processing, linear algebra, numerical prototypes                         | Appropriate                                                | Appropriate                                             | Appropriate                                               | Best default when gradients and labels are not required                                                                   |
| 20. Library Selection          | Choose pandas                                |                                            Problem-centered decision | Use when labels, joins, missing data, schemas, or time series are central                                                        | Data cleaning and analytics                                                     | Appropriate                                                | Appropriate                                             | Appropriate                                               | Convert to arrays only at the numerical-model boundary                                                                    |
| 20. Library Selection          | Choose JAX                                   |                                            Problem-centered decision | Use when differentiable functions, compilation, and vectorization are central                                                    | Scientific ML and function-transform research                                   | Backend support must be checked                            | Strongest general accelerator support                   | Backend support differs from Linux                        | Best when pure numerical functions are the main abstraction                                                               |
| 20. Library Selection          | Choose PyTorch                               |                                            Problem-centered decision | Use when model modules, optimizers, DataLoaders, and ecosystem tools are central                                                 | Deep-learning model development                                                 | Strong local and CUDA workflows                            | Strongest server and cluster workflows                  | Strong Apple Silicon development path                     | Best when the model-training system is the main abstraction                                                               |
| 20. Operating-System Selection | Choose Windows                               |                                           Workload-centered decision | Use when Windows applications, desktop integration, or local NVIDIA workflows matter                                             | General development and workstation ML                                          | Native platform                                            | Not applicable                                          | Not applicable                                            | Use WSL2 when Linux-first tools provide better parity with deployment                                                     |
| 20. Operating-System Selection | Choose Linux                                 |                                           Workload-centered decision | Use when servers, clusters, containers, CUDA, ROCm, or HPC matter                                                                | Large-scale training and deployment                                             | Through WSL2 or remote servers                             | Native platform                                         | Through remote servers or VMs                             | Dominant environment for production and research-scale ML                                                                 |
| 20. Operating-System Selection | Choose macOS                                 |                                           Workload-centered decision | Use when Apple Silicon efficiency, local development, and MPS matter                                                             | Local prototyping and application development                                   | Not applicable                                             | Not applicable                                          | Native platform                                           | Do not expect CUDA compatibility                                                                                          |
| 21. Final Conceptual Summary   | Shell resolves interpreter                   |                                                  Universal invariant | The shell determines which Python executable starts                                                                              | Establishes runtime identity                                                    | PATH and PowerShell/cmd rules                              | PATH and Unix shell rules                               | PATH and Zsh/Bash rules                                   | Verify with `sys.executable`                                                                                              |
| 21. Final Conceptual Summary   | Interpreter runs modules                     |                                                  Universal invariant | Python uses its import system to run `pip`, `venv`, or other modules                                                             | Connects command execution to one environment                                   | Same                                                       | Same                                                    | Same                                                      | Use `python -m ...`                                                                                                       |
| 21. Final Conceptual Summary   | pip installs distributions                   |                                                  Universal invariant | pip installs package artifacts into the selected environment                                                                     | Manages dependencies                                                            | Platform-specific wheels                                   | Platform-specific wheels                                | Platform-specific wheels                                  | Bind pip to the intended Python                                                                                           |
| 21. Final Conceptual Summary   | venv isolates Python packages                |                                                  Universal invariant | A project receives its own site-packages and executable prefix                                                                   | Prevents cross-project dependency pollution                                     | `Scripts` layout                                           | `bin` layout                                            | `bin` layout                                              | Recreate, do not copy across platforms                                                                                    |
| 21. Final Conceptual Summary   | pandas adds labels                           |                                          Universal library hierarchy | Tables gain indexes, schemas, joins, and missing-data semantics                                                                  | Analytical data representation                                                  | Same                                                       | Same                                                    | Same                                                      | Use before dense numerical modeling                                                                                       |
| 21. Final Conceptual Summary   | NumPy adds efficient arrays                  |                                          Universal library hierarchy | Homogeneous values gain shape, dtype, strides, and vectorized operations                                                         | Scientific numerical computing                                                  | Same API                                                   | Same API                                                | Same API                                                  | Performance backend differs                                                                                               |
| 21. Final Conceptual Summary   | JAX transforms functions                     |                                          Universal library hierarchy | Numerical functions become differentiable, vectorized, compiled, or parallel                                                     | Transformable scientific computation                                            | Backend-dependent                                          | Broad backend support                                   | Backend-dependent                                         | Functional semantics are central                                                                                          |
| 21. Final Conceptual Summary   | PyTorch trains models                        |                                          Universal library hierarchy | Tensors, autograd, modules, optimizers, and data pipelines form a training system                                                | Deep learning                                                                   | CUDA/CPU                                                   | CUDA/ROCm/CPU                                           | MPS/CPU                                                   | Device-aware logic is required                                                                                            |
| 21. Final Conceptual Summary   | OS controls the platform edge                |                                                  Universal invariant | Operating system determines paths, processes, permissions, binaries, and hardware access                                         | Explains cross-platform differences                                             | Windows-specific edge                                      | Linux-specific edge                                     | macOS-specific edge                                       | Mathematical code is portable; execution infrastructure is not                                                            |
| 21. Final Conceptual Summary   | Reproducibility exceeds environment creation |                                                  Universal invariant | A venv alone does not capture data, code, hardware, seeds, or native backends                                                    | Enables trustworthy research                                                    | Full record required                                       | Full record required                                    | Full record required                                      | Treat the environment as generated output and preserve the complete experimental specification                            |







<br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br>









## References

  - [2025 - Nested Learning](https://research.google/blog/introducing-nested-learning-a-new-ml-paradigm-for-continual-learning/), Junior Researcher




<br><br><br><br>




