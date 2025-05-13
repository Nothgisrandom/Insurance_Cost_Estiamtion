# 🏥 Insurance Cost Prediction & Risk Segmentation

This project explores how personal attributes such as **age**, **BMI**, **smoking habits**, and **geographic region** affect medical costs. 
It also segments individuals into cost groups to help insurers optimize premium pricing.

---

## 📊 Project Overview

**Dataset**: [Medical Cost Personal Dataset](https://raw.githubusercontent.com/stedy/Machine-Learning-with-R-datasets/master/insurance.csv)  
**Sample Size**: 1,338  
**Features**:  
- `age`: Age of primary beneficiary  
- `sex`: Gender of policyholder  
- `bmi`: Body Mass Index  
- `children`: Number of children covered by insurance  
- `smoker`: Smoking status  
- `region`: U.S. residential area  
- `charges`: Individual medical costs (target variable)

---

## 🔍 Techniques Used

- **Exploratory Data Analysis (EDA)**: Histograms, box plots, and correlation heatmaps
- **Dimensionality Reduction**: PCA (planned)
- **Clustering**: KMeans (planned)
- **Predictive Modeling**: Linear Regression, Random Forest (planned)

---

## 💡 Key Insights

- **Charges are heavily skewed to the right**, with a small group of individuals incurring very high costs.
- **Smoking status is a dominant factor** influencing medical expenses.
- **BMI and Age are also positively correlated with increased charges**.
- Most individuals fall into four cost brackets: **$0–15K**, **15K–30K**, **30K–50K**, and a few outliers over **$50K**.

---

## 📁 File Structure
- `Revised_Insurance_EDA_Notebook.ipynb`: Cleaned-up version with additional EDA visuals
- `README.md`: Project summary and insights

---

## 🚀 Next Steps

- Add clustering for risk segmentation (low/medium/high)
- Build and evaluate machine learning models


---



