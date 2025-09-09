# Autoencoders for Data Governance

This repository accompanies a paper exploring the intersection of machine learning and data governance, with a particular focus on the use of autoencoders. This work investigates how autoencoders can be leveraged to create latent vector representations of tabular data, which in turn can be used to more effectively monitor and explore distribution drift, a key challenge when deploying and maintaining models.

## Project Overview

Data governance is increasingly important as organisations increasingly rely on large, dynamic datasets. One challenge is detecting and understanding distribution drift, as changes in the underlying distribution can impact downstream analytics, compliance, and machine learning model performance.

In this project, we demonstrate how autoencoders, a type of unsupervised neural network, can be trained on tabular data to produce compact, informative latent vectors., which can be used to:
1. Visualise and quantify distribution drift over time
2. Comparing datasets for similarity
3. Supporting data quality and governance workflows with machine learning insights

## Getting Started
1. Clone the Repository
2. Install Dependencies. We recommend using a virtual environment. To install all required packages, run:
``` sh
$ pip install -e .
```

## Download Pretrained Models and Vector Representations
To save time, you can download the pretrained autoencoder model and the generated vector representations:
Download the pretrained model
Download the vector representations 
Place these files in the appropriate directories

## Read the Full Paper
For a detailed explanation of our methodology, results, and the broader implications for data governance, please read the full paper:
Read the full paper here <!-- Replace # with your actual link -->


