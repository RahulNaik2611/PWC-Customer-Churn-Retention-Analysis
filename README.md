# PWC-Customer-Churn-Retention-Analysis



📌 Table of Contents
Problem Statement
Datasource
Data Preparation
Data Modeling
Data Analysis (DAX)
Data Visualization (Dashboard)
Insights
Recommendations
📊 Problem Statement
🔹 The purpose of this analysis is to:

✅ Define key KPIs 📈

✅ Create a dashboard for the Retention Manager 👨‍💼
✅ Provide recommendations for reducing customer churn 🛑
🔹 Key Data Points:

📌 Customer Churn Trends (Who left last month?)
📌 Services Subscribed (Phone, Internet, Security, etc.)
📌 Account Details (Tenure, Contract Type, Payment Method, Charges, Tickets)
📌 Demographics (Gender, Age, Dependents, Partners)
📂 Datasource
📍 The dataset used for this analysis is the PwC Customer Churn Retention dataset.

📌 Dataset Name: Customer Churn Retention
📌 Rows: 7,043 observations
📌 Columns: 23
🛠 Data Preparation
✔ Data Cleaning & Transformation:

🔹 Replaced values in SeniorCitizen: "N" → "No", "Y" → "Yes"
🔹 Created a Loyalty Category (<1 year, <2 years, <3 years, etc.)
🔹 Removed unnecessary columns & rows
🔹 Ensured correct data types
✔ Loyalty Categorization (M-Formula):
    loyalty = SWITCH(TRUE(),
        '01 Churn-Dataset'[tenure] <= 12, "< 1 year",
        '01 Churn-Dataset'[tenure] <= 24, "< 2 years",
        '01 Churn-Dataset'[tenure] <= 36, "< 3 years",
        '01 Churn-Dataset'[tenure] <= 48, "< 4 years",
        '01 Churn-Dataset'[tenure] <= 60, "< 5 years",
        '01 Churn-Dataset'[tenure] <= 72, "< 6 years"
)
📐 Data Modeling
📊 The dataset was cleaned and structured into tables for analysis & visualization.

📊 Data Analysis (DAX)
    Key DAX Measures:
    Average MonthlyCharges = AVERAGE('01 Churn-Dataset'[MonthlyCharges])
    Average TotalCharges = AVERAGE('01 Churn-Dataset'[TotalCharges])
    Churn Count = CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "Yes")
    Churn Rate % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "Yes"), COUNT('01 Churn-Dataset'[Churn]), 0)

📌 Additional measures calculated for:
✔ Dependent Customers
✔ Device Protection
✔ Online Backup & Security
✔ Phone Services
✔ Senior Citizens & Streaming Services

📊 Data Visualization (Dashboard)
📌 Dashboard Views:
✔ Customer Churn Analysis
✔ Customer Risk Assessment
✔ Service Subscription Overview

📸 Screenshots of the Dashboard:
## 📊 **Data Visualization (Dashboard)**  
📌 **Dashboard Views:**  
✔ **Customer Churn Analysis**  
✔ **Customer Risk Assessment**  
✔ **Service Subscription Overview**  

📸 **Screenshots of the Dashboard**:  

| Dashboard Section | Screenshot |
|-------------------|------------|
| **Customer Churn** | [![Customer Churn](https://github.com/RahulNaik2611/PWC-Customer-Churn-Retention-Analysis/blob/d6eafeea46aa632436ead3a5818da3b534283fbf/PowerBi_DashBoard/Screenshot/CustomerChurn.png)](https://github.com/RahulNaik2611/PWC-Customer-Churn-Retention-Analysis/blob/main/PowerBi_DashBoard/Screenshot/CustomerChurn.png) |
| **Customer Risk** | [![Customer Risk](https://github.com/RahulNaik2611/PWC-Customer-Churn-Retention-Analysis/blob/d6eafeea46aa632436ead3a5818da3b534283fbf/PowerBi_DashBoard/Screenshot/customer%20Risk.png)](https://github.com/RahulNaik2611/PWC-Customer-Churn-Retention-Analysis/blob/main/PowerBi_DashBoard/Screenshot/customer%20Risk.png) |
| **Services Analysis** | [![Services](https://github.com/RahulNaik2611/PWC-Customer-Churn-Retention-Analysis/blob/d6eafeea46aa632436ead3a5818da3b534283fbf/PowerBi_DashBoard/Screenshot/Services.png)](https://github.com/RahulNaik2611/PWC-Customer-Churn-Retention-Analysis/blob/main/PowerBi_DashBoard/Screenshot/Services.png) |
| **Insights Summary** | [![Insights](https://github.com/RahulNaik2611/PWC-Customer-Churn-Retention-Analysis/blob/d6eafeea46aa632436ead3a5818da3b534283fbf/PowerBi_DashBoard/Screenshot/insights.png)](https://github.com/RahulNaik2611/PWC-Customer-Churn-Retention-Analysis/blob/main/PowerBi_DashBoard/Screenshot/insights.png) |


Dashboard Section	Screenshot
Customer Churn	
Customer Risk	
Services Analysis	
Insights Summary	
🔍 Insights
🔹 Customers on Two-Year contracts stay longer 📅, while Month-to-Month customers are at higher risk of churn ⚠️.
🔹 7,043 customers are at risk, with a 27% churn rate 📉.
🔹 Financial Impact: 📉 $16.06M lost annually & $456.12K lost monthly.
🔹 Service Issues: 📌 42% of churned customers used Fiber Optic Internet 🚀.
🔹 Support Issues: ❌ Most churned customers did not subscribe to Online Security, Tech Support, or Phone Services.

🎯 Recommendations
✅ Encourage Month-to-Month customers to switch to One-Year or Two-Year contracts with incentives.
✅ Educate customers on the importance of Online Security & Tech Support to improve retention.
✅ Enhance Fiber Optic service quality to reduce churn among users.
✅ Increase One-Year & Two-Year contract sales by 5% 📊.
✅ Increase auto-payments by 5% annually 💳.
✅ Offer discounts & retention incentives to high-risk customers 🎁.

