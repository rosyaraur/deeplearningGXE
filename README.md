# Genomic Selection Pipeline: Bayesian Benchmarks & Neural Network Consensus

A robust, high-efficiency genomic selection workflow designed to identify the top 10% elite wheat breeding lines across diverse agricultural environments. This repository frames genomic selection as a binary operational decision, combining the rigor of traditional Bayesian quantitative genetic models with an optimized deep learning classifier.

## Overview

Predicting continuous yield phenotypes in small populations often leads to severe overfitting when utilizing deep learning architectures. This pipeline bypasses that limitation by deploying Neural Networks as binary classifiers aimed at replicating a high-accuracy Bayesian consensus target. This approach achieves comparable selection accuracy to intensive Markov Chain Monte Carlo (MCMC) algorithms at a fraction of the computational cost.

## Key Features

* **Custom MCMC Gibbs Samplers:** Efficient implementations for BayesA, BayesB, and BayesC to generate baseline Genomic Estimated Breeding Values (GEBVs).
* **Consensus Indexing:** A unified breeding value target formed by averaging the Bayesian predictions to define the top 10% elite threshold across multiple environments.
* **Dimensionality Reduction:** Principal Component Analysis (PCA) compression of high-dimensional molecular marker matrices.
* **Deep Learning Classifier:** A Multi-Layer Perceptron (MLP) trained on the reduced genomic feature space to replicate the computationally intensive Bayesian consensus logic.

## Repository Structure

* `genomic_selection_pipeline.ipynb`: The core executable Jupyter Notebook containing the full computational workflow, from MCMC sampling to neural network training and validation.
* `genomic_selection_report.md`: A complementary methodological document detailing the experimental design, computational steps, classification performance, and recall metrics.
* `yieldata.csv`: Standardized grain yield evaluations for 599 lines across four target environments (E1-E4). *(Data requirement)*
* `markerMatrix.csv`: High-dimensional matrix consisting of 1,279 binary molecular markers. *(Data requirement)*

## Requirements

To run the pipeline locally, you will need a standard data science environment (Python 3.8+) and the following core dependencies:

* `pandas`
* `numpy`
* `scikit-learn`
* `matplotlib`
* `seaborn`

## Getting Started

1. Clone this repository to your local machine.
2. Ensure your phenotypic (`yieldata.csv`) and genotypic (`markerMatrix.csv`) datasets are located in the project's root directory alongside the scripts.
3. Launch your preferred environment (Jupyter Notebook, JupyterLab, or VS Code).
4. Open `genomic_selection_pipeline.ipynb` and execute the cells sequentially to reproduce the MCMC sampling, consensus generation, and neural network evaluation.

## Results Summary

The optimized PCA-MLP classifier successfully replicates the Bayesian consensus choices with **88.3% to 98.3% accuracy** across environments. When evaluated against empirical field data, the pipeline reliably isolates **51.7% to 61.7%** of the true highest-yielding lines, establishing a highly stable tool for automated germplasm advancement.
