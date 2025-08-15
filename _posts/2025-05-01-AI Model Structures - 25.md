---
layout: post
title: AI Model Structures - 25
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

Welcome, <br>

Let's take a look at the history of The Model Structures we're using today.<br><br>

# 1. Why「Deep Structure」<br><br>

Compared with the original machine learning models:

 - **Linear Regression / SVM / Shallow Decision Trees**
 
 Deep structures refer to neural networks with **Multiple Layers of Nonlinear Transformations**

<br>

## 📍 Content

- Transformer
- BERT
- **Mamba**
- GPT
- Tokenization
- **ARIMA**
- RNN
- Diffusion Models
- **Flow Matching**
- TensorRT
- **Quantization - LoRA + QLoRA**
📍 

<br>

These deep models are capable of **Learning Hierarchical Features**, where each layer captures increasingly abstract representations of the data.

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

- Or even hundreds of layers in modern transformers like GPT and BERT


<br><br>


# 2. Key Tech<br><br>

- **MLP**
  - Multilayer Perceptron
  - Feedforward fully connected networks
  - Used in classification, regression, or small-scale tabular/audio tasks
  - 1989 - Universal Approximation Theorem / Still used as light head in multimodal systems<br>

<br><br>

- **RNN -> LSTM**
  - When inputs are sequences<br>
  - [Hochreiter & Schmidhuber 1997 - LSTM](https://ieeexplore.ieee.org/abstract/document/6795963)<br>

<br><br>

- **CNN**
  - Convolutional Neural Networks
  - When inputs are images or grid-like data
  - Extracts spatial features, widely used in image/audio tasks
  - Fully Connected Layer -> Receptive Field -> Parameter Sharing -> Convolutional Layer
  - 1998 - LeNet / 2012 - AlexNet: ImageNet Classification with Deep Convolutional Neural Networks<br>

<br><br>

- **Transformer**
  - When inputs are sequences<br>
  - Self-attention + Parallel computation<br>
  - [2015 ICLR - Neural Machine Translation by Jointly Learning to Align and Translate - **Additive Attention**](https://arxiv.org/abs/1409.0473)<br>
  - [2017 NeuralPS - Attention Is All You Need - **Self-Attention / Scaled Dot-Product Attention**](https://arxiv.org/abs/1706.03762)<br>

<br><br>

- **📍 Mamba**
  - Linear-Time Sequence Modeling<br>
  - State Space Model - SSM - with selective long-range memory<br>
  - [2023 - Mamba: Linear-Time Sequence Modeling with Selective State Spaces](https://arxiv.org/abs/2312.00752)<br>

<br><br>

- **BERT**
  - Bidirectional Encoder Representations from Transformers<br>
  - using Masked language modeling<br>
  - [2019 - BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://aclanthology.org/N19-1423/?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz-_m9bbH_7ECE1h3lZ3D61TYg52rKpifVNjL4fvJ85uqggrXsWDBTB7YooFLJeNXHWqhvOyC)<br>

<br><br>


- **Conformer**
  - Convolution + Transformer = Conformer
  - Combines local - CNN - and Global Self-attention Features
  - Widely used in speech recognition tasks
  - [2020 - Conformer: Convolution-augmented Transformer for Speech Recognition](https://arxiv.org/abs/2005.08100)<br>

<br><br>


 - **GAN**
   - Generator vs Discriminator<br>
   - Generates Images, Audio<br>
   - Popular in TTS, audio enhancement, and image generation<br>
   - [2014 - Generative Adversarial Nets](https://proceedings.neurips.cc/paper_files/paper/2014/hash/f033ed80deb0234979a61f95710dbe25-Abstract.html)<br>

<br><br>

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
     - [2020 - Denoising Diffusion Probabilistic Models](https://proceedings.neurips.cc/paper/2020/hash/4c5bcfec8584af0d967f1ab10179ca4b-Abstract.html)<br>

<br><br>

- **📍 SSL**
  - Learns from unlabeled data by solving pretext tasks<br>
  - Strong performance in low-resource and zero-shot setups<br>
  - [2020 - wav2vec 2.0: A Framework for Self-Supervised Learning of Speech Representations](https://proceedings.neurips.cc/paper/2020/hash/92d1e1eb1cd6f9fba3227870bb6d7f07-Abstract.html)<br>

<br><br>

- **📍 MEMORY - Transformers vs. RNN / LSTM**
  - [Add Reflection - 2024 - You Only Cache Once: Decoder-Decoder Architectures for Language Models](https://arxiv.org/abs/2405.05254)
    - **RetNet** - Retention Network -> Gated Retention
    - [2023 - RetNet: Retinal Disease Detection using Convolutional Neural Network](https://ieeexplore.ieee.org/abstract/document/10101661?casa_token=uZQehKNSJt0AAAAA:UWdRNBHC8WlsoNpwbNVIm9Wr147Q-292JEFwcP6bLglKLDlNtTVfIe7RuHyVD6ryjeuQTFUOaw)
    - **DeltaNet** - [2025 - Parallelizing Linear Transformers with the Delta Rule over Sequence Length](https://arxiv.org/abs/2406.06484)


<br><br>


# Deep Learning

<br>

`1. Premise of Deep Learning`

<br>

The **premise of deep learning** refers to the underlying assumptions and principles that explain *why* deep neural networks work and *when* they are effective:

- **Manifold / Smoothness Assumption**: High-dimensional data (images, speech, text) often lie on a lower-dimensional manifold, and semantic changes are locally smooth → can be approximated by continuous functions
  
- **Distributed & Hierarchical Representations**: Complex concepts can be formed by hierarchical composition of features (edges → textures → objects)
  
- **Inductive Bias**: Architectures like CNNs (translation equivariance) and Transformers (content-based selection) embed useful priors
  
- **Over-parameterization & SGD Implicit Regularization**: Even with more parameters than samples, SGD tends to find “flat” minima that generalize well
  
- **i.i.d. and Distribution Stability**: Training and test data should follow similar distributions, or be adapted via transfer learning/fine-tuning
  
- **Scalability (Scaling Laws)**: Increasing data, compute, and model size tends to yield predictable performance gains

**Use cases**: guiding architecture design, choosing regularization/data augmentation, understanding transfer learning, anticipating risks from domain shifts or small datasets


<br><br>


`2. Word Embeddings`


<br>

**Word embeddings** map discrete words into dense numerical vectors (usually 100–1024 dimensions) where geometric relationships capture semantic/grammatical similarity

- **Motivation**: One-hot vectors are sparse and lack similarity information; embeddings allow “similar words” to be close in vector space

- **Classic methods**:
  - **Word2Vec (CBOW / Skip-gram)**, **GloVe** – static embeddings from word co-occurrence
  - **FastText** – includes subword n-grams to handle out-of-vocabulary words
  - **Contextual embeddings (BERT, LLMs)** – same word can have different vectors depending on context
- **Similarity measure**: cosine similarity
  
  $$
  \cos = \frac{u \cdot v}{\|u\| \, \|v\|}
  $$

- **Applications**: text classification, semantic search, clustering, recommendation, retrieval-augmented generation (RAG), cross-modal alignment (e.g., CLIP)

<br><br>

`3. Dot Products`

<br>

The **dot product** (inner product) between two vectors \(a\) and \(b\):

$$
a \cdot b = \sum_i a_i b_i = \|a\| \, \|b\| \cos\theta
$$

- **Geometric meaning**: projection of one vector onto another, scaled by the first vector’s length
- **Relation to cosine similarity**: if vectors are normalized, dot product equals cosine similarity
- **Deep learning usage**:
  - **Attention scoring**:
 
    $$
    \text{score}_{ij} = \frac{q_i \cdot k_j}{\sqrt{d_k}}
    $$
    
  - **Similarity in retrieval / contrastive learning** (e.g., InfoNCE, CLIP)
  - **Final classification layer**: logits as dot products between features and class weights
- **Tip**: often L2-normalize or apply scaling/temperature to control numerical stability


<br><br>

`4. Softmax`

<br>

The **softmax** function converts raw scores (logits) into probabilities:

$$
\text{softmax}(z)_i = \frac{e^{z_i}}{\sum_j e^{z_j}}
$$

- **Shift invariance**: adding the same constant to all logits doesn’t change output
- **Numerical stability**: use
  
$$
  z' = z - \max(z)
$$

- **Temperature scaling**: \(\tau < 1\) → sharper distribution; \(\tau > 1\) → smoother
- **Gradient-friendly**: with cross-entropy, gradients simplify to `softmax(z) - y`
- **Applications**:  
  - multi-class classification output
  - attention weight normalization
  - contrastive learning normalization
  - language model token sampling

<br><br>

`Summary Connection`

<br>

- **Word embeddings**: map words to vectors 
- **Dot product**: measure similarity between embeddings 
- **Softmax**: turn similarity scores into probabilities
- **Premise of deep learning**: explains why such representation + similarity + normalization pipelines work for large-scale AI tasks


<br><br><br><br>


# 4. Some Norms and Their Nature<br><br>

**CTC - Connectionist Temporal Classification** - is a loss function used for sequence tasks where input and output lengths don’t match — like speech-to-text

  - You don't need exact alignment between audio frames and text
  - CTC learns to map long input sequences (e.g. 1000 audio frames) to short outputs (e.g. "hello")
  - It introduces **a special blank token - ∅** to allow flexible alignment
  - The model can output repeated characters + blanks, and CTC will collapse them into the final label<br>

--
Input frames:    [x1, x2, x3, x4, x5, x6, x7, x8]
Model output:     ∅   h   ∅   e   l   l   ∅   o
CTC collapse:              →         "hello"
--

<br><br>

**📍 Why LSTM / other RNN Layer after Self-Attention Layer**
   - Streamability
   - Positional bias
   - Smoothing
   - Lightweight after quantization
   - Distillation bridge
   - TLDR - **Attention offers Global Context, the follow-up LSTM supplies Sequential Inertia, Latency Control, and Quantization**-friendly compression—ideal for hearing-aid ASR


<br><br>

# 4. Some References<br><br>

- [2014 Deeply-Supervised Nets](https://proceedings.mlr.press/v38/lee15a.html)


<br><br><br><br>

<img width="468" height="634" alt="image" src="https://github.com/user-attachments/assets/c92129bf-c8ea-42cd-9a87-8c2fd9aa7f03" />
