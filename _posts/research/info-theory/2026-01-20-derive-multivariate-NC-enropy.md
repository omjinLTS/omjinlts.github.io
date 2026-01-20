---
title: "Derivation of Entropy for Multivariate Complex Gaussian Distribution"
categories:
  - Research
  - InformationTheory
tags:
  - Research
  - InformationTheory
  - ShannonCapacity
  - Entropy
last_modified_at: 2026-01-20 13:09:18
toc: true
toc_sticky: true
use_math: true
---

## Introduction

In the [previous post](/research/informationtheory/derive-NC-entropy/), we saw that the entropy of a scalar complex Gaussian variable is $\log_2(\pi e \sigma^2)$. When we move to MIMO systems, we deal with a signal vector $\mathbf{x} \in \mathbb{C}^{P \times 1}$. 

The resulting entropy formula involves a **determinant**: $H(\mathbf{x}) = \log_2 \det(\pi e \mathbf{R}_{xx})$. But why? In this post, we will derive this result from the Multivariate Complex Gaussian PDF.

---

## 1. The Multivariate Complex Gaussian PDF

For a zero-mean complex Gaussian random vector $\mathbf{x} \in \mathbb{C}^{P \times 1}$ with an autocorrelation matrix $\mathbf{R}_{xx} = \mathbb{E}[\mathbf{xx}^H]$, the Probability Density Function (PDF) is defined as:

> For convinience, let $\mu = 0$

$$f(\mathbf{x}) = \frac{1}{\pi^P \det(\mathbf{R}_{xx})} \exp\left( -\mathbf{x}^H \mathbf{R}_{xx}^{-1} \mathbf{x} \right)$$



Here, the determinant $\det(\mathbf{R}_{xx})$ acts as the normalization constant that accounts for the "spread" of the distribution across all $P$ dimensions.

---

## 2. Derivation of Differential Entropy

Differential entropy for a continuous random vector is defined as $H(\mathbf{x}) = -\mathbb{E}[\log_2 f(\mathbf{x})]$.

### Step 1: Log-Likelihood Expansion
Taking the $\log_2$ of the PDF:

$$
\begin{aligned}
\log_2 f(\mathbf{x}) &= \log_2 \left( \frac{1}{\pi^P \det(\mathbf{R}_{xx})} \right) + \log_2 \left( e^{-\mathbf{x}^H \mathbf{R}_{xx}^{-1} \mathbf{x}} \right) \\
&= -\log_2(\pi^P) - \log_2 \det(\mathbf{R}_{xx}) - (\mathbf{x}^H \mathbf{R}_{xx}^{-1} \mathbf{x}) \log_2 e
\end{aligned}
$$

### Step 2: Applying Expectation
The entropy is the negative expectation of the above:

$$
\begin{aligned}
H(\mathbf{x}) &= -\mathbb{E} \left[ -\log_2(\pi^P) - \log_2 \det(\mathbf{R}_{xx}) - (\mathbf{x}^H \mathbf{R}_{xx}^{-1} \mathbf{x}) \log_2 e \right] \\
&= \log_2(\pi^P) + \log_2 \det(\mathbf{R}_{xx}) + \log_2 e \cdot \mathbb{E} \left[ \mathbf{x}^H \mathbf{R}_{xx}^{-1} \mathbf{x} \right]
\end{aligned}
$$

### Step 3: The Trace Trick
To solve the expectation $\mathbb{E} [ \mathbf{x}^H \mathbf{R}_{xx}^{-1} \mathbf{x} ]$, we use the property that a scalar is equal to its trace, and $\text{Tr}(\mathbf{AB}) = \text{Tr}(\mathbf{BA})$:

$$
\begin{aligned}
\mathbb{E} [ \mathbf{x}^H \mathbf{R}_{xx}^{-1} \mathbf{x} ] &= \mathbb{E} [ \text{Tr}(\mathbf{x}^H \mathbf{R}_{xx}^{-1} \mathbf{x}) ] \\
&= \mathbb{E} [ \text{Tr}(\mathbf{R}_{xx}^{-1} \mathbf{xx}^H) ] \\
&= \text{Tr}(\mathbf{R}_{xx}^{-1} \mathbb{E}[\mathbf{xx}^H]) \\
&= \text{Tr}(\mathbf{R}_{xx}^{-1} \mathbf{R}_{xx}) \\
&= \text{Tr}(\mathbf{I}_P) = P
\end{aligned}
$$

### Step 4: Final Result
Substituting $P$ back into the entropy equation:

$$
\begin{aligned}
H(\mathbf{x}) &= \log_2(\pi^P) + \log_2 \det(\mathbf{R}_{xx}) + P \log_2 e \\
&= \log_2(\pi^P) + \log_2 \det(\mathbf{R}_{xx}) + \log_2 (e^P) \\
&= \log_2 \det(\pi e \mathbf{R}_{xx})
\end{aligned}
$$

Thus, the differential entropy of a $P$-dimensional complex Gaussian vector is **$\log_2 \det(\pi e \mathbf{R}_{xx})$**.

---

## 3. Why the Determinant?

The appearance of the determinant is mathematically inevitable, but it also carries deep physical meaning:

1.  **Geometric Intuition:** In one dimension, uncertainty is "length" ($\sigma^2$). In multiple dimensions, uncertainty is the **volume** of the ellipsoid formed by the correlation of the antennas. The determinant measures this volume.
2.  **Independence:** If the antennas are independent (i.e., $\mathbf{R}_{xx}$ is diagonal), the determinant is simply the product of the powers: $\prod_{p=1}^P \sigma_p^2$. The $\log \det$ then becomes the **sum of individual entropies**, which perfectly aligns with the concept of parallel spatial channels.
3.  **The Origin of MIMO Capacity:** Since capacity is derived from the difference between the entropy of the received signal and the noise ($H(\mathbf{y}) - H(\mathbf{n})$), the "Log-Det" form of the capacity formula is a direct inheritance from this multivariate entropy.

---

## Conclusion

By understanding that entropy is proportional to the log-determinant of the autocorrelation matrix, we can see why maximizing MIMO capacity is essentially an exercise in **maximizing the "volume" of our signal space** under a total power (Trace) constraint.