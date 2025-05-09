# Smart Credit Risk Scoring: A Machine Learning Approach to Predicting Defaults for Ethical Lending

## Overview

This project addresses a pressing challenge faced by a digital micro-lender in Kenya: **rising loan defaults** that threaten its **cash flow, profitability, and investor confidence**. The existing credit scoring system is manual and based on basic heuristics such as age, job type, and loan limits. This reactive approach lacks the precision and adaptability required to accurately identify potential defaulters early on.

Using **machine learning**, we developed a predictive model to assess the likelihood of a customer defaulting on their next month’s credit payment. This solution aims to enable **smarter, data-driven, and ethical lending decisions** while supporting **financial inclusion** and minimizing institutional risk.

---

## Business and Data Understanding

### Stakeholders
Our primary stakeholders include:
- **Risk Managers** and **Credit Officers** who want a more accurate credit scoring tool.
- **Executives** and **Investors** seeking to minimize financial risk and boost profitability.
- **Product and Innovation Teams** aiming to integrate predictive analytics into digital loan platforms.

### Dataset Overview
The dataset simulates typical customer records for a credit service and contains:
- **Demographic information** (e.g., Age, Employment)
- **Financial metrics** (e.g., Annual Salary, Bank Balance)
- **Behavioral indicators** (e.g., Default History, Index Score)
- **Target variable**: Whether a client defaulted on their next month’s payment.

We also identified **class imbalance** in the target variable—common in default prediction problems—and addressed it through **SMOTE (Synthetic Minority Oversampling Technique)**.

---

## Modeling

To create a robust model, we followed the CRISP-DM methodology:

1. **Baseline Model**: Logistic Regression was used to set a performance benchmark.
2. **Addressed Imbalance**: Applied SMOTE to balance the dataset.
3. **Modeling Algorithms**:
   - **Logistic Regression (Post-SMOTE)**
   - **Random Forest Classifier** (Ensemble Model)
4. **Hyperparameter Tuning**: GridSearchCV was used to fine-tune the Random Forest model.

We selected Random Forest for its ability to handle non-linear relationships and feature interactions without requiring intensive preprocessing.

---

## Evaluation

We evaluated models using metrics aligned with our business objective of **identifying defaulters early**:
- **Accuracy**: Overall correctness of the model.
- **Precision (Class 1)**: How many predicted defaulters were actual defaulters.
- **Recall (Class 1)**: How many actual defaulters we correctly identified.
- **F1-Score**: Harmonic mean of precision and recall.
- **AUC Score**: Measures the ability of the model to distinguish between classes.

| Model                      | Accuracy | Precision (1) | Recall (1) | F1-Score (1) | AUC Score |
|---------------------------|----------|---------------|------------|--------------|-----------|
| Baseline Logistic Reg.    | 0.973    | 0.72          | 0.31       | 0.44         | N/A       |
| SMOTE + Logistic Reg.     | 0.860    | 0.17          | 0.88       | 0.29         | N/A       |
| **SMOTE + Random Forest** | **0.905**| **0.22**      | **0.73**   | **0.34**     | **0.91**  |

While the precision remains moderate, the recall and AUC of the Random Forest model make it a powerful tool to **minimize false negatives**—a key business priority.

### Feature Importance
Our Random Forest model revealed that **Bank Balance**, **Credit Index**, and **Annual Salary** were the top predictors of default. These insights can help design fairer, income-aware credit products.

---

## Conclusion

We successfully developed a machine learning model to predict loan defaults, outperforming the existing rule-based system. Our final model (Random Forest with SMOTE) achieves:
- **High recall**, helping identify at-risk clients early.
- **Strong AUC**, indicating reliable separation between defaulters and non-defaulters.
- **Interpretable results**, supporting ethical and transparent lending practices.

### Recommendations
- Integrate the model into the micro-lender's credit decision workflow.
- Regularly retrain the model with new customer data for adaptability.
- Use feature importance insights to enhance customer support and product design.

---

**Author**: Allan Ofula  
**Affiliation**: Data Science Student, Moringa School & DataCamp  
**Project Type**: Phase 3 Final Project (Machine Learning – Ensemble Modeling)
