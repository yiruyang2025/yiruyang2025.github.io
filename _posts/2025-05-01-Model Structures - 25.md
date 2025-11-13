---
layout: post
title: Model Structures - 25
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

  - Let's take a look at the history of the Model Structures we're using today.

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
<br>

## Content

- Transformer
- Mamba
- GPT
- Tokenization
- ARIMA
- RNN
- Diffusion Models
- Flow Matching
- Quantization / Adapter Guided - LoRA + QLoRA



  - These deep models are capable of **Learning Hierarchical Features**, where each layer captures increasingly abstract representations of the data.

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

- **RNN -> LSTM**
  - When inputs are sequences<br>
  - [Hochreiter & Schmidhuber 1997 - LSTM](https://ieeexplore.ieee.org/abstract/document/6795963)<br>

- **Some Other Temporal Modeling**
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



## Some References



<br><br>




