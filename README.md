# Supplementary-Material-for-the-Rebuttal-of-ICML-Submission-752

This repository is provided solely as supplementary material for the rebuttal of **ICML Submission 752**.

To ensure compliance with the **ICML rebuttal policy** and the **double-blind reviewing requirements**, the repository contains only:

- experimental figures,
- tables,
- and brief descriptive captions / necessary explanatory text directly associated with those figures and tables.

***No additional substantive text, discussion, or identifying information is included.***

In particular, this repository does **not** contain any extra technical write-up, extended argumentation, author-identifying content, or materials beyond what is permitted under the ICML rebuttal guidelines.

## Relevant ICML Policy

> **Anonymity and Links:** Your responses to reviewers should not contain or link to any identifying information that may violate the double-blind reviewing policy. While links are allowed, reviewers are not required to follow them, and links may only be used for figures (including tables) and captions that describe the figure (no additional text).


## Supplementary Figures for the Rebuttal

### Figure S1. ProcGen result (2 seeds)

<h2>ProcGen result (2 seed)</h2>
<img src="./ProcGen%20result%20%282seed%29.png" alt="ProcGen result (2 seed)" width="400">

---

### Figure S2. ProcGen result (5 seeds)

<h2>ProcGen result (5 seed)</h2>
<img src="./ProcGen%20result%20%285seed%29.png" alt="ProcGen result (5 seed)" width="400"

*Caption:* ProcGen evaluation with **5 seeds** on 16 tasks at 50 million steps. This figure provides the higher-confidence comparison requested in the review. FlowMAP remains competitive with Dreamer and stronger than the other RL baselines.

---

### Figure S3. Sensitivity analysis for the quantile filtering ratio $\alpha$

<h2>Sensitivity experiment of parameter alpha</h2>
<img src="./Sensitivity%20experiment%20of%20parameter%20alpha.png" alt="Sensitivity experiment of parameter alpha" width="400">

*Caption:* Minecraft episodic return under different values of the quantile filtering ratio $\alpha$. Performance is strongest in the small-to-moderate range, with the best result observed near $\alpha=0.005$. The trend suggests that FlowMAP is not overly brittle to $\alpha$ within a reasonable operating region, while very large filtering ratios degrade performance.

---

### Figure S4. Sensitivity analysis for the temperature parameter $\beta$

<h2>Sensitivity experiment of parameter belta</h2>
<img src="./Sensitivity%20experiment%20of%20parameter%20belta.png" alt="Sensitivity experiment of parameter belta" width="400">

*Caption:* Minecraft episodic return under different values of the temperature parameter $\beta$. Performance is strongest around $\beta=1$, while both overly small and overly large values reduce return. This supports the claim that FlowMAP has a stable intermediate operating region for value shaping.

---


## Supplementary Tables

### Table S1. Atari 100k ablation results

*Caption:* Atari 100k ablation results. For consistency with the main paper, all environments report **episodic return**, i.e., the undiscounted sum of environment rewards over an episode. Brackets denote 95% confidence intervals.

| Method | Mean Return | Median Return | IQM Return |
|---|---:|---:|---:|
| No Flow (RL only) | 101.2 | 49.5 | 62.1|
| RL + Cons only | 106.5 | 53.0 | 66.4 |
| Flow w/o Value Target | 95.8 | 52.4 | 60.5 |
| Pointwise Value Update | 115.3 | 55.2 | 70.4 |
| VTFM w/o Consistency | 125.0  | 51.0 | 68.5|
| Frozen Flow | 118.2 | 60.1 | 76.2  |
| Full FlowMAP | 127.4 | 65.8 | 85.3 |

---

### Table S2. BSuite ablation results

*Caption:* BSuite ablation results. For consistency with the main paper, the reported metric is **episodic return**. Values are shown as task-level mean episodic return with 95% confidence intervals.

| Method | BSuite Mean Return (95% CI) |
|---|---:|
| No Flow (RL only) | 54.2 |
| RL + Cons only | 55.5 |
| Flow w/o Value Target | 53.8 |
| Pointwise Value Update | 61.3 |
| VTFM w/o Consistency | 57.8 |
| Frozen Flow | 65.2 |
| Full FlowMAP | 69.0 |

---

### Table S3. Benchmark setup and resource summary

*Caption:* Benchmark-level setup and resource summary for the supplementary experiments.

| Benchmark | Tasks | Replay Ratio | GPU Days | Model Size | Peak RAM Usage (GB) |
|---|---:|---:|---:|---:|---:|
| Minecraft | 1 | 32 | 1.5 | 200M | 250 |
| DMLab | 30 | 32 | 0.5 | 200M | 245 |
| ProcGen | 16 | 32 | 1.2 | 200M | 320 |
| Atari | 57 | 32 | 0.9 | 200M | 217 |
| Atari 100k | 26 | 128 | 0.1 | 200M | 30 |
| BSuite | 23 | 1024 | 0.1 | 200M | 14 |
| DMC Vision | 20 | 256 | 0.3 | 200M | 95 |
| DMC Proprio | 20 | 1024 | 0.4 | 1M | 18 |

---

### Table S4. Hardware configuration

*Caption:* Hardware used for the supplementary experiments. Unless otherwise noted, each run used a single GPU.

| Item | Value |
|---|---|
| GPU Model | NVIDIA RTX A6000 |
| Number of GPUs Available | 8 |
| GPU Memory per Card | 48 GB (49140 MiB reported) |
| CUDA Version | 12.2 |
| Driver Version | 535.288.01 |
| Per-Run GPU Usage | Single GPU |
| Total System RAM | 528 GB |

---

### Table S6. Benchmark-level dynamic heterogeneity (MDHI)

*Caption:* Benchmark-level dynamic heterogeneity measured in the same meta-state space used by FlowMAP. $H_{\mathrm{ctx}}$ denotes cross-context heterogeneity, $H_{\mathrm{temp}}$ denotes temporal non-stationarity, and $H(\mathcal{B})$ is their normalized average.

| Benchmark | $H_{\mathrm{ctx}}$ | $H_{\mathrm{temp}}$ | $H(\mathcal{B})$ |
|---|---:|---:|---:|
| ProcGen | 0.78 | 0.65 | 0.72 |
| Minecraft | 0.77 | 0.66 | 0.71 |
| Atari | 0.83 | 0.48 | 0.66 |
| DMControl | 0.41 | 0.37 | 0.39 |
