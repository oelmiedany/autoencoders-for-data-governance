# Autoencoders for Data Governance

This repository accompanies the white paper *From Governance to Insight: Using Autoencoders to Monitor Data Distribution Drift*. It explores the application of autoencoders in modern data governance strategies, particularly their use in surfacing distribution shifts in high-dimensional tabular data.

The full paper can be found [here](#https://1drv.ms/b/c/61e43c887e06eaac/EX7GH0tV7idPjUWw6Q73ZYYBGUpTSZfsHleCBBWa5v2wEg?e=iA5TtQ)

## Project Overview

Data governance plays a pivotal role in ensuring analytical and operational integrity in data-driven organisations. A central challenge in this domain is identifying and responding to distribution drift, which occurs when the statistical properties of input data evolve over time. Such drift can silently degrade model performance or compromise downstream decision-making.

This project demonstrates how autoencoders, a class of unsupervised neural networks, can be used to:

- Encode complex tabular datasets into latent vector representations
- Track and quantify drift in latent space across time periods
- Visualise structural changes using tools like Wasserstein distance and PCA
- Augment data quality monitoring pipelines with noise-resistant diagnostic metrics

By embedding machine learning into upstream data workflows, the aim is to shift from reactive governance to proactive insight.

### Why Autoencoders?

Autoencoders provide:

- A noise-resistant summary of data via compact latent encodings
- The ability to track complex inter-feature relationships
- A model-agnostic tool for monitoring upstream data shifts

Unlike tools that rely solely on raw distributions or feature-wise drift, this approach accounts for holistic data structure, making it more robust to real-world complexity.

### Methodology

Using the [Lending Club dataset](https://www.kaggle.com/datasets/wordsforthewise/lending-club), a symmetrical deterministic autoencoder was developed:

- **Input Features**: 110 features (categorical, ordinal, and numerical)
- **Latent Space**: 16-dimensional representation
- **Custom Loss Function**: Combines RMSE for numerical/ordinal values and binary cross-entropy for categorical features, with loss weights and missing value masking
- **Training Regime**:
  - Training set: Jan 2012 – May 2017
  - Validation set: May 2017 – Dec 2017
  - Test set: 2018 (by quarter)

Cross-validation and per-quarter evaluation assessed reconstruction quality.

### Results

- **Reconstruction Performance**  
  - RMSE (numerical): 0.43–0.47 across quarters  
  - F1 Score (binary): consistently ~0.98  
  These metrics show the model captures stable patterns in the data.

- **Latent Space Drift**  
  - Using Wasserstein distance** between mean latent vectors, a gradual but significant shift was detected across quarters  
  - PCA visualisation confirmed directional drift in data structure from Q1 to Q4

This indicates that while the surface-level metrics (e.g., reconstruction loss) may appear stable, deeper structural drift can still occur. This is a critical insight for data governance.

## Setup and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/your_org/autoencoders-for-data-governance.git
cd autoencoders-for-data-governance
```

### 2. Install Dependencies

A virtual environment is recommended to manage your dependencies. Once the environment is activated, install the required packages using:

```bash
pip install -e .
```

### 3. Download Pretrained Assets

To skip training and quickly start exploring latent vector analysis, you can use the provided pretrained assets:

- **Pretrained autoencoder model**: [Download here](#https://1drv.ms/u/c/61e43c887e06eaac/EQkBSGRIU31Hh-UEFmzUVZwBEnb9n7KlvbMFwpMJXoGBow?e=w1cAVo)
  - Ensure the trained model follows the naming convention "vae_best-input_size:{input_size}.pt"
- **The fitted data handler**: [Download here](#https://1drv.ms/u/c/61e43c887e06eaac/EdBygTG4xz5NthcJXI-r7mIB9XQtPvFZ18jeywuOVlb8bg?e=8bd0hP)
- **Latent vector representations**: [Download here](#https://1drv.ms/x/c/61e43c887e06eaac/EQONE8w85dFKqch1WZN9NMYBdmAKSgQ6PWzrb4rMXVoA8w?e=z8xlbt)

### Directory Placement

After downloading, place the files in the appropriate locations:

- Place the pretrained autoencoder model and the fitted data handler in a directory labeled trained_models located in the root of the repository
- Vector representations csv should be also placed in the root of the repository

