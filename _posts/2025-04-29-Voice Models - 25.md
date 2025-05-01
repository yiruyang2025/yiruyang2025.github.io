---
layout: post
title: Voice Models - 25
date: 2025-04-29
description: 🥥
categories: AI/ML
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---

Welcome ✨! 

Let's start with the Model Post-training for Hearing Assistance - An Coding Demo Example using xxxxx<br><br>

# 0. Some Background Knowledge<br><br>

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


<br><br><br>

# 1. Latest Models in Industry<br><br>

**1.1 Google Sound Amplifier, 2019**
  - [Sound Amplifier](https://play.google.com/store/apps/details?id=com.google.android.accessibility.soundamplifier)
  - [AudioEffect API](https://developer.android.com/reference/android/media/audiofx/AudioEffect)<br><br>
 
**1.2 Rogervoice, 2014**
  - [Rogervoice](https://rogervoice.com/)
  - [GitHub repository](https://github.com/rogervoice)<br><br>

**1.3 Pedius, 2013**
  - [Pedius](https://www.pedius.org/zh/zhuye/)<br><br><br><br>



# 2. Model Training<br><br>

**2.1 Pre-training with text**<br><br>

- [Spirit LM: Interleaved Spoken and Written Language Model](https://arxiv.org/abs/2402.05755)
- [OpenAI - Navigating the Challenges and Opportunities of Synthetic Voices](https://openai.com/index/navigating-the-challenges-and-opportunities-of-synthetic-voices/)
- [Toward Joint Language Modeling for Speech Units and Text](https://arxiv.org/abs/2310.08715)
- [Dialogue GSLM](https://arxiv.org/abs/2203.16502)<br><br><br><br>


**2.2 Post-Training**<br><br>

- **Pre-Train Style**<br><br>


- **Supervised-Fine-Tuning Style**<br><br>



- **Reinforcement-Learning Style**<br><br>




# 3. Possible Improvements to the Foundation Models / During Fine-Tuning<br><br>


**3.1 Catastrophic Forgetting**
- 2024 [Scaling Laws for Forgetting When Fine-Tuning Large Language Models](https://arxiv.org/abs/2401.05605)
- 2023 [An Empirical Study of Catastrophic Forgetting in Large Language Models During Continual Fine-tuning](https://arxiv.org/abs/2308.08747)<br><br><br><br>


**Possible Solutions 🪨**
- 2024 [LoRA Learns Less and Forgets Less](https://arxiv.org/abs/2405.09673)
- 2018 [The Natural Language Decathlon: Multitask Learning as Question Answering](https://arxiv.org/abs/1806.08730)<br><br><br><br>



**3.2 Task Targeted Post-training will Degrade the model's performance on other Tasks - e.g. Safety Alignment**

- Supervised-Fine-Tuning Style Post-training - 2024 [Self-Distillation Bridges Distribution Gap in Language Model Fine-Tuning](https://arxiv.org/abs/2402.13669)<br><br><br><br>

- 2023 [Safety-Tuned LLaMAs: Lessons From Improving the Safety of Large Language Models that Follow Instructions](https://arxiv.org/abs/2309.07875)<br><br><br><br>


**Possible Solutions 🪨**<br><br><br><br>



**3.3 Benchmarks**

- 2024 [Dynamic-SUPERB Phase-2: A Collaboratively Expanding Benchmark for Measuring the Capabilities of Spoken Language Models with 180 Tasks
](https://arxiv.org/abs/2411.05361)<br><br><br><br>



# 4. Recent Technical Advances<br><br>

- 2023 [Speak, Read and Prompt: High-Fidelity Text-to-Speech with Minimal Supervision](https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00618/118854)
- 2014 [Deep Speech: Scaling up end-to-end speech recognition](https://arxiv.org/abs/1412.5567)<br><br><br><br>



# 5. Products for Disabled People<br><br>


**5.1 Aspects**<br><br>

- Model Adaptability<br><br>


- Computational Efficiency<br><br>


- Customization / Personalization<br><br><br><br>



**5.2 Products**<br><br>
- 2024 Hearing Tracker - [Hearing Aids with Artificial Intelligence (AI): Review of Features, Capabilities and Models that Use AI and Machine Learning](https://www.hearingtracker.com/resources/ai-in-hearing-aids-a-review-of-brands-and-models)
- 2023 DNN - [Restoring speech intelligibility for hearing aid users with deep learning](https://www.nature.com/articles/s41598-023-29871-8)<br><br><br><br>






# 6. Speech Processing Labs<br><br><br><br>




# 7. Others<br><br>

**7.1 ASR: Automatic Speech Recognition**
  - [Whisper - OpenAI](https://github.com/openai/whisper)


**7.2 TTS: Text-to-Speech**
  - [Tacotron2 - Google](https://github.com/Rayhane-mamah/Tacotron-2)


**7.3 Voice Cloning / Real-Time TTS**
  - [ElevenLabs](https://elevenlabs.io/)
  - [Real-Time Voice Cloning](https://github.com/CorentinJ/Real-Time-Voice-Cloning)


**7.4 Emotion & Multi-speaker TTS**
  - [ChatTTS - 中英对话](https://github.com/2noise/ChatTTS)
  - [OpenVoice](https://github.com/myshell-ai/OpenVoice)

**7.5 Audio Agents**
  - [GPT-4 Turbo with Audio](https://openai.com/gpt-4-turbo/)
  - [FunAudioLLM](https://github.com/FunAudioLLM)  <br><br><br><br>



# References

- [Hung-yi Lee](https://www.youtube.com/@HungyiLeeNTU) <br><br><br><br>




