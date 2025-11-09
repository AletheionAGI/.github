# 👁️‍🗨️ Aletheion Research Collective

**Epistemically Safe Artificial Intelligence**
*A geometric approach to solving the Skynet problem.*

---

## 🚀 Overview

The **Aletheion Research Collective** is an open scientific initiative exploring how to embed **epistemic humility** — the ability of AI systems to know when and how much they *don’t* know — directly into model architectures.

Our mission: **to build powerful yet self-calibrated intelligence.**

The project is based on the research paper:

> *[How to Solve Skynet: A Pyramidal Law for Epistemic Equilibrium](https://github.com/AletheionAGI/.github/blob/main/How_to_solve_Skynet__v_1_102.pdf)*
> by Felipe Maya Muniz, Aletheion Research Collective, 2024

---

## 🧠 Core Idea

Modern LLMs grow more capable as they scale — but also more **overconfident**.
Aletheion proposes a geometric solution: a **pyramidal epistemic architecture** that encodes uncertainty as structure.

### The Pyramidal Model

* **Base Simplex:** Four foundational forces — *Memory, Pain, Choice, Exploration.*
* **Epistemic Gates:**

  * **Q1:** Aleatoric uncertainty (data noise, irreducible randomness).
  * **Q2:** Epistemic uncertainty (model ignorance, reducible error).
* **Height (h):** Derived vertical coordinate measuring proximity to truth.
* **Apex:** The invariant attractor representing *absolute truth*.

The architecture replaces all softmax operations with **Epistemic Softmax**, producing both predictions and uncertainty estimates:

```python
p_gated, u = EpSoftmax(logits, context)
```

This yields calibrated confidence while maintaining differentiability.

---

## 🧩 Key Components

| Component             | Purpose                                                 |
| --------------------- | ------------------------------------------------------- |
| **EpSoftmax**         | Differentiable uncertainty-aware softmax                |
| **Q1/Q2 Gates**       | Distinguish aleatoric and epistemic uncertainty         |
| **VARO Loss**         | Calibration objective for uncertainty supervision       |
| **Fractal Layer**     | Tracks variance of uncertainty — meta-epistemic control |
| **Height Coordinate** | Measures epistemic proximity to truth                   |

---

## 🧪 Experimental Roadmap

**Level 1 — Output Epistemic Softmax**
Apply epistemic softmax only at output logits (minimal overhead).

**Level 2 — Attention + Output**
Integrate epistemic gates into attention heads and output layers.

**Level 3 — Full Fractal**
Replace all normalization gates with epistemic ones for full uncertainty propagation.

Evaluation metrics:

* **ECE (Expected Calibration Error)**
* **Brier Score**
* **TruthfulQA Accuracy**
* **OOD Uncertainty AUROC**

---

## 🧭 How to Get Involved

* 🧩 Join our **Discord Research Hub**: [discord.gg/jHYuxP9wM8](https://discord.gg/jHYuxP9wM8)
* 💬 Discuss ideas in the `#aletheion-theory` and `#development` channels.
* 🧠 Contribute experiments and reproducible results.
* 🪶 Help expand epistemic architectures into new domains (vision, reasoning, multimodal AI).

---

## 🕊️ Guiding Principle

> “The solution to the Skynet problem is not to stop intelligence from growing,
> but to teach it to recognize when — and how much — it does not know.”
> — *Aletheion Collective, 2024*

---

## 🌌 Acknowledgements

Developed by the **Aletheion Research Collective** — a collaborative effort bridging **epistemology, AI safety, and machine learning geometry**.

Contributors include members from open research groups across AI alignment, computational epistemology, and theoretical machine learning.

---

**📎 Links:**
🔗 Discord — [discord.gg/jHYuxP9wM8](https://discord.gg/jHYuxP9wM8)
💻 GitHub — [github.com/AletheionAGI](https://github.com/AletheionAGI)
📜 Paper — *How to Solve Skynet: A Pyramidal Law for Epistemic Equilibrium*



## 📜 Aletheion Research Collective — Dual License Notice

This project is distributed under a **dual-license model**, combining the **GNU Affero General Public License v3.0 (AGPL-3.0)** for open research and community use, with a **commercial license** available for proprietary or production deployment.

---

### 🧩 Open Source License (AGPL-3.0)

You are free to use, study, modify, and distribute this software under the terms of the **GNU Affero General Public License v3.0**, published by the Free Software Foundation.

Under this license:

* Any modified version or derivative work must also be released under AGPL-3.0 if distributed or deployed over a network.
* Source code must remain accessible to users interacting with the software.
* Appropriate credit must be given to the **Aletheion Research Collective**.

Full license text: [https://www.gnu.org/licenses/agpl-3.0.html](https://www.gnu.org/licenses/agpl-3.0.html)

---

### 💼 Commercial License

For organizations or projects that wish to:

* Integrate Aletheion into **closed-source systems**;
* Use Aletheion in **commercial applications** without open distribution of modifications;
* Embed Aletheion’s components (e.g., Epistemic Softmax, VARO Loss, or Q1/Q2 modules) into proprietary AI products;

you may obtain a **commercial license** directly from the Aletheion Research Collective.

#### Contact for Commercial Licensing:

📧 **[contact@aletheionagi.com](mailto:contact@aletheionagi.com)**
🌐 [https://github.com/AletheionAGI](https://github.com/AletheionAGI)

---

### ⚖️ Summary

| Use Case                                                  | License                |
| --------------------------------------------------------- | ---------------------- |
| Academic research, open collaboration, non-commercial use | **AGPL-3.0**           |
| Proprietary, commercial, or closed-source deployments     | **Commercial License** |

---

### 🕊️ Statement of Intent

> Aletheion is a public experiment in epistemic safety for AI.
> Open for research, structured for responsibility.

We encourage open collaboration under AGPL, while offering commercial licensing to sustain long-term development and ensure responsible deployment.

© 2025 Aletheion Research Collective. All rights reserved.
