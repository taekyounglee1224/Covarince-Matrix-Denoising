## Covarince-Matrix-Denoising

### 1. Introduction

Covariance matrix estimation is a cornerstone of financial modeling, underpinning critical tasks such as portfolio optimization, risk management, and asset allocation. In practice, sample covariance matrices (𝚺") are often noisy due to the limited number of observations, particularly when market dynamics evolve rapidly or datasets span diverse asset classes. This noise undermines the reliability of covariance matrices, leading to suboptimal decisions in financial applications.
   
### 2. Data
![image](https://github.com/user-attachments/assets/bfa39eb9-6b4a-4dff-9faf-8cc990055e52)

### 3. Methodology

This paper introduces a diffusion-based framework for denoising covariance matrices, addressing the challenges posed by noisy sample covariance matrices 𝚺", particularly in high-dimensional financial datasets. The framework systematically reduces noise while preserving critical statistical properties such as variances and positive definiteness, ensuring applicability to downstream tasks like portfolio optimization.

The evolution of the covariance matrix 𝚺" is modeled through a stochastic differential equation 
(SDE): d𝚺 =−𝜆(𝚺 −𝜇)𝑑𝑡+𝛽d𝑊

The mean target 𝜇" balances the original noisy estimate 𝚺" and a regularized identity matrix II through a shrinkage parameter 𝛼:

𝜇" = (1−𝛼)𝚺+𝛼𝐈.

The diffusion schedule is set as a hyperparameter,
![image](https://github.com/user-attachments/assets/a4f5f9b4-d038-43e7-8acb-dafaa4d1555b)


### 4. Experimental Design

The experimental framework utilizes 20 years of financial data from 2005 to 2024, employing a monthly rebalancing strategy to evaluate the performance of the proposed diffusion-based denoising framework. For each month, historical data up to the last day of the current month is used to compute the sample covariance matrix 5𝚺"6, ensuring that only available information is utilized, maintaining a realistic, out-of-sample evaluation. 

Specifically, for each evaluation period, the sample covariance matrix is computed using the in-sample period, which consists of 𝑁in months of historical data. This sample covariance matrix undergoes denoising via the diffusion-based framework, producing a refined matrix (𝚺∗) that mitigates noise while preserving statistical properties like variances and positive definiteness. The denoised covariance matrix is subsequently used to construct an optimized portfolio for the following out-of-sample period, spanning 𝑁out months. The in/out sample combinations are stated in the table below.

![image](https://github.com/user-attachments/assets/cfae8e45-614d-4744-b56d-6dde3d8b473b)

### 5. Tools

- Python 3.11.7
- VS Code
- scikit-learn 2.3.1
  



