---
layout: post
title: Speech Processing x Transfer Learning - 25
date: 2025-05-01
description: ⛺️
categories: Research
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---

Welcome,<br>

A Coding Demo Example for **Distilled-ASR** using xxx with - A Visual Interactive Demo - **teach** you about the **Latent Space** I / we **used in the project**<br><br>


- [Apr 2025 - Generative modelling in latent space](https://sander.ai/2025/04/15/latents.html)

<br>

- **A dynamic Latent Trajectory Visualization**
- with **LoRA / QLoRA Adapter**
 
<br>

- CTC
- Seq2Seq+Attention
- RNN-Transducer
- QLoRA-Based Adapters
- KL-Distillation
- FLEURS - DataSet
- on-device ASR
📍

<br><br>


- [1989 - Coalescing Random Walks and Voter Model Consensus Times on the Torus in Zd](https://www.jstor.org/stable/2244439?casa_token=JLkXGaPGnN4AAAAA%3AdilCP1I_ycPHRJZwy3gqVagBmb4T0JvSR9vCKwd9araQIF20i3Xrh1p2XTQDA4sAAOrcLER824IHRo1QREgBzI-wyf_cA5lzvlbI-S8-PQEu6t5g0Do&seq=1)<br>

- [2015 - FitNets: Hints for Thin Deep Nets](https://arxiv.org/abs/1412.6550)<br>

- [2019 - ASR - Patient Knowledge Distillation for LSTM-Based Acoustic Models](https://ieeexplore.ieee.org/abstract/document/8461995?casa_token=Gt1xXKEuogcAAAAA:vei62XD7sihmdRw5nyPvOhklfKQdNoKUL0VfqM-L_J4sHnmzIfWGMUIjs4UksARaoaYRpURoDg)<br>

- [2016 - Sequence-Level Knowledge Distillation](https://aclanthology.org/D16-1139.pdf)<br>

- [1985 - Interacting Particle Systems - Chp5](https://link.springer.com/book/10.1007/b138374)<br>

<br><br><br>


## References

<br>

- [2025 - Nature Human Behaviour - A unified acoustic-to-speech-to-language embedding space captures the neural basis of NLP](https://www.nature.com/articles/s41562-025-02105-9)
  
- [1989 - The Cascade-Correlation Learning Architecture](https://proceedings.neurips.cc/paper_files/paper/1989/hash/69adc1e107f7f7d035d7baf04342e1ca-Abstract.html)


<br><br>



# 0. Some Background Knowledge<br><br>

**0.1 Core Evolution of Voice Models**

| Year | Milestone                        | Model / Paper                                                     |
|------|----------------------------------|-------------------------------------------------------------------|
| 2014 | End-to-end ASR                   | DeepSpeech ([Hannun et al.](https://arxiv.org/abs/1412.5567))     |
| 2017 | Tacotron (neural TTS)            | Tacotron ([Wang et al.](https://arxiv.org/abs/1703.10135))        |
| 2019 | Real-time voice synthesis        | FastSpeech ([Ren et al.](https://arxiv.org/abs/1905.09263))       |
| 2020 | Self-supervised                  | wav2vec 2.0 ([Baevski et al.](https://arxiv.org/abs/2006.11477))  |
| 2022 | Multilingual speech models       | Whisper ([OpenAI, 2022](https://github.com/openai/whisper))       |
| 2023 | Zero-shot voice cloning          | VALL-E  ([Microsoft, 2023](https://arxiv.org/abs/2301.02111))     |
| 2023–2024 | Diffusion-based TTS         | FastDiff ([Huang et al.](https://arxiv.org/abs/2305.10973))       |
| 2024 | Multi-modal voice models         | AudioLM 2 ([Borsos et al.](https://arxiv.org/abs/2402.05427))     |


<br><br>

**0.2 Key Technical History**

| Period        | Model Category                  | Core Principle                                                     |
|---------------|---------------------------------|--------------------------------------------------------------------|
| 2014–2017     | RNN - LSTM / GRU                | Sequence modeling, LSTM / GRU Solved vanishing gradient issues     |
| 2018–2020     | Transformer / Conformer         | Self-Attention + CNN, Parallelizable computation for Efficiency    |
| 2019–2022     | GAN-based Models                | TTS, Real-time audio Denoising for Hearing Aids                    |
| 2021–Present  | Diffusion Models                | Zero-shot / Few-shot                                               |
| Present       | SSL / Lightweight               | Self-supervised learning, Compression, Distillation                |

<br><br><br>

- [RNN - 1990 Finding structure in time](https://www.sciencedirect.com/science/article/abs/pii/036402139090002E)<br>
- [LSTM - 1997 Long Short-Term Memory](https://ieeexplore.ieee.org/abstract/document/6795963)<br>
- [GRU - 2014 Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](https://aclanthology.org/D14-1179/)<br>
- [Transformer - 2017 Attention Is All You Need](https://proceedings.neurips.cc/paper/2017/hash/3f5ee243547dee91fbd053c1c4a845aa-Abstract.html)<br>
- [BERT - 2018 BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)- Masked Language Modeling - MLM<br>
- [Conformer - 2020 Conformer: Convolution-augmented Transformer for Speech Recognition](https://arxiv.org/abs/2005.08100)<br>
- [GAN - 2014 Generative Adversarial Networks](https://arxiv.org/abs/1406.2661)<br>


<br>

- **Diffusion Models**<br>

  - [2015 Deep Unsupervised Learning using Nonequilibrium Thermodynamics](https://arxiv.org/abs/1503.03585)
  - [2020 Denoising Diffusion Probabilistic Models](https://arxiv.org/abs/2006.11239)<br>

<br>

- **SSL**<br>

  - [2016 - Vision - Unsupervised Learning of Visual Representations by Solving Jigsaw Puzzles](https://arxiv.org/abs/1603.09246)<br>
  - [2020 - Vision - Momentum Contrast for Unsupervised Visual Representation Learning](https://arxiv.org/abs/1911.05722)<br>
  - [2019 - Speech - wav2vec - Unsupervised Pre-training for Speech Recognition](https://arxiv.org/abs/1904.05862)<br>

<br><br>


**📍 0.3 Label Encoding Methods in Speech Models and Distillation**

<br>

- Label encoding refers to methods that convert categorical labels into numerical representations for machine learning. These strategies have evolved to serve different training paradigms, including classification, multi-label tasks, and model compression (e.g., distillation).


<br>

### Historical Context

- **One-hot encoding**: Early standard in classification models.
- **Label/Ordinal/Binary encoding**: Introduced for efficient encoding in decision trees and statistical models.
- **Embedding encoding**: Emerged with deep learning to represent semantic relationships.
- **Soft label**: Popularized in knowledge distillation (Hinton et al., 2015).

<br>

### Common Label Encodings Overview

<br>

| Method        | Example              | Relationship Preserved | Use Case |
|---------------|----------------------|--------------------------|----------|
| One-hot       | `[0, 1, 0]`          | ❌                      | CTC loss in ASR |
| Integer Label | `0, 1, 2`            | ⚠️ (Implied order)      | Tree models |
| Ordinal       | `1, 2, 3`            | ✅                      | Ranked categories |
| Binary        | `A=0001`             | Partially               | Large-ID categories |
| Embedding     | `[0.1, -0.2, 0.3]`   | ✅ (Learned)            | Token representation |
| Multi-hot     | `[1, 0, 1]`          | ❌                      | Multi-label tasks |
| Soft label    | `[0.1, 0.7, 0.2]`    | ✅                      | Distillation training |

<br><br>


## What Domain Does Label Encoding Belong To?

<br>

- Label encoding methods are fundamental to many stages of machine learning pipelines, from raw data preprocessing to model compression.

<br>

| Encoding Knowledge | Domain |
|--------------------|--------|
| Categorical label transformation | **Machine Learning** |
| One-hot, Binary, Ordinal encoding | **Data Preprocessing / Feature Engineering** |
| Embedding encoding | **Representation Learning / NLP / Speech** |
| Soft label distillation | **Model Compression / Knowledge Transfer** |
| Token label supervision | **Deep Learning (CTC, ASR, Transformer)** |

<br>

- These methods are crucial for enabling models to interpret, learn, and generalize from categorical data, especially in speech and language processing.

<br><br>

## Historical Timeline and Motivation

| Encoding Method | Introduced | Why It Was Introduced |
|-----------------|------------|------------------------|
| **One-hot Encoding** | 1960s–1970s | To represent categories without implying order; widely used in early neural nets and perceptrons |
| **Label / Integer Encoding** | 1980s | Compact representation for tree models; useful in statistical and rule-based methods |
| **Ordinal Encoding** | 1980s | Needed when categories have intrinsic order (e.g., low < medium < high) |
| **Binary Encoding** | 1990s | To handle high-cardinality categories without exploding dimensionality (e.g., postal codes, product IDs) |
| **Embedding Encoding** | 2013+ | Emerged with Word2Vec and deep learning to learn semantic similarity between tokens |
| **Soft Label (for Distillation)** | 2015 (Hinton et al.) | To enable compact student models to mimic richer knowledge from larger teachers |
| **Multi-hot Encoding** | 2000s | Designed for multi-label classification tasks (e.g., image with multiple objects) |

<br>

- Most modern deep learning tasks—especially those involving transformers, adapters, or sequence models—use a combination of one-hot, embedding, and soft labels depending on the training phase.



<br><br><br><br>


# 1. Some Sample Models from Industry<br><br>

**1.1  - Self-supervised**

<br><br>

**1.2 - Zero-shot**

<br><br>

**1.3 - Diffusion-based**

<br><br>

**1.4  - Neural Audio Codec**


<br><br>

****<i>1.5  - Multi-modal<i>** - will discuss in the future

<br><br>


# 2. Model Training<br><br>

**2.1 Pre-training with text**<br>

- [Spirit LM: Interleaved Spoken and Written Language Model](https://arxiv.org/abs/2402.05755)
- [OpenAI - Navigating the Challenges and Opportunities of Synthetic Voices](https://openai.com/index/navigating-the-challenges-and-opportunities-of-synthetic-voices/)
- [Toward Joint Language Modeling for Speech Units and Text](https://arxiv.org/abs/2310.08715)
- [Dialogue GSLM](https://arxiv.org/abs/2203.16502)<br><br><br>

- **📍 Model in use**
  - **[wav2vec2-large-robust-ft-libri-960h](https://huggingface.co/facebook/wav2vec2-large-robust-ft-libri-960h)**

  <br><br>


  - **[wav2vec 2.0](https://github.com/facebookresearch/fairseq/tree/main/examples/wav2vec)**
  - Structure - **CNN encoder + Transformer**
  - Original Task - **CTC-based ASR - Automatic Speech Recognition**
  - [base model](https://huggingface.co/facebook/wav2vec2-base)
  - [Speech Recognition Pre-Training - Sample codes](https://github.com/huggingface/transformers/tree/main/examples/pytorch/speech-pretraining)
  - [Some discussion](https://discuss.huggingface.co/t/pre-training-for-wav2vec2-xlsr-via-huggingface/7490)
 
  <br><br>

  - **Some Others**

  - [Official Llama 3](https://github.com/meta-llama/llama3?utm_source=chatgpt.com)
  - [meta-llama/Llama-3.1-8B](https://huggingface.co/meta-llama/Llama-3.1-8B?utm_source=chatgpt.com)
  - [Toolkit for Llama models](https://github.com/meta-llama/llama-models?utm_source=chatgpt.com)
  - [2024 - Blog - Introducing Llama 3.1: Our most capable models to date](https://ai.meta.com/blog/meta-llama-3-1/?utm_source=chatgpt.com)
  - **[Ollama - Get up and running with LLMs Locally](https://github.com/ollama/ollama)**

<br><br>

- **DataSet in use**
  - LibriSpeech ASR Corpus
  - Hugging Face: https://huggingface.co/datasets/librispeech_asr
  - OpenSLR: http://www.openslr.org/12


<br><br>


**Products**

<br>

- **2024 Hearing Tracker** - [Hearing Aids with Artificial Intelligence (AI): Review of Features, Capabilities and Models that Use AI and Machine Learning](https://www.hearingtracker.com/resources/ai-in-hearing-aids-a-review-of-brands-and-models)<br><br>


- **2023 DNN** - [Restoring speech intelligibility for hearing aid users with deep learning](https://www.nature.com/articles/s41598-023-29871-8)


<br>



## Some Startups

- **[AudioShake](https://www.audioshake.ai/)**<br>
  - Key Tech<br>
    - Stem Separation - **CNN / RNN**<br>
    - **Supervised Fine-Tuning** - Utilizes labeled datasets to train models for separating different audio stems (e.g., vocals, drums)<br>
    - **Transfer Learning** - Leverages pre-trained models on large audio datasets, adapting them to specific stem separation tasks
  - Markets
    - Music production, film and television post-production, podcast editing, game audio processing, user-generated content - UGC<br>


- **[ElevenLabs](https://elevenlabs.io/)** <br>

  - Key Tech
    - TTS, Voice Cloning, Voice Conversion, STT - **DNN**<br>
    - Supervised Fine-Tuning - Trains models on paired text and speech data to generate natural-sounding speech<br>
    - Voice Cloning - Adapts models to replicate specific voices using limited voice samples<br>
    - **Multilingual Fine-Tuning** - Extends models to support multiple languages by fine-tuning on diverse linguistic datasets.
  - Markets<br>
    - Audiobooks, podcast production, game dubbing, virtual assistants, educational content, film and television dubbing<br>
  - [Python SDK](https://github.com/elevenlabs/elevenlabs-python)<br>


- **[LiveKit](https://livekit.io/)** <br>

  - Key Tech
    - Real-Time Communication Platform, Voice AI Agent Framework, Edge Infrastructure<br>
    - **Transformer / DNN / VAD**<br>
    - Supervised Fine-Tuning<br>
    - Transfer Learning<br>
  - Markets
    - Live video conferencing, voice chat, virtual events, online education, customer support<br>
  - [livekit](https://github.com/livekit/livekit)<br>


- **[RealAvatar.ai](https://www.realavatar.ai/)** <br>

  - Key Tech
    - Multimodal AI Interaction, AI Avatars - **DNN / Transformer**<br>
    - Supervised Fine-Tuning<br>
    - Transfer Learning<br>
  - Markets
    - Education and training, customer service, virtual assistant, online consultation, content creation<br>

<br><br><br>


## Some Terms and their Nature

- **Attention** - Vector of Importance Weights<br>

- **Encoder** - Bidirectional RNN<br>

- **Activation Recomputation / Gradient Checkpoint** - Memory-saving technique - Save “important activations” during Forward pass, then recompute / computation overhead when needed in backward pass - Typically Save 30–70% GPU Memory, **depending on model depth and recompute granularity**<br>

- **Additive Attention** - [2014 Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)<br>

- **Dot-product Attention** - [2023 Attention Is All You Need](https://arxiv.org/abs/1706.03762)<br>


## Additive Attention

Additive Attention computes the attention scores using a feed-forward neural network

$$
e_i = \mathbf{v}^T \tanh(\mathbf{W}_1 \mathbf{q} + \mathbf{W}_2 \mathbf{k}_i)
$$

$$
\alpha_i = \frac{\exp(e_i)}{\sum_j \exp(e_j)}
$$

$$
\mathbf{c} = \sum_i \alpha_i \mathbf{v}_i
$$

## Dot-Product Attention

Dot-Product Attention calculates the attention scores by taking the dot product of the query and key vectors

$$
e_i = \mathbf{q}^T \mathbf{k}_i
$$

$$
\alpha_i = \frac{\exp(e_i)}{\sum_j \exp(e_j)}
$$

$$
\mathbf{c} = \sum_i \alpha_i \mathbf{v}_i
$$

### Scaled Dot-Product Attention

To mitigate the issue of large dot product values in high-dimensional spaces, Scaled Dot-Product Attention scales the dot products

$$
\text{Attention}(\mathbf{Q}, \mathbf{K}, \mathbf{V}) = \text{softmax}\left( \frac{\mathbf{Q} \mathbf{K}^T}{\sqrt{d_k}} \right) \mathbf{V}
$$


<br>


- **Attention Layer** - Parameterized by a simple feed-forward network<br>

- **Decoder** - RNN with input from previous state + dynamic context vector<br>

- [**Tensor2Tensor Notebook**](https://colab.research.google.com/github/tensorflow/tensor2tensor/blob/master/tensor2tensor/notebooks/hello_t2t.ipynb)<br>

- **Self-Attention** - Where **Each Token Attends to All other tokens** in the **same Sequence**<br>


- **Multi-head Self-attention** - Runs multiple self-attention mechanisms **in Parallel to capture different relationships**<br>


- **Activation Functions - Non-linear functions after Neural Layers** <br>

  - **Softmax**:  
  $$ \alpha_i = \frac{\exp(e_i)}{\sum_j \exp(e_j)} $$  
  Used to normalize attention scores into a probability distribution over keys<br>

  - **Tanh**:  
  $$ \tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}} $$  
  Maps input to the range \([-1, 1]\), commonly used in RNNs and attention scoring<br>

  - **ReLU - Rectified Linear Unit**:  
  $$ \text{ReLU}(x) = \max(0, x) $$  
  Introduces sparsity and alleviates the vanishing gradient problem<br>

  - **GELU - Gaussian Error Linear Unit**:  
  $$ \text{GELU}(x) = x \cdot \Phi(x) $$  
  where $$ \Phi(x) = \frac{1}{2} \left[ 1 + \text{erf} \left( \frac{x}{\sqrt{2}} \right) \right] $$ is the standard Gaussian cumulative distribution function - CDF 
  GELU is smoother than ReLU and is widely used in Transformers<br>
  
<br>

- **Why need Positional Encodings** - To give the model a sense of token order, since Transformers have no recurrence or convolution<br>

- **Why Adding Residual Connections** - To Ease Gradient Flow and Improve Training Stability in Deep Networks<br>

- **Why Need Normalizations**
  - Stabilize + Accelerate Training
  - Improve Generalization
  - Handle **scale variance across features**

<br><br>

## 📍 Why Need Normalizations

- **Stabilize and accelerate training** by controlling the distribution of activations  
- Improve **generalization** across tasks  
- Handle **scale variance** across features, samples, and batches  
- Enable training with **higher learning rates** without divergence  

<br>

## Techniques

- **Layer Normalization**  
  - Normalizes across all features within each token (sample-wise)  
  - Used in: Transformers, Speech Models (e.g., wav2vec2, ASR)  

- **Batch Normalization**  
  - Normalizes each feature across the batch  
  - Used in: CNNs, MLPs, Image Classification (ResNet, VGG)  

- **Instance Normalization**  
  - Normalizes each sample and channel separately  
  - Used in: Style Transfer, Image Generation  

- **Group Normalization**  
  - Normalizes within groups of channels  
  - Used in: Vision tasks with small batches (e.g., segmentation, GANs)  

- **RMSNorm**  
  - Root-mean-square-only scaling (no mean subtraction)  
  - Used in: Lightweight Transformers, TinyLMs  

- **Weight Normalization**  
  - Normalizes weight vectors instead of activations  
  - Used in: Reinforcement Learning, Sparse Models  

<br><br><br>

## 📍 Why Need Regularization

- Prevent **overfitting** to training data  
- Improve **robustness** and **generalization**  
- Avoid **co-adaptation** of neurons  
- Stabilize **weight growth and gradient flow**  

<br><br>

##  Techniques

- **L1 Regularization (Lasso)**  
  - Encourages sparsity, useful for feature selection  

- **L2 Regularization (Ridge)**  
  - Penalizes large weights, discourages complexity  

- **Elastic Net**  
  - Combines L1 + L2 for balanced sparsity + smoothness  

- **Dropout**  
  - Randomly removes neurons during training to prevent co-adaptation  

- **DropConnect**  
  - Randomly removes connections (weights), adds structural noise  

- **Stochastic Depth**  
  - Randomly skips entire layers, improves ensemble-like diversity  

- **Early Stopping**  
  - Halts training when validation loss stops improving  

- **Weight Decay**  
  - Applies L2 penalty during optimizer update (e.g., AdamW)  

- **Label Smoothing**  
  - Softens targets to avoid overconfidence in classification  

- **Data Augmentation**  
  - Expands training data via noise, rotation, cropping, etc.  

- **Mixup / CutMix**  
  - Mix inputs and/or regions from multiple samples for better decision boundaries  

- **Noise Injection**  
  - Adds Gaussian noise to inputs or gradients for robustness  

- **Max-Norm Constraint**  
  - Limits the norm of weights for regularized learning  

- **Gradient Clipping**  
  - Prevents exploding gradients, especially in RNNs  
  


<br><br>



