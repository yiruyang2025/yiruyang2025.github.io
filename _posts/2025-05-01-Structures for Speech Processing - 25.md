---
layout: post
title: Structures for Speech Processing - 25
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

- Neural Structures + Signal Terms

<br><br>

**CNN**

<br>

**RNN**

<br>

**LSTM**

<br>

**GRU**

<br>

**Purned LSTM**

<br>

**Transformer**

<br>

**Conformer**

<br>

**Flow Matching**

<br>

**Embedding Space**

<br>

**Signal Processing**

<br><br>



```
Traditional RNN Seq2Seq                           Transformer
─────────────────────                            ──────────────

Input Sequence                                   Input Sequence
x₁, x₂, ..., xₙ                                  x₁, x₂, ..., xₙ
     │                                               │
     ▼                                               ▼
Sequential Processing                             Parallel Processing
h₁ → h₂ → ... → hₙ                               All positions simultaneously
(SLOW, O(n) steps)                               (FAST, O(1) steps)
     │                                               │
     ▼                                               ▼
RNN Encoder                                       Transformer Encoder
Hidden states: h₁, h₂, ..., hₙ                   Self-Attention + FFN
     │                                               │
     ▼                                               ▼
Attention Mechanism                               Encoder-Decoder Attention
     │                                               │
     ▼                                               ▼
RNN Decoder                                       Transformer Decoder
y₁ → y₂ → ... → yₘ                               Masked Self-Attention + FFN
(Sequential generation)                           (Parallel training possible)
```

<br>

```
x₁ → x₂ → ... → xₙ
 ↓     ↓        ↓
h₁    h₂     ... hₙ
       ↓（soft attention）
   context = Σ αₜ · hₜ
       ↓
   Decoder y₁, y₂, ...
```

<br>



$$
\begin{aligned}
\text{Soft Attention:}\quad
&\mathbf{c}_{\text{soft}} \;=\; \sum_{t=1}^{n} \alpha_t\,\mathbf{h}_t,
\qquad
\alpha_t \;=\; \frac{\exp(e_t)}{\displaystyle\sum_{k=1}^{n}\exp(e_k)},
\qquad
e_t = f\!\bigl(\mathbf{q},\mathbf{k}_t\bigr) \\[1em]
\text{Hard Attention:}\quad
&\tilde t \;\sim\; \operatorname{Categorical}\!\bigl(\alpha_1,\dots,\alpha_n\bigr),
\qquad
\mathbf{c}_{\text{hard}} \;=\; \mathbf{h}_{\tilde t}, \\[4pt]
&\mathcal{L}_{\text{hard}}
      \;=\;
      \mathbb{E}_{\tilde t\sim\alpha}\!\bigl[
         \ell\!\bigl(\mathbf{c}_{\text{hard}},\text{target}\bigr)
      \bigr]
      \;\; \text{(optimized via REINFORCE or Gumbel-Softmax).}
\end{aligned}
$$


<br>

```
Encoder
x₁ → x₂ → … → xₙ
 ↓     ↓        ↓
h₁    h₂   …   hₙ
 │     │        │
 └─────┼────────┘
       │
   ┌───┴───┐
   │       │
   ▼       ▼

Soft Attention (differentiable)      Hard Attention (non-differentiable)
│  • Complexity: O(n) per step       │  • Complexity: O(1) per step
│  • Stability & Performance:        │  • Stability & Performance:
│    gradient-smooth, training-      │    quickly locks onto a few
│    stable; averages teacher        │    high-probability positions
│    signal → more global & robust.  │    → sparse and precise but
│                                    │    may suffer mode-collapse.
│                                    │
▼                                    ▼
αₜ = softmax(eₜ)                     t̃ ∼ Categorical(αₜ)
│                                    │
▼                                    ▼
c_soft  = Σ αₜ·hₜ                    c_hard = h_{t̃}
│  [O(n) computation]                │  [O(1) computation]
▼                                    ▼
Standard back-propagation            REINFORCE / Gumbel-Softmax
│  [O(n) gradient flow]              │  [O(1) gradient estimation]
▼                                    ▼
Decoder generates y₁, y₂, …          Decoder generates y₁, y₂, …

Total Training Complexity:           Total Training Complexity:
O(n·T) for sequence length T         O(T) for sequence length T

T: output sequence length (number of decoding steps)
```

