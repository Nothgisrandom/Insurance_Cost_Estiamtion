#  Insurance Cost Prediction & Risk Segmentation

This project examines how personal attributes, including **age**, **BMI**, **smoking habits**, and **geographic region**, influence medical costs. 
It also segments individuals into cost groups to help insurers optimize premium pricing.

---

## Project Overview

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
- `charge_category`: Categorical variable derived from charges using 5-number summary

---

##  Techniques Used

- **Exploratory Data Analysis (EDA)**: Histograms, box plots, correlation heat maps, bivariate exploration via scatter plots and side-by-side box plots. 
- **Predictive Modeling**: Multiple Linear Regression
- Interpretation The multiple linear model explains 78% of the variability in health care costs based on the insured's demographic data. 
- **Clustering**: KMeans (planned)

---

## Data Visualizations & Exploration

![Charges Distribution](https://github.com/Nothgisrandom/Insurance_Cost_Estiamtion/blob/main/charges_distribution.png?raw=true)

![Charges Distribution](Charges_Vs_Age_Region.png)

![Charges Distribution](charges_by_smoker.png)

![Charges Distribution](Charges_Age_by_Smoker.png)

##  Key Insights

- **Charges are heavily skewed to the right**, with a small group of individuals incurring very high costs.
- **Smoking status is a dominant factor** influencing medical expenses.
- **BMI and Age are also positively correlated with increased charges**.
- Most individuals fall into four cost brackets: **$0–15K**, **15K–30K**, **30K–50K**, and a few outliers over **$50K**.


### Model Coefficients Table

| Index | Feature              | Standard Deviation | Original Coefficients | Unstandardized Coefficients |
|-------|----------------------|---------------------|------------------------|-----------------------------|
| 4     | smoker_yes           | N/A                 | 11825.564428           | 11825.564428                |
| 3     | smoker_no            | N/A                 | -11825.564428          | -11825.564428               |
| 11    | y_intercpt           | N/A                 | 20311.928139           | -493.605637                 |
| 7     | region_northeast     | N/A                 | 459.585244             | 459.585244                  |
| 2     | children             | 1.205493            | 516.890247             | 428.779229                  |
| 10    | region_southwest     | N/A                 | -350.214110            | -350.214110                 |
| 1     | bmi                  | 6.098187            | 2036.228123            | 333.907135                  |
| 0     | age                  | 14.04996            | 3614.975415            | 257.294349                  |
| 9     | region_southeast     | N/A                 | -198.279052            | -198.279052                 |
| 8     | region_northwest     | N/A                 | 88.907918              | 88.907918                   |
| 6     | sex_male             | N/A                 | -9.295846              | -9.295846                   |
| 5     | sex_female           | N/A                 | 9.295846               | 9.295846                    |
 
### Interpretation of the fitted coefficients

- **y-intercept:**  The expected cost of healthcare is approximately $ 20,000 when all input features are at their mean values in the dataset.

- **smoker_yes:** 	increases the cost by 11.8 thousand dollars compared to non-smokers.	

 - **BMI:** For each additional unit in BMI, the cost increases by $ 333.90 if all other variables are held constant.

- **Children:** For each additional child in the family, the cost increases by $428.78, assuming all other variables remain constant.

- **Sex_female:** For females, the cost increases by $ 9.30 compared to males of the same age, BMI, etc.

-  The fitted coefficient shows the mean cost for the region variables if all other variables are at their mean value in the dataset.
-  This helps compare the group means across different regions. Southern regions have a lower average cost compared to northern ones.

---

### MLM Evaluation Metrics
- Interpretation: The multiple linear model explains 78% of the variability in healthcare costs based on the insured's demographic data. 


##  File Structure
- EDA data visualizations and images. 
- Python Notebook: https://github.com/Nothgisrandom/Insurance_Cost_Estiamtion/blob/main/Insurance_EDA_with_Saved_Images.ipynb 
- `README.md`: Project summary and insights

---

##  Model Enhancements:
- `charge_category`: Categorical variable derived from charges using 5-number summary

---

## Techniques Used

- **Exploratory Data Analysis (EDA)**: Histograms, box plots, correlation heatmaps, bivariate exploration via scatter plots and side-by-side box plots.  
- **Regression Modeling**: Multiple Linear Regression and Random Forest Regressor  
- **Risk Group Segmentation**: Charges were categorized into bins using the 5-number summary:
  - Very Low (≤ $4,740), Low ($4,740–$9,382), Medium ($9,382–$16,640), High (>$16,640)
  - The categorization was updated basewd on the visible clusters in the histogram.
- **Classification Models**: SVM, Random Forest, and Dummy Classifier were trained to predict `charge_category`  
- **Class Imbalance Handling**: Applied SMOTE (Synthetic Minority Oversampling Technique) to improve model fairness  
- **Model Evaluation**: Confusion matrices, macro-averaged classification reports, and performance bar plots for F1, precision, recall, and accuracy  
- **Model Interpretability**:
  - Feature importance via Random Forest

---

## Updated Insights

- **Random Forest Feature Importance (Charges Prediction)**:
  1. **Smoker** (most important)
  2. **BMI**
  3. **Age**
  4. Children, Region, and Sex (minor contributors)

- **Model Comparison (Charge Category Classification)**:
  - Best overall performance from **Random Forest** with SMOTE balancing
  - **Smoker status** is a dominant predictor for classification and regression alike
  - Models were evaluated using **confusion matrices** and **macro F1-score comparisons**

- **Risk Category Distribution** (based on 5-number summary bins):
  ```
  Very Low      (~1122–4740):    ███████████████████████
  Low           (~4740–9382):    █████████████████
  Medium        (~9382–16640):   ████
  High          (>16640):        ████
  ```

---

## New Visuals

- Classification Metric Comparison Chart
![metric comparison](https://github.com/Nothgisrandom/Insurance_Cost_Estiamtion/blob/main/classification%20metric%20comparison.png)
- Bar chart of feature importances from Random Forest
-![Feature Importance](https://github.com/Nothgisrandom/Insurance_Cost_Estiamtion/blob/main/Feature%20Importance%20from%20Random%20Forest.png)

- Confusion matrix heatmaps for each classifier
- F1-score, Precision, Recall, Accuracy bar plots across models

---


## Next Steps
- Extend the model to include external social/demographic variables  
- Deploy as a simple Streamlit dashboard or Tableau integration for real-time prediction 


---



