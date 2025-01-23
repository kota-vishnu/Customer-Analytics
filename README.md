# Customer Analytics & Pricing Optimization

## Project Overview
This project analyzes customer transactions to extract business insights using data analytics and machine learning. The main objectives include customer segmentation, churn prediction, anomaly detection, and pricing optimization.

### Problem Statement
Businesses need to understand **customer purchasing behavior** to improve **retention, pricing strategies, and fraud detection**. This project applies **data science and machine learning techniques** to analyze historical transaction data and extract actionable insights.

## Key Features
- **Customer Segmentation**: Applied RFM analysis and clustering to classify customers into high-value, frequent, and inactive segments.
- **Churn Prediction**: Implemented **machine learning models** to identify customers at risk of leaving.
- **Anomaly Detection**: Detected fraudulent transactions using **Local Outlier Factor (LOF)** and Isolation Forest.
- **Market Basket Analysis**: Identified frequently co-purchased products to optimize **cross-selling strategies**.
- **Price Elasticity Modeling**: Analyzed pricing sensitivity to **optimize dynamic pricing strategies**.

## Data Description
- **Customers Data**: Includes `CustomerID`, `CustomerName`, `Region`, `SignupDate`.
  - **Example:** `C0001 - Lawrence Carroll - South America - 2022-07-10`
  - **Key Insight**: Customers from **Asia and South America** dominate new signups.

- **Transactions Data**: Includes `TransactionID`, `CustomerID`, `ProductID`, `TransactionDate`, `Quantity`, `TotalValue`, `Price`.
  - **Example:** `T00001 - C0199 - P067 - 2024-08-25 12:38:23 - 1 - $300.68`
  - **Key Insight**: High sales volume in **Q2 and Q3 of the year**.

- **Products Data**: Includes `ProductID`, `ProductName`, `Category`, `Price`.
  - **Example:** `P001 - ActiveWear Biography - Books - $169.30`
  - **Key Insight**: **Electronics and Clothing contribute to the highest revenue.**

## Findings from Data Cleaning
- **No Missing Values** → Data is complete and reliable.
- **No Duplicates** → Ensures consistency across datasets.
- **Date Formatting** → Converted `SignupDate` and `TransactionDate` to datetime format.

## Exploratory Data Analysis (EDA)
- **Customer Signup Trends**: Peak signups in **March and October**.
- **Monthly Sales Trend**: High sales recorded in **August and April**.
- **Top-Selling Products**: `P067` (**$300.68 per unit**) dominates sales.
- **Revenue by Region**: **Europe and South America** lead revenue generation.

## Business Insights from EDA
### Customer Segmentation (RFM Clustering)
| Cluster | Description | Avg Spend ($) | Frequency |
|---------|------------|---------------|------------|
| **1** | High-Value Customers | 5,354.88 | 8 |
| **2** | Occasional Shoppers | 2,034.24 | 3 |
| **3** | At-Risk Customers | 931.83 | 2 |

### Churn Prediction Model Performance
#### **XGBoost Model**
| Metric         | Class 0 | Class 1 | Macro Avg | Weighted Avg |
|---------------|---------|---------|-----------|--------------|
| Precision     | 97.37%  | 100.00% | 98.68%    | 97.57%       |
| Recall        | 100.00% | 66.67%  | 83.33%    | 97.50%       |
| F1-Score      | 98.67%  | 80.00%  | 89.33%    | 97.27%       |
| Accuracy      | -       | -       | -         | 97.50%       |

#### **Random Forest Model**
| Metric         | Class 0 | Class 1 | Macro Avg | Weighted Avg |
|---------------|---------|---------|-----------|--------------|
| Precision     | 100.00% | 100.00% | 100.00%   | 100.00%      |
| Recall        | 100.00% | 100.00% | 100.00%   | 100.00%      |
| F1-Score      | 100.00% | 100.00% | 100.00%   | 100.00%      |
| Accuracy      | -       | -       | -         | 100.00%      |

**Key Takeaway**:
- **Random Forest achieved 100% accuracy**, indicating possible overfitting due to dataset size.
- **XGBoost performed well (97.5% accuracy) but struggled with Class 1 recall (66.67%)**, meaning **some churned customers were not identified correctly**.
- **Random Forest may require further validation on a larger dataset.**

- ## Business Impact
- **Customer Retention** → Data-driven strategies improve engagement and retention.
- **Fraud Prevention** → AI-driven anomaly detection enhances transaction security.
- **Dynamic Pricing** → Optimized price sensitivity models increase revenue.
- **Personalized Marketing** → Market basket analysis helps refine product recommendations.
