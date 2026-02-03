---
title: 'Kumaraswamy Distributions for Conformal Prediction'
date: 2025-02-03
permalink: /posts/2025/02/kumaraswamy-conformal/
tags:
  - conformal-prediction
  - uncertainty-quantification
  - machine-learning
---

Exploring the analytical advantages of Kumaraswamy mixture models for conformal prediction with closed-form region statistics.

## Introduction

When working with conformal prediction for binary classification, we often need to compute region masses and posteriors. The Kumaraswamy distribution offers a compelling alternative to Beta distributions because of its **closed-form CDF**, eliminating the need for incomplete beta functions.

## The Kumaraswamy Distribution

The Kumaraswamy distribution on $[0,1]$ has PDF and CDF:

$$
f(x; a, b) = abx^{a-1}(1-x^a)^{b-1}
$$

$$
F(x; a, b) = 1 - (1-x^a)^b
$$

The closed-form CDF is the key advantage! For Beta distributions, we'd need:

$$
F_{\text{Beta}}(x; \alpha, \beta) = I_x(\alpha, \beta) \quad \text{(incomplete beta function)}
$$

## Conformal Prediction Setup

Consider a binary classification problem where we use label-conditional conformal prediction. We have:

- Class-conditional distributions: $f(x|Y=0) \sim \text{Kumaraswamy}(a_0, b_0)$ and $f(x|Y=1) \sim \text{Kumaraswamy}(a_1, b_1)$
- Prior: $c = P(Y=0)$
- Miscoverage levels: $\alpha_0, \alpha_1$

The conformal cutpoints are computed using the quantiles:

$$
L = F_0^{-1}(\alpha_1) = \left(1-(1-\alpha_1)^{1/b_0}\right)^{1/a_0}
$$

$$
U = F_1^{-1}(1-\alpha_0) = \left(1-\alpha_0^{1/b_1}\right)^{1/a_1}
$$

## Region Statistics

We partition $[0,1]$ into three regions based on $r_- = \min(L,U)$ and $r_+ = \max(L,U)$:

- $R_0 = [0, r_-)$: Predict class 0
- $R_M = [r_-, r_+)$: Hedge set $\\{0,1\\}$ (if $L < U$) or abstain $\emptyset$ (if $L > U$)
- $R_1 = [r_+, 1]$: Predict class 1

The **region mass** (probability that $x$ falls in region $[a,b]$):

$$
m([a,b]) = c[F_0(b) - F_0(a)] + (1-c)[F_1(b) - F_1(a)]
$$

The **in-region rate** (posterior probability of class 1 given $x \in [a,b]$):

$$
\bar{p}([a,b]) = \frac{(1-c)[F_1(b) - F_1(a)]}{m([a,b])}
$$

All computed in **closed form** with simple algebra!

## Information Theory

We can measure the uncertainty of predictions using binary entropy:

$$
H(p) = -p \log_2(p) - (1-p) \log_2(1-p)
$$

This reveals an important insight: **validity ≠ optimality**

- Conformal sets with coverage guarantees can still have high entropy (uncertain predictions)
- Some regions may have low entropy despite being hedge sets

## Interactive Exploration

I've created an [interactive tool](/tools/) where you can explore these concepts by adjusting:

- Shape parameters $(a_0, b_0, a_1, b_1)$
- Prior probability $c$
- Miscoverage levels $(\alpha_0, \alpha_1)$

Try it out to see how different configurations affect the region partitioning and posterior distributions!

## Key Takeaways

1. **Analytical tractability**: Kumaraswamy distributions give closed-form calculations
2. **No numerical integration**: Everything computes exactly with elementary operations
3. **Interpretable regions**: Clear partitioning of feature space with meaningful posteriors
4. **Coverage vs. certainty**: Conformal guarantees ensure coverage but don't guarantee low-entropy predictions

## References

Zwart, P.H. (2025). "Probabilistic Conformal Coverage Guarantees in Small-Data Settings." arXiv:2509.15349

---