<br>

```
🗳️ Soft Attention (Democratic Voting)           👑 Hard Attention (Expert Selection)
════════════════════════════════               ═══════════════════════════

Each decoding step:                            Each decoding step:
┌─────────────────┐                            ┌─────────────────┐
│  🏛️ Public Poll │                            │  🎯 Expert Pick │
└─────────────────┘                            └─────────────────┘
         │                                              │
         ▼                                              ▼
Consult ALL voters:                            4-Step Expert Selection:
┌─────┬─────┬─────┬─────┐                      ┌─────┬─────┬─────┬─────┐
│ h₁  │ h₂  │ h₃  │ h₄  │                      │ h₁  │ h₂  │ h₃  │ h₄  │
│ 🗣️  │ 🗣️  │ 🗣️  │ 🗣️  │                      │ 😴  │ 🎯  │ 😴  │ 😴  │
│0.2  │0.5  │0.2  │0.1  │                      │Score│PICK │     │     │
└─────┴─────┴─────┴─────┘                      └─────┴─────┴─────┴─────┘
         │                                              │
         ▼                                              ▼
Weighted average of ALL opinions:              Expert Selection Process:
c = 0.2×h₁ + 0.5×h₂ + 0.2×h₃ + 0.1×h₄         1. eᵢ = score(query, hᵢ)
                                               2. pᵢ = softmax(eᵢ) 
                                               3. i* ~ Categorical(p)
                                               4. c = h_{i*}

💰 Cost: O(n) - Expensive                      💰 Cost: O(1) - Cheap  
📊 Stability: High                             📊 Stability: Requires special training
🎯 Precision: Global view but may blur         🎯 Precision: Focused but may miss info

Key: Probabilistic expertise - highest scorer  Key: Democratic consensus - everyone 
     usually wins, but allows exploration           contributes proportionally
```


<br>

**Softmax**

```
Extreme Case Analysis
─────────────────────

Input: [1, 10, 100]
         │
         ▼
Simple Normalization Path:              Softmax Exponential Path:
Step 1: Sum = 1+10+100 = 111           Step 1: Exponential Explosion
Step 2: [1/111, 10/111, 100/111]             exp(1) = 2.72
Step 3: [0.009, 0.09, 0.90]                  exp(10) = 22,026  ← HUGE!
                                              exp(100) = 2.7×10⁴³  ← ASTRONOMICAL!
Result: Still some competition                    │
                                                  ▼
                                         Step 2: Total dominance
                                         Sum ≈ 2.7×10⁴³ (exp(100) dominates)
                                                  │
                                                  ▼
                                         Step 3: [tiny, tiny, ~1.0]
                                         Result: [0.00004, 0.00009, 0.999]
                                         
                                         Winner takes EVERYTHING!
```

```
softmax(xᵢ) = exp(xᵢ) / Σⱼ exp(xⱼ)
softmax(x, T) = exp(x/T) / Σ exp(x/T)

-> Why e?
d/dx(eˣ) = eˣ
```

<br>

**FFN**

```
┌─────────────────────────┐
│   Input Embeddings      │
│   + Position Encoding   │
└─────────┬───────────────┘
          │
          ▼
┌─────────────────────────┐
│  Multi-Head             │
│  Self-Attention         │ ← 
└─────────┬───────────────┘
          │
          ▼
┌─────────────────────────┐
│  Add & Norm             │
│  (Residual + LayerNorm) │
└─────────┬───────────────┘
          │
          ▼
┌─────────────────────────┐
│  Position-wise          │
│  Feed-Forward Network   │ ← 
│  (FFN)                  │
└─────────┬───────────────┘
          │
          ▼
┌─────────────────────────┐
│  Add & Norm             │
│  (Residual + LayerNorm) │
└─────────┬───────────────┘
          │
          ▼ 
```



