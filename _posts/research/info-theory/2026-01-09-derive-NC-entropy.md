---
title: "Derivation of Differential Entropy for Complex Gaussian Distribution"
categories:
  - Research
  - InformationTheory
tags:
  - Research
  - InformationTheory
  - ShannonCapacity
  - Entropy
last_modified_at: 2026-01-19 19:31:09
toc: true
toc_sticky: true
use_math: true
---

## Derivation of Complex Gaussian Entropy

Why is the entropy of a complex Gaussian signal $\log_2(\pi e \sigma^2)$?

Let's derive it step-by-step using the **Expectation** property, rather than solving the integral directly.

**1. Probability Density Function (PDF)**
For a circular symmetric complex Gaussian random variable $x \sim \mathcal{CN}(0, \sigma^2)$, the PDF is given by:

$$f(x) = \frac{1}{\pi \sigma^2} e^{-\frac{|x|^2}{\sigma^2}}$$

**2. Log-Likelihood**
First, take the logarithm ($\log_2$) of the PDF. This separates the exponential term.

$$
\begin{aligned}
\log_2 f(x) &= \log_2 \left( \frac{1}{\pi \sigma^2} \right) + \log_2 \left( e^{-\frac{|x|^2}{\sigma^2}} \right) \\
&= -\log_2(\pi \sigma^2) - \frac{|x|^2}{\sigma^2} \log_2 e
\end{aligned}
$$

**3. Applying Expectation (Definition of Entropy)**
Entropy is the negative expected value of the log-likelihood: $H(x) = -\mathbb{E}[\log_2 f(x)]$.

$$
\begin{aligned}
H(x) &= -\mathbb{E} \left[ -\log_2(\pi \sigma^2) - \frac{|x|^2}{\sigma^2} \log_2 e \right] \\
&= \underbrace{\log_2(\pi \sigma^2)}_{\text{Constant}} + \frac{\log_2 e}{\sigma^2} \underbrace{\mathbb{E}[|x|^2]}_{\text{Variance } \sigma^2}
\end{aligned}
$$

**4. Final Result**
By definition, the variance $\mathbb{E}[|x|^2]$ is $\sigma^2$. The terms cancel out beautifully.

$$
\begin{aligned}
H(x) &= \log_2(\pi \sigma^2) + \frac{\log_2 e}{\sigma^2} \cdot \sigma^2 \\
&= \log_2(\pi \sigma^2) + \log_2 e \\
&= \log_2(\pi \sigma^2 e)
\end{aligned}
$$

Thus, the entropy of a complex Gaussian variable is **$\log_2(\pi e \sigma^2)$**.