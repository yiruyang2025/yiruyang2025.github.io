---
layout: post
title: Deploy an AI Agent - 25
date: 2025-05-21
description: ⛄️
categories: Research
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---


Welcome<br>


# 1. From [Hung-yi Lee](https://www.youtube.com/@HungyiLeeNTU)

<br><br><br>

## 1.1 Model Editing<br>

- [ACL 2024] An Easy-to-use Knowledge Editing Framework for LLMs - [Easy Edit](https://github.com/zjunlp/EasyEdit)

<br><br>

## 1.1 Model Editing<br>

- [ACL 2024] An Easy-to-use Knowledge Editing Framework for LLMs - [Easy Edit](https://github.com/zjunlp/EasyEdit)

<br><br>


## 1.2 Model Editing<br>

- [Github] - [Tools for merging pretrained large language models](https://github.com/arcee-ai/mergekit?utm_source=chatgpt.com)
- [2025 - Mergenetic: a Simple Evolutionary Model Merging Library](https://arxiv.org/abs/2505.11427?utm_source=chatgpt.com)

<br><br><br><br>




# 2. Other Key Technologies for Enterprise-Grade AI Agent Deployment

<br><br><br>

1. **Model Management & Versioning**  
   - Model registry (e.g. MLflow, SageMaker Model Registry)  
   - Code + data version control (Git + DVC/Git LFS)  
   - Rollback to validated model versions
   
<br><br>

2. **Inference & High-Performance Delivery**  
   - Serving frameworks: TensorFlow Serving, TorchServe, BentoML, Ray Serve  
   - Acceleration: ONNX Runtime, TensorRT, OpenVINO (FP16/INT8)  
   - Batch vs. low-latency real-time inference
  
  <br><br>

3. **Containerization & Orchestration**  
   - Docker packaging  
   - Kubernetes + Helm/Operators for rolling updates & canary releases  
   - Edge deployment (K3s, MicroK8s)

<br><br>

4. **Automated CI/CD & GitOps**  
   - CI pipelines: GitHub Actions, GitLab CI, Jenkins  
   - CD tools: Argo CD, Flux (Config-as-Code, auto-rollback)  
   - Testing: unit, integration, A/B, canary

<br><br>

5. **Observability & Monitoring**  
   - Metrics: Prometheus + Grafana (QPS, latency, GPU/CPU, memory)  
   - Logs: ELK/EFK or Loki  
   - Alerts: threshold-based or anomaly detection (e.g. Sentry)

<br><br>

6. **Security & Access Control**  
   - AuthN/AuthZ: OAuth2/OpenID Connect, mTLS  
   - API gateway: Kong, Istio, AWS API Gateway (rate limiting, circuit breaking)  
   - Network & workload isolation (NetworkPolicy, PSP, TEE)

<br><br>

7. **Data & Feature Engineering**  
   - Feature store: Feast, Hopsworks (online/offline lookups)  
   - Data pipelines: Airflow, Argo Workflows, Prefect  
   - Data quality: Great Expectations, Deequ

<br><br>

8. **Retrieval & Knowledge Augmentation**  
   - Vector databases: Pinecone, Weaviate, Milvus  
   - Retrieval-Augmented Generation (RAG)  
   - Knowledge graphs: Neo4j, AWS Neptune

<br><br>

9. **Scalable Interaction Interfaces**  
   - Conversational frameworks: Rasa, Botpress, Microsoft Bot Framework  
   - Microservices for NLU/NLG, dialogue management  
   - Multi-channel support: Web, WeChat, Slack, Teams

<br><br>

10. **Continuous Learning & Feedback**  
    - Online/incremental training (LoRA, PEFT)  
    - Feedback loops: user ratings, human annotation  
    - A/B testing for model variants

<br><br>

11. **High Availability & Resilience**  
    - Multi-Region deployments & backups  
    - Disaster recovery drills & auto-failover  
    - Load balancing with health checks

<br><br>

12. **Cost Optimization**  
    - Auto-scaling: Kubernetes HPA/VPA, GPU schedulers (e.g. Karpenter)  
    - Spot/preemptible instances  
    - Hybrid cloud and on-premise setups

<br><br><br><br>

