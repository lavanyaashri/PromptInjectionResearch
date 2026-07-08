# Prompt Injection Detection using Machine Learning and Transformers

> Comparative evaluation of classical machine learning and transformer-based models for detecting prompt injection attacks in Large Language Models (LLMs).

---

## Overview

Prompt injection is one of the most significant security vulnerabilities affecting Large Language Models (LLMs), allowing malicious users to manipulate model behavior through carefully crafted prompts.

This project investigates the effectiveness of both traditional machine learning and transformer-based approaches for automated prompt injection detection. Multiple NLP models were implemented, benchmarked, and analyzed using standard evaluation metrics and attack severity analysis.

---

## Objectives

- Detect prompt injection attacks as a binary text classification task
- Compare classical machine learning and transformer-based models
- Evaluate the impact of text preprocessing
- Investigate ensemble learning through Gradient Boosting
- Fine-tune DistilBERT for contextual prompt injection detection
- Analyze model robustness across varying attack severity levels

---

## Dataset

**Dataset:** SPML Chatbot Prompt Injection Dataset

Source:
https://huggingface.co/datasets/reshabhs/SPML_Chatbot_Prompt_Injection

Dataset Characteristics:

- 16,000+ labeled prompts
- Binary classification
  - **0:** Benign Prompt
  - **1:** Prompt Injection
- Attack severity ("Degree") annotations
- Prompt source metadata

---

## Project Pipeline

```text
Raw Prompt
      │
      ▼
 Text Preprocessing
      │
      ▼
 TF-IDF Feature Extraction
      │
      ▼
 Machine Learning Models
      │
      ├── Logistic Regression
      ├── Support Vector Machine
      ├── Random Forest
      ├── Gradient Boosting
      │
      ▼
 DistilBERT Fine-Tuning
      │
      ▼
 Model Evaluation
      │
      ├── Accuracy
      ├── Precision
      ├── Recall
      ├── F1 Score
      ├── Confusion Matrix
      └── Recall by Attack Severity
```

---

# Models Evaluated

### Classical Machine Learning

- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest
- Gradient Boosting

### Transformer

- DistilBERT (Hugging Face Transformers)

---

# Technologies Used

- Python
- Scikit-learn
- Hugging Face Transformers
- PyTorch
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

---

# Experiments Performed

## Baseline Models

Implemented and evaluated:

- Logistic Regression
- Random Forest
- SVM

using TF-IDF feature vectors.

---

## Text Preprocessing

Investigated the impact of preprocessing techniques on prompt injection detection, including cleaning and feature engineering.

Finding:

Heavy preprocessing did not improve model performance, suggesting that preserving original prompt structure may retain useful security-related information.

---

## Gradient Boosting

Implemented Gradient Boosting to compare ensemble boosting against Random Forest.

Result:

Gradient Boosting achieved the highest overall classification performance.

---

## DistilBERT Fine-Tuning

Fine-tuned DistilBERT for binary prompt injection classification using Hugging Face Transformers.

Compared contextual language representations against TF-IDF-based approaches.

---

## Attack Severity Analysis

Evaluated detection performance across different prompt injection severity levels using the dataset's Degree annotations.

---

# Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---------|---------:|----------:|--------:|---------:|
| Logistic Regression | 82.98% | 94.27% | 83.34% | 88.47% |
| Random Forest | 96.60% | **99.38%** | 96.25% | 97.79% |
| SVM | 89.73% | 98.14% | 88.56% | 93.11% |
| **Gradient Boosting** | **97.22%** | 98.67% | 97.77% | **98.22%** |
| **DistilBERT** | 94.88% | 95.04% | **98.61%** | 96.79% |

---

# Key Findings

- Gradient Boosting achieved the highest overall performance across Accuracy and F1 Score.
- DistilBERT achieved the highest Recall, detecting the greatest proportion of malicious prompt injection attacks.
- Classical machine learning methods remained highly competitive despite the availability of transformer-based models.
- Contextual embeddings provided by DistilBERT significantly improved attack coverage while introducing a small decrease in overall precision.

---

# Repository Structure

```
Prompt-Injection-Research/
│
├── notebooks/
│   ├── 01_baseline_models.ipynb
│   ├── 02_preprocessing.ipynb
│   ├── 03_gradient_boosting.ipynb
│   ├── 04_distilbert.ipynb
│   └── 05_hyperparameter_tuning.ipynb
│
├── figures/
│   ├── accuracy_comparison.png
│   ├── confusion_matrices/
│   └── model_visualizations/
│
├── results/
│   ├── final_model_comparison.csv
│   ├── distilbert_results.csv
│   └── distilbert_recall_by_degree.csv
│
├── requirements.txt
└── README.md
```

---

# Future Work

- Hyperparameter optimization using GridSearchCV
- Evaluate larger transformer architectures (RoBERTa, DeBERTa)
- Benchmark on newer prompt injection datasets
- Investigate adversarial training methods
- Develop explainable prompt injection detection techniques

---

# References

- SPML Chatbot Prompt Injection Dataset
- Hugging Face Transformers
- Scikit-learn Documentation
- DistilBERT: *DistilBERT, a distilled version of BERT: smaller, faster, cheaper and lighter*