# User Churn Prediction: A Machine Learning Approach for Waze

This project was completed as part of a six-course professional certificate, applying machine learning to a real-world business problem: predicting user churn for Waze. It demonstrates end-to-end data analysis, model development, and business-oriented insights.

**Complete analysis, including code and visualizations, can be found in the [Jupyter Notebook](https://github.com/your-username/waze-user-churn-prediction/blob/main/your-notebook-name.ipynb).**

---

### 1. Project Overview

This project focused on building a machine learning model to predict monthly user churn for Waze, enabling timely intervention strategies such as incentives or promotions. Through targeted feature engineering, the final **XGBoost model achieved a recall of 15.9%, nearly double that of the baseline logistic regression**, while maintaining strong accuracy and precision.

---

### 2. Business Understanding

Churn was defined as users who uninstall or stop using the app. The objective was to identify at-risk customers early to reduce churn and support growth. **Recall** was chosen as the most critical metric, as the cost of missing a churner (false negative) is higher than incorrectly flagging a retained user (false positive). For the purposes of this project, the defined stakeholders were the Waze leadership team and department heads in Finance, Administration, and Operations. This framing was provided to simulate a realistic business scenario.  

---

### 3. Data Understanding

The analysis used a synthetic dataset provided by the course in partnership with Waze, designed to mimic real-world user activity. The dataset contains 14,999 rows and 13 columns, with each row representing a unique user. Key variables include `sessions`, `driving_days`, `driven_km_drives`, and `device`, which were used to predict the binary target variable, `label` (retained vs. churned).

- **Data preparation**: Approximately **18% of the users** were found to have churned, indicating a somewhat unbalanced dataset but still workable without resampling. The data had missing values in the `label` column, which were dropped as there was no evidence of a non-random cause.

- **Exploratory Data Analysis (EDA)**: It was crucial for understanding the data's quality and structure before modeling. The analysis confirmed that **tree-based models were a good choice, as they are resilient to the many outliers** present in the data.

---

### 4. Modeling and Evaluation

To achieve maximum predictive power, two models were developed for cross-comparison: **Random Forest** and **XGBoost**. The data was split into training, validation, and test sets to ensure an unbiased selection of the champion model and a reliable estimate of future performance.

* **Baseline Model (Logistic Regression):** As part of a previous course, a logistic regression model was built to serve as a simple, interpretable baseline for comparison. While it achieved a moderate overall accuracy of 82%, **its recall for the "churned" class was very low at 9%**, indicating that it failed to identify most of the at-risk users.
* **Model Performance:** On the validation set, the XGBoost model achieved a higher recall of **16.2%**, while the Random Forest model’s recall was **12%**. The XGBoost model was selected as the champion model because it performed better at identifying users who actually churned, aligning with the business objective of prioritizing recall.
* **Feature Importance:** Feature engineering was a critical step, as five of the top ten most important features were engineered, including `km_per_hour` and `percent_sessions_in_last_month`. 
* **Results:** The final XGBoost model achieved a **recall of 15.9%** and **accuracy of 80%** on the test data.
  
---

### 5. Conclusion
 
- The tree-based ensemble models outperformed the baseline logistic regression, achieving higher scores across all metrics while requiring less data preprocessing. However, the XGBoost's overall accuracy of ~80% is misleading given the recall is only 15.9%.
- This low recall means the model fails to identify many at-risk customers, limiting its usefulness for the primary business objective of churn detection and intervention.
- While the models provide valuable exploratory insights and a foundation for future work, they are not yet strong predictors of churn. Further refinement is needed to better identify customers at risk of churning.
  
---

### 6. Final Deliverables

For a concise, business-focused summary of this project, including key insights and recommendations with data visualizations, please see the full report below.
* **[Project Executive Summary](https://github.com/your-username/waze-user-churn-prediction/blob/main/reports/Waze%20User%20Churn%20Executive%20Summary.pdf)**  

---

### 7. Future Steps

* Improve recall through further feature engineering and advanced hyperparameter tuning.  
* Incorporate more detailed, drive-level data (e.g., location-based or user interaction patterns) to improve model performance and better capture patterns that indicate potential churn. 
* Test different variable combinations to get a more predictive signal.
