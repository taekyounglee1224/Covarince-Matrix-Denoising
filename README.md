## Covarince-Matrix-Denoising

### 1. Introduction

Covariance matrix estimation is a cornerstone of financial modeling, underpinning critical tasks such as portfolio optimization, risk management, and asset allocation. In practice, sample covariance matrices (𝚺") are often noisy due to the limited number of observations, particularly when market dynamics evolve rapidly or datasets span diverse asset classes. This noise undermines the reliability of covariance matrices, leading to suboptimal decisions in financial applications.
   
### 2. Data
![image](https://github.com/user-attachments/assets/bfa39eb9-6b4a-4dff-9faf-8cc990055e52)

### 3. Methodology

This paper introduces a diffusion-based framework for denoising covariance matrices, addressing the challenges posed by noisy sample covariance matrices 𝚺", particularly in high-dimensional financial datasets. The framework systematically reduces noise while preserving critical statistical properties such as variances and positive definiteness, ensuring applicability to downstream tasks like portfolio optimization.

The evolution of the covariance matrix 𝚺" is modeled through a stochastic differential equation (SDE): d𝚺 =−𝜆(𝚺 −𝜇)𝑑𝑡+𝛽d𝑊,
