# Autoencoders for Data Governance

This repository accompanies a paper exploring the intersection of machine learning and data governance, with a particular focus on the use of autoencoders. It investigates how autoencoders can be leveraged to create latent vector representations of tabular data, which in turn can be used to more effectively monitor and explore distribution drift, a key challenge when deploying and maintaining models.

## Project Overview
Data governance is increasingly important as organisations progressively rely on models and insights built on large, dynamic datasets for decision making. Yet this reliance on live data makes governance inseparable from the problem of distribution drift, as shifts in the underlying distribution alter the patterns on which analytics are built upon, amplifying risk when left unaddressed.

In this project, I demonstrate how autoencoders, a type of unsupervised neural network, can be trained on tabular data to produce compact, informative latent vectors, which can be used to:
1. Identify and visualise distribution drift over time.
2. Quantify the nature and direction of the shift.
3. Fascilitate an early warning system.

## Getting Started
1. Clone the Repository
2. Install dependencies by running
``` sh
$ pip install -e .
```
3.  Open and run the notebook: [`vae_data_governance_experiment.ipynb`](./experiments/vae_data_governance_experiment.ipynb) in the `experiments` directory.

## Read the Full Paper
For a detailed explanation of the methodology, results, and a broader discussion on the role of machine learning in data governance please read the [full paper] (https://1drv.ms/b/c/61e43c887e06eaac/EX7GH0tV7idPjUWw6Q73ZYYBbTg1ILnaXzSe81xOVy_2cA?e=U33R7Y)