<br>

```
Raw Input                                        Processed Input
─────────                                       ──────────────

Text: "Hello world"                             Token Embeddings
     │                                               │
     ▼                                               ▼
Tokenization                                    Linear Projection
["Hello", "world"]                              E ∈ ℝᵛˣᵈᵐᵒᵈᵉˡ
     │                                               │
     ▼                                               ▼
Token IDs                                       Position Encoding
[1045, 2088]                                    PE(pos,2i) = sin(pos/10000^(2i/d_model))
     │                                          PE(pos,2i+1) = cos(pos/10000^(2i/d_model))
     ▼                                               │
Embedding Lookup                                     ▼
x₁ = E[1045], x₂ = E[2088]                     Final Input = Embedding + Position
(each x ∈ ℝᵈᵐᵒᵈᵉˡ)                              X = [x₁+PE₁, x₂+PE₂, ...]
```


<br>





<br>

```
Multi-Head Self-Attention Computation
─────────────────────────────────────

Input: X ∈ ℝⁿˣᵈᵐᵒᵈᵉˡ                           Single Head Attention
     │                                               │
     ▼                                               ▼
Linear Projections                              Scaled Dot-Product Attention
Q = XW_Q ∈ ℝⁿˣᵈₖ                               Attention(Q,K,V) = softmax(QKᵀ/√dₖ)V
K = XW_K ∈ ℝⁿˣᵈₖ                                        │
V = XW_V ∈ ℝⁿˣᵈᵥ                                        ▼
     │                                          Score Matrix: S = QKᵀ/√dₖ
     ▼                                          S[i,j] = similarity(query_i, key_j)
Parallel Processing (h=8 heads)                         │
Head₁: Q₁, K₁, V₁ (dₖ=dᵥ=64)                          ▼
Head₂: Q₂, K₂, V₂ (dₖ=dᵥ=64)                   Attention Weights: A = softmax(S)
...                                            A[i,j] = how much position i attends to j
Head₈: Q₈, K₈, V₈ (dₖ=dᵥ=64)                          │
     │                                                 ▼
     ▼                                          Weighted Values: Z = AV
Concatenate Heads                               Z[i] = Σⱼ A[i,j] * V[j]
Z = Concat(head₁, ..., head₈)                          │
     │                                                 ▼
     ▼                                          Output ∈ ℝⁿˣᵈᵥ
Final Projection
Output = ZW_O ∈ ℝⁿˣᵈᵐᵒᵈᵉˡ
```

<br>

```
Single Encoder Layer                           Computational Flow
────────────────────                          ─────────────────

Input: X ∈ ℝⁿˣᵈᵐᵒᵈᵉˡ                          X (sequence representation)
     │                                               │
     ▼                                               ▼
Multi-Head Self-Attention                      Calculate attention scores
Attention(X, X, X)                            for all position pairs
     │                                               │
     ▼                                               ▼
Residual Connection                            Add & Norm
X₁ = LayerNorm(X + Attention(X))              X₁ = LayerNorm(X + SubLayer₁(X))
     │                                               │
     ▼                                               ▼
Position-wise FFN                             Two linear transformations
FFN(x) = max(0, xW₁ + b₁)W₂ + b₂             ReLU activation between them
W₁ ∈ ℝᵈᵐᵒᵈᵉˡˣᵈff, W₂ ∈ ℝᵈffˣᵈᵐᵒᵈᵉˡ           Hidden dim: dff = 2048
     │                                               │
     ▼                                               ▼
Residual Connection                            Add & Norm
X₂ = LayerNorm(X₁ + FFN(X₁))                  X₂ = LayerNorm(X₁ + SubLayer₂(X₁))
     │                                               │
     ▼                                               ▼
Output: X₂ ∈ ℝⁿˣᵈᵐᵒᵈᵉˡ                        Ready for next layer
```


<br>


