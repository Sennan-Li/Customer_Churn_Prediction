# Customer Churn Prediction Using Logistic Regression

## 📌 Objectives

This project analyses customer data from the last quarter for Swan Teleco's Customer Retention Marketing team, employing predictive modelling techniques. The main objectives are to:

* Identify the demographics and product usage of customers who churn.
* Determine the reasons behind customer churn and the factors that encourage customers to stay.
* Pinpoint the most significant factors influencing churn and suggest a metric for incentivizing new customer sign-ups.
* Use predictive modelling to produce a list of the 500 customers most likely to churn for a targeted mailer campaign.
* Use predictive modelling to generate a churn risk score for all remaining customers to aid customer service interactions.
* Create an information presentation deck summarizing these findings for the retention team.

## 🔍 Exploratory Data Analysis

### 💸 Why Our Beloved Customers Are Drifting Away 🚶‍♀️🚶‍♂️

#### 📊 **Churn Insight 1:** Overall Churning Rate & Retaining Rate

- **Positive:** 73.5% customer retention rate shows good customer loyalty.
- **Room for Improvement:** 26.5% churn rate is notable, we have to investigate reasons to reduce it.

![Churn_Rate](https://sennanliimages.blob.core.windows.net/churn-prediction-project/Churn_Rate.png)

### 💰 **Churn Insight 2:** Tenure Months, Monthly Charges & Total Charges

- **Tenure:**
  - Customers with **less than one year of tenure** are at higher risk of churn.
  - Tenure **more than 5 years** has the most retained customers
- **Monthly Charges:**
  - With **charges below $30** retaining the most customers, it seems **affordability** is a key factor.
- **Profitability:**
 - The profitability of retained customers indicates that **improving retention** efforts can directly **increase revenue**.

![Charges](https://sennanliimages.blob.core.windows.net/churn-prediction-project/Charges.png)

### 🧍‍♂️ **Churn Insight 3:** Senior Citizen, Family Makeup

- Majority of the churner are **non-senior**, **single**, **without dependents**, same as retained customers.

![Demographis](https://sennanliimages.blob.core.windows.net/churn-prediction-project/Demographis.png)

### 📞 **Churn Insight 4:** Phone Service & Its Add-on Multi-lines Service

- **Phone Service:** 91% of churned customers had phone service, cannot be a reason for churn, as nearly every customer gets phone services.
- **Multi-lines:** Among churned customers with phone service, half had multi-lines and half didn't. No clear preference or deterrence from multi-lines for churn.

![Phone_Service](https://sennanliimages.blob.core.windows.net/churn-prediction-project/Phone_Service.png)

### 🌐 **Churn Insight 5:** Internet Service & Its Add-on Services

- The majority of churners are using **Fiber Optic** connections.
- A significant portion of them churn due to dissatisfaction with **Streaming TV and Movies** add-on services.

![Internet_Service](https://sennanliimages.blob.core.windows.net/churn-prediction-project/Internet_Service.png)

### 🤝 **Churn Insight 6:** Churn Reasons

- **Pie Chart:** Competitor (37.5%) is top churn factor, followed by customer experience (32.8%), product (15.0%), and price (14.7%).
- **Bar Chart:** Attitude of support person and competitor's higher download speeds are leading churn reasons.
- **Actions:** Analyze competitors, enhance customer service, review product and pricing.

![Churn_Reasons](https://sennanliimages.blob.core.windows.net/churn-prediction-project/Churn_Reasons.png)

### 🌟 **Churn Insights Summary**

1. **Retention & Churn:** **Retention** at **73.5%** is strong, but **26.5% churn** needs attention. 📊  
2. **Tenure & Charges:** Short-tenure (<1 year) customers churn most; affordability (<$30) boosts retention. 💰  
3. **Demographics:** Churners are often **non-senior, single**, with no dependents. 🧍‍♂️  
4. **Phone Services:** Neither phone service nor multi-lines significantly impact churn. 📞  
5. **Internet & Add-ons:** **Fiber Optic** and dissatisfaction with **Streaming TV/Movies** drive churn. 🌐
6. **Churn Reasons:** **Competitors (37.5%)** lead causes, followed by **customer experience (32.8%)**. 🤝  
7. **High-Risk Customers:** Streaming and competition remain top drivers for <1-year tenure churners. ⚡  

## 🤖 Modelling

**Feature Engineering:**  Labeled Encoding, Log transformation, Z-score Standarisation

**Pipeline:** Applied the SMOTE oversampling method and K-fold Cross Validation at the Same Time

**Hyper Tuning:** Implement Grid-search to find the best parameters of the predictive model

**Prediction:** the Churn Probabilities on whole dataset

## ✅ Evaluation

### Confustion Metrix Evaluation

- **Class 0 (Non-Churners):** High precision (0.91) and good F1-score (0.83), though recall is slightly lower (0.77).
- **Class 1 (Churners):** Strong recall (0.78) ensures most churners are identified, but lower precision (0.55) indicates many false positives.
- **Overall:** Accuracy is 0.77, with a weighted F1-score of 0.78, balancing the class imbalance well.

### ROC Evaluation

The Area Under the Curve (AUC) of **0.85** (**well above threshold of 0.5**), confirms that the model has a strong ability to differentiate between classes. It's a sign that the model is well-calibrated for predicting churn probabilities.