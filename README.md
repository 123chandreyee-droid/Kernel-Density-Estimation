# Kernel Density Estimation with Cross-Validated Bandwidth Selection

## Overview

This project implements **Kernel Density Estimation (KDE)** from scratch to estimate the probability density function of an unknown data distribution.

A Gaussian kernel is used for density estimation, while **leave-one-out cross-validation** is employed to select the optimal bandwidth by maximizing the **log joint likelihood**.

The estimated density is compared with the known true probability density using graphical and quantitative analysis.

---

## Objectives

- Implement Gaussian Kernel Density Estimation from first principles
- Study the effect of bandwidth on density estimation
- Develop a leave-one-out cross-validation framework
- Select the optimal bandwidth using log joint likelihood
- Compare the estimated PDF with the true PDF
- Quantify estimation accuracy using MSE and MAE

---

## Methodology

The overall workflow followed in the project is:

1. Generate a synthetic dataset from a known Gaussian mixture distribution
2. Calculate the corresponding true probability density function
3. Implement Gaussian KDE from scratch
4. Evaluate KDE for different bandwidth values
5. Perform leave-one-out cross-validation
6. Calculate log joint likelihood for each candidate bandwidth
7. Select the bandwidth maximizing the likelihood
8. Generate the final KDE using the optimized bandwidth
9. Compare the estimated and true PDFs
10. Evaluate the estimation error using MSE and MAE

---

## Mathematical Formulation

The Kernel Density Estimator is given by:

$$
\hat{f}_h(x)
=
\frac{1}{nh}
\sum_{i=1}^{n}
K\left(\frac{x-x_i}{h}\right)
$$

where $h$ is the bandwidth and $K$ is the kernel function.

A Gaussian kernel was used:

$$
K(u)
=
\frac{1}{\sqrt{2\pi}}
e^{-u^2/2}
$$

The bandwidth was selected by maximizing the leave-one-out log likelihood:

$$
L(h)
=
\sum_{i=1}^{n}
\log\left[\hat{f}_{-i,h}(x_i)\right]
$$

---

## Results

The optimized KDE produced the following results:

| Metric | Value |
|---|---:|
| Optimal Bandwidth | **0.3127** |
| Maximum LOO Log Likelihood | **-963.5156** |
| Mean Squared Error | **0.000212** |
| Mean Absolute Error | **0.010450** |

The optimized bandwidth provides a balance between excessive fluctuations caused by small bandwidths and oversmoothing caused by large bandwidths.

---

## Visual Analysis

The notebook includes:

- Generated data distribution
- True probability density function
- KDE for different bandwidth values
- Cross-validation log likelihood curve
- Final KDE vs. true PDF comparison

---

## Technologies Used

- **Python**
- **NumPy**
- **Matplotlib**
- **Jupyter Notebook**

---

## Project Structure

```text
Kernel-Density-Estimation/
│
├── Kernel_Density_Estimation.ipynb
├── README.md
└── requirements.txt
