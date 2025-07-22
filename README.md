 **SyriaTel Customer Churn Prediction Project**

*Overview*

Customer churn poses a significant challenge for SyriaTel, leading to revenue loss and increased customer acquisition costs. This project aims to build a predictive system capable of identifying customers most at risk of leaving, enabling SyriaTel to proactively intervene with retention strategies. By leveraging behavioral, billing, and service interaction data, we develop a machine learning pipeline that delivers high-precision churn predictions for data-driven business decision-making.

*Business and Data Understanding*

*Stakeholder Audience*

•	SyriaTel’s Executive Leadership: Seeking cost-saving strategies and revenue retention.
•	Customer Retention & Marketing Teams: Need actionable insights for targeted retention campaigns.
•	Service Operations Managers: Interested in reducing support-related churn.
•	Data Science and Analytics Teams: Supporting infrastructure and deployment.

*Dataset Description*

The dataset consists of 3,333 customer records with 21 features, including:
•	Usage metrics across day, evening, night, and international calls.
•	Customer service interaction frequency.
•	Billing-related metrics.
•	Plan subscriptions, e.g. international plan, voicemail plan.
The target variable is a binary label: churn (True/False), with 14.5% of customers labeled as churners.

Notable attributes:

•	No missing values, which simplified preprocessing.
•	Skewed class distribution highlighted an imbalance that needed to be addressed during model training.


**Modeling**

*Methodology*

We followed a structured pipeline:
1.	Exploratory Data Analysis (EDA)
•	Analyzed the distribution of churn, correlations, and feature significance.
•	Identified top predictive features like total charge, customer service calls, and international plan status.

3.	Feature Engineering
•	Created derived metrics such as average daytime call duration and total usage metrics.
•	Encoded categorical variables using Label Encoding.

5.	Feature Selection
Applied SelectKBest with ANOVA F-test to extract the top 15 predictive features.


7.	Model Selection
Trained and evaluated 4 models:
i.	Logistic Regression
ii.	Random Forest
iii.	Gradient Boosting
iv.	Decision Tree
9.	Hyperparameter Tuning
Optimized Gradient Boosting parameters using RandomizedSearchCV.

 *Evaluation*
Each model was assessed using 5-fold stratified cross-validation and tested on unseen data. Metrics included:

Model	Precision	Recall	F1 Score	ROC-AUC
Logistic Regression	34.1%	74.2%	46.8%	0.819
Random Forest	100.0%			0.922
Gradient Boosting	100.0%	81.4%	89.8%	0.921
Decision Tree	81.9%	79.4%	80.6%	0.882

*Final Model: Gradient Boosting (Tuned)*

•	ROC-AUC improved to 0.937 after tuning.
•	Achieved perfect precision and strong recall, identifying genuine churners without false positives.
 Feature importance highlighted:
•	total_charge, customer_service_calls, and number_vmail_messages as the top three drivers of churn.

*Conclusion*

The tuned Gradient Boosting model presents a powerful predictive tool for SyriaTel:
•	Business Impact: Enables strategic targeting of high-risk customers for retention.
•	Operational Precision: Ensures resources are allocated only to actual churners.
•	Scalability: Model supports real-time scoring and segmentation.

 *Strategic Recommendations*
1.	Deploy targeted billing interventions for high-charge customers.
2.	Proactively follow up with customers, making frequent service calls.
3.	Monitor voicemail usage patterns as churn indicators.
Through intelligent data use and robust modeling, SyriaTel can transform churn prediction into a strategic asset, significantly improving customer retention and reducing revenue leakage.