```
Encoder Stack (N=6 layers)                    Information Flow
──────────────────────────                   ───────────────

Input Embeddings + Positional Encoding       Raw sequence information
     │                                               │
     ▼                                               ▼
Encoder Layer 1                               Local attention patterns
Multi-Head Attention + FFN                    learned in first layer
     │                                               │
     ▼                                               ▼
Encoder Layer 2                               More complex patterns
Multi-Head Attention + FFN                    building on previous layer
     │                                               │
     ▼                                               ▼
Encoder Layer 3                               Hierarchical feature
Multi-Head Attention + FFN                    extraction continues
     │                                               │
     ▼                                               ▼
... (up to Layer 6)                          Deep semantic
                                             representations
     │                                               │
     ▼                                               ▼
Final Encoder Output                          Rich contextual
Z = [z₁, z₂, ..., zₙ] ∈ ℝⁿˣᵈᵐᵒᵈᵉˡ            representations
```


<br>

```
Decoder Layer                                 Masked Self-Attention
─────────────                                ─────────────────────

Target Sequence (Training)                   Attention Mask Matrix
y = [<START>, w₁, w₂, ..., wₘ]               │ 1 0 0 0 │  ← position 1 only sees itself
     │                                       │ 1 1 0 0 │  ← position 2 sees 1,2
     ▼                                       │ 1 1 1 0 │  ← position 3 sees 1,2,3
Shifted Right (Teacher Forcing)              │ 1 1 1 1 │  ← position 4 sees 1,2,3,4
Input: [<START>, w₁, w₂, ...]                       │
Target: [w₁, w₂, w₃, ...]                          ▼
     │                                       Prevents "looking ahead"
     ▼                                       during training
Masked Self-Attention                               │
Only attend to previous positions                   ▼
     │                                       Ensures autoregressive property
     ▼                                       is maintained during training
Encoder-Decoder Attention
Query: from decoder
Key, Value: from encoder output Z
     │
     ▼
Position-wise FFN
Same as encoder FFN
     │
     ▼
Output Predictions
```

<br>

```
Scaled Dot-Product Attention Computation
───────────────────────────────────────

Mathematical Formula                         Step-by-Step Calculation
──────────────────                         ────────────────────────

Attention(Q,K,V) = softmax(QKᵀ/√dₖ)V       Given:
                                           Q ∈ ℝⁿˣᵈₖ (queries)
Where:                                     K ∈ ℝᵐˣᵈₖ (keys)  
Q = queries                                V ∈ ℝᵐˣᵈᵥ (values)
K = keys                                          │
V = values                                        ▼
dₖ = key dimension                         Step 1: Compute dot products
                                          S = QKᵀ ∈ ℝⁿˣᵐ
Scaling Factor: 1/√dₖ                     S[i,j] = Σₖ Q[i,k] * K[j,k]
Why? Prevents saturation of softmax               │
when dₖ is large                                  ▼
                                          Step 2: Scale by √dₖ
Example with dₖ=64:                       S_scaled = S / √64 = S / 8
√dₖ = √64 = 8                                     │
                                                  ▼
                                          Step 3: Apply softmax
                                          A[i,j] = exp(S_scaled[i,j]) / Σₖ exp(S_scaled[i,k])
                                                  │
                                                  ▼
                                          Step 4: Weighted sum of values
                                          Output[i] = Σⱼ A[i,j] * V[j]
```

<br>


```
Multi-Head Attention Detailed Computation
────────────────────────────────────────

Single Model vs Multi-Head                  Parallel Head Processing
─────────────────────                       ─────────────────────

Single Attention (dₘₒdₑₗ=512)                Head 1 (dₖ=dᵥ=64):
All 512 dimensions together                  Q₁ = XW₁Q, K₁ = XW₁K, V₁ = XW₁V
Limited representation power                 A₁ = Attention(Q₁, K₁, V₁)
     │                                              │
     ▼                                              ▼
Multi-Head (h=8, dₖ=dᵥ=64)                 Head 2 (dₖ=dᵥ=64):
Each head: 512/8 = 64 dimensions           Q₂ = XW₂Q, K₂ = XW₂K, V₂ = XW₂V
Different representation subspaces          A₂ = Attention(Q₂, K₂, V₂)
     │                                              │
     ▼                                              ▼
Benefits:                                   ... (parallel computation)
- Attend to different types of info                │
- Different positions simultaneously              ▼
- Syntactic vs semantic relationships      Head 8 (dₖ=dᵥ=64):
                                          Q₈ = XW₈Q, K₈ = XW₈K, V₈ = XW₈V
Concatenation:                            A₈ = Attention(Q₈, K₈, V₈)
MultiHead = Concat(A₁, A₂, ..., A₈)              │
Final projection: MultiHeadW₀                    ▼
                                          Final Output:
                                          Concat(A₁, A₂, ..., A₈)W₀
```

