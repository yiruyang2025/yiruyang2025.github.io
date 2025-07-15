---
layout: post
title: Neuroscience Basis For Hearing & Vision - 25
date: 2025-06-02
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

Neuroscience Basis for “Perceptual Quality Depends on Few Dimensions”

<br>

  - Human vision and hearing are most sensitive to low-frequency, structural, and semantic features, while high-frequency perturbations or extreme details are often ignored<br>

  - In other words, only a small part of the overall signal information determines our subjective judgment of “realism” and “clarity”<br>


<br>

**Since** our sensory organs and early neural circuits preferentially encode low‐to‐mid frequency, structural, and semantic features—while largely filtering out imperceptible high-frequency noise—generative models that concentrate capacity on those perceptually relevant dimensions achieve high subjective quality with far less computational cost

<br>

E.g.

<br>

**The Generalization of Sampling**

```
def generalized_sampling_theory():
    Why downsampling always works in deep learning

    Classical Nyquist theorem limitations
    classical_nyquist = "f_sample ≥ 2 × f_max"  # Perfect reconstruction requires
    
    # Deep learning's relaxed conditions
    dl_sampling = {
        "No need for perfect reconstruction",
        "Only need to preserve task-relevant information",
        "Tolerate controlled information loss",
        "Compensate loss through learning"
    }
    
    # Effective sampling rate
    # f_effective = f_original × (task_relevance_ratio)
    # in most cases task_relevance_ratio = 0.1-0.3
    # Usually task_relevance_ratio = 0.1-0.3
    
    -> 📍 Task-oriented sampling more efficient than signal-oriented
```

<br>

**The Essence of DownSampling**

```
def downsampling_essence():

   fundamental_principles = {
       "Information_Theoretic_Foundation": {
           "principle": "Natural signals have high intrinsic redundancy",
           "quantification": "80-90% of information is redundant"
       },
       
       "Perceptual_Science": {
           "principle": "Human perceptual systems have limitations", 
           "application": "Details beyond perceptual thresholds can be safely discarded"
       },
       
       "Statistical_Learning": {
           "principle": "High-dimensional data lies on low-dimensional manifolds",
           "implementation": "Encoders learn this dimensionality reduction mapping"
       },
       
       "Task_Optimization": {
           "principle": "Only need to preserve task-relevant information",
           "benefits": "Improve generalization, reduce overfitting"
       },
       
       "Computational_Reality": {
           "principle": "Limited resources require tradeoffs",
           "solution": "Downsampling provides optimal efficiency-performance balance"
       }
   }
   
   return fundamental_principles
    -> information reorganization and abstraction
```

<br>

**Human Perceptual Limitations**

```
# Human perceptual characteristics
perceptual_limits = {
    "Vision": {
        "temporal_resolution": "24-60 fps (excess is redundant)",
        "spatial_resolution": "Huge central vs peripheral difference",
        "color_resolution": "Green > Red > Blue sensitivity"
    },
    
    "Audition": {
        "temporal_resolution": "2-3ms (10ms frames clearly oversample)",
        "frequency_resolution": "Logarithmic scale, low high-freq resolution",
        "loudness_perception": "Logarithmic, subtle differences imperceptible"
    }
}

-> Encoders can safely discard imperceptible information
```

<br><br>


**Hybrid Approach**
<br>

Many state-of-the-art systems embed prior knowledge of classical compression domains (such as DCT and subband decomposition) into learnable networks, which not only retains the interpretability and stability of manual design, but also uses machine learning to supplement details from data


**Prior + Learning**

  - 1. Prior (handcrafted) - provides a "good starting point", narrows the model search space, and makes training more efficient and stable
<br>

  - 2. Learning (data-driven) - further fine-tuning or expansion within the prior framework allows the model to better adapt to the complexity of actual data

<br>

