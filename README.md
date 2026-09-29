# Customer Loyalty & Segmentation Analysis

## Overview

This project analyses customer behaviour within a multi-merchant loyalty program to understand how customers differ in spending, engagement, redemption behaviour and retention.

The analysis combines customer-level feature engineering, descriptive analysis, customer segmentation using K-means clustering, merchant engagement analysis and churn analysis.

The broader goal was to identify meaningful customer groups and understand how engagement across multiple merchants relates to customer value and loyalty.

---

## Business Questions

The analysis focused on questions such as:

- How do customers differ in terms of spending and engagement?
- Can customers be grouped into meaningful behavioural segments?
- How does customer value vary across those segments?
- Are customers who shop across multiple merchants more likely to remain active?
- How are loyalty points earned and redeemed across different merchants?
- Are there imbalances within the loyalty program that may affect long-term sustainability?

---

## Dataset

The project uses data from a loyalty program involving three merchant categories:

- Fast Food
- Grocery
- Petrol

The dataset contains customer information, purchase transactions and loyalty-point redemption records.

The original dataset is not included in this repository.

---

## Analysis Workflow

### 1. Data Preparation

Customer, purchase and redemption data were combined to create a customer-level analytical dataset.

Features created included:

- Total number of purchases
- Total amount spent
- Number of unique merchants used
- Customer activity duration
- Total redemptions
- Total points redeemed
- Average transaction value
- Spend by merchant category
- Number of purchases by merchant category

Skewed numerical variables were transformed using `log1p()` and the clustering features were standardised before modelling.

---

## 2. Customer Segmentation

K-means clustering was used to identify groups of customers with similar behaviour.

The elbow method was used to explore an appropriate number of clusters, and a three-cluster solution was selected.

The resulting segments were interpreted as:

### Low-Engagement At-Risk

Customers with relatively low levels of activity, spending and loyalty-program engagement.

### Moderate-Value Single-Merchant

Customers with moderate levels of value and activity, but whose engagement is concentrated around fewer merchants.

### High-Value Multi-Merchant Loyal

Highly engaged customers who interact with multiple merchants and demonstrate stronger overall customer value and loyalty behaviour.

The clusters were profiled using spending, purchase frequency, merchant diversity, redemption activity, satisfaction, Net Promoter Score and churn behaviour.

---

## 3. Merchant Engagement

The project also examined how customer behaviour changes depending on the number of merchants used.

Customers who participated across more merchants showed substantially higher levels of activity and spending.

Average total spend increased from approximately:

- **$708** for customers using one merchant
- **$1,551** for customers using two merchants
- **$4,135** for customers using all three merchants

Multi-merchant customers also completed more transactions and showed higher levels of program satisfaction and Net Promoter Score. :chatgpt-content-reference{index="0"}

---

## 4. Customer Retention

Merchant engagement was also associated with customer retention.

Retention rates were:

- **66.5%** for customers using one merchant
- **85.7%** for customers using two merchants
- **87.5%** for customers using all three merchants

A Chi-Square test found a statistically significant relationship between merchant diversity and customer retention:

**χ² = 167.23, p < 0.001**

This suggests that customers engaging with multiple merchants were significantly more likely to remain active in the loyalty program. :chatgpt-content-reference{index="1"}

---

## 5. Loyalty Point Imbalance

The analysis identified a notable imbalance in how loyalty points were earned and redeemed across merchants.

Grocery and Petrol together generated more than **93% of all points issued**, while Fast Food generated only **6.37%**.

However, Fast Food accounted for approximately **65% of all points redeemed**.

Grocery acted almost entirely as a points-earning merchant, with no recorded point redemptions in the analysed data. :chatgpt-content-reference{index="2"}

This suggests that customers were earning points primarily through everyday purchases such as groceries and fuel, while redeeming a large proportion of those points through Fast Food.

---

## 6. Churn Modelling

Two logistic regression approaches were explored to better understand customer churn.

The first model focused mainly on merchant-engagement variables and achieved an AUC of approximately **0.634**.

A broader model combining merchant engagement with satisfaction and Net Promoter Score achieved an AUC of approximately **0.889**.

This indicated that merchant diversity alone was not enough to explain retention. Customer satisfaction also played an important role in understanding churn behaviour. :chatgpt-content-reference{index="3"}

---

## Key Findings

The analysis highlighted several important patterns:

- Customers using multiple merchants were substantially more valuable than single-merchant customers.
- Multi-merchant customers had higher spending, transaction frequency and retention.
- Merchant diversity and customer retention were statistically related.
- High-value customers tended to interact with a broader part of the loyalty ecosystem.
- The loyalty-point system was uneven across merchants, with Grocery and Petrol acting primarily as point generators while Fast Food captured a large share of redemptions.
- Customer engagement alone did not fully explain churn; satisfaction and advocacy measures added substantial predictive value.

---

## Customer Segmentation Features

The K-means model used customer-level behavioural features including:

- Total purchases
- Total spend
- Unique merchants used
- Days active
- Total redemptions
- Total points redeemed
- Average transaction value
- Fast Food spend and purchases
- Grocery spend and purchases
- Petrol spend and purchases

---

## Technologies

- R
- tidyverse
- dplyr
- ggplot2
- readxl
- cluster
- K-means clustering
- Logistic regression
- Statistical testing
- Customer segmentation

---

## Repository Structure

```text
loyalty-program-customer-analysis/
│
├── README.md
│
├── analysis/
│   └── Cluster_Analysis.Rmd
│
├── data/
│   └── README.md
│
└── images/
```
## Running the Analysis
The analysis was developed in R using an R Markdown workflow.
Required libraries include:
```text
library(tidyverse)
library(readxl)
library(knitr)
library(cluster)
```
## Project Context
This analysis was completed as part of an academic group project.
This repository focuses on the analytical work, including customer-level feature engineering, clustering, customer profiling, merchant engagement and churn analysis.
## Author
Pranav Ghatigar
Data Analyst · Data Engineer