<br>


```
Position Encoding Necessity                 Sinusoidal Position Encoding
─────────────────────────                  ──────────────────────────

Problem: Attention is permutation          Formula:
equivariant                                PE(pos,2i) = sin(pos/10000^(2i/dₘₒdₑₗ))
                                          PE(pos,2i+1) = cos(pos/10000^(2i/dₘₒdₑₗ))
"cat sat mat" vs "mat sat cat"                    │
Same attention weights!                           ▼
     │                                     Properties:
     ▼                                     - Different wavelengths for each dim
Need position information                  - Relative position relationships
     │                                     - Can handle variable lengths
     ▼                                            │
Two options:                                      ▼
1. Learned embeddings                      Example (dₘₒdₑₗ=4):
2. Sinusoidal encoding                     pos=0: [sin(0/10000^0), cos(0/10000^0),
     │                                             sin(0/10000^0.5), cos(0/10000^0.5)]
     ▼                                     pos=1: [sin(1/10000^0), cos(1/10000^0),
Transformer choice: Sinusoidal                    sin(1/10000^0.5), cos(1/10000^0.5)]
Reason: Generalization to longer sequences        │
                                                  ▼
                                          Added to word embeddings:
                                          Final_input = Word_emb + Pos_emb
```

<br>

```
Training Process                            Loss Computation
───────────────                            ─────────────────

Teacher Forcing Mode                       Cross-Entropy Loss
Input:  [<START>, "Hello", "world"]       Given target: ["Hello", "world", <END>]
Target: ["Hello", "world", <END>]         Predicted: [P₁, P₂, P₃]
     │                                           │
     ▼                                           ▼
Parallel Training                          Loss = -Σᵢ log(Pᵢ[correct_tokenᵢ])
All positions computed simultaneously      Where Pᵢ is probability distribution
(unlike RNN sequential)                    over vocabulary at position i
     │                                           │
     ▼                                           ▼
Decoder Output:                           Label Smoothing (ε=0.1):
Logits ∈ ℝᵛᵒᶜᵃᵇ for each position       Instead of hard targets [0,0,1,0,...]
     │                                   Use soft: [0.025, 0.025, 0.9, 0.025,...]
     ▼                                          │
Softmax → Probabilities                        ▼
P = softmax(logits)                       Improves generalization
     │                                   Prevents overconfidence
     ▼
Compute loss with ground truth
```

<br>

```
Inference Process (Autoregressive)         Step-by-Step Generation
─────────────────────────────              ──────────────────────

Different from Training!                   Step 1: Start token
No teacher forcing                         Input: [<START>]
     │                                     Decoder output: P₁
     ▼                                     Sample: w₁ = argmax(P₁)
Sequential Generation                             │
Each step depends on previous                     ▼
     │                                     Step 2: Extend sequence
     ▼                                     Input: [<START>, w₁]
Step 1:                                   Decoder output: P₂
Input: [<START>]                          Sample: w₂ = argmax(P₂)
Output: w₁                                       │
     │                                           ▼
     ▼                                     Step 3: Continue...
Step 2:                                   Input: [<START>, w₁, w₂]
Input: [<START>, w₁]                      Output: w₃
Output: w₂                                       │
     │                                           ▼
     ▼                                     Until: <END> token generated
Continue until <END>                      or max_length reached
     │
     ▼
Final sequence: [w₁, w₂, ..., wₙ]

Efficiency Note:
Can reuse previous computations
with KV-caching in practice
```




<br><br>