```
The reason why latent vectors are particularly effective is largely because human perception itself is "multi-scale". In the audio field:

  1. Very fast amplitude changes make us feel pitch
  2. Slower changes make us feel rhythm

In the visual field:

  1. Local rapid color intensity fluctuations will be perceived by us as texture
  2. Large-scale layout (such as object outline and structure) is the key information for us to truly identify "objects"

If the latent vector can automatically discard the "high-frequency texture" details that do not affect perception, but retain the "low-frequency structure" that determines the shape or rhythm of the object, it will not only conform to the human perception mechanism, but also greatly simplify the content that the generation model needs to learn.

A good latent vector will abstract all the subtle variations of “grass texture” into a simple “grass present” label, while keeping key structural information like eyes intact. In this way, the generative model only needs to learn the distribution of “grass present or not present”, without having to simulate endless grass blade noise.
```

<br>


## Entropy in Perceptual Signals

For a random variable \( X \) (e.g., pixel intensity) with probability distribution \( p(x) \), its entropy is defined as:

$$
H(X) = - \sum_x p(x)\,\log_2 p(x)
$$

- If a pixel’s value is nearly constant (e.g., the uniform blue of the sky), then $H(X) \approx 0$.
- If a pixel’s value is uniformly distributed over many colors, then $H(X)$ approaches its maximum, $\log_{2}(\text{number of possible values})$.

- In a photograph of a dog in a field:  
  - The **sky region** has **low entropy** (neighboring pixels are easy to predict),  
  - The **grass texture** has **high entropy** (neighboring pixels vary unpredictably).


<br><br>


```
if entropy < threshold_low:
    encode_as_constant_block(region)  

if entropy > threshold_high:
    abstract_as_texture_type(region)
```


<br><br>


## 📍 SparseMAE & Contrastive-Sparse - 25

<br>

```
class GazeContrastiveSparse:
    def __init__(self):

        self.contrastive_sparse = ContrastiveSparse()
        self.gaze_augment = GazeAugmentation()
        
    def train_on_gaze_data(self, gaze_sequence):

        aug1 = self.gaze_augment.temporal_jitter(gaze_sequence)
        aug2 = self.gaze_augment.spatial_noise(gaze_sequence)
        
        loss, feat1, feat2 = self.contrastive_sparse(aug1, aug2)
        
        key_fixations = self.extract_sparse_fixations(feat1)
        
        return loss, key_fixations
        
    def extract_sparse_fixations(self, features):

        activation_mask = (torch.abs(features) > threshold)
        sparse_indices = torch.nonzero(activation_mask)
        
        return sparse_indices
```



<br><br>

## Flow Matching for Temporal Consistency



<br><br>


## 📍 Neuroscience Perception Modeling - 25


- Biological inspiration from the human visual system:
  - Multi-scale perception mechanism (fovea vs peripheral vision)
  - Sparsity of attention (spotlight attention)
  - Hierarchy of visual priorities
  - Coupling relationship between eye movement and cognition

<br>

```
class PredictiveGazeInteraction:
    def predict_user_next_action(self, gaze_sequence):

        intention = self.extract_intention(gaze_sequence)
        
        next_action = self.predict_action(intention)

        self.prepare_for_action(next_action)
        
        return next_action


class RealTimeEyeTracking:
    def __init__(self):

        self.latency_target = 1  # 1ms

        self.sparse_processor = UltraSpareProcessor()
        
    def process_gaze_realtime(self, eye_data):

        sparse_features = self.sparse_processor(eye_data)
        
        prediction = self.fast_predict(sparse_features)
        
        return prediction
```





<br><br>

# References
<br>

- [2025 - Generative modelling in latent space](https://sander.ai/#acknowledgements)<br>

- Tancik, Srinivasan, Mildenhall, Fridovich-Keil, Raghavan, Singhal, Ramamoorthi, Barron, Ng, “Fourier Features Let Networks Learn High Frequency Functions in Low Dimensional Domains”, Neural Information Processing Systems, 2020.


<br><br><br><br>

