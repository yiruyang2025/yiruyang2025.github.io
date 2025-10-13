---
layout: page
title: 2025 - Thesis - Multimodal
description: MedGamma, Into A Hospital
img: assets/img/4.jpg
importance: 4
category: work
related_publications: true
---

<br>

## NeurlPS 2026 Submission Quick Check

<br>

 | Focus Area                 | **ICML**                                           | **ICLR**                                             | **NeurIPS**                                                  |
| -------------------------- | -------------------------------------------------- | ---------------------------------------------------- | ------------------------------------------------------------ |
| **Core Identity**          | Theory & Algorithms                                | Representation & Deep Learning                       | Broad AI & Computational Science                             |
| **Theoretical Work**       | Optimization, convergence, learning theory         | Representation learning theory                       | Mathematical + computational perspectives (theory + applied) |
| **Architecture**           | Classical ML (kernels, boosting, graphical models) | Neural architectures (Transformers, Diffusion, GNNs) | Novel architectures with interdisciplinary impact            |
| **Reinforcement Learning** | Algorithmic + theoretical RL                       | Representation-based RL, world models                | RL + neuroscience + multi-agent + cognitive links            |
| **Generative Models**      | Probabilistic & Bayesian models                    | Neural generative models (GANs, VAEs, Diffusion)     | Foundation models, multimodal, scaling laws                  |
| **Applications**           | Applied ML (health, econ, systems, social science) | Deep-learning apps (CV, NLP, multimodal)             | Cross-domain (AI + physics, bio, climate, neuroscience)      |
| **Experiment Style**       | Balanced theory & experiments                      | Large-scale empirical results                        | Technically deep + interdisciplinary demos                   |

<br>

## References



[UK Biobank](https://www.ukbiobank.ac.uk/)

[SCAI](https://scai.ethz.ch/)

[2025 - MC-MED](https://github.com/dkimlab/MCMED)

[2020 - Topological Autoencoders](https://proceedings.mlr.press/v119/moor20a.html?ref=https://githubhelp.com)


[2025 - Development of a multimodal vision transformer model for predicting traumatic versus degenerative rotator cuff tears on magnetic resonance imaging: A single-centre retrospective study](https://esskajournals.onlinelibrary.wiley.com/doi/10.1002/ksa.70000)

<br>


## Toolkit


[2025 - Brainchop: In-browser 3D MRI rendering and segmentation](https://github.com/neuroneural/brainchop)


<br><br>


## Organ / Liver Preservation

  
[USZ - Department of Visceral Surgery and Transplantation](https://www.usz.ch/en/department/visceral-and-transplantation/)

[2025 - Predicting Rejection Risk in Heart Transplantation: An Integrated Clinical–Histopathologic Framework for Personalized Post-Transplant Care](https://www.linkedin.com/posts/anant-madabhushi-9a75a21_hearttransplant-ai-digitalpathology-activity-7372616055581585408-x86I?utm_source=share&utm_medium=member_desktop&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk)


[2025 - MC-MED, multimodal clinical monitoring in the emergency department](https://www.nature.com/articles/s41597-025-05419-5)


[📍 2025 - USZ + ETHz - Regenerative Heart Repair](https://www.linkedin.com/posts/omer-dzemali-prof-dr-med-dr-h-c-2702b9104_from-lab-to-beating-hearts-activity-7358452392071262208-bPba?utm_medium=ios_app&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk&utm_source=social_share_send&utm_campaign=copy_link)

[Department of Thoracic Surgery](https://www.usz.ch/team/sami-hosari/)



<br>

## End-to-End Real-World Data Flow - [USZ](https://www.usz.ch/en/department/diagnostic-and-interventional-radiology/)



```
Hospital CT / MRI 🏥
        ↓

DICOM (raw slices + metadata)
        ↓ Segmentation + Reconstruction

Surface Mesh (OBJ / STL / PLY / VTK)
        ↓ Projection

2D SVG (interactive) / PNG (static)
        ↓ Annotation

Surgeon marks points / lines on SVG
        ↓ Mapping

Handles mapped back to 3D mesh
        ↓ Deformation

FastAPI /deform → ARAP deformation applied
        ↓ Visualization

Updated 3D mesh rendered in LiverViewer (three.js)
        ↓ Export

Surgical plan → PDF / PNG / QR for clinical workflow
```

<br>








