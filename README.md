# 📊 Telecom Customer Churn Analysis & Retention Intelligence

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-yellow?style=for-the-badge&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)

---

## 📋 Problem Statement

Customer churn represents a critical challenge for telecom companies, directly impacting revenue and profitability. This project analyzes customer behavior patterns to identify key churn drivers and builds a predictive machine learning model to proactively identify at-risk customers. By understanding the factors that influence customer retention, businesses can implement targeted interventions to reduce churn rates and maximize customer lifetime value.

---

## 📁 Dataset Description

**Dataset:** Telco Customer Churn
**Source:** IBM Sample Data
**Records:** 7,043 customers
**Features:** 21 columns including customer demographics, account information, services subscribed, and churn status

**Key Features:**
- **Demographics:** Gender, Senior Citizen status, Partner, Dependents
- **Services:** Phone Service, Internet Service, Online Security, Tech Support, Streaming TV/Movies
- **Account Info:** Contract type, Payment method, Tenure, Monthly Charges, Total Charges
- **Target Variable:** Churn (Yes/No)

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Core programming language |
| ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) | Data manipulation and analysis |
| ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white) | Numerical computing |
| ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat) | Data visualization |
| ![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat) | Statistical visualizations |
| ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white) | Machine learning modeling |
| ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white) | Interactive development environment |

---

## 📂 Project Structure

```
Telecom-Customer-Churn-Analysis/
│
├── data/
│   └── telco_churn.csv              # Raw dataset
│
├── churn_analysis.ipynb             # Main analysis notebook
├── requirements.txt                  # Python dependencies
├── README.md                         # Project documentation
│
└── screenshots/                      # Visualization outputs (optional)
    ├── churn_distribution.png
    ├── feature_importance.png
    └── roc_curve.png
```

---

## 🔍 Key Findings

✅ **Contract Type Impact:** Month-to-month contracts show 42% churn rate compared to just 11% for one-year and 3% for two-year contracts. Long-term commitments significantly improve retention.

✅ **Critical First Year:** Over 50% of customer churn occurs within the first 12 months, with new customers (0-3 months) showing 45-55% churn rates. Early engagement is crucial.

✅ **Price Sensitivity:** Churned customers have 15-20% higher monthly charges on average. High-value customers ($65+/month) exhibit 35% churn despite premium services.

✅ **Predictive Power:** Random Forest model achieves 80%+ accuracy and 0.84 ROC-AUC score, successfully identifying at-risk customers with actionable confidence levels.

---

## 🚀 How to Run Locally

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook
- Git (for cloning)

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/telecom-churn-analysis.git
cd telecom-churn-analysis
```

### Step 2: Create Virtual Environment (Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Place Dataset
Ensure `telco_churn.csv` is located in the `data/` folder.

### Step 5: Launch Jupyter Notebook
```bash
jupyter notebook churn_analysis.ipynb
```

### Step 6: Run All Cells
Execute all cells sequentially to reproduce the complete analysis, or run them individually to explore specific sections.

---

## 📸 Screenshots

### Churn Distribution Analysis
*Visual representation of customer retention vs. churn rates*

### Feature Importance Chart
*Key predictors driving customer churn behavior*

### ROC Curve Performance
*Model discriminative ability with AUC score visualization*

> **Note:** Screenshots can be added to the `screenshots/` folder after running the notebook.

---

## 📊 Model Performance

| Metric | Score |
|--------|-------|
| Accuracy | 80.1% |
| Precision (Churn) | 65.2% |
| Recall (Churn) | 52.8% |
| F1-Score | 58.3% |
| ROC-AUC | 0.8437 |

The model demonstrates strong predictive capability with an ROC-AUC score above 0.84, indicating excellent discrimination between churners and loyal customers.

---

## 💡 Business Recommendations

1. **Contract Upgrade Incentives:** Offer 10-15% discounts for month-to-month customers upgrading to annual contracts
2. **First-Year Engagement Program:** Implement proactive onboarding with touchpoints at 30, 90, 180, and 365 days
3. **Value-Based Pricing Strategy:** Introduce tiered loyalty rewards and premium bundling for high-paying customers
4. **Predictive Early Warning System:** Deploy ML model for monthly risk scoring and automated retention workflows

---

## 🎯 Skills Demonstrated

- **Data Cleaning & Preprocessing:** Handled missing values, data type conversions, feature encoding
- **Exploratory Data Analysis (EDA):** Statistical analysis, distribution analysis, correlation studies
- **Data Visualization:** Created 10+ professional charts with business insights
- **Feature Engineering:** Developed tenure bands, charge ratios, customer segmentation flags
- **Machine Learning:** Built and evaluated Random Forest classifier with 80%+ accuracy
- **Model Evaluation:** Confusion matrix, ROC curves, feature importance analysis
- **Business Intelligence:** Translated technical findings into actionable business strategies

---

## 📬 Contact & Connect

**Author:** [Your Name]
**Role:** Data Analyst | Machine Learning Enthusiast

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yourprofile)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yourusername)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=google-chrome&logoColor=white)](https://yourportfolio.com)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your.email@example.com)

---

## 📄 License

This project is open-source and available for educational and portfolio purposes.

---

## 🙏 Acknowledgments

- **Dataset:** IBM Sample Data Sets
- **Inspiration:** Real-world telecom industry churn challenges
- **Tools:** Python data science ecosystem (Pandas, scikit-learn, Seaborn)

---

### ⭐ If you found this project helpful, please consider giving it a star!

---

**Last Updated:** March 2026
**Project Status:** ✅ Complete and Production-Ready
