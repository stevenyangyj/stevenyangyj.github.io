---
title: "Continual Task Allocation in Meta-Policy Network via Sparse Prompting"
collection: talks
type: "Presentation"
permalink: /talks/2023-07-23-ICML23-presentation
venue: "The Fortieth International Conference on Machine Learning"
date: 2023-07-23
location: "Hawaiʻi Convention Center, 1801 Kalākaua Avenue Honolulu, HI 96815"
---

[More information here](https://icml.cc/virtual/2023/poster/24080)

[link to the poster](../assets/cotasp_icml23_poster.pdf)

How to train a generalizable meta-policy by continually learning a sequence of tasks? It is a natural human skill yet challenging to achieve by current reinforcement learning: the agent is expected to quickly adapt to new tasks (plasticity) meanwhile retaining the common knowledge from previous tasks (stability). We address it by "Continual Task Allocation via Sparse Prompting (CoTASP)", which learns over-complete dictionaries to produce sparse masks as prompts extracting a sub-network for each task from a meta-policy network. CoTASP trains a policy for each task by optimizing the prompts and the sub-network weights alternatively. The dictionary is then updated to align the optimized prompts with tasks' embedding, thereby capturing tasks' semantic correlations. Hence, relevant tasks share more neurons in the meta-policy network due to similar prompts while cross-task interference causing forgetting is effectively restrained. Given a meta-policy and dictionaries trained on previous tasks, new task adaptation reduces to highly efficient sparse prompting and sub-network finetuning. In experiments, CoTASP achieves a promising plasticity-stability trade-off without storing or replaying any past tasks' experiences. It outperforms existing continual and multi-task RL methods on all seen tasks, forgetting reduction, and generalization to unseen tasks.

![Image](../images/icml-23.png)