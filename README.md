

# Monte Carlo Methods and Importance Sampling

This repository explores the implementation of **Monte Carlo methods** and **Importance Sampling**, focusing on their applications in estimating probabilities and integrals for complex or rare events.

## Table of Contents
- [Introduction](#introduction)
- [Monte Carlo Methods](#monte-carlo-methods)
- [Importance Sampling](#importance-sampling)
- [Examples](#examples)
- [References](#references)

---

## Introduction
Monte Carlo methods are a class of computational algorithms that rely on repeated random sampling to solve problems that might be deterministic in principle. These methods are widely used in physics, engineering, finance, and other fields for tasks like numerical integration, optimization, and simulating rare events.

**Importance Sampling** improves Monte Carlo estimates by reducing variance, especially for rare events, by sampling from a different distribution (the *importance density*) rather than the target distribution.

---

## Monte Carlo Methods
Monte Carlo methods rely on the following key ideas:
1. Randomly sample points from a known distribution.
2. Use these samples to estimate the desired quantities.
3. The accuracy improves with the number of samples (law of large numbers).

For example, to estimate the probability of a rare event \( P(X > 5) \), a naive Monte Carlo method may require a large number of samples to achieve accurate results.

---

## Importance Sampling
Importance Sampling addresses the inefficiency of standard Monte Carlo simulations for rare events. Instead of sampling directly from the original distribution, samples are drawn from an **importance density** \( \pi(x) \), chosen to cover the event of interest more effectively. 

The estimator for an integral \( I(f) \) using Importance Sampling is given by:

\[
I(f) \approx \frac{1}{N} \sum_{i=1}^{N} f(\tilde{x}^{(i)}) w(\tilde{x}^{(i)}),
\]

where the weight \( w(\tilde{x}) = \frac{p(\tilde{x})}{\pi(\tilde{x})} \) adjusts for the mismatch between the target distribution \( p(x) \) and the importance density \( \pi(x) \).

### Example
To estimate \( P(X > 5) \) for \( X \sim \mathcal{N}(0, 1) \), we can use an exponential importance density \( \pi(y) = e^{-(y-5)} \), which focuses sampling on the tail region \( [5, \infty) \).






## Examples
### Naive Monte Carlo Simulation
A simple Monte Carlo simulation to compute \( P(X > 5) \) for \( X \sim \mathcal{N}(0, 1) \) using random samples.

### Importance Sampling for Rare Events
An improved estimator for \( P(X > 5) \) using an exponential importance density:
\[
\pi(y) = e^{-(y-5)}.
\]

The results demonstrate significantly reduced variance compared to the naive approach.

---

## References
1. Robert, C. P., & Casella, G. (2004). *Monte Carlo Statistical Methods*. Springer.
2. Owen, A. B. (2013). *Monte Carlo Theory, Methods, and Examples*.
3. Bishop, C. M. (2006). *Pattern Recognition and Machine Learning*. Springer.

