# Prompt Injection Detection Research

This project investigates the use of lightweight machine learning models for prompt injection detection and explores how detection performance varies with prompt injection severity.

Models evaluated:

* Logistic Regression
* Random Forest
* SVM (LinearSVC)

Dataset:

* SPML Prompt Injection Dataset

Current Results:

| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | 82.98%   |
| SVM                 | 89.73%   |
| Random Forest       | 96.60%   |

Current Findings:

* Random Forest achieved the highest performance.
* Detection performance improves as attack severity increases.
* Low-severity prompt injections are significantly more difficult to detect than high-severity attacks.
* High-severity attacks were detected with near-perfect recall.

Repository Structure:

```text
data/
figures/
notebooks/
results/
```

Work in progress.
