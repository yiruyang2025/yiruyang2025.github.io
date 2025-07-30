---
layout: page
title: 2025 - A Highly Efficient ASR Knowledge Distillation
description: Whisper, Low Latency Inference on-device
img: assets/img/4.jpg
importance: 1
category: work
related_publications: true
---

<br>

**Whisper-large-v3-turbo** - Sep 2024 → `our_model_Säuseln-v3.en` + LoRA-guided Dynamic + Geometric Distillation

parallel training on `s3it Cluster`, with **Contrastive Learning in the Hidden Space**


<br>

```
Sonnet 64

And nothing ’gainst Time’s scythe can make defence,
From each of life moment, to brave him when he takes thee hence.

**Shakespeare, William.** “Sonnet 64,” lines 11–12, in The Sonnets * (1609).*
```
<br>

`WER` -> `Inference Latency` + `Memory` -> xx-MB On-Device

Test it on your own device for the inference + WER with model Cell 2.6 (Hypersphere alignment) / 2.7 (Dynamic geometric alignment)

<br>

-> `INT8` - Inference - Post-Training [`Quantization`](https://www.youtube.com/watch?v=t509sv5MT0w) -> can try Quantization-Aware Training by yourself

<br>

**Key Improvements**

1. LoRA + Lightweight Decoders + non-linear Projection to Guide the Student in the Hidden State -> similar WER with `lower inference Latency`


<br>

```
the parameters that dominate memory footprint and inference latency
- fused LoRA into the backbone and applied quantization:

1. Embedding matrix
Quantized token‑to‑hidden lookup table (+ scale/zero‑point metadata)

2. Fused Transformer weights
Self‑Attention: Q, K, V, and output projection matrices (each with fused LoRA ΔW), plus biases; all quantized
Feed‑Forward: two linear layers (with fused LoRA updates), plus biases; all quantized

3. LayerNorm parameters
γ (scale) and β (shift) for each layer—typically kept in FP16/FP32 for stability

4. Output projection head
Final hidden‑to‑vocab weight matrix and bias, quantized (+ metadata)

5. Quantization metadata
Per‑tensor (or per‑channel) scale and zero‑point arrays that map integer ops back to real values
```

<br>

```
- Extract the spectral or time domain features, then train the U-Net, Conv-TasNet, Demucs and other networks to output multiple audio streams

- Give it a "label" to tell it how many channels to split (vocals/drums/bass/other), and it will split the signal
```

<br>

`📍 If you have some Time`

- Accurately analyze `how` LoRA `weights affect knowledge transfer`
- Use `feature visualization` to understand `what` the student have learned
- Verify the role of different loss functions through ablation experiments

<br>

```
%load_ext tensorboard
%tensorboard --logdir /content/drive/MyDrive/distil_run_cell2.x/tb
```

<br>


`The choice of your Surface`

- Write a script to test


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

- **Säuseln-v3.en** - 📍 ≈ xx M parameters (FP16) - on-device
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


```
Raw Audio
    ↓
[ Encoder (frozen) ]
    ↓
[ Decoder + LoRA adapters ]    ←— LoRA injects low-rank ΔW here, directly modifying student logits
    ↓
Student logits zˢᵗᵘᵈᵉⁿᵗ      ←— LoRA’s effect appears in these logits
    ↓
÷ T   (temperature scaling)     ←— Temperature T then scales these logits
    ↓
softmax(z/T)                   ←— T smooths the distribution, controlling gradient strength
    ↓
KL(pᵗᵉᵃᶜʰᵉʳ ‖ pˢᵗᵘᵈᵉⁿᵗ)
    ↓
Backpropagate to update LoRA adapter parameters
```
<br>


`check points` of Sample Student Models

**distil-large-v3** (≈756 M parameters) is the **best-performing** distilled checkpoint, performing to within 1.5% WER of Whisper large-v3 on out-of-distribution short-form audio and within 1% WER on long-form decoding

**distil-medium.en** (≈394 M params) provides a balanced trade-off between performance and efficiency, and is recommended for most applications along with distil-large-v2

**distil-small.en** (≈166 M params) is the most compact option and performs to within 3% WER of Whisper large-v2 while being 5.6x faster, making it ideal for `memory-constrained applications (e.g. on-device)`

<br>

**Each token output by `Attention carries global context information`, while `FFN applies "fine-tuning" or "feature combination" to each token` to improve the feature quality at each position**

<br>

```
🍩 Transformer = Non-Sugar Donut Factory Assembly Line  
═══════════════════════════════════════════════════════
Raw Donuts → Community Check → Solo Decoration → Finished Donuts  
(Input)       (Attention)       (FFN)            (Output)
    ↓             ↓                ↓               ↓
┌─────────┐  ┌──────────────┐  ┌──────────────┐    ┌─────────┐
│ Plain   │→ │👥 Community  │→ │ 🎨 Solo       │ →  │Gourmet  │
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

<br>

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project1_4.jpg" alt="Project 1 Visualization" width="50%">
</p>

<br>

**🧊 Distillation Ice Factory**

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

`TAID`

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

- CPU: Load→Preprocess→Transfer | GPU idle | Load→Preprocess→Transfer
- GPU: Idle                     | Compute  | Idle
  
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

<br>

```
🍩 Vocabulary Mismatch = Multilingual "Plain" vs English "Decorated" Pipeline
═══════════════════════════════════════════════════════════════════════════════

Large Vocab → Filter English → Student English‑Only → Aligned Output
(Original)    (Trim Embedding)  (Slice/Filter)        (Consistent vocab)
    ↓                 ↓                      ↓                      ↓
┌─────────────┐   ┌─────────────────┐   ┌─────────────────┐   ┌─────────────┐
│Multi‑Lingual│→  │🍰 Trim Large    │→  │🎯 Keep English   │→  │ Distil Vocab│
│51866 tokens │   │Embedding ↓ to   │   │Tokens Only ↓    │   │51864 size   │
│(v3)         │   │51864            │   │keep 51864       │   │             │
└─────────────┘   └─────────────────┘   └─────────────────┘   └─────────────┘
    ↓                 ↓                      ↓                      ↓
  V₀ (51866)      V₁ (trimmed)         V₂ (student)         V_out (match)

Pipeline Steps:
1. **V₀**: Teacher `openai/whisper-large-v3` uses a 51 866‑token multilingual vocabulary  
2. **V₁**: Resize the teacher’s embedding matrix down to **51 864** slots (remove non‑English tokens)  
3. **V₂**: Student model (English‑only) loads that 51 864‑sized embedding  
4. **V_out**: Ensures output token IDs align exactly between teacher‑derived embeddings and student’s vocab  

Vocabulary Alignment Strategy:
┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│   Teacher    │ →  │   Student    │ →  │   Output     │
│ Whisper-v3   │    │ English‑Only │    │  Aligned     │
│ 51866 tokens │    │  51864 toks  │    │  51864 toks  │
└──────────────┘    └──────────────┘    └──────────────┘

Key Technical Details:
- **Teacher**: `openai/whisper-large-v3` (51 866‑token vocab)  
- **Student**: English‑only distilled model (51 864‑token vocab)  
- **Solution**: Align token spaces by trimming the teacher’s embedding to the student’s English subset  
- **Result**: Consistent token IDs & embedding dimensions for seamless knowledge distillation
```

<br>

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


<br><br>


`Some other topics`

`4. Low-Latency Decoding` - `CTC + RNN-Transducer`

- Graves, A., Fernández, S., Gomez, F., & Schmidhuber, J. “Connectionist Temporal Classification: Labelling Unsegmented Sequence Data with Recurrent Neural Networks.” ICML 2006. - **CTC**

- Graves, A. “Sequence Transduction with Recurrent Neural Networks.” ICASSP 2012. - **RNN-T**

- For interactive translation, non-autoregressive decoders such as CTC or RNN-Transducer enable single-pass inference
- Understanding the trade-offs between greedy decoding and beam search is essential for minimizing latency under resource constraints

- [2022 - Cross-Architecture Knowledge Distillation](https://openaccess.thecvf.com/content/ACCV2022/html/Liu_Cross-Architecture_Knowledge_Distillation_ACCV_2022_paper.html)

- [2025 - Cross-Architecture Knowledge Distillation for Speech Enhancement: From Cmgan to Unet](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5222345)

- [2024 - Factorized and progressive knowledge distillation for CTC-based ASR models](https://www.sciencedirect.com/science/article/pii/S0167639324000438?casa_token=uw4aHelNS6oAAAAA:cl02wSLichxkfoxRAs1WroOWDX1J4qVvXCS_IwhHsw--BBZXuYgzNUn4t99IBiRuhkrXv9P2Fw)

<br>

```
VQ-VAE

Motivation for Discrete Latent Audio Representations

- **Information Bottleneck & Compression**  
  Continuous waveforms contain abundant redundancies; modeling them directly (e.g., WaveNet) is computationally expensive.  
  VQ-VAE quantizes latent vectors into a fixed-size codebook (e.g., 512 or 1024 entries), achieving lossy compression while preserving salient features.  
  Subsequent priors (PixelCNN/Transformer) operate on shorter discrete sequences, yielding far greater efficiency.

- **Advantages of Discrete Sequence Modeling**  
  Autoregressive Transformers, PixelCNNs, and RNNs excel at modeling discrete tokens.  
  Mapping audio to discrete tokens enables these models to capture long-range dependencies, linguistic structures, and prosody, without struggling in high-dimensional continuous spaces.

- **Denoising & Semantic Extraction**  
  Codebook entries tend to represent prototypical acoustic units (e.g., phonemes).  
  Quantization suppresses minor noise and emphasizes semantic/prosodic features, yielding more robust representations for synthesis and recognition.

- **Hierarchical & Multi-Rate Structure**  
  VQ-VAE-2 employs multi-scale codebooks:  
  - **Lower levels:** fine details (timbre, noise)  
  - **Higher levels:** global structure (intonation, rhythm)  
  This hierarchical discrete design is hard to achieve with continuous latent models.
```

<br>

```
1. NVIDIA Megatron-LM (GPT / BERT Pretraining)

- **Compute**: All forward/backward kernels (e.g., matrix multiplies, attention, activations) execute in **FP16** on Tensor Cores.  
- **Master Weights & Optimizer State**: A **FP32** “master copy” of model weights is maintained; FP16 gradients are accumulated into FP32 weights, then cast back to FP16 for the next iteration.  
- **Numerical Stability**: Overflow-sensitive ops (e.g., Softmax) remain in **FP32** to avoid divergence, without meaningful speed penalty.  
- **Implementation**: Uses NVIDIA Apex/AMP or NeMo’s automatic mixed-precision modules to orchestrate autocasting, dynamic loss scaling, and master-weight management :contentReference[oaicite:0]{index=0}.  

2. Google PaLM / AlphaFold2 (Transformer & Scientific Models)

- **Core Operators** (e.g., GEMM, LayerNorm, Dropout) run in **bfloat16** (BF16)—a 16-bit format with the same exponent range as FP32 but reduced mantissa.  
- **Critical Sections** (e.g., logits normalization, loss computation) remain in **FP32** to prevent underflow/overflow.  
- **Framework Support**: JAX/Flax users enable BF16 globally via flags like `jax.experimental.enable_x64=False` and per-op control via `jax.lax.cond` :contentReference[oaicite:1]{index=1}.  


3. Stable Diffusion / GAN Inference

- **Inference Precision**: Entire U-Net, scheduler, and CLIP text encoder run in **FP16**, halving memory and nearly doubling throughput compared to FP32, with negligible impact on image quality.  
- **Selective FP32 Fallback**: For maximum stability or visual fidelity (e.g., in the VAE decoder), critical layers can be temporarily cast back to **FP32**.  

4. Frontiers: FP8-LM (8-bit Mixed-Precision)

- **FP8 Framework**: Base weights, gradients, and optimizer states use **8-bit FP8** (e.g., NVIDIA’s NF4 or Microsoft’s custom FP8); key stability ops (Softmax, LayerNorm) stay in FP16/BF16 or FP32.  
- **Efficiency Gains**: In GPT-175B training, FP8 mixed-precision achieved a **75% speedup** and **39% memory reduction** over BF16 baselines—without changing hyperparameters :contentReference[oaicite:2]{index=2}.  
- **Adoption**: Offers a drop-in replacement for existing FP16/BF16 pipelines, open-sourced via MS-AMP (aka.ms/MS.AMP).  

*References*  
- Micikevicius *et al.*, “Mixed Precision Training,” NVIDIA Developer Blog, 2018.  
- Shoeybi *et al.*, “Megatron-LM: Training Multi-Billion Parameter Language Models,” *arXiv:1909.08053*, 2019.  
- Narang *et al.*, “How To Fit a Bigger Model and Train It Faster,” Hugging Face Docs, 2022.  
- Peng *et al.*, “FP8-LM: Training FP8 Large Language Models,” *arXiv:2310.18313*, 2023.
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


```
class WhisperLargeV2AudioEncoder(nn.Module):
   """
   Whisper Large V2 Audio Encoder Implementation
   Converts mel spectrogram to transformer-ready features
   """
   def __init__(self):
       super().__init__()
       
       # First convolution: extract features from mel bins
       self.conv1 = nn.Conv1d(
           in_channels=80,      # 80 mel frequency bins
           out_channels=1280,   # Large model hidden dimension
           kernel_size=3,
           stride=1,
           padding=1
       )
       
       # Second convolution: downsample time dimension
       self.conv2 = nn.Conv1d(
           in_channels=1280,
           out_channels=1280,
           kernel_size=3,
           stride=2,           # Halves the time axis
           padding=1
       )
       
       # Positional embeddings for transformer
       self.register_buffer(
           "positional_embedding", 
           torch.randn(1500, 1280)  # Max sequence length 1500
       )
   
   def forward(self, x):
       """
       Forward pass through audio encoder
       
       Args:
           x: Tensor of shape [batch_size, 80, time_steps]
              Log mel spectrogram input
       
       Returns:
           Tensor of shape [batch_size, time_steps//2, 1280]
           Encoded audio features ready for transformer
       """
       # Apply convolutions with GELU activation
       x = F.gelu(self.conv1(x))   # [batch, 1280, time_steps]
       x = F.gelu(self.conv2(x))   # [batch, 1280, time_steps//2]
       
       # Transpose for transformer: [batch, seq_len, hidden_dim]
       x = x.transpose(1, 2)       # [batch, time_steps//2, 1280]
       
       # Add positional encoding
       seq_len = x.size(1)
       x = x + self.positional_embedding[:seq_len]
       
       return x

# Dimension verification
model = WhisperLargeV2AudioEncoder()
test_input = torch.randn(2, 80, 3000)  # 2 samples, 80 mel bins, 3000 time frames
output = model(test_input)

print(f"Input shape: {test_input.shape}")   # [2, 80, 3000]
print(f"Output shape: {output.shape}")      # [2, 1500, 1280]

Some Notes
1. Conv1d preserves time dimension: 3000 -> 3000
2. Conv1d with stride=2 halves time: 3000 -> 1500  
3. Transpose rearranges for transformer: [B,C,T] -> [B,T,C]
4. Positional encoding adds learned position information
```



<br>


`Temporal Smoothness`


```
 Audio Signal Characteristics:
├── High Continuity
│   └── Speech changes relatively slowly
├── Local Similarity  
│   └── Adjacent 10-30ms audio content is similar
└── Perceptual Redundancy
    └── Human ear is insensitive to small temporal differences
```

-> `Encoder's role` - preserve important scales, compress unimportant scales


<br><br>


## References

- [FitNets]
- [1991 - Adaptive Mixtures of Local Experts](https://ieeexplore.ieee.org/abstract/document/6797059)
- [2022 - Knowledge Distillation via Hypersphere Features Distribution Transfer](https://dl.acm.org/doi/abs/10.1145/3511808.3557621?casa_token=5zxwbIg9Lp8AAAAA:LqsNXD0NVGJIFJqlulaWKhSG8kp69U673xQL0Jr2vauz2MlxmVoTq0rlxXzyKdR0IRthPyemq9_t)
- [2025 - An Intuitive Overview of Few-Step Diffusion Distillation](https://ronaldyu.substack.com/p/an-intuitive-overview-of-few-step)
- [2025 - TAID]
- [2025 - Efficient Distillation of Classifier-Free Guidance using Adapters](https://arxiv.org/abs/2503.07274)
- [2025 - AXLearn: Modular Large Model Training on Heterogeneous Infrastructure](https://arxiv.org/abs/2507.05411)
- [2013 - Efficient Estimation of Word Representations in Vector Space](https://arxiv.org/abs/1301.3781)
- [2014 - Adam: A Method for Stochastic Optimization](https://arxiv.org/abs/1412.6980)
- [2016 - Information Geometry and Its Applications](https://link.springer.com/book/10.1007/978-4-431-55978-8)
- [2015 - Matrix Backpropagation for Deep Networks With Structured Layers](https://openaccess.thecvf.com/content_iccv_2015/html/Ionescu_Matrix_Backpropagation_for_ICCV_2015_paper.html)
- [2019 - Auxiliary teacher - Improved Knowledge Distillation via Teacher Assistant](https://arxiv.org/abs/1902.03393?utm_source=chatgpt.com)
- [2023 - Accelerating Large Language Model Decoding with Speculative Sampling](https://arxiv.org/pdf/2302.01318)
- [ASR WER + Latency](https://huggingface.co/spaces/hf-audio/open_asr_leaderboard)
- [2021 - 1-bit Adam: Communication Efficient Large-Scale Training with Adam’s Convergence Speed](https://proceedings.mlr.press/v139/tang21a.html)
- [2024 - SqueezeAttention: 2D Management of KV-Cache in LLM Inference via Layer-wise Optimal Budget](https://arxiv.org/abs/2404.04793)
- [2025 - Qwen/Qwen3-235B-A22B-Instruct-2507](https://huggingface.co/Qwen/Qwen3-235B-A22B-Instruct-2507)

<br><br>



