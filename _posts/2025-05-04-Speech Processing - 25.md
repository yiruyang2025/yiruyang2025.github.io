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

# 0. Some Background Knowledge<br>

Core Evolution of Voice Models:

| Year | Milestone                        | Model / Paper                                                     |
|------|----------------------------------|-------------------------------------------------------------------|
| 2014 | End-to-end ASR                   | DeepSpeech ([Hannun et al.](https://arxiv.org/abs/1412.5567))     |
| 2017 | Tacotron (neural TTS)            | Tacotron ([Wang et al.](https://arxiv.org/abs/1703.10135))        |
| 2019 | Real-time voice synthesis        | FastSpeech ([Ren et al.](https://arxiv.org/abs/1905.09263))       |
| 2020 | Self-supervised speech learning  | wav2vec 2.0 ([Baevski et al.](https://arxiv.org/abs/2006.11477))  |
| 2022 | Multilingual speech models       | Whisper (OpenAI, 2022)                                            |
| 2023 | Zero-shot voice cloning          | VALL-E  [Microsoft, 2023](https://arxiv.org/abs/2301.02111)       |
| 2023–2024 | Diffusion-based TTS         | FastDiff ([Huang et al.](https://arxiv.org/abs/2305.10973))       |
| 2024 | Multi-modal voice models         | AudioLM 2 ([Borsos et al.](https://arxiv.org/abs/2402.05427)      |


<br><br>

# 1. Sample Models from Industry<br><br>





<br><br>

# 2. Model Training<br>

**2.1 Pre-training with text**<br><br>

- [Spirit LM: Interleaved Spoken and Written Language Model](https://arxiv.org/abs/2402.05755)
- [OpenAI - Navigating the Challenges and Opportunities of Synthetic Voices](https://openai.com/index/navigating-the-challenges-and-opportunities-of-synthetic-voices/)
- [Toward Joint Language Modeling for Speech Units and Text](https://arxiv.org/abs/2310.08715)
- [Dialogue GSLM](https://arxiv.org/abs/2203.16502)<br><br><br><br>


**2.2 Post-Training**<br><br>


- **Pre-Train Style**<br><br>

- 📍 **Distillation**
- Self-supervised (Label-free representation learning)
- demo 1<br><br>

- **Supervised-Fine-Tuning Style**<br><br>

- 📍 **Adapter (LoRA / QLoRA)**
- Prompt-tuning 
- demo 2<br><br>

- **Reinforcement-Learning Style**<br><br>

- RLHF<br>

<br><br>

# 3. Possible Improvements to the Foundation Models / During Fine-Tuning<br><br>


**3.1 Catastrophic Forgetting**
- 2024 [Scaling Laws for Forgetting When Fine-Tuning Large Language Models](https://arxiv.org/abs/2401.05605)
- 2023 [An Empirical Study of Catastrophic Forgetting in Large Language Models During Continual Fine-tuning](https://arxiv.org/abs/2308.08747)<br><br><br>


**Possible Solutions 🪨**
- 2024 [LoRA Learns Less and Forgets Less](https://arxiv.org/abs/2405.09673)
- 2018 [The Natural Language Decathlon: Multitask Learning as Question Answering](https://arxiv.org/abs/1806.08730)<br><br><br><br>



**3.2 Task Targeted Post-training will Degrade the model's performance on other Tasks - e.g. Safety Alignment**

- Supervised-Fine-Tuning Style Post-training - 2024 [Self-Distillation Bridges Distribution Gap in Language Model Fine-Tuning](https://arxiv.org/abs/2402.13669)<br><br>

- 2023 [Safety-Tuned LLaMAs: Lessons From Improving the Safety of Large Language Models that Follow Instructions](https://arxiv.org/abs/2309.07875)<br><br><br><br>


**Possible Solutions 🪨**<br><br><br><br>



**3.3 Benchmarks**

- 2024 [Dynamic-SUPERB Phase-2: A Collaboratively Expanding Benchmark for Measuring the Capabilities of Spoken Language Models with 180 Tasks](https://arxiv.org/abs/2411.05361)<br><br><br><br>




# 4. Recent Technical Advances - pay attention to the 📍 ones<br><br>

- **2025 – [Neuralink – gets FDA nod for chip that will let speech impaired people speak, human trials soon](https://x.com/neuralink/status/1918005257252098197)**  <br><br>
  This includes those affected by ALS, stroke, spinal cord injury, cerebral palsy, multiple sclerosis, and other neurological conditions.
<br><br>
- 📍 **2023 – [Speak, Read and Prompt: High-Fidelity Text-to-Speech with Minimal Supervision](https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00618/118854)**  <br><br>
  Proposes a novel approach to text-to-speech synthesis using minimal supervision while maintaining high fidelity, making TTS systems more accessible for low-resource settings.<br><br>

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


**5.1 Aspects**<br><br>

- Model Adaptability<br><br>


- Computational Efficiency<br><br>


- Customization / Personalization<br><br>



**5.2 Products**<br><br>
- 2024 Hearing Tracker - [Hearing Aids with Artificial Intelligence (AI): Review of Features, Capabilities and Models that Use AI and Machine Learning](https://www.hearingtracker.com/resources/ai-in-hearing-aids-a-review-of-brands-and-models)<br><br>
- 2023 DNN - [Restoring speech intelligibility for hearing aid users with deep learning](https://www.nature.com/articles/s41598-023-29871-8)<br><br><br><br>





# 6. Speech Processing Labs<br><br><br><br>





# 7. Others<br><br>





# References

<br><br>


<br><br><br><br>

# Jounals and Conferences (pending)

<br><br>


1.1 [Transactions of the Association for Computational Linguistics (TACL)](https://direct.mit.edu/tacl)<br>
Top-tier open-access journal by ACL for high-quality NLP research.<br><br>

1.2 [Computational Linguistics (MIT Press)](https://direct.mit.edu/coli)<br>
The longest-running journal dedicated exclusively to computational linguistics and NLP theory and systems.<br><br>

1.3 [Speech Communication (Elsevier)](https://www.journals.elsevier.com/speech-communication)<br>
Covers research in speech processing, perception, and spoken dialogue systems across science and engineering.<br><br>

1.4 [IEEE/ACM Transactions on Audio, Speech, and Language Processing (TASLP)](https://dl.acm.org/journal/taslp)<br>
Publishes state-of-the-art techniques in audio, speech recognition, signal enhancement, and language processing.<br><br>

1.5 [Journal of the Acoustical Society of America (JASA)](https://asa.scitation.org/journal/jas)<br>
A foundational journal for research in acoustics, phonetics, speech production and perception.<br><br>