*This post accompanies my research on conformal prediction and uncertainty quantification. See the [interactive tool](/tools/) for hands-on exploration.*---
title: 'Kumaraswamy Distributions for Conformal Prediction'
date: 2025-02-03
permalink: /posts/2025/02/kumaraswamy-conformal/
tags:
  - conformal-prediction
  - uncertainty-quantification
  - machine-learning
---

Exploring the analytical advantages of Kumaraswamy mixture models for conformal prediction with closed-form region statistics.

## Introduction

When working with conformal prediction for binary classification, we often need to compute region masses and posteriors. The Kumaraswamy distribution offers a compelling alternative to Beta distributions because of its **closed-form CDF**, eliminating the need for incomplete beta functions.

## The Kumaraswamy Distribution

The Kumaraswamy distribution on $[0,1]$ has PDF and CDF:

$$
f(x; a, b) = abx^{a-1}(1-x^a)^{b-1}
$$

$$
F(x; a, b) = 1 - (1-x^a)^b
$$

The closed-form CDF is the key advantage! For Beta distributions, we'd need:

$$
F_{\text{Beta}}(x; \alpha, \beta) = I_x(\alpha, \beta) \quad \text{(incomplete beta function)}
$$

## Conformal Prediction Setup

Consider a binary classification problem where we use label-conditional conformal prediction. We have:

- Class-conditional distributions: $f(x|Y=0) \sim \text{Kumaraswamy}(a_0, b_0)$ and $f(x|Y=1) \sim \text{Kumaraswamy}(a_1, b_1)$
- Prior: $c = P(Y=0)$
- Miscoverage levels: $\alpha_0, \alpha_1$

The conformal cutpoints are computed using the quantiles:

$$
L = F_0^{-1}(\alpha_1) = \left(1-(1-\alpha_1)^{1/b_0}\right)^{1/a_0}
$$

$$
U = F_1^{-1}(1-\alpha_0) = \left(1-\alpha_0^{1/b_1}\right)^{1/a_1}
$$

## Region Statistics

We partition $[0,1]$ into three regions based on $r_- = \min(L,U)$ and $r_+ = \max(L,U)$:

- $R_0 = [0, r_-)$: Predict class 0
- $R_M = [r_-, r_+)$: Hedge set $\\{0,1\\}$ (if $L < U$) or abstain $\emptyset$ (if $L > U$)
- $R_1 = [r_+, 1]$: Predict class 1

The **region mass** (probability that $x$ falls in region $[a,b]$):

$$
m([a,b]) = c[F_0(b) - F_0(a)] + (1-c)[F_1(b) - F_1(a)]
$$

The **in-region rate** (posterior probability of class 1 given $x \in [a,b]$):

$$
\bar{p}([a,b]) = \frac{(1-c)[F_1(b) - F_1(a)]}{m([a,b])}
$$

All computed in **closed form** with simple algebra!

## Information Theory

We can measure the uncertainty of predictions using binary entropy:

$$
H(p) = -p \log_2(p) - (1-p) \log_2(1-p)
$$

This reveals an important insight: **validity ≠ optimality**

- Conformal sets with coverage guarantees can still have high entropy (uncertain predictions)
- Some regions may have low entropy despite being hedge sets

## Interactive Exploration

I've created an [interactive tool](/tools/) where you can explore these concepts by adjusting:

- Shape parameters $(a_0, b_0, a_1, b_1)$
- Prior probability $c$
- Miscoverage levels $(\alpha_0, \alpha_1)$

Try it out to see how different configurations affect the region partitioning and posterior distributions!

## Key Takeaways

1. **Analytical tractability**: Kumaraswamy distributions give closed-form calculations
2. **No numerical integration**: Everything computes exactly with elementary operations
3. **Interpretable regions**: Clear partitioning of feature space with meaningful posteriors
4. **Coverage vs. certainty**: Conformal guarantees ensure coverage but don't guarantee low-entropy predictions

## References

Zwart, P.H. (2025). "Probabilistic Conformal Coverage Guarantees in Small-Data Settings." arXiv:2509.15349

---

*This post accompanies my research on conformal prediction and uncertainty quantification. See the [interactive tool](/tools/) for hands-on exploration.*
