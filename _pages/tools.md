---
layout: archive
title: "Interactive Tools"
permalink: /tools/
author_profile: true
---

## Research Demonstrations

These interactive tools demonstrate concepts from my research in conformal prediction, uncertainty quantification, and statistical machine learning.

---

## Kumaraswamy Mixture Model: Conformal Prediction Explorer

An interactive visualization demonstrating conformal prediction with Kumaraswamy mixture models on $[0,1]$. This tool shows how label-conditional conformal calibration partitions the feature space and induces region-specific posteriors.

**Key Concepts Illustrated:**
- Analytical tractability of Kumaraswamy distributions (closed-form CDF)
- Conformal cutpoint computation: $L = (1-(1-\alpha_1)^{1/b_1})^{1/a_1}$, $U = (1-\alpha_0^{1/b_0})^{1/a_0}$
- Region-specific marginals and posterior distributions
- Information-theoretic metrics (binary entropy) for prediction sets
- The distinction between coverage guarantees (validity) and prediction quality (optimality)

**Interactive Controls:**
- Shape parameters ($a_0, b_0, a_1, b_1$) for class-conditional distributions
- Prior probability $c = P(Y=0)$
- Miscoverage levels $\alpha_0, \alpha_1$
- Five preset configurations demonstrating different scenarios

### [Launch Tool](https://claude.ai/public/artifacts/b241e325-3237-4dd1-ac6a-328b87e97a6c)

**Related Publication:**  
Zwart, P.H. (2025). "Probabilistic Conformal Coverage Guarantees in Small-Data Settings." arXiv:2509.15349

---

## Technical Details

All calculations use closed-form expressions—no numerical integration required. The Kumaraswamy distribution's analytical CDF enables exact computation of:
- Region masses: $m([a,b]) = c[F_0(b)-F_0(a)] + (1-c)[F_1(b)-F_1(a)]$
- In-region rates: $\bar{p}([a,b]) = (1-c)[F_1(b)-F_1(a)] / m([a,b])$
- Binary entropy: $H(p) = -p \log_2(p) - (1-p) \log_2(1-p)$

Three regions are determined by $r_- = \min(L,U)$ and $r_+ = \max(L,U)$:
- If $L < U$: Regions $R_0 = [0, r_-)$, $R_M = [r_-, r_+)$ (hedge), $R_1 = [r_+, 1]$
- If $L > U$: Regions $R_0 = [0, r_-)$, $R_M = [r_-, r_+)$ (abstain), $R_1 = [r_+, 1]$

---

## Upcoming Tools

Additional interactive demonstrations are in development:

**Quantile Regression for Autonomous Experimentation**  
Visualizing adaptive data acquisition strategies using conformalized quantile regression

**Small Sample Beta Correction (SSBC) Demo**  
Interactive exploration of PAC coverage guarantees in small-sample settings

**Representation Learning Visualizations**  
Tools for exploring emergent representations in conformal quantile regression

---

## Source Code

The source code for these tools is available on [GitHub](https://github.com/phzwart) and can be adapted for your own research or educational purposes.

---

*These tools complement my research on conformal prediction and uncertainty quantification. For theoretical background, see my [Publications](/publications/) page.*
