# SQL/Tableau Project

Welcome to my collection of SQL-Tableau projects, showcasing my skills in data analysis, database management, and data visualization. These projects aim deriving actionable insights from Consumer Spending Patterns dataset , employing SQL for data exploration and Tableau for creating interactive visualizations.

Feel free to navigate through the project listed below,  providing a unique perspective on data-driven decision-making.

<h1 align="center">Consumer Spending Patterns - Data Analysis using Tableau & SQL </h1>

## Introduction
This project aims to analyze consumer spending habits across various categories and items for the years 2023 and 2024. By examining trends, identifying high-value customers and items, and proposing actionable strategies, businesses can optimize marketing efforts and drive revenue growth.

---
## Table of Contents
1. [Introduction](#introduction)
2. [Project Scope and Dataset Overview](#project-scope-and-dataset-overview)
3. [Project Planning](#project-planning)
4. [Spending Analysis Using MySQL](#spending-analysis-using-mysql)
5. [Data Analysis Using Tableau ](#data-analysis-using-tableau)
6. [Insights and Recommendations](#insights-and-recommendations)
7. [Fitness and Medical Insights and Strategic Applications](#fitness-and-medical-insights-and-strategic-applications)
8. [Summary and Future Scope](#summary-and-future-scope)
9. [Key Learnings](#key-learnings)
10. [Contact Information](#contact-information)

---

## Project Scope and Dataset Overview
- ### Data Source: [Visit Kaggle Spending Habits Dataset](https://www.kaggle.com/datasets/ahmedmohamed2003/spending-habits)

- ### Dataset Highlights:
  - 13 categories and 48 items
  - 10,000 transactions for 200 unique customers
  - Analysis filtered for years 2023 and 2024

### About Project 👨‍💻

- Analyzing consumer spending data across various categories to uncover trends and patterns.
- By analyzing this data, businesses can identify emerging trends, keep up with customer needs, and make smart choices to grow and stay competitive.
- Used Microsoft Excel and MySQL for data extraction, transformation, and loading.
- Created an interactive Tableau dashboard showcasing spending patterns and valuable insights.
- Provided recommendations for strategic applications based on trends.


### Technologies used ⚙️
* Tableau for visualization
* SQL/MySQL for data analysis
* Advanced Excel


### Problem Statements
- Q1. Which spending category contributes the most to total expenditures, and why? 

- Q2. Are there any high-value items that drive a significant portion of revenue despite low purchase frequency?

- Q3. Which is low-engagement category ? What strategies can be recommended to increase spending ?​

- Q4. Who are the top 10 customers based on total spending, and what are their preferred categories?​
  
- Q5. Is there a correlation between spending on fitness and healthcare costs? ​
  

## Project Planning 
  
#### 1. Purpose: What? Why? What do we want to achieve?
Unlock deeper insights into consumer spending patterns, automate reporting, and enhance strategic decision-making.

#### 2. Stake Holders: Who will be involved?
- Business Managers
- Marketing Teams
- Data Analysts
- Product Developers

#### 3. End Result: What do we want to achieve?
- Interactive dashboards reduce manual effort, enable data-driven decisions, and deliver measurable cost savings.

#### 4. Success Criteria: What will be our success criteria?
- Dashboards uncovering sales insights with latest data available.
- Sales team able to take better decision & prove 10% cost savings of total spend.
- Sales analysts stop data gathering manually in order to save 20% of their business time & reinvest it in value added activity.

### Setup Process 🔍
  
Step 1: Download file: <code>[spending_patterns_detailed.sql]()</code> or <code>[spending_patterns_detailed.xlsx]()</code>

Step 2: Import it in MySql do ETL(Extract, Transform, Load) if required

Step 3: Download [Tableau Public](https://www.tableau.com/products/public/download) (Free) or [Tableau Desktop](https://www.tableau.com/products/desktop/download) (14 days trial) to perform Data Analysis
  
Step 4: Connect Tableau with MySql database or Excel database
  
Step 5: Save the file as (.twb or .twbx)

## Spending Analysis Using MySQL

---

### 1. Total Expenditure by Each Spending Category
```sql
SELECT category, SUM(total_spent) AS total_expenditure
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY category
ORDER BY total_expenditure DESC;
```
**Purpose:** Identify the spending categories contributing the most during the selected years.

---

### 2. High-Value Items with Low Purchase Frequency
```sql
SELECT item, COUNT(*) AS purchase_frequency, SUM(total_spent) AS revenue
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY item
ORDER BY revenue DESC, purchase_frequency ASC
LIMIT 10;
```
**Purpose:** Highlight items driving significant revenue despite fewer transactions in 2023 and 2024.

---

### 3. Top 10 Customers Based on Spending
```sql
SELECT customer_id, SUM(total_spent) AS total_spending
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY customer_id
ORDER BY total_spending DESC
LIMIT 10;
```
**Purpose:** Identify the top 10 customers by total spending during these years, along with their preferred spending categories.

---

### 4. Correlation Between Fitness and Medical Expenses
```sql
SELECT customer_id,
       SUM(CASE WHEN category = 'Fitness' THEN total_spent ELSE 0 END) AS fitness_spending,
       SUM(CASE WHEN category IN ('Medical/Dental') THEN total_spent ELSE 0 END) AS medical_spending
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY customer_id
ORDER BY fitness_spending DESC;
```
**Purpose:** Analyze spending on fitness and healthcare costs for individual customers during these years.

---

### 5. Identify Low-Engagement Categories
```sql
SELECT category, SUM(quantity) AS quantity_sold, SUM(total_spent) AS total_revenue
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY category
ORDER BY quantity_sold ASC, total_revenue ASC
LIMIT 5;
```
**Purpose:** Identify the least engaged categories based on quantity count and revenue during 2023 and 2024.

---

### 6. Frequently Purchased Items
```sql
SELECT item, SUM(quantity) AS quantity_sold, SUM(total_spent) AS total_revenue
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY item
ORDER BY quantity_sold DESC
LIMIT 10;
```
**Purpose:** List the most frequently purchased items during these years.

---

### 7. Customer Segmentation
**High Spenders:**
```sql
SELECT customer_id, SUM(total_spent) AS total_spending
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY customer_id
ORDER BY total_spending DESC
LIMIT 50;
```
**Insights:** These customers contribute a significant portion of revenue. Focus marketing efforts with exclusive offers, tiered loyalty programs, and personalized services.

**Habitual Buyers:**
```sql
SELECT customer_id, COUNT(*) AS transaction_count
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY customer_id
ORDER BY transaction_count DESC
LIMIT 50;
```
**Insights:** These customers are highly engaged and may be more loyal. Retain them with consistent rewards, discounts, and targeted promotions.

---

### 8. Spending by Month
```sql
SELECT MONTH(transaction_date) AS month, YEAR(transaction_date), SUM(total_spent) AS total_revenue
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY MONTH(transaction_date), YEAR(transaction_date)
ORDER BY YEAR(transaction_date), MONTH(transaction_date);
```
**Purpose:** Analyze spending trends across months in the selected years.

**Comparing side-by-side:**
```sql
SELECT 
    MONTH(transaction_date) AS Month,
    SUM(CASE WHEN YEAR(transaction_date) = 2023 THEN total_spent ELSE 0 END) AS total_revenue_2023,
    SUM(CASE WHEN YEAR(transaction_date) = 2024 THEN total_spent ELSE 0 END) AS total_revenue_2024
FROM spending_details
WHERE YEAR(transaction_date) IN (2023, 2024)
GROUP BY Month
ORDER BY Month;
```
**Purpose:** Compare monthly spending side by side for 2023 and 2024.

---

## Data Analysis Using Tableau 
### Tableau Public Dashboards: [Consumer Spending Patterns](https://public.tableau.com/views/ConsumerSpendingPatterns-DataAnalysisusingTableauDashboard_project/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) 🔗


- **Dashboard 1:** [Understanding consumer spending pattern across different categories and items](https://public.tableau.com/views/ConsumerSpendingPatterns-DataAnalysisusingTableauDashboard_project/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

- <p  align="center"><a href="https://public.tableau.com/views/ConsumerSpendingPatterns-DataAnalysisusingTableauDashboard_project/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link"><img width="100%" src="https://github.com/MitalKasturiwale/DataAnalysis_Sql_Tableau/blob/main/Images/Spending_pattern_Dashboard1.png?raw=true" /></a></p>

- **Dashboard2:**[Is there a correlation between spending on fitness and healthcare costs?](https://public.tableau.com/views/ConsumerSpendingPatterns-DataAnalysisusingTableauDashboard_project/Dashboard2?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

- <p  align="center"><a href="https://public.tableau.com/views/ConsumerSpendingPatterns-DataAnalysisusingTableauDashboard_project/Dashboard2?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link"><img width="100%" src="https://github.com/MitalKasturiwale/DataAnalysis_Sql_Tableau/blob/main/Images/Spending_pattern_Dashboard2.png?raw=true" /></a></p>

---

## Insights and Recommendations


### Key Insights:
- **Shopping** emerges as the dominant spending category, followed by Housing and Fitness.  
- High-value items like cars contribute significantly to revenue, despite lower purchase frequency.  
- Frequent purchases in categories like dining or personal hygiene suggest habitual spending behavior.
- Fitness vs. Medical Costs:Importance of promoting fitness as a strategy for long-term health savings and 
highlight the potential for businesses to capitalize on this trend by encouraging preventive health measures.
- Categories like subscriptions show low engagement but present opportunities for recurring revenue through strategic incentives like free trials or bundles.
  
### Recommendations:
1. **High-Spending Categories:** Introduce loyalty programs with tiered rewards.  
2. **Low-Engagement Categories to Increase Spending:** Offer free trials, annual plan discounts, and referral incentives to drive adoption.  
3. **Retention Strategies:** Focus on high-value customers with personalized offers and exclusive benefits.
4. **Promote Bundled Offers:** Combine low-engagement categories with high-demand items to create appealing bundles.Highlight the value of bundled deals to drive spending across multiple categories.

 ## **Fitness and Medical Insights** and **Strategic Applications** 

 ### **Fitness and Medical Insights**
- **Preventive Health Benefits**: Customers investing in fitness activities, such as personal trainers, yoga classes, and gym memberships, tend to have lower healthcare expenses. This highlights the positive impact of preventive health measures.
- **Spending Trends**:
  - **Workout Equipment** dominates fitness spending, reflecting a preference for high-value, one-time investments.
  - Medical costs, such as doctor visits and medicines, tend to be recurring and higher for customers with minimal fitness spending.
- **Correlation**: An inverse relationship exists between fitness spending and medical expenses, emphasizing the cost-saving potential of regular fitness investments.

### **Strategic Applications**
1. **Preventive Health Campaigns**:
   - Promote bundled packages (e.g., gym memberships + discounted health check-ups) to encourage fitness adoption and healthcare cost savings.

2. **Subscription Models**:
   - Offer affordable fitness subscriptions, including online classes, guided meditation sessions, or personalized coaching.

3. **Loyalty Programs**:
   - Reward recurring fitness spending with exclusive benefits like discounts on wellness products or free health consultations.

4. **Targeted Marketing**:
   - Focus personalized campaigns on customers with low fitness engagement to drive adoption. Offer trials, referral programs, or fitness equipment promotions.

5. **Corporate Collaborations**:
   - Partner with healthcare providers to offer combined fitness and wellness solutions (e.g., free fitness classes with medical insurance).


## Summary and Future Scope

- The analysis provides actionable insights into customer behaviors, which can be leveraged for personalized marketing and strategy building.
- Future improvements include seasonal trend analysis to identify spikes and shifts in consumer habits.

### Future Plans for Personalized Marketing

- Targeted Campaigns: Analyze spending patterns based on age, location, and income levels.
- Seasonal Trends: Explore spikes in categories during holidays or special events.
- Loyalty Programs: Develop tailored rewards for high-value customers and habitual buyers.

 ## Key Learnings
- Understanding consumer behavior drives long-term success.
- Seasonal trends and preventive health spending offer new avenues for growth.
- High-value customers are crucial for sustained revenue generation.
   
## Contact Information
- **Author: Mital Kasturiwale**
  
### Liked my Contributions :Question: [Follow Me](https://github.com/MitalKasturiwale):Point_right: [Nominate Me for GitHub Stars](https://stars.github.com/nominate/) :star: :sparkles:






