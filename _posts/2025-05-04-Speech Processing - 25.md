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

Welcome! 

Let's start with the Model Post-training for Hearing Assistance - An Coding Demo Example using xxxxx<br><br>

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

<br><br>

- [RNN - 1990 Finding structure in time](https://www.sciencedirect.com/science/article/abs/pii/036402139090002E)

<br><br>

- [LSTM - 1997 Long Short-Term Memory](https://ieeexplore.ieee.org/abstract/document/6795963)

<br><br>

- [GRU - 2014 Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](https://aclanthology.org/D14-1179/)

<br><br>

- [Transformer - 2017 Attention Is All You Need](https://proceedings.neurips.cc/paper/2017/hash/3f5ee243547dee91fbd053c1c4a845aa-Abstract.html)

<br><br>

- [Conformer - 2020 Conformer: Convolution-augmented Transformer for Speech Recognition](https://arxiv.org/abs/2005.08100)

<br><br>

- [GAN - 2014 Generative Adversarial Networks](https://arxiv.org/abs/1406.2661)


<br><br>

- **Diffusion Models**<br>

  - [2015 Deep Unsupervised Learning using Nonequilibrium Thermodynamics](https://arxiv.org/abs/1503.03585)<br>
  
  - [2020 Denoising Diffusion Probabilistic Models](https://arxiv.org/abs/2006.11239)<br>


<br><br>

- **SSL**<br>

  - [2016 - Vision - Unsupervised Learning of Visual Representations by Solving Jigsaw Puzzles](https://arxiv.org/abs/1603.09246)<br>
  - [2020 - Vision - Momentum Contrast for Unsupervised Visual Representation Learning](https://arxiv.org/abs/1911.05722)<br>
  - [2019 - Speech - wav2vec - Meta: Unsupervised Pre-training for Speech Recognition](https://arxiv.org/abs/1904.05862)<br>


<br><br>

<br><br>

# 1. Sample Models from Industry<br><br>

**1.1 wav2vec 2.0 - Self-supervised**<br>

- [Baevski et al.](https://arxiv.org/abs/2006.11477)<br>
- [GitHub - facebookresearch/fairseq](https://github.com/facebookresearch/fairseq/tree/main/examples/wav2vec) <br>


<br><br>

**1.2 VALL-E - Zero-shot**<br>

- [Microsoft, 2023](https://arxiv.org/abs/2301.02111)<br>
- [Unofficial GitHub Implementation](https://github.com/enhuiz/vall-e)<br>


<br><br>

**1.3 FastDiff - Diffusion-based**<br>

- [Huang et al.](https://arxiv.org/abs/2305.10973)<br>
- [GitHub - FastDiff](https://github.com/yl4579/FastDiff)<br>


<br><br>

**1.4 EnCodec - Neural Audio Codec**<br>

- [Défossez et al., Meta (2022)](https://arxiv.org/abs/2210.13438) <br> 
- [GitHub - facebookresearch/encodec](https://github.com/facebookresearch/encodec)<br>

<br><br>

****<i>1.5 AudioLM 2 - Multi-modal<i>** - will discuss in the future <br>

- [Borsos et al., 2024](https://arxiv.org/abs/2402.05427)<br>  
- [Google Research AudioLM Page](https://google-research.github.io/seanet/audiolm/)<br> 


<br><br><br><br>



# 2. Model Training<br><br>

**2.1 Pre-training with text**<br>

- [Spirit LM: Interleaved Spoken and Written Language Model](https://arxiv.org/abs/2402.05755)
- [OpenAI - Navigating the Challenges and Opportunities of Synthetic Voices](https://openai.com/index/navigating-the-challenges-and-opportunities-of-synthetic-voices/)
- [Toward Joint Language Modeling for Speech Units and Text](https://arxiv.org/abs/2310.08715)
- [Dialogue GSLM](https://arxiv.org/abs/2203.16502)<br><br><br>


**2.2 Post-Training**<br>

- **Pre-Train Style**
  - 📍 Distillation
  - Self-supervised / Label-free representation Learning
  - demo 1<br><br>

- **Supervised-Fine-Tuning Style**
  - 📍 Adapter (LoRA / QLoRA)
  - Prompt-tuning 
  - demo 2<br><br>

- **Reinforcement-Learning Style**
  - RLHF<br>

<br><br>

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

- **2020 – [Conformer: Convolution-augmented Transformer for ASR](https://arxiv.org/abs/2005.08100)**  <br><br>
  Combined CNNs and Transformers for effective modeling of both local and global features in speech, improving ASR accuracy.<br><br>

- **2019 – [Project Euphonia (Google)](https://blog.google/outreach-initiatives/accessibility/speech-accessibility-project/)**  <br><br>
  Uses AI to improve ASR for users with atypical speech, such as those with ALS or other disorders, enhancing speech accessibility.<br><br>

- **2019 – [Parrotron: End-to-End Speech Conversion for Atypical Speech](https://arxiv.org/abs/1904.04169)**  <br><br>
  Converts unintelligible speech into more standard patterns using speech-to-speech models, aiding those with speech impairments.<br><br>

- **2019 – [Translatotron: Direct Speech-to-Speech Translation](https://ai.googleblog.com/2019/05/introducing-translatotron.html)**  <br><br>
  First model to perform speech-to-speech translation directly without intermediate text, even preserving speaker identity.<br><br>

- **2018 – [Google Duplex](https://ai.googleblog.com/2018/05/duplex-ai-system-for-natural-conversation.html)** <br><br> 
  Demonstrated natural-sounding, automated phone conversations using advanced TTS and speech understanding in constrained domains.<br><br>

- **2017 – [Tacotron 2: Natural TTS Synthesis](https://arxiv.org/abs/1712.05884)**  <br><br>
  Combines a sequence-to-sequence model with WaveNet to produce highly natural-sounding synthetic speech.<br><br>

- **2017 – [Tacotron: Towards End-to-End Speech Synthesis](https://arxiv.org/abs/1703.10135)**  <br><br>
  A unified neural network that predicts speech spectrograms from character sequences, streamlining the TTS pipeline.<br><br>

- **2016 – [WaveNet: A Generative Model for Raw Audio](https://arxiv.org/abs/1609.03499)**  <br><br>
  Introduced deep generative modeling of raw audio, setting a new bar for natural-sounding speech synthesis.<br><br>

- **2015 – [Listen, Attend and Spell](https://arxiv.org/abs/1508.01211)**  <br><br>
  Proposed an attention-based sequence-to-sequence model for end-to-end speech recognition, replacing phoneme-based systems.<br><br>

- **2015 – [Deep Speech 2: End-to-End Speech Recognition in English and Mandarin](https://arxiv.org/abs/1512.02595)** <br><br> 
  Demonstrated that deep learning can perform ASR across languages and noisy conditions without hand-engineered features.<br><br>

- **2014 – [Deep Speech: Scaling up End-to-End Speech Recognition](https://arxiv.org/abs/1412.5567)**  
  One of the first end-to-end deep learning systems for large-scale speech recognition, trained on hundreds of hours of data.<br><br><br><br>


# 5. Products for Disabled People / Hearing Aid Enhancement<br><br>

**5.1 Key References**<br><br>

- [2023 A scoping review of literature using speech recognition technologies by individuals with disabilities in multiple contexts](https://pubmed.ncbi.nlm.nih.gov/34670100/)<br><br>

- [2024 ASR - Using Voice Technologies to Support Disabled People](https://www.scienceopen.com/hosted-document?doi=10.57197%2FJDR-2023-0063)


<br><br><br><br>


**5.2 Aspects**<br><br>

- Model Adaptability<br><br>


- Computational Efficiency<br><br>


- Customization / Personalization<br><br>



**5.3 Products**<br><br>
- 2024 Hearing Tracker - [Hearing Aids with Artificial Intelligence (AI): Review of Features, Capabilities and Models that Use AI and Machine Learning](https://www.hearingtracker.com/resources/ai-in-hearing-aids-a-review-of-brands-and-models)<br><br>


- 2023 DNN - [Restoring speech intelligibility for hearing aid users with deep learning](https://www.nature.com/articles/s41598-023-29871-8)



<br><br><br><br>



# 6. Some Startups<br><br>

- **[AudioShake](https://www.audioshake.ai/)**

<br><br>

- **[ElevenLabs](https://elevenlabs.io/)**

<br><br>

- **[LiveKit](https://livekit.io/)**

<br><br>

- **[RealAvatar.ai](https://www.realavatar.ai/)**

<br><br>


- **[ElevenLabs](https://elevenlabs.io/)**

<br><br><br><br>


# 7. Some Terms and their Nature<br><br>

- **Attention** - Vector of Importance Weights<br>

- **Encoder** - Bidirectional RNN<br>

- **Additive Attention** - [2014 Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)<br>

- **Dot-product Attention** - [2023 Attention Is All You Need](https://arxiv.org/abs/1706.03762)<br>




---
layout: post
title: "Understanding Additive and Dot-Product Attention Mechanisms"
date: 2025-05-10
description: "An in-depth look at Additive and Dot-Product Attention with mathematical formulations."
tags: [attention, deep learning, NLP]
categories: [machine-learning]
related_posts: false
---

In this post, we explore two fundamental attention mechanisms in deep learning: **Additive Attention** and **Dot-Product Attention**.

### Additive Attention

Additive Attention computes the attention scores using a feed-forward neural network:

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

Dot-Product Attention calculates the attention scores by taking the dot product of the query and key vectors:

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

To mitigate the issue of large dot product values in high-dimensional spaces, Scaled Dot-Product Attention scales the dot products:

$$
\text{Attention}(\mathbf{Q}, \mathbf{K}, \mathbf{V}) = \text{softmax}\left( \frac{\mathbf{Q} \mathbf{K}^T}{\sqrt{d_k}} \right) \mathbf{V}
$$

Understanding these attention mechanisms is crucial for grasping the inner workings of models like Transformers and their applications in NLP tasks.


<br><br>


- **Attention Layer** - Parameterized by a simple feed-forward network<br>

- **Decoder** - RNN with input from previous state + dynamic context vector<br>

- [**Tensor2Tensor Notebook**](https://colab.research.google.com/github/tensorflow/tensor2tensor/blob/master/tensor2tensor/notebooks/hello_t2t.ipynb)<br>

- **Self-Attention** - <br>


- **Multi-head Self-attention** - <br>


- **Activation Functions** - <br>

  - **Softmax**:  
  $$ \alpha_i = \frac{\exp(e_i)}{\sum_j \exp(e_j)} $$  
  Used to normalize attention scores into a probability distribution over keys<br>

  - **Tanh**:  
  $$ \tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}} $$  
  Maps input to the range \([-1, 1]\), commonly used in RNNs and attention scoring<br>

  - **ReLU (Rectified Linear Unit)**:  
  $$ \text{ReLU}(x) = \max(0, x) $$  
  Introduces sparsity and alleviates the vanishing gradient problem<br>

  - **GELU (Gaussian Error Linear Unit)**:  
  $$ \text{GELU}(x) = x \cdot \Phi(x) $$  
  where $$ \Phi(x) = \frac{1}{2} \left[ 1 + \text{erf} \left( \frac{x}{\sqrt{2}} \right) \right] $$ is the standard Gaussian cumulative distribution function (CDF).  
  GELU is smoother than ReLU and is widely used in Transformers<br>
  
 
<br><br>

- **Why need Positional Encodings** - <br>

- **Why Adding Residual Connections** - <br>

- **Layer Normalization** - <br>


<br><br><br><br>




# Jounals and Conferences (pending)

<br><br>


- [Transactions of the Association for Computational Linguistics (TACL)](https://direct.mit.edu/tacl)<br>
Top-tier open-access journal by ACL for high-quality NLP research.<br><br>

- [Computational Linguistics (MIT Press)](https://direct.mit.edu/coli)<br>
The longest-running journal dedicated exclusively to computational linguistics and NLP theory and systems.<br><br>

- [Speech Communication (Elsevier)](https://www.journals.elsevier.com/speech-communication)<br>
Covers research in speech processing, perception, and spoken dialogue systems across science and engineering.<br><br>

- [IEEE/ACM Transactions on Audio, Speech, and Language Processing (TASLP)](https://dl.acm.org/journal/taslp)<br>
Publishes state-of-the-art techniques in audio, speech recognition, signal enhancement, and language processing.<br><br>

- [Journal of the Acoustical Society of America (JASA)](https://asa.scitation.org/journal/jas)<br>
A foundational journal for research in acoustics, phonetics, speech production and perception.<br><br>



# References

<br><br>

- [2021 Attention, Transformer, and BERT](https://www.aiotlab.org/teaching/dl_app/slides/6_3_attention_n_bert.pdf)



<br><br><br><br>



