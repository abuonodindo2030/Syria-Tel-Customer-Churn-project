# SyriaTel Customer Churn Prediction Project

##  Overview

Customer churn poses a significant challenge for SyriaTel, leading to revenue loss and increased customer acquisition costs.  
This project aims to build a predictive system capable of identifying customers most at risk of leaving, enabling SyriaTel to proactively intervene with retention strategies.

By leveraging behavioral, billing, and service interaction data, we develop a machine learning pipeline that delivers high-precision churn predictions for data-driven business decision-making.



## 👥 Stakeholder Audience

- **SyriaTel’s Executive Leadership**: Seeking cost-saving strategies and revenue retention.  
- **Customer Retention & Marketing Teams**: Need actionable insights for targeted retention campaigns.  
- **Service Operations Managers**: Interested in reducing support-related churn.  
- **Data Science and Analytics Teams**: Supporting infrastructure and deployment.  



## 📊 Dataset Description

The dataset consists of **3,333 customer records** with **21 features**, including:

- Usage metrics across day, evening, night, and international calls  
- Customer service interaction frequency  
- Billing-related metrics  
- Plan subscriptions, e.g. international plan, voicemail plan  

**Target variable**:  
- Binary label: `churn (True/False)`  
- ~14.5% of customers are labeled as churners  

**Notable Attributes**:
- No missing values, which simplified preprocessing  
- Skewed class distribution highlighted an imbalance that needed to be addressed during model training  



## 🔬 Modeling Methodology

### 1. Exploratory Data Analysis (EDA)
- Analyzed churn distribution, feature correlations, and significance  
- Identified top predictive features: `total_charge`, `customer_service_calls`, and `international_plan`  

### 2. Feature Engineering
- Derived metrics like average daytime call duration and total usage  
- Categorical variables encoded using **Label Encoding**

### 3. Feature Selection
- Applied **SelectKBest** with **ANOVA F-test** to extract top 15 predictive features  

### 4. Model Selection
Trained and evaluated the following models:

- Logistic Regression  
- Random Forest  
- Gradient Boosting  
- Decision Tree  

### 5. Hyperparameter Tuning
- Tuned Gradient Boosting using **RandomizedSearchCV**



## 📈 Evaluation Results

Each model was evaluated using **5-fold stratified cross-validation** on unseen data.  
**Metrics**: Precision, Recall, F1 Score, ROC-AUC

| Model              | Precision | Recall | F1 Score | ROC-AUC |
|-------------------|-----------|--------|----------|---------|
| Logistic Regression | 34.1%   | 74.2%  | 46.8%    | 0.819   |
| Random Forest       | 100.0%  | -      | -        | 0.922   |
| Gradient Boosting   | 100.0%  | 81.4%  | 89.8%    | 0.921   |
| Decision Tree       | 81.9%   | 79.4%  | 80.6%    | 0.882   |



##  Final Model: Tuned Gradient Boosting

- **ROC-AUC** improved to **0.937** after tuning  
- Achieved **perfect precision** and **strong recall**  
- Identified genuine churners with **no false positives**

###  Top Feature Importances:
1. `total_charge`  
2. `customer_service_calls`  
3. `number_vmail_messages`  



##  Conclusion

The tuned Gradient Boosting model is a powerful predictive tool for SyriaTel:

- **Business Impact**: Enables strategic targeting of high-risk customers  
- **Operational Precision**: Allocates resources only to likely churners  
- **Scalability**: Ready for real-time scoring and segmentation  



##  Strategic Recommendations

1. Deploy **targeted billing interventions** for high-charge customers  
2. Proactively **follow up with customers** who make frequent service calls  
3. **Monitor voicemail usage patterns** as early churn indicators  

Through intelligent data use and robust modeling, SyriaTel can transform churn prediction into a strategic asset, significantly improving customer retention and reducing revenue leakage.
