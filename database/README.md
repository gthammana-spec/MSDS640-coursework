# Customer Churn Prediction in Banking

**Author:** Ganesh Thammana  
**Project Type:** Capstone Project - Machine Learning  
**Date:** 6 August 2026

---

## 📋 Project Overview

This project develops a machine learning solution to predict customer churn in the banking sector. Using a dataset of 8,101 customers with 98 behavioral and demographic features, we built and evaluated multiple classification models to identify at-risk customers and enable proactive retention strategies.

### Key Achievements
- **Model Performance:** Achieved exceptional ROC-AUC scores of 0.9996-0.9999 across all models
- **Hypothesis Validation:** Confirmed that lower customer engagement (tenure, product count, satisfaction) strongly predicts churn
- **Business Impact:** Identified actionable insights for 30-40% churn reduction through targeted interventions
- **Statistical Rigor:** Comprehensive evaluation with 5-fold cross-validation and significance testing

---

## 🎯 Business Problem

Customer acquisition in banking costs 5-7x more than retention. With a baseline churn rate of 16.07% (1,302 out of 8,101 customers), the bank faces significant revenue loss. This project aims to:
1. Predict which customers are likely to churn
2. Identify key churn drivers
3. Enable proactive retention strategies

---

## 📊 Dataset

- **Size:** 8,101 customer records
- **Features:** 98 (demographic, behavioral, transactional, engagement metrics)
- **Target Variable:** Churn (binary: 0 = retained, 1 = churned)
- **Class Distribution:** 83.93% retained, 16.07% churned (imbalanced)
- **Key Features:** Satisfaction score, NPS score, digital engagement index, tenure, product count, customer lifetime value

---

## 🔬 Methodology

### 1. Data Preprocessing
- Handled missing values (only 1 feature with 56% missing)
- Feature engineering and selection using XGBoost importance
- Addressed class imbalance using SMOTE
- Removed data leakage features

### 2. Models Evaluated
- Logistic Regression
- XGBoost Classifier
- Random Forest Classifier
- Support Vector Machine (SVM)

### 3. Evaluation Metrics
- ROC-AUC (primary metric)
- F1-Score
- Precision & Recall
- Accuracy
- 5-fold cross-validation
- Paired t-tests for statistical significance

---

## 🏆 Results

### Model Performance Comparison

| Model | ROC-AUC | F1-Score | Precision | Recall | Accuracy |
|-------|---------|----------|-----------|--------|----------|
| **XGBoost** | **0.9999** | 0.9884 | 0.9961 | 0.9808 | 0.9963 |
| **Logistic Regression** | 0.9996 | **0.9885** | 0.9923 | **0.9847** | 0.9963 |
| **SVM** | 0.9996 | 0.9846 | 0.9922 | 0.9770 | 0.9951 |
| **Random Forest** | 0.9996 | 0.9497 | **1.0000** | 0.9042 | 0.9846 |

### Statistical Validation
- Paired t-tests showed no significant performance differences between top models (p > 0.05)
- All models significantly outperform naive baseline (ROC-AUC = 0.50)

### Top Churn Predictors
1. Satisfaction Score
2. NPS Score
3. Digital Engagement Index
4. Customer Lifetime Value
5. Tenure (months)
6. Number of Products
7. Average Monthly Balance
8. Total Transaction Count
9. Monthly Transaction Count
10. Age

---

## 💼 Business Recommendations

1. **Proactive Monitoring:** Implement real-time churn risk scoring
2. **Targeted Interventions:** Focus on customers with satisfaction < 3.0 and NPS < 0
3. **Product Cross-Selling:** Encourage single-product customers to adopt additional services
4. **Digital Engagement Programs:** Incentivize mobile/online banking adoption
5. **Early Tenure Support:** Enhanced onboarding for customers in first 24 months

**Expected Impact:** 30-40% reduction in churn rate through data-driven retention campaigns

---

## 📁 Repository Organization

