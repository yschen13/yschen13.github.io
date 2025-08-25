---
layout: default
title: Publications
---

# Research topics

### 1. Data driven discovery of computation principles 
Historically, scientists have inferred the brain’s plasticity rules and decision making principles (e.g., reinforcement learning) manually from neural recordings and behavioral observations. However, as datasets grow larger and task paradigms become increasingly complex, these traditional approaches may become less feasible. This underscores the need for algorithms that enable data-driven discovery of learning rules. Some of my onging work is guided by this line of thoughts: 
  - Multi-agent inverse reinforcement learning to **reveal the value functions**, Theory-of-Mind mentalization process of animals. My current work has setup an [inference algorithm](https://www.biorxiv.org/content/10.1101/2024.10.09.617461v1.abstract) to achieve that in multiple animals.
  - Data driven discovery of **social learning rules**. By accessing value functions at different snapshots of the learning process, we can link their updates to various functional forms of decisions, outcomes, and others’ choices. [My ongoing work](/assets/files/Poster_RL_LDS.pdf) explores that using reinformence learning constrained state-space modeling.How DeepMind team approaches that using [LLMs](https://www.biorxiv.org/content/10.1101/2025.02.05.636732v1.full.pdf).
  - Data driven discovery of **neural plasticity rules**. After inferring behavioral-level learning rules, the next step is to uncover how the brain implements them. Recent advances in meta-learning provide promising tools for this endeavor. [[Ref1](https://proceedings.neurips.cc/paper/2020/hash/bdbd5ebfde4934142c8a88e7a3796cd5-Abstract.html)] [[Ref2](https://proceedings.neurips.cc/paper_files/paper/2024/hash/47dfa401aa7f51bd16783fc62c0684ee-Abstract-Conference.html)]


 <!-- Examples of work in this direction that I find inspiring include inverse reinforcement learning approaches ([[1](https://openreview.net/forum?id=nosngu5XwY9)]), meta-learning approaches ([[2](https://proceedings.neurips.cc/paper/2020/hash/bdbd5ebfde4934142c8a88e7a3796cd5-Abstract.html)], [[3](https://proceedings.neurips.cc/paper_files/paper/2024/hash/47dfa401aa7f51bd16783fc62c0684ee-Abstract-Conference.html)], [[4](https://www.biorxiv.org/content/10.1101/2025.02.05.636732v1.full.pdf)]), as well as my own ongoing work:  -->


### 2. Revealing network learning from representations
Where we are now can provide important clues about where we came from. By examining the neural representations that emerge during a given behavioral paradigm, it is possible—at least in artificial neural networks (ANNs)—to infer the underlying learning trajectories. In recent years, there has been a surge of theoretical work in machine learning aimed at opening the “black box” of learning dynamics and representations in ANNs. These advances offer powerful tools that we can also leverage to illuminate the black box of brain networks. 
- What is the unifying objective function of the brain that accounts for the wide range of findings observed in neuroscience experiments? [My previous work](https://www.cell.com/neuron/fulltext/S0896-6273(24)00371-4) focused on temporal predictive coding in hippocampus. Future work would be focusing on extending the temporal predictive coding framework to cortical column computation in neural processing hierachy. 
- What unique inductive biases and constraints of the brain contribute to its flexible and adaptive learning? [My onging work](/assets/files/Poster_CogMap.pdf) explored the emergence of cognitive maps underlying different network learning rules and initialization. 


### 3. Revealing the brain's functional connectivity 
While many statistical methods can reveal correlational structures, evaluating the brain’s functional connectivity requires accounting for its intrinsic dynamics. [My previous work](https://www.pnas.org/doi/abs/10.1073/pnas.2117234119) was the first to integrate network dynamics into the evaluation of functional connectivity, opening opportunities for many extensions-for example, incorporating specific nonlinearities or modeling the influence of external inputs.

---

### Selected Publications
* **Chen, Y.**, Zhang, H., Cameron, M. & Sejnowski, T.J. (2024) Predictive sequence learning in the hippocampal formation. Neuron 112, 1-14. [[paper](https://www.cell.com/neuron/fulltext/S0896-6273(24)00371-4)]

* **Chen, Y.**, Rosen, B. Q. & Sejnowski, T. J. (2022) Dynamical differential covariance recovers directional network structure in multiscale neural systems. _Proceedings of the National Academy of Sciences (2022)._ [[paper](https://www.pnas.org/doi/abs/10.1073/pnas.2117234119)][[code](https://github.com/yschen13/DDC)] [[5-min video](https://www.youtube.com/watch?v=okGOtK3Y7IM)]

### Preprints
* **Chen, Y.**, Radulescu, A. & Wu, Z. (2024) Unveiling the latent dynamics in social cognition with multi-agent inverse reinforcement learning. _bioRxiv_ [[paper](https://www.biorxiv.org/content/10.1101/2024.10.09.617461v1.full.pdf+html)]

* Cameron, M., **Chen, Y.** & Sejnowski, T. A biologically-plausible alternative to backpropagation using pseudoinverse feedback connections. _Accepted to Cosyne 2025_

* **Chen, Y.**, Recanatesi, S., Jiang, P., Rao, R., Mihalas, S., Fairhall, A., & Shea-Brown, E. (2024) How learning regimes shape the emergence of cognitive maps. _in prep_

* **Chen, Y.**, Recanatesi, S., Liu, S., Cohen, J., Shea-Brown, E. (2024) Reinforcement learning constrained state space modeling of neural decisions. _in prep_

---

### Service
* Reviewer for _Nature_, _Proceedings of the National Academy of Sciences_, _ICLR_, _Neural Computation_
* TA for Allen Summer Workshop on the Dynamics Brain
* Graduate instructor assistant for system computational neuroscience, UCSD
* Graduate instructor assistant for bioinformatics, UCSD

### Awards
* Swartz Postdoctoral Fellowship (2023)
* Kavli-Helinski Fellowship (2021, 2022)
* National Scholarship of China (2016)

---

<div style="text-align: center; margin-top: 30px;">
  <a href="{{ "/" | relative_url }}" style="display: inline-block; padding: 12px 24px; background-color: #f0f0f0; color: #333; text-decoration: none; border-radius: 5px; font-weight: 600; border: 2px solid #ddd; transition: all 0.3s ease;">
    ← Return to Main Page
  </a>
</div> 