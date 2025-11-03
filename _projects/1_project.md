---
layout: page
title: 2025 - Thesis - Deep Learning
description: Latent Space, Multimodal, AI Center
img: assets/img/4.jpg
importance: 1
category: work
related_publications: true
---

<br>

## Diffusion Models

  - [📍 How Diffusions Work](https://x.com/docmilanfar/status/1977913980820848912)
  - [Workflow with your auto Research paper generation Tools](https://github.com/jhfnetboy/DSR-Research-Flow-Template/blob/main/README_EN.md)
  - [Model Structures](https://yiruyang2025.github.io/blog/2025/AI-Model-Structures-25/)
  - [2025 - Video models are zero-shot Learners and Reasoners](https://video-zero-shot.github.io/)


```
def compute_distillation_loss()
    cos_sim = (s * t).sum(dim=-1).clamp(-1 + eps, 1 - eps)
    geo_loss = torch.acos(cos_sim).mean()
    ...
    total_loss = ()
return total_loss, ce_loss.item(), kl_loss.item(), geo_loss.item()
```

 - [1/3] Stabilizing the Training, in **Latent Space**
   - [2024 - nGPT](https://arxiv.org/html/2410.01131v1)
   - [2025 - TAID](https://iclr.cc/virtual/2025/poster/29025)
   - [2025 - Why Stacking Sliding Windows Can't See Very Far](https://guangxuanx.com/blog/stacking-swa.html)

 - [2/3] Training Loss with different training set amounts
    - [What a real loss curve for 70B looks like (with y-axis labels)](https://x.com/haeggee/status/1962933627584413721)
    - [ASR SOTA](https://huggingface.co/spaces/hf-audio/open_asr_leaderboard)


  - [3/3] **Codebase - 2025 - Pre-Training Pipeline**

- `A Neural Network` is essentially a differentiable function approximator. Its difference from traditional linear regression lies not in the objective function, but in the `optimization method` and `the complexity of the function it can represent`

<br>

## Backpropagation


| Stage | Operation | Expression | Meaning |
|--------|------------|--------------------------|----------|
| **Forward Pass** | Compute layer outputs | $$ z^{(l)} = W^{(l)} a^{(l-1)} + b^{(l)}, \quad a^{(l)} = f(z^{(l)}) $$ | Obtain network predictions |
| **Compute Loss** | Compute error | $$ L = \tfrac{1}{2}\|\hat{y} - y\|^2 $$ | Measure output error |
| **Backward Pass** | Backpropagate from output layer | $$ \delta^{(L)} = (\hat{y} - y) \odot f'(z^{(L)}) $$ | Compute output-layer gradient |
|  | Propagate to previous layers | $$ \delta^{(l)} = (W^{(l+1)})^T \delta^{(l+1)} \odot f'(z^{(l)}) $$ | Compute hidden-layer gradients |
| **Gradient Computation** | Compute parameter gradients | $$ \frac{\partial L}{\partial W^{(l)}} = \delta^{(l)} (a^{(l-1)})^T $$ | Obtain weight gradients |
| **Update** | Update parameters | $$ W^{(l)} \leftarrow W^{(l)} - \eta \frac{\partial L}{\partial W^{(l)}} $$ | Optimize via gradient descent |

<br>

## Optimal Method as Below with Hash Value

| Problem                       | Original Complexity | Optimal Complexity | Optimal Method                 | Further Optimization      |
| ----------------------------- | ------------------- | ------------------ | ------------------------------ | ------------------------- |
| **Check Anagram**             | O(n)                |  O(n)             | Counter / Hash Map             | Cannot Be Improved        |
| **Dictionary Anagram Lookup** | O(M × N log N)      | O(M × N)         | Hash Value + Character Count Key | Significantly Optimizable |

<br>

## Hash Map and Graph for Optimization

| Analogy        | **Hash Map in Data Structures**                | **Dynamic Programming / Graph in Algorithms**                                 |
| -------------- | ---------------------------------------------- | ----------------------------------------------------------------------------- |
| **Essence**    | Trade space for time — achieve O(1) lookup.  | Trade state-graph computation for optimal solution — typically O(N × M).    |
| **Advantage**  | Globally optimal method for key lookup.        | Globally optimal framework for decision and optimization.                     |
| **Limitation** | Only applicable to key–value lookup problems.  | Only applicable to decomposable problems with optimal substructure.           |
| **Conclusion** | The most efficient in the **lookup** domain. | The most general but not universal in the **optimization/decision** domain. |



| **Dimension**               | **English Name** | **State Form** | **Typical Examples**             |
| --------------------------- | ---------------- | -------------- | -------------------------------- |
| **0D (Constant DP)**        | Constant DP      | `dp = x`       | Fibonacci (rolling optimization) |
| **1D (One-Dimensional DP)** | 1D DP            | `dp[i]`        | Climbing Stairs, LIS             |
| **2D (Two-Dimensional DP)** | 2D DP            | `dp[i][j]`     | LCS, Edit Distance               |



<br>

## Languages

| **Dimension**            | **Rust**                                                                | **Go (Golang)**                                                   | **C++**                                                  | **Python**                                         |
| ------------------------ | ----------------------------------------------------------------------- | ----------------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------- |
| `Essentially OOP`      | ✗ (OOP-like, but primarily functional)                                  | ✗ (Has OOP features, but fundamentally procedural and concurrent) | ✓ (Classic, strongly object-oriented)                    | ✓ (Dynamic, fully object-oriented)                 |
| **Programming Paradigm** | **Multi-paradigm:** Primarily functional + systems, supports OOP traits | **Procedural + concurrent**, limited OOP                          | **Multi-paradigm:** Strongly object-oriented + generic   | **Multi-paradigm:** Object-oriented + scripting    |
| **Type System**          | Static, compiled                                                        | Static, compiled                                                  | Static, compiled                                         | Dynamic, interpreted                               |
| **Memory Management**    | No GC; uses **ownership + borrow checker**                              | Automatic GC                                                      | Manual (new/delete) or smart pointers                    | Automatic GC                                       |
| **Concurrency Model**    | Lock-free, type-safe (“fearless concurrency”)                           | **Goroutines + channels** (CSP model)                             | Multithreading with manual locks                         | GIL limits true multithreading                     |
| **Performance**          | Nearly equal to C++                                                     | Close to C++, slightly slower (GC overhead)                       | Fastest native performance                               | Slowest (interpreted)                              |
| **Safety**               | Compile-time memory safety; prevents data races                         | Memory-safe but not thread-safe                                   | Very fast but error-prone (dangling pointers, overflows) | Safe but slow                                      |
| **Learning Curve**       | Steep (requires ownership understanding)                                | Easy (simple syntax)                                              | Steep (complex syntax and templates)                     | Easiest (beginner-friendly)                        |
| **Compile Speed**        | Slow                                                                    | Fast                                                              | Slow (especially for large projects)                     | None (interpreted)                                 |
| **Ecosystem**            | Young but growing fast (systems, embedded, backend)                     | Mature (cloud, DevOps, microservices)                             | Broadest (systems, games, embedded)                      | Broadest (AI, data science, web)                   |
| **Applications**         | System programming, secure backend, embedded, WebAssembly               | Cloud-native systems, microservices, networking                   | OS, game engines, graphics                               | AI/ML, scripting, automation, data analysis        |
| **Philosophy**           | **“Zero-cost abstraction”** — safety + performance                      | **“Pragmatic simplicity”** — simplicity + efficiency              | **“Total control”** — performance + flexibility          | **“Ease of use”** — simplicity + rapid prototyping |
| **Key Projects**         | Firefox, Tokio, AWS Firecracker                                         | Docker, Kubernetes, Terraform                                     | Unreal Engine, Chrome, TensorRT                          | PyTorch, TensorFlow, YouTube                       |

<br>

## Latent Space Structure

| Space                      | Core Definition                                                                        | Difference from Others                                                                              | Application Domains                                                  |
| -------------------------- | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `Hilbert Space`         | A complete `inner product` space where lengths, angles, and projections are well-defined | Serves as the foundational “perfect” geometric space; all others are generalizations or relaxations | Quantum mechanics, signal processing, optimization, machine learning |
| **Banach Space**           | A complete normed vector space, not necessarily with an inner product                  | Has length but no angles                                                                            | Non-Euclidean optimization, functional analysis                      |
| **Riemannian Manifold**    | Each point has a local inner-product space (tangent space)                             | Locally Hilbert, globally curved                                                                    | General relativity, geometric deep learning                          |
| **Symplectic Space**       | Equipped with an area-preserving bilinear form                                         | No distance, only conserved quantities                                                              | Classical mechanics, Hamiltonian systems                             |
| **Topological Space**      | Defined only by neighborhood relationships, no metric required                         | No notion of length or angle                                                                        | Generalized geometry, continuity, homotopy theory                    |
| **Metric Space**           | A set with a defined distance function d(x, y)                                         | Hilbert space is a special case                                                                     | Clustering, manifold learning, distance-metric learning              |
| **Probability Space**      | A measurable space (Ω, F, P) defining random events                                    | Describes the geometry of events                                                                    | Probability theory, information geometry, Bayesian inference         |
| **Information Manifold**   | A Riemannian manifold on probability distributions                                     | Uses Fisher information metric                                                                      | Statistical inference, information geometry, variational inference   |
| **Kähler / Complex Space** | Complex structure + symmetric geometry + metric                                        | Conformal generalization of Hilbert space                                                           | Quantum geometry, string theory, complex optimization                |

<br>

## Algorithms

```
├── I. Data Structures
│   ├── Stack, Queue, <HashMap>, LinkedList
│
├── II. Algorithmic Patterns 
│   ├── Two Pointers
│   ├── Sliding Window
│   ├── Prefix Sum
│   ├── Monotonic Stack / Queue
│   ├── Binary Search Patterns
│
├── III. Complex Algorithms  
│   ├── <Dynamic Programming (DP)>
│   ├── <Graph Theory (DFS/BFS/Dijkstra)>
│   ├── Recursion / Backtracking
│   ├── Greedy Algorithms
│   ├── Divide & Conquer
│
└── IV. Problem Integration
    ├── Hard composite problems
    ├── Algorithm design questions
```

## Diffusion, Stable Diffusion, Rectified Flow

| **Dimension**                            | **Vanilla Diffusion Model (DDPM / DDIM)**                                     | **Stable Diffusion (Latent Diffusion Model, LDM)**                                | **Rectified Flow (Flow Matching)**                                     |
| ---------------------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **Start Distribution**                   | Starts from pure Gaussian noise N(0, I)                                       | Starts from latent-space noise (compressed through an encoder)                    | Starts from any distribution point (usually N(0, I), but customizable) |
| **Generative Process**                   | Multi-step denoising: reverses the noise diffusion process (xₜ₋₁ = fθ(xₜ, t)) | Multi-step denoising in latent space (computationally cheaper) (zₜ₋₁ = fθ(zₜ, t)) | Continuous one-step flow: learns an ODE (dxₜ/dt = vθ(xₜ, t))           |
| **Mathematical Formulation**             | Discrete Markov chain (reverse SDE)                                           | Discrete SDE in latent space                                                      | Continuous ODE or flow field                                           |
| **Computational Complexity**             | Multi-step sampling (20–1000 steps)                                           | Multi-step but faster in latent space (20–50 steps)                               | Single continuous integration step                                     |
| **Advantages**                           | High generation quality; theoretically grounded                               | High resolution, lightweight, and controllable (supports text prompts)            | Fast convergence, continuous generation, minimal mode collapse         |
| **Limitations**                          | Slow sampling; many denoising steps required                                  | Strong dependence on encoder design and latent structure                          | Sensitive training stability; harder conditional control               |
| **Representative Papers / Applications** | DDPM (Ho et al., 2020); DDIM (Song et al., 2021)                              | LDM / Stable Diffusion (Rombach et al., CVPR 2022)                                | Flow Matching / Rectified Flow (Liu et al., ICLR 2023)                 |


<br>


## Optimization

| **Component / Technique**           | **Description**                                                                                 | **Implementation**                                                                |
| ----------------------------------- | ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **Optimizer**                       | Gradient-based weight updates with decoupled weight decay to improve stability on large models. | `AdamW` optimizer with `lr=2.6e-4` and default β=(0.9, 0.999); stable for transformer-like models. |
| **Learning-Rate Schedule**          | Smooth cosine decay to avoid abrupt gradient shocks after warm-up.                              | `get_cosine_schedule_with_warmup(opt, 1000, 10000)` — warm-up = 1 k steps, total = 10 k steps.     |
| **Warm-Up Phase**                   | Gradually increases learning rate and KL weight to prevent early divergence in distillation.    | Linear warm-up for both learning rate and λₖₗ (0 → 0.020584 during first 1000 steps).              |
| **Mixed-Precision Training**        | Uses half precision (`torch.amp.autocast`) to reduce GPU memory and improve throughput.         | Forward/backward passes wrapped in `autocast`, scaled by `GradScaler()` for numerical stability.   |
| **Gradient Clipping**               | Prevents exploding gradients in long sequences.                                                 | `torch.nn.utils.clip_grad_norm_(params, 1.0)` each iteration.                                      |
| **Loss Function (Multi-Objective)** | Balances semantic accuracy, distribution matching, and geometric alignment.                     | Total loss: **L = LCE + λₖₗ · LKL + λGeo · LGeo**, with λGeo = 0.969909 constant.                  |
| **CE Loss**                         | Supervised label alignment ensuring correct transcription semantics.                            | Cross-entropy between student predictions and true tokens.                                         |
| **KL Divergence**                   | Soft-target distillation to transfer probability distributions from teacher logits.             | `F.kl_div(log_softmax(student/T), softmax(teacher/T)) · T²`, T = 2.0.                              |
| **Riemannian Geodesic Loss**        | Aligns feature geometry on curved manifold instead of flat Euclidean MSE.                       | Geodesic distance = `acos(cos_sim)` between normalized hidden states.                              |
| **Model Architecture (Student)**    | Lightweight CNN + Transformer hybrid for speech sequence modeling.                              | Two 1-D Conv layers → 6 Transformer encoder blocks → linear output head.                           |
| **Teacher Model**                   | Provides target logits and hidden features for distillation.                                    | Frozen `Whisper-large-v2` (FP16) encoder-decoder model.                                            |

<br>

```
distil_run_cell2.7.2/
│
├── tb/                           ← TensorBoard log files
│   ├── events.out.tfevents...    
│
├── adapter_final/                ← Final trained student model
│   └── student_model.pt
│
├── checkpoint.pt                 ← Intermediate checkpoint (used if training was interrupted)
├── training_history.json         ← Recorded training and validation loss curves
├── best_params.json              ← Best hyperparameter record (e.g., kl_weight, geo_weight)
└── training_config.json          ← Training configuration and setup details
```

<br>

## Structure

```
Machine Learning Fundamentals
      │
      ├── Data → Representation → Optimization → Generalization
      │       ├─ Focus: Data quality, bias mitigation, and representation learning
      │       ├─ Link to Gemini: multimodal data fusion (text, audio, vision, code)
      │       └─ Goal: Learn unified latent spaces that enable reasoning across modalities
      │
      ├── Deep Learning (CNN / RNN / Transformer)
      │       ├─ Forward & backward propagation as differentiable computation graphs
      │       ├─ Initialization, normalization, regularization → stability & convergence
      │       ├─ Loss design + learning rate scheduling → control of optimization dynamics
      │       └─ Transformer family as universal sequence learners (foundation for Gemini)
      │
      ├── Optimization & Geometry
      │       ├─ Gradient-based optimization viewed as navigating the loss landscape
      │       ├─ Flat vs. sharp minima → generalization and robustness trade-offs
      │       ├─ Riemannian geometry in embedding space → alignment on curved manifolds
      │       └─ Connection: Gemini’s embedding consistency and representation curvature
      │
      ├── Model Compression & Distillation
      │       ├─ Knowledge transfer from large to small models (teacher → student)
      │       ├─ Soft vs. hard labels → probabilistic vs. symbolic supervision
      │       ├─ LoRA / Adapter-based fine-tuning → parameter-efficient adaptation
      │       ├─ Trade-offs: accuracy ↔ latency ↔ memory footprint ↔ energy efficiency
      │       └─ Relevance: LearnLM and Gemini use adapter-tuned submodels for learning tasks
      │
      └── ML Engineering & Responsible AI
              ├─ Data pipelines, reproducibility, evaluation, and continuous integration
              ├─ Monitoring, checkpointing, scalable deployment on distributed accelerators
              ├─ Safety alignment and interpretability — understanding model decisions
              ├─ Evaluation beyond accuracy: robustness, fairness, value alignment
              └─ Ethical ML engineering: accountability and transparency in large systems
```



## Time

| Big-O          | Name              | Typical Example                                |
| -------------- | ----------------- | ---------------------------------------------- |
| **O(1)**       | Constant time     | Accessing array element                        |
| **O(log n)**   | Logarithmic time  | Binary search                                  |
| **O(n)**       | Linear time       | Single loop through array                      |
| **O(n log n)** | Linearithmic time | Merge sort, Quick sort                         |
| **O(n²)**      | Quadratic time    | Nested loops, Bubble sort                      |
| **O(n³)**      | Cubic time        | Triple nested loops                            |
| **O(2ⁿ)**      | Exponential time  | Subset / permutation generation                |
| **O(n!)**      | Factorial time    | Traveling Salesman, N-Queens                   |
| **O(bᵈ)**      | Branching search  | DFS in state tree with branching b and depth d |

<br>

```
O(n):            O(n log n):                 O(n²):
loop → → →       divide → sort → merge      double loop → compare all
(one pass)       (log layers × n work)       (each pair compared)
linear scan       merge / quick sort         bubble / selection sort
```

## Space

| Big-O        | Name              | Typical Example                        | 
| ------------ | ----------------- | -------------------------------------- | 
| **O(1)**     | Constant space    | In-place swap, variable assignment     |
| **O(log n)** | Logarithmic space | Recursive binary search                | 
| **O(n)**     | Linear space      | Storing array, dynamic programming 1-D | 
| **O(n²)**    | Quadratic space   | 2-D matrix, Floyd-Warshall DP          | 
| **O(n³)**    | Cubic space       | 3-D DP table                           | 
| **O(2ⁿ)**    | Exponential space | Memoization of all subsets             | 


<br>

## Data Loader

| Stage                     | Code Section                                          | Padding Applied  | Explanation                                             |
| ------------------------- | ----------------------------------------------------- | ---------------- | ------------------------------------------------------- |
| ① Dataset structure check | `os.walk()` file scan                                 |No             | Only scans file names, counts, and sizes.               |
| ② Load audio–text pairs   | `pairs = load_audio_text_pairs(DATA_DIR)`             | No             | Generates file paths, no tensor involved.               |
| ③ Build Dataset           | `dataset = LibriSpeechLocalDataset(pairs, processor)` | Not yet       | Each sample is returned separately, no unified length.  |
| ④ Build DataLoader        | `train_loader = DataLoader(...)`                      | Yes (here)     | Padding is applied when combining samples into a batch. |
| ⑤ Train model             | `for step, batch in enumerate(train_loader):`         | Already padded | Batch tensors have equal dimensions for training.       |



<br>

## Protocol and Ports

```
[You: MacBook]  ←→  [Encrypted Tunnel (AES)]  ←→  [Mac Studio Server]
         ↕                             ↕
   ssh user@ip_address         sshd (daemon listening on port 22)
```

<br>

| Protocol | Port | Purpose |
|-----------|------|----------|
| HTTP | 80 | Web traffic |
| HTTPS | 443 | Secure web traffic |
| FTP | 21 | File transfer |
| **SSH** | **22** | Secure remote shell |

<br>

| Function              | Command Example                                  | Description                                                   |
| --------------------- | ------------------------------------------------ | ------------------------------------------------------------- |
| `Remote Login`    | ssh user@192.xxx.x.xx                          | Open a command-line session on a remote computer              |
| `File Transfer`      | scp file.txt user@host:/path/                  | Securely copy a file to a remote machine                      |
| `Port Forwarding`    | ssh -L 8080:localhost:80 user@host             | Map a remote port to a local port through an encrypted tunnel |
| Passwordless Login | Public key authentication (`~/.ssh/id_rsa.pub`)  | Automatically authenticate using key pairs                    |
| Automation Control | Use SSH to execute commands or sync data in bulk | Common in DevOps or HPC environments                          |


<br>

## Optimizers

| Era | Optimizer | Year | Core Innovation | Key Equation / Concept | Limitation Solved | Remarks |
|-----|------------|------|-----------------|------------------------|------------------|----------|
| **Classical GD** | **Gradient Descent (GD)** | 1951 | Update weights along the negative gradient direction | $$ w_{t+1} = w_t - \eta \nabla L(w_t) $$ | None (too simple) | Foundation of all optimizers |
|  | **Stochastic Gradient Descent (SGD)** | 1983 | Uses random mini-batches to improve efficiency | $$ \nabla L(w_t) \approx \frac{1}{\lvert B \rvert} \sum_{i \in B} \nabla L_i(w_t) $$ | High variance and slow convergence | Enables online / large-scale learning |
| **Momentum Era** | **SGD + Momentum** | 1989 | Adds velocity term to accumulate past gradients | $$ v_t = \beta v_{t-1} + (1-\beta)\nabla L(w_t), \quad w_{t+1} = w_t - \eta v_t $$ | Oscillations in narrow valleys | Faster convergence, physics-inspired |
|  | **Nesterov Accelerated Gradient (NAG)** | 1991 | Looks ahead using gradient of estimated future position | $$ v_t = \beta v_{t-1} + (1-\beta)\nabla L(w_t - \eta \beta v_{t-1}) $$ | Overshooting in Momentum | Smoother convergence and stability |
| **Adaptive Learning** | **Adagrad** | 2011 | Per-parameter adaptive learning rate | $$ G_t = \sum_{\tau=1}^{t} g_\tau^2, \quad \eta_{t,i} = \frac{\eta}{\sqrt{G_{t,i}}+\epsilon} $$ | Manual learning rate tuning | Excellent for sparse features (NLP) |
|  | **RMSProp** | 2012 | Exponentially weighted moving average of squared gradients | $$ v_t = \rho v_{t-1} + (1-\rho)g_t^2, \quad w_{t+1} = w_t - \frac{\eta}{\sqrt{v_t+\epsilon}}g_t $$ | Adagrad’s decaying rate problem | Stable for non-stationary objectives |
| **Modern Standard** | **Adam** | 2014 | Combines Momentum and RMSProp | $$ m_t = \beta_1 m_{t-1} + (1-\beta_1)g_t, \quad v_t = \beta_2 v_{t-1} + (1-\beta_2)g_t^2 $$ $$ \hat{m}_t = \frac{m_t}{1-\beta_1^t}, \quad \hat{v}_t = \frac{v_t}{1-\beta_2^t}, \quad w_{t+1} = w_t - \eta \frac{\hat{m}_t}{\sqrt{\hat{v}_t}+\epsilon} $$ | Gradient noise and curvature imbalance | Default optimizer for most deep networks |
|  | **AdamW** | 2017 | Decouples weight decay from gradient update | $$ w_{t+1} = w_t(1-\eta\lambda) - \eta \frac{m_t}{\sqrt{v_t}+\epsilon} $$ | L2 regularization bias in Adam | Default for Transformer / LLM training |
| **Geometry-Aware & Large Batch** | **LARS (Layer-wise Adaptive Rate Scaling)** | 2018 | Layer-wise adaptive learning rate | $$ \eta_l = \eta \frac{\|w_l\|}{\|g_l\|+\epsilon} $$ | Scale mismatch in large-batch training | Used in ResNet / ImageNet large-batch setups |
|  | **LAMB (Layer-wise Adaptive Moments)** | 2019 | Extends LARS with Adam-style moments | $$ r_t = \frac{\|w_t\|}{\|\hat{m}_t / (\sqrt{\hat{v}_t}+\epsilon)\|}, \quad w_{t+1}=w_t - \eta r_t \frac{\hat{m}_t}{\sqrt{\hat{v}_t}+\epsilon} $$ | Poor scaling of Adam for huge batches | Core optimizer for BERT, GPT |
| **Variance Rectification & Belief Models** | **RAdam** | 2019 | Rectifies variance of adaptive learning rate | $$ \eta_t = \eta \frac{\sqrt{(1-\beta_2^t)/(1-\beta_2)}}{\sqrt{v_t}+\epsilon} $$ | Instability in early training | More robust warm-up-free Adam |
|  | **AdaBelief** | 2020 | Tracks belief in gradient direction | $$ v_t = \beta_2 v_{t-1} + (1-\beta_2)(g_t - m_t)^2 $$ | Gradient over-smoothing | Better generalization for small datasets |
| **Second-Order & Natural Gradient** | **K-FAC (Kronecker-Factored Approximate Curvature)** | 2015–2023 | Approximates curvature via blockwise Kronecker products | $$ F^{-1} \approx A^{-1} \otimes B^{-1}, \quad w_{t+1} = w_t - \eta F^{-1}\nabla L $$ | Ignores curvature in SGD/Adam | Faster convergence, heavy memory use |
|  | **Shampoo** | 2021 | Matrix preconditioning per layer | $$ G_t = \sum_{\tau=1}^{t} g_\tau g_\tau^\top, \quad W_{t+1}=W_t - \eta G_t^{-1/2}\nabla L $$ | Slow convergence on ill-conditioned loss | Improves conditioning for large models |
| **Modern LLM Optimizers** | **Lion** | 2023 | Momentum with sign-based updates | $$ w_{t+1} = w_t - \eta \, \text{sign}(\beta_1 m_t + (1-\beta_1)g_t) $$ | Over-adaptation of Adam | Efficient and strong generalization for LLMs |
|  | **Sophia** | 2023 | Second-order curvature-aware optimizer | $$ w_{t+1} = w_t - \eta \frac{g_t}{\sqrt{h_t+\epsilon}}, \quad h_t \approx \text{diag}(H_t) $$ | Slow convergence in large-scale Adam | State-of-the-art for Transformer training |



<br>

## Riemannian Projector, Geodesic Loss

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
Student (<Structure-free> Student from the teacher + LoRA adapters)
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
  LoRA Adapter Checkpoint
        ↓
Evaluation (WER / RTF / Memory)


s_hid = student_proj(s_out.encoder_last_hidden_state)
t_hid = normalize(t_out.encoder_last_hidden_state)
geo = geodesic_distance_on_sphere(s_hid, t_hid)
```

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


## Background Knowledge

## RL On Diffusion

I. Base Diffusion Backbone (Generative Prior)
```
Input (x₀ = real data sample: image, trajectory, audio, 3D scene)
      ↓
Forward Diffusion Process (adds Gaussian noise)
      ↓
x₁ ← √α₁·x₀ + √(1−α₁)·ε₁
x₂ ← √α₂·x₁ + √(1−α₂)·ε₂
⋮
x_T ≈ pure Gaussian noise N(0, I)
      ↓
Reverse Denoising Process (parameterized by neural network ε_θ)
      ↓
x_{t−1} = (x_t − √(1−α_t)·ε_θ(x_t, t, cond)) / √α_t + η·σ_t
      ↓
UNet / Transformer backbone → learns to reconstruct x₀
```


II. Policy Representation via Diffusion

```
Environment State s_t
      ↓
Noise z_t ~ N(0, I)
      ↓
Diffusion Policy Network ε_θ(s_t, z_t, t)
      ↓
Sample Action a_t = Denoise(z_t | s_t)
      ↓
Execute Action in Environment → Receive Reward r_t
      ↓
Collect Trajectory τ = {s_t, a_t, r_t}
```

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project1_6.jpg" alt="Project 1 Visualization" width="75%">
</p>


IV. Reward-Guided Diffusion Training (Diffusion Policy Optimization)

```
For each episode:
  1. Sample noise x_T ~ N(0, I)
  2. Run reverse diffusion (ε_θ) conditioned on state s_t
  3. Generate predicted action trajectory x₀
  4. Execute in environment → collect reward R
  5. Compute loss:
         L_total = L_diffusion + λ·L_RL
         L_RL = − E[R(τ)]
  6. Backpropagate through ε_θ network
```

<br>


## Diffusion Policy, Decision Diffuser

```
Random Noise in Action Space
      ↓
Diffusion or Flow Process
      ↓
Denoising Steps / Continuous Flow
      ↓
Policy Network predicts εθ(x_t,t)
      ↓
Clean Action Sequence (Optimal Trajectory)
      ↓
Execute in Environment (Robotics / Control)
```


| Function | Formula | Derivative | Core Idea | Usage / Notes |
|-----------|----------|-------------|------------|----------------|
| **Sigmoid** | $$f(x) = \frac{1}{1 + e^{-x}}$$ | $$f'(x) = f(x)\,[1 - f(x)]$$ | Smooth bounded mapping (0, 1) | Common in probabilistic outputs |
| **Tanh** | $$f(x) = \tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}$$ | $$f'(x) = 1 - f(x)^2$$ | Zero-centered output | Improves symmetry over Sigmoid |
| **ReLU** | $$f(x) = \max(0,\,x)$$ | $$f'(x)=\begin{cases}1,&x>0\\0,&x\le0\end{cases}$$ | Sparse and efficient | Fast convergence, stable training |
| **Leaky ReLU** | $$f(x)=\max(\alpha x,\,x)$$ | piecewise constant | Avoids dead neurons | Small negative slope for x < 0 |
| **Swish / SiLU** | $$f(x)=x\,\sigma(x),\ \sigma(x)=\frac{1}{1+e^{-x}}$$ | $$f'(x)=\sigma(x)+x\,\sigma(x)[1-\sigma(x)]$$ | Smooth, self-gated ReLU | Used in Google EfficientNet |
| **Mish** | $$f(x)=x\,\tanh(\ln(1+e^x))$$ | smooth | Non-monotonic, better gradient flow | Used in YOLOv4, ResNet variants |
| **GELU** | $$f(x)=x\,\Phi(x),\ \Phi(x)\text{: Gaussian CDF}$$ | smooth | Probabilistic gating | Default in Transformers (BERT, GPT) |
| **JumpReLU (DeepMind)** | $$f(x)=\max(0,\,x-j),\ j\text{ learned}$$ | piecewise constant | Learnable sparsity threshold | Used in Sparse Autoencoders for interpretability |
| **Softmax** | $$f_i(x)=\frac{e^{x_i}}{\sum_j e^{x_j}}$$ | — | Converts logits → probabilities | Standard output for classification |




<br>

## Learning Rates

| Trend                                  | Description                                     | Representative Systems                |
| -------------------------------------- | ----------------------------------------------- | ------------------------------------- |
| **Cosine + Warmup → Standard Default** | Most stable across architectures.               | ViT, GPT-J, Whisper, Stable Diffusion |
| **Adaptive + Restart Hybrids**         | Combine SGDR + ReduceLROnPlateau.               | DeepSpeed, Megatron-LM, PaLM 2        |
| **Optimizer-Integrated Scheduling**    | Scheduler coupled with optimizer (AdamW, LAMB). | GPT-4, Gemini 1.5, Claude 3           |
| **Noisy / Stochastic Schedules**       | Inject noise to encourage flat minima.          | Google Brain NAS, RL-based training   |
| **Dynamic Data-Aware LR Control**      | LR adapted by validation loss or gradient norm. | Reinforcement fine-tuning (RLHF, PPO) |


<br>

## Scaling Law

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

## Generalization and Regularization

```
Underfitting:     Overfitting:        Good Embedding:
 • • • • •        ●●●  ○○○  ▲▲▲       ● ●   ○ ○   ▲ ▲
 ○ ○ ○ ○ ○        (tight) (tight)      (clear but smooth)
 ▲ ▲ ▲ ▲ ▲        val points outside   val & train overlap
```

| **Principle**                                                                        | **Intuition**                                                                                                                                                                                                   |
| ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Regularization** = adding controlled noise or constraints to prevent memorization. | Introduces noise or limits (e.g., dropout, weight decay, data augmentation) so the model learns general patterns instead of memorizing the training set. <br> |
| **Overfitting** = perfect fit on training data, poor generalization.                 | The model minimizes training loss too well, capturing noise instead of true structure — leads to poor performance on unseen data. <br>                                       |
| **Goal** = flatter minima + smoother decision boundaries.                            | Seek regions in the loss landscape where small parameter changes do not greatly affect loss — resulting in more stable, generalizable models. <br>              |


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



## Optimization for Training

| Stage                   | **Method**                                  | **Purpose / Effect**                                        |
| --------------------------- | ------------------------------------------- | ----------------------------------------------------------- |
| **Initialization Stage**    | Xavier / He initialization                  | Avoid falling into poor regions at the start                |
| **Early Exploration Stage** | Large learning rate + Momentum              | Maintain global exploration ability                         |
| **Mid Convergence Stage**   | Adam / RMSProp + Cosine Annealing           | Ensure smooth descent and curvature adaptation              |
| **Late Fine-tuning Stage**  | SAM / Entropy-SGD / Weight Decay            | Locate flat minima and enhance generalization               |
| **During Training**         | Mini-batch noise + Dropout                  | Prevent getting stuck at saddle points                      |
| **Architectural Level**     | Residual connections / Normalization layers | Improve gradient flow and smooth the optimization landscape |


<br>

## Normalization and Regularization in different Model Structures

| Item              | **L1 Regularization**                                 | **L2 Regularization**                                |
| ----------------- | ----------------------------------------------------- | ---------------------------------------------------- |
| **Shape**         | Diamond-shaped constraint                             | Circular constraint                                  |
| **Optimum Point** | Usually lies on the coordinate axes (sparse solution) | Usually lies on the circle (continuous shrinkage)    |
| **Result**        | Some weights are “cut” to exactly 0                   | All weights are smoothly reduced but remain non-zero |


<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project1_5.jpg" alt="Project 1 Visualization" width="75%">
</p>



| Model Example          | **Normalization**                                                                                                           | **Regularization**                                                                                                           | **Essence & How It Works**                                                                                                            |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **CNN (e.g., ResNet)** | **Batch Normalization** — normalizes activations within a mini-batch to stabilize gradients and speed up convergence.       | **Weight Decay + Dropout** — penalizes large weights and randomly drops neurons to reduce overfitting.                       | Normalization equalizes feature scales during training, while *Regularization* constrains model capacity to improve generalization. |
| **Transformer / LLM**  | **Layer Normalization** — normalizes hidden states across features to maintain stable activations in deep attention layers. | **Attention Dropout + L2 Regularization** — randomly masks attention links and adds weight penalties to prevent overfitting. | Normalization stabilizes internal representations; regularization prevents memorization of training data.                             |
| **MLP**                | **Input Standardization** — rescales each input feature to zero mean and unit variance.                                     | **L2 Regularization (Ridge)** — discourages large parameter magnitudes for smoother mappings.                                | Normalization improves numerical stability; regularization enforces simpler models with better generalization.                        |


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

## Single card peak ~ 13–15 GB VRAM -> Start your Experiment with FP16 + AMP

Whisper large-v3 has the same architecture as the previous large and large-v2 models, except for the following minor differences:

1. The spectrogram input uses 128 Mel frequency bins instead of 80
2. A new language token for Cantonese
3. Each token output by `Attention carries global context information`, while `FFN applies "fine-tuning" or "feature combination" to each token` to improve the feature quality at each position

<br>


```
Transformer Assembly Line  
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


```
Activation Function Characteristics Comparison
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

Input Features From Whisper

- [librosa.feature.melspectrogram](https://librosa.org/doc/main/generated/librosa.feature.melspectrogram.html)

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project1_3.jpg" alt="Project 1 Visualization" width="40%">
</p>

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project1_4.jpg" alt="Project 1 Visualization" width="50%">
</p>

<br>

## Fourier Transform

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


```
Teacher (Whisper-large-v2)                     Student
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


  - Audio Signal Characteristics - Redundancy -> why can be **compressed** to T~499 frames

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


- Always remember to do **Automatic checkpoint saving**
- !pip install -U bitsandbytes>=0.41.0
- Put Your Teacher model on CPU
- MIN_DURATION = 1.0
- MAX_DURATION = 30.0 # Same as **Whispe maximum acceptance length**


<br>

**Orignial LoRA Paper**

```
ΔW = A · B -> only low-rank increments are made to W_q and W_v in the attention
```

<br>

## Choices of LoRA Injection

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

## Temperature

- **Initial pilot temperature**: `T =  `  
- **Search range**: `[ ]`  
- **Optuna hyperparameter**: include `temp` as a tunable parameter  
- **Guidance**: prevent over-smoothing (i.e. avoid `T > 5`)


<br>


## Hard vs. Soft Labels in Knowledge Distillation

- **Hard Labels**: one-hot vectors from ground truth  
  `y = [0, …, 1, …, 0]`  
  • Strong supervision → binary certainty  
  • Forces correct classification

- **Soft Labels**: teacher’s softmax outputs  
  `p_teacher = [0.6, 0.3, 0.1]`  
  • Confidence & uncertainty  
  • Encodes inter-class similarity


<br>

## Why num_workers Affects GPU Performance

The num_workers parameter in PyTorch DataLoader controls the number of CPU processes responsible for data loading and preprocessing. This directly impacts GPU utilization through data pipeline optimization

<br>

## Performance Comparison

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

<br>

**KL Distillation Loss - Soft Supervision**

KL Distillation Loss compares the teacher’s and student’s posterior distributions over labels at each time-step in latent space

  - Soft Distribution Matching
  - Preference Transfer
  - Capturing Uncertainty


Since the softmax outputs retain probabilities for all tokens, the KL term transfers the teacher’s uncertainty patterns—e.g., when the teacher is unsure between two phonemes, the student learns to mirror that ambiguity


**Total Loss**

$$
L_{\text{total}}
= L_{\mathrm{CE}}
+ 0.xx\,T^{2}\,L_{\mathrm{KD}}
+ \alpha\,L_{\mathrm{hidden\_align}}
$$



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

## Hyperparameter Optimization


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

<br>


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


| **Stage** | **Process** | **Mathematical Meaning** | **Intuitive Explanation** |
|------------|--------------|---------------------------|----------------------------|
| **Forward Process** | Add Gaussian noise to clean trajectories $$(x_0 \rightarrow x_T)$$. | $$q(x_t \mid x_{t-1}) = \mathcal{N}(\sqrt{1 - \beta_t} \, x_{t-1}, \, \beta_t I)$$ | Gradually “scrambles” a human driving path — this step is fixed and not learned. |
| **Reverse Process** | Learn to denoise noisy trajectories $$(x_T \rightarrow x_0)$$ conditioned on perception $$c$$. | $$p_\theta(x_{t-1} \mid x_t, c) = \mathcal{N}(\mu_\theta(x_t, t, c), \Sigma_\theta)$$ | The model learns to “restore order from noise,” reconstructing human-like trajectories that fit the scene. |
| **Prior-Guided Learning** | Add an Anchored Gaussian prior for realistic initialization. | $$x_T \sim \mathcal{N}(\mu_{anchor}, \sigma^2 I)$$ | The model doesn’t predict trajectories directly—it learns to move toward the probability distribution of human driving behaviors. |


<br>


## Temporal Alignment Leakage

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



