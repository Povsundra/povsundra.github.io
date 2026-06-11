---
title: "Fraud Detection in Financial Transactions"
excerpt: "Machine learning classification model to detect fraudulent banking transactions using ensemble methods and SMOTE."
collection: portfolio
date: 2025-10-12
header:
  teaser: /assets/images/portfolio-fraud-detection-teaser.jpg
---

## Problem Statement

Financial institutions face significant losses due to fraudulent transactions, which are rare events compared to legitimate ones. The challenge lies in building an accurate fraud detection model that handles severe class imbalance (0.13% fraud rate) while maintaining high precision and recall to minimize both false positives and false negatives.

## Approach

- **Dataset Analysis:** Analyzed 6.3M financial transaction records to understand fraud patterns and class distribution
- **Class Imbalance Handling:** Applied SMOTE, random oversampling, and under-sampling techniques to address the highly imbalanced dataset
- **Algorithm Comparison:** Built and compared three supervised learning models—Logistic Regression, Decision Tree, and Random Forest
- **Model Evaluation:** Assessed performance using precision, recall, F1-score, and AUC-ROC metrics to identify the best model
- **Optimization:** Fine-tuned hyperparameters to maximize fraud detection while minimizing false positives

## Tech Stack

`Python` `pandas` `NumPy` `Scikit-learn` `Matplotlib` `Imbalanced-learn`

## Key Results

- **Highest Performance:** Random Forest with oversampling achieved **99.98% accuracy**
- **Key Finding:** Class-balancing strategies are critical for effective fraud detection in imbalanced datasets
- **Model Insights:** Demonstrated the trade-off between precision and recall across different resampling techniques

## Detailed Analysis

[View Manuscript PDF](/assets/slides/manuscript.pdf){: .btn .btn--info}

---

**Dataset:** 6.3M transactions  
**Fraud Rate:** 0.13%  
**Date:** October 12, 2025  
**Status:** Completed
