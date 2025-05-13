---
layout: post
title: Speech Processing - 25
date: 2025-05-04
description: ⛺️
categories: Research
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---

Welcome,

Let's start with the Model Post-training for Hearing Assistance - A Coding Demo Example using Llama 3.1 as text Pre-Training model<br><br>

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

<br>

- [RNN - 1990 Finding structure in time](https://www.sciencedirect.com/science/article/abs/pii/036402139090002E)<br>
- [LSTM - 1997 Long Short-Term Memory](https://ieeexplore.ieee.org/abstract/document/6795963)<br>
- [GRU - 2014 Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](https://aclanthology.org/D14-1179/)<br>
- [Transformer - 2017 Attention Is All You Need](https://proceedings.neurips.cc/paper/2017/hash/3f5ee243547dee91fbd053c1c4a845aa-Abstract.html)<br>
- [BERT - 2018 BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)- Masked Language Modeling - MLM<br>
- [Conformer - 2020 Conformer: Convolution-augmented Transformer for Speech Recognition](https://arxiv.org/abs/2005.08100)<br>
- [GAN - 2014 Generative Adversarial Networks](https://arxiv.org/abs/1406.2661)<br>


<br>

- **Diffusion Models**<br>

  - [2015 Deep Unsupervised Learning using Nonequilibrium Thermodynamics](https://arxiv.org/abs/1503.03585)<br>
  
  - [2020 Denoising Diffusion Probabilistic Models](https://arxiv.org/abs/2006.11239)<br>

<br>

- **SSL**<br>

  - [2016 - Vision - Unsupervised Learning of Visual Representations by Solving Jigsaw Puzzles](https://arxiv.org/abs/1603.09246)<br>
  - [2020 - Vision - Momentum Contrast for Unsupervised Visual Representation Learning](https://arxiv.org/abs/1911.05722)<br>
  - [2019 - Speech - wav2vec - Unsupervised Pre-training for Speech Recognition](https://arxiv.org/abs/1904.05862)<br>

<br><br>


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
  - [Official Llama 3](https://github.com/meta-llama/llama3?utm_source=chatgpt.com)
  - [meta-llama/Llama-3.1-8B](https://huggingface.co/meta-llama/Llama-3.1-8B?utm_source=chatgpt.com)
  - [Toolkit for Llama models](https://github.com/meta-llama/llama-models?utm_source=chatgpt.com)
  - [2024 - Blog - Introducing Llama 3.1: Our most capable models to date](https://ai.meta.com/blog/meta-llama-3-1/?utm_source=chatgpt.com)


<br><br><br>

**📍 2.2 Some Sample Models from the Industry**<br>

- **📍 Tülu 3 - by Ai2 - 2024**
  - [Tech Report](https://allenai.org/blog/tulu-3-technical)
  - [OLMo 2](https://allenai.org/olmo) - Language models
  - [Open Source](https://huggingface.co/collections/allenai/tulu-3-models-673b8e0dc3512e30e7dc54f5)



<br><br><br>




**2.3 Post-Training**<br>

- **Pre-Train Style**
  - 📍 **Distillation**
  - SSL
  - demo 1<br><br>

  <br><br><br>

- **Supervised-Fine-Tuning Style**
  - 📍 **Adapter - LoRA / QLoRA**
  - Prompt-tuning 
  - demo 2<br><br>

  <br><br><br>

- **Reinforcement-Learning Style**
  - RLHF<br><br>

  <br><br><br>

- Others - Generative Enhancement Style
  - 📍 **DNN-GAN for Speech Denoising**
  - demo 3<br><br>

<br><br><br><br>

# 3. Possible Improvements to the Foundation Models / During Fine-Tuning<br><br>

**3.1 Catastrophic Forgetting**
- 2024 [Scaling Laws for Forgetting When Fine-Tuning Large Language Models](https://arxiv.org/abs/2401.05605)
- 2023 [An Empirical Study of Catastrophic Forgetting in Large Language Models During Continual Fine-tuning](https://arxiv.org/abs/2308.08747)<br><br>

**Possible Solutions 🪨**
- 2024 [LoRA Learns Less and Forgets Less](https://arxiv.org/abs/2405.09673)
- 2018 [The Natural Language Decathlon: Multitask Learning as Question Answering](https://arxiv.org/abs/1806.08730)<br><br><br><br>



**3.2 Task Targeted Post-training will Degrade the model's performance on other Tasks - e.g. Safety Alignment**

- Supervised-Fine-Tuning Style Post-training - 2024 [Self-Distillation Bridges Distribution Gap in Language Model Fine-Tuning](https://arxiv.org/abs/2402.13669)
- 2023 [Safety-Tuned LLaMAs: Lessons From Improving the Safety of Large Language Models that Follow Instructions](https://arxiv.org/abs/2309.07875)<br><br>


**Possible Solutions 🪨**


<br><br><br><br>



# 4. Recent Technical Advances - pay attention to the 📍 ones<br><br>

- 📍 **2025 – [Efficient Distillation of Classifier-Free Guidance using Adapters](https://arxiv.org/abs/2503.07274)**  <br><br>
   - [A codebase](https://github.com/cristianpjensen/agd)
<br><br>
 
- **2025 – [Neuralink – gets FDA nod for chip that will let speech impaired people speak, human trials soon](https://x.com/neuralink/status/1918005257252098197)**  <br><br>
  This includes those affected by ALS, stroke, spinal cord injury, cerebral palsy, multiple sclerosis, and other neurological conditions.
<br><br>

- 📍 **2024 – [Fast Timing-Conditioned Latent Audio Diffusion](https://openreview.net/forum?id=jOlO8t1xdx)**  <br><br>

- 📍 **2023 – [Speak, Read and Prompt: High-Fidelity Text-to-Speech with Minimal Supervision](https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00618/118854)**  <br><br>
  Proposes a novel approach to text-to-speech synthesis using minimal supervision while maintaining high fidelity, making TTS systems more accessible for low-resource settings.<br><br>

- 📍 **2023 – [Vocos: Closing the gap between time-domain and Fourier-based neural vocoders for high-quality audio synthesis](https://arxiv.org/abs/2306.00814)**  <br><br>

- **2023 – [Voicebox: Versatile Generative Speech AI (Meta)](https://about.fb.com/news/2023/06/introducing-voicebox-ai-for-speech-generation/)**  <br><br>
  A generative model capable of text-to-speech, style transfer, noise removal, and speech editing using just 2 seconds of input audio.<br><br>

- 📍 **2023 – [VALL-E: Zero-Shot Text-to-Speech via Neural Codec Language Modeling](https://arxiv.org/abs/2301.02111)**  <br><br>
  Achieves personalized speech synthesis from a 3-second voice sample, preserving emotion and acoustic context in zero-shot TTS tasks.<br><br>

- **2023 – [Apple Personal Voice & Live Speech](https://www.apple.com/newsroom/2023/05/apple-previews-live-speech-personal-voice-and-more-new-accessibility-features/)**  <br><br>
  Allows users to generate a personal synthetic voice using only 15 minutes of audio, aiding those at risk of speech loss due to ALS or other conditions.<br><br>

- **2023 – [Meta Massively Multilingual Speech (MMS)](https://about.fb.com/news/2023/05/ai-massively-multilingual-speech-technology/)**  <br><br>
  Open-source speech-to-text and text-to-speech models for 1,100+ languages, massively expanding multilingual accessibility in speech AI.<br><br>

- 📍 **2022 – [Whisper: Multilingual ASR via Large-Scale Weak Supervision](https://openai.com/research/whisper)**  <br><br>
  A general-purpose speech recognition system trained on 680,000 hours of audio, robust across accents, background noise, and multiple languages.<br><br>

- **2021 – [Apple On-Device Speech Recognition for Siri](https://www.apple.com/newsroom/2021/06/ios-15-brings-new-ways-to-stay-connected-and-powerful-features-that-help-users-focus-explore-and-do-more-with-on-device-intelligence/)**  <br><br>
  Introduced local processing of Siri speech recognition, enhancing privacy and enabling offline voice commands.<br><br>

- 📍 **2020 – [wav2vec 2.0: Self-Supervised Learning of Speech Representations](https://arxiv.org/abs/2006.11477)** <br><br> 
  Demonstrated state-of-the-art ASR using very limited labeled data via self-supervised learning on large-scale unlabeled audio.<br><br>

- 📍 **2020 – [Conformer: Convolution-augmented Transformer for ASR](https://arxiv.org/abs/2005.08100)**  <br><br>
  Combined CNNs and Transformers for effective modeling of both local and global features in speech, improving ASR accuracy.<br><br>

- **2019 – [Project Euphonia (Google)](https://blog.google/outreach-initiatives/accessibility/speech-accessibility-project/)**  <br><br>
  Uses AI to improve ASR for users with atypical speech, such as those with ALS or other disorders, enhancing speech accessibility.<br><br>

- 📍 **2016 – [WaveNet: A Generative Model for Raw Audio](https://arxiv.org/abs/1609.03499)**  <br><br>
  Introduced deep generative modeling of raw audio, setting a new bar for natural-sounding speech synthesis.<br><br>

- 📍 **2015 – [Deep Speech 2: End-to-End Speech Recognition in English and Mandarin](https://arxiv.org/abs/1512.02595)** <br><br> 
  Demonstrated that deep learning can perform ASR across languages and noisy conditions without hand-engineered features.<br><br>

<br><br>


# 5. Products for Disabled People / Hearing Aid Enhancement<br><br>

**5.1 Key References**<br><br>

- [2023 A scoping review of literature using speech recognition technologies by individuals with disabilities in multiple contexts](https://pubmed.ncbi.nlm.nih.gov/34670100/)

- [2024 ASR - Using Voice Technologies to Support Disabled People](https://www.scienceopen.com/hosted-document?doi=10.57197%2FJDR-2023-0063)

<br>


**5.2 Aspects**<br><br>

- Model Adaptability<br><br>


- Computational Efficiency<br><br>


- Customization / Personalization<br><br>



**5.3 Products**<br><br>
- **2024 Hearing Tracker** - [Hearing Aids with Artificial Intelligence (AI): Review of Features, Capabilities and Models that Use AI and Machine Learning](https://www.hearingtracker.com/resources/ai-in-hearing-aids-a-review-of-brands-and-models)<br><br>


- **2023 DNN** - [Restoring speech intelligibility for hearing aid users with deep learning](https://www.nature.com/articles/s41598-023-29871-8)


<br><br><br>



# 6. Some Startups<br><br>

- **[AudioShake](https://www.audioshake.ai/)**<br>
  - Key Tech<br>
    - Stem Separation - **CNN / RNN**<br>
  - Markets
    - Music production, film and television post-production, podcast editing, game audio processing, user-generated content - UGC<br>


- **[ElevenLabs](https://elevenlabs.io/)** <br>

  - Key Tech
    - TTS, Voice Cloning, Voice Conversion, STT - **DNN**<br>
  - Markets
    - Audiobooks, podcast production, game dubbing, virtual assistants, educational content, film and television dubbing<br>
  - [Python SDK](https://github.com/elevenlabs/elevenlabs-python)<br>


- **[LiveKit](https://livekit.io/)** <br>

  - Key Tech
    - Real-Time Communication Platform, Voice AI Agent Framework, Edge Infrastructure<br>
    - **Transformer / DNN / VAD**<br>
  - Markets
    - Live video conferencing, voice chat, virtual events, online education, customer support<br>
  - [livekit](https://github.com/livekit/livekit)<br>


- **[RealAvatar.ai](https://www.realavatar.ai/)** <br>

  - Key Tech
    - Multimodal AI Interaction, AI Avatars - **DNN / Transformer**<br>
  - Markets
    - Education and training, customer service, virtual assistant, online consultation, content creation<br>

<br><br><br>


# 7. Some Terms and their Nature<br><br>

- **Attention** - Vector of Importance Weights<br>

- **Encoder** - Bidirectional RNN<br>

- **Additive Attention** - [2014 Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)<br>

- **Dot-product Attention** - [2023 Attention Is All You Need](https://arxiv.org/abs/1706.03762)<br>


### Additive Attention

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

### Dot-Product Attention

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


<br><br>


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

### **Normalizations**<br><br>

- **Layer Normalization - For Speech Processing - Transformer** - To normalize inputs across features, speeding up convergence and Improving Generalization<br>

- **Batch Normalization - CNN / MLP** - To stabilize learning by normalizing across the batch for each feature<br>

- **Instance Normalization** - To normalize each sample per channel, useful for style transfer and Image Generation<br>

- **Group Normalization - Small Batch Image Generation** - To divide channels into groups and normalize within each group<br>

- **RMSNorm - Lightweight Transformer** - A simplified version of LayerNorm without centering the mean.<br>

- **Weight Normalization - RL / Sparse Network** - Normalizes weight vectors instead of activations.<br>


<br><br><br>



# 8. Some Labs<br><br>

- [Distributed Computing](https://pw.ethz.ch/research/research-areas/distributed-computing.html)<br>

<br><br><br><br>


# References<br><br>

- [ICASSP - IEEE Intl. Conf. on Acoustics, Speech and Signal Processing](https://2025.ieeeicassp.org/)<br>

- [INTERSPEECH - Intl. Conf. on Spoken Language Processing](https://www.interspeech2025.org/home)<br>

- [TASLP - IEEE/ACM Trans. on Audio, Speech, and Language Processing](https://signalprocessingsociety.org/publications-resources/ieee-transactions-audio-speech-and-language-processing)<br>


<br><br>



