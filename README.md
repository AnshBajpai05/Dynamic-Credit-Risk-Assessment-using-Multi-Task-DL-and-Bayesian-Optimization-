# Dynamic-Credit-Risk-Assessment-using-Multi-Task-DL-and-Bayesian-Optimization-


Dynamic Credit Risk Assessment using Multi-Task Deep Learning & Bayesian Optimization

This project implements a multi-task deep learning model for credit risk assessment, inspired by the paper “Dynamic Credit Risk Assessment Based on Multi-Task Deep Learning and Bayesian Optimization.”

The model learns from dynamic credit behavior, uses a shared neural backbone, and optimizes hyperparameters with Bayesian Optimization.

🚀 Features

Shared Multi-Task Neural Network

Two Output Heads

Task A: Credit Default Classification

Task B: Credit Score Regression (optional)

Combined Loss Function

𝐿
=
𝛼
𝐿
𝐴
+
𝛽
𝐿
𝐵
L=αL
A
	​

+βL
B
	​


Dynamic Time-Based Modeling using GRU + sliding windows

Bayesian Hyperparameter Optimization (Optuna)

Deep Learning Pipeline: preprocessing, training, evaluation, saving model

📁 Project Structure
data/                        # Input dataset
src/                         # Code (model, training, optimization)
results/                     # Saved models and plots
notebooks/                   # Jupyter notebooks
README.md

🧠 Method Overview

Preprocessing:

Numeric scaling, categorical encoding

Dynamic sequence building per customer

Model Architecture:

Embeddings + GRU shared backbone

Classification + Regression heads

Optimization:

Optuna tunes LR, hidden size, dropout, batch size, etc.

Training:

Multi-task loss

Evaluation on AUC, Accuracy, F1

🔧 Setup
pip install -r requirements.txt

▶️ Run the Pipeline
1. Hyperparameter Optimization
python src/optimize.py

2. Train Final Model
python src/train.py

3. Evaluate
python src/evaluate.py

📊 Outputs

Best model: results/best_model.pt

Training curves

Validation metrics (Accuracy, Precision, Recall, F1, AUC)
