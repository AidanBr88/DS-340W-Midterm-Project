# DS-340W-Midterm-Project

# Project Overview

This project uses machine learning to assess a pasted URL and
assign a Low, Moderate, or High estimated phishing risk category.

## Dataset

Dataset for Link Phishing Detection, shared by Winson on Kaggle:
https://www.kaggle.com/datasets/winson13/dataset-for-link-phishing-detection

The original dataset contains 19,431 records. After removing
repeated URLs, 11,429 unique URLs remain:
- 5,715 legitimate
- 5,714 phishing

## Methodology

The dataset is split into:
- 60% training: 6,857 URLs
- 20% validation: 2,286 URLs
- 20% testing: 2,286 URLs

The notebook compares a majority-class baseline, Logistic
Regression, and Random Forest. Random Forest achieved the
highest validation F1. Random Forest was selected to be the prototype.

Risk thresholds were selected using validation data and fixed
before evaluating the test set:
- Low: score below 0.230
- Moderate: score from 0.230 to below 0.697
- High: score of 0.697 or higher

## Test Results

At the default binary cutoff:
- Accuracy: 85.65%
- Phishing precision: 86.03%
- Phishing recall: 85.13%
- Phishing F1: 0.8558
- ROC AUC: 0.9328
- False positive rate: 13.82%

Using the three risk categories:
- 4.99% of actual phishing URLs received Low risk.
- 4.90% of actual legitimate URLs received High risk.
- 28.17% of all test URLs received Moderate risk.

## How to Run

1. Download MidtermProject.ipynb from this repository.
2. Open it in Google Colab.
3. Download the dataset from the Kaggle link above.
4. Run the notebook cells in order.
5. Upload the dataset ZIP or CSV when prompted.
6. Use the URL input box in the final cell to evaluate a link.
