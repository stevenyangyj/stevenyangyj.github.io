---
title: "Embodied Multi-Modal Agent trained by an LLM from a Parallel TextWorld"
collection: talks
type: "Presentation"
permalink: /talks/2024-06-17-CVPR24-presentation
venue: "The IEEE/CVF Conference on Computer Vision and Pattern Recognition 2024"
date: 2024-06-17
location: "Seattle Convention Center, Seattle, WA, USA"
---

[More information here](https://cvpr.thecvf.com/virtual/2024/poster/30385)

[link to the poster](../assets/emma_cvpr24_poster.pdf)

While large language models (LLMs) excel in a simulated world of texts, they struggle to interact with the more realistic world without perceptions of other modalities such as visual or audio signals. Although vision-language models (VLMs) integrate LLM modules (1) aligned with static image features, and (2) may possess prior knowledge of world dynamics (as demonstrated in the text world), they have not been trained in an embodied visual world and thus cannot align with its dynamics. On the other hand, training an embodied agent in a noisy visual world without expert guidance is often challenging and inefficient. In this paper, we train a VLM agent living in a visual world using an LLM agent excelling in a parallel text world. Specifically, we distill LLM's reflection outcomes (improved actions by analyzing mistakes) in a text world's tasks to finetune the VLM on the same tasks of the visual world, resulting in an Embodied Multi-Modal Agent (EMMA) quickly adapting to the visual world dynamics. Such cross-modality imitation learning between the two parallel worlds is achieved by a novel DAgger-DPO algorithm, enabling EMMA to generalize to a broad scope of new tasks without any further guidance from the LLM expert. Extensive evaluations on the ALFWorld benchmark's diverse tasks highlight EMMA's superior performance to SOTA VLM-based agents, e.g., 20%-70% improvement in the success rate.

![Image](../images/cvpr-24.png)