```
customer-churn-prediction/
│
├── CustomerChurn_Final_Ganesh_Thammana.ipynb    # Final notebook with all analysis
├── Customer_Churn_Prediction_Final_Report.docx      # Comprehensive written report
├── Customer Churn Prediction Slide Presentation_Ganesh Thammana.pptx  # Presentation slides
├── requirements.txt                                  # Python dependencies
├── README.md                                         # This file
│
└── data/                                             # (Dataset - not included in repo)
    └── customer_churn_data.csv
```

---

## 🚀 Instructions for Reproducing Results

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or JupyterLab

### Step 1: Clone the Repository
```bash
git clone https://github.com/[your-username]/customer-churn-prediction.git
cd customer-churn-prediction
```

### Step 2: Create Virtual Environment (Recommended)
```bash
# Using venv
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# OR using conda
conda create -n churn-prediction python=3.8
conda activate churn-prediction
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Launch Jupyter Notebook
```bash
jupyter notebook
```

### Step 5: Run the Analysis
1. Open `CustomerChurn_Final_Ganesh_Thammana (4).ipynb`
2. Ensure the dataset is in the correct path (update path in notebook if needed)
3. Run all cells sequentially (Cell → Run All)
4. Results will be generated including model performance metrics and visualizations

### Expected Runtime
- Full notebook execution: ~5-10 minutes (depending on hardware)
- Model training: ~2-3 minutes
- Cross-validation: ~3-5 minutes

---

## 📍 Location of Required Project Components

| Component | File Name | Location |
|-----------|-----------|----------|
| **Final Report** | `Customer_Churn_Prediction_Final_Report.docx` | Root directory |
| **Presentation Slides** | `Customer Churn Prediction Slide Presentation_Ganesh Thammana.pptx` | Root directory |
| **Final Notebook** | `CustomerChurn_Final_Ganesh_Thammana.ipynb` | Root directory |
| **Requirements File** | `requirements.txt` | Root directory |
| **README** | `README.md` | Root directory (this file) |

---

## 🔍 Key Findings

### Hypothesis Validation ✅
**Original Hypothesis:** Customers with lower engagement (shorter tenure, fewer banking products, lower balances, and inactive accounts) are more likely to churn than highly engaged customers.

**Result:** **SUPPORTED** - Statistical analysis confirmed:
- Satisfaction score shows strong negative correlation with churn
- NPS detractors (< 0) have 3x higher churn rate
- Low digital engagement customers churn at 2.5x rate
- Customers with < 24 months tenure show elevated churn risk
- Single-product customers churn at significantly higher rates

---

## ⚠️ Limitations & Ethical Considerations

### Limitations
- Model trained on historical data; may not capture emerging patterns
- Requires regular retraining to maintain accuracy
- Interpretability challenges with ensemble models

### Bias & Fairness
- Potential demographic bias if certain groups underrepresented
- Risk of discriminatory targeting without proper monitoring
- **Mitigation:** Regular fairness audits across age, gender, income segments

---

## 🔮 Future Work

1. **Deep Learning:** Explore LSTM/GRU models for temporal churn patterns
2. **Real-Time Deployment:** Integrate model into CRM system for live scoring
3. **Explainability:** Implement SHAP/LIME for individual prediction explanations
4. **A/B Testing:** Validate retention campaign effectiveness
5. **Feature Engineering:** Incorporate customer service interaction data
6. **Multi-Class Prediction:** Predict churn timing (30/60/90 days)
7. **Cost-Sensitive Learning:** Optimize for business value, not just accuracy

---

## 📚 References

- Scikit-learn Documentation: https://scikit-learn.org/
- XGBoost Documentation: https://xgboost.readthedocs.io/
- Imbalanced-learn Documentation: https://imbalanced-learn.org/

---

## 📧 Contact

**Ganesh Thammana**  
GitHub: [your-github-username]  
Email: [your-email]

---

## 📄 License

This project is submitted as part of academic coursework. All rights reserved.

---

**Last Updated:** August 2026
