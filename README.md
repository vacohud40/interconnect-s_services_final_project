# Churn Forecasting Model: Project Summary

This project focuses on building a machine learning model to predict **customer churn** for the telecom operator Interconnect, aiming to enable proactive customer retention.

## Project Goal

The primary objective is to develop a model that accurately predicts customer churn. Success will be measured primarily by **AUC-ROC**, targeting at least $0.75$ and striving for $0.88$. `Accuracy` will be a secondary metric.

## Project Work Plan Highlights

1.  **Data Integration & Cleaning:** Merge `contract`, `personal`, `phone`, and `internet` datasets using `customerID`. Clean `TotalCharges` by handling non-numeric entries and converting to a numeric type.

2.  **Feature Engineering & Preprocessing:**

    * Transform `BeginDate` and `EndDate` into `Tenure` (contract duration in months).

    * Create a binary `Churn` target variable based on `EndDate`.

    * Convert categorical features to numerical (e.g., One-Hot Encoding).

    * Scale numerical features.

3.  **Model Selection, Training & Tuning:**

    * Split data into training and test sets.

    * Focus on **boosting algorithms** (LightGBM, XGBoost) due to their performance on tabular data.

    * Tune hyperparameters using cross-validation, optimizing for **AUC-ROC**.

4.  **Final Model Evaluation & Interpretation:** Evaluate the best model on the test set using **AUC-ROC** and **Accuracy**. Extract feature importances to understand churn drivers and formulate actionable recommendations.

## Conclusion and Recommendations

The project successfully developed a robust churn prediction solution. The **LightGBM model** emerged as the best performer, achieving a **Test AUC-ROC of** $0.8476$, significantly surpassing the $0.75$ target.

### Key Insights from EDA:

* The dataset has a class imbalance (more active customers).

* Higher monthly charges strongly correlate with churn.

* Total charges indicate customer longevity.

### Recommendations:

* **Deploy the LightGBM Model:** Integrate it into operations for continuous churn identification.

* **Differentiate Retention by Tenure:**

    * **New Customers (**$0-10$ **months):** Focus on onboarding, satisfaction checks, and addressing early issues.

    * **Long-Term Customers (**$60+$ **months):** Implement loyalty programs, personalized plan reviews, and competitive renewal options.

* **Target High Monthly Charge Customers:** Prioritize these for retention campaigns, offering tailored adjustments or value-added services.

* **Monitor Model Performance Continuously:** Regularly monitor AUC-ROC on new data and retrain the model periodically.

These recommendations aim to leverage the model's predictive power to reduce customer attrition and enhance lifetime value for Interconnect.
