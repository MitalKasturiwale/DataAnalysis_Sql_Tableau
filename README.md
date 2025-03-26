# SQL/Tableau Project

Welcome to my collection of SQL-Tableau projects, showcasing my skills in data analysis, database management, and data visualization. These projects, developed for school, work, or personal exploration, cover a range of topics like deriving actionable insights from Consumer Spending Patterns dataset , employing SQL for data exploration and Tableau for creating interactive visualizations.

Feel free to navigate through the project listed below,  providing a unique perspective on data-driven decision-making.



<h1 align="center">Consumer Spending Patterns - Data Analysis using Tableau & SQL </h1>

**I am sharing insights from Market Trend Analysis, exploring Consumer Spending Patterns - A Data Analysis Project performed on Tableau & SQL in my journey into Data Analytics.** 


### About Project 👨‍💻

- Analyzing consumer spending data across various categories to uncover trends and patterns.
- By analyzing this data, businesses can identify emerging trends, keep up with customer needs, and make smart 
  choices to grow and stay competitive.
- Used Microsoft Excel and MySQL for data extraction, transformation, and loading.
- Created an interactive Tableau dashboard showcasing spending patterns and valuable insights.
- Provided recommendations for strategic applications based on trends.


## Technologies used ⚙️
* Tableau
* SQL/MySQL
* Advanced Excel


## Project - Consumer Spending Patterns - Sales Insights  

### Problem Statements
Company executives needs to know spending pattern and category among the users in USA with different age groups.

- Q1. Which spending category contributes the most to total expenditures, and why? 

- Q2. Are there any high-value items that drive a significant portion of revenue despite low purchase frequency?

- Q3. Identify the **Top 10 customers** based on total spending and their preferences.

- Q4. Correlation between spending on fitness activities and healthcare costs.
  
- Q5. Recommendations for low-engagement categories.  Which is low-engagement category ? What strategies can be        recommended to increase spending?


## Project Planning 🚀
  
#### 1. Purpose: What? Why? What do we want to achieve?
Unlock deeper insights into consumer spending patterns, automate reporting, and enhance strategic decision-making.

#### 2. Stake Holders: Who will be involved?
- Business managers
- marketing teams
- data analysts
- product developers

#### 3. End Result: What do we want to achieve?
Interactive dashboards reduce manual effort, enable data-driven decisions, and deliver measurable cost savings.

#### 4. Success Criteria: What will be our success criteria?
- Dashboards uncovering sales insights with latest data available.
- Sales team able to take better decision & prove 10% cost savings of total spend.
- Sales analysts stop data gathering manually in order to save 20% of their business time & reinvest it in value added activity.

### Data Analysis - Approach
<p  align="center"><a href="https://github.com/mrankitgupta"><img width="80%" src="https://github.com/mrankitgupta/Sales-Insights-Data-Analysis-using-Tableau-and-SQL/blob/main/images/flow.jpg" /></a></p>

## Data Analysis Process 🔍

### **Setup**:
1. Import dataset into MySQL for ETL.  
2. Download and install [Tableau Public](https://www.tableau.com/products/public/download) or Tableau Desktop for analysis.  
3. Perform data analysis, filtering transactions by years 2023 and 2024.  
4. Visualize insights with Tableau dashboards.  

---

## Tableau Dashboards 📊

- **Category Analysis**: Spending distribution across categories like Shopping, Fitness, Housing, etc.
- **Top Customers**: High-value customer behaviors and their impact.
- **Relation**: Spending on fitness activities and healthcare costs.
- **Recommendations**: Strategies to boost engagement and revenue.

### [View Dashboard](https://public.tableau.com/views/your-dashboard-link-here) 🔗

---

## Insights and Recommendations 📜

### Key Insights:
- **Shopping** emerges as the dominant spending category, followed by Housing and Fitness.  
- High-value items like cars contribute significantly to revenue, despite lower purchase frequency.  
- Frequent purchases in categories like dining or personal hygiene suggest habitual spending behavior.
- Fitness vs. Medical Costs:Importance of promoting fitness as a strategy for long-term health savings and 
  highlight the potential for businesses to capitalize on this trend by encouraging preventive health measures.
- Categories like subscriptions show low engagement but present opportunities for recurring revenue through   
  strategic incentives like free trials or bundles.

### Recommendations:
1. **High-Spending Categories:** Introduce loyalty programs with tiered rewards.  
2. **Low-Engagement Categories:** Offer free trials, annual plan discounts, and referral incentives to drive adoption.  
3. **Retention Strategies:** Focus on high-value customers with personalized offers and exclusive benefits.
4. **Opportunity for Combined Strategies:** Businesses can promote bundles such as gym memberships paired with discounted health check-ups or fitness equipment with free personal training sessions to encourage both fitness adoption and medical cost reduction.

 ### **Fitness and Medical Insights** and **Strategic Applications** 

 **Fitness and Medical Insights**
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



(
### Setup Process
  
Step 1: Download file: <code>[db_dump.sql](https://github.com/mrankitgupta/Sales-Insights-Data-Analysis-using-Tableau-and-SQL/blob/main/Databases/db_dump.sql)</code> or <code>[db_dump.xlsx](https://github.com/mrankitgupta/Sales-Insights-Data-Analysis-using-Tableau-and-SQL/blob/main/Databases/db_dump.xlsx)</code>

Step 2: Import it in MySql do ETL(Extract, Transform, Load) if required

Step 3: Download [Tableau Public](https://www.tableau.com/products/public/download) (Free) or [Tableau Desktop](https://www.tableau.com/products/desktop/download) (14 days trial) to perform Data Analysis
  
Step 4: Connect Tableau with MySql database or Excel database
  
Step 5: Save the file as (.twb or .twbx)

  
## Data Analysis Using SQL
  
1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001)

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai.

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars.

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table.

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020and transactions.market_code="Mark001";`


## Data Analysis Using Tableau 
  
### Tableau Public Dashboards: [Revenue & Profit Analysis](https://public.tableau.com/views/SalesInsights-DataAnalysisProject/Dashboard-RevenueAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link)  <a href="https://public.tableau.com/views/SalesInsights-DataAnalysisProject/Dashboard-RevenueAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/mrankitgupta/mrankitgupta/a768d6bf0a001f03327578ae12f8867e4056cbaf/tableau-software.svg" alt="tableau" width="40" height="20"/> </a>

#### Creating Star Schema in Tableau
	
<p  align="center"><a href="https://public.tableau.com/app/profile/mrankitgupta"><img width="80%" src="https://github.com/mrankitgupta/Sales-Insights-Data-Analysis-using-Tableau-and-SQL/blob/main/images/Star%20Schema.png" /></a></p>

#### Tableau Dashboard - [Revenue Analysis](https://public.tableau.com/views/SalesInsights-DataAnalysisProject/Dashboard-RevenueAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link)
	
<p  align="center"><a href="https://public.tableau.com/views/SalesInsights-DataAnalysisProject/Dashboard-RevenueAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link"><img width="100%" src="https://github.com/mrankitgupta/Sales-Insights-Data-Analysis-using-Tableau-and-SQL/blob/main/images/Tableau%20Dashbpard%20Revenue%20Analysis.png" /></a></p>

#### Tableau Dashboard - [Profit Analysis](https://public.tableau.com/views/SalesInsights-DataAnalysisProject/Dashboard-ProfitAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link)
	
<p  align="center"><a href="https://public.tableau.com/views/SalesInsights-DataAnalysisProject/Dashboard-ProfitAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link"><img width="100%" src="https://github.com/mrankitgupta/Sales-Insights-Data-Analysis-using-Tableau-and-SQL/blob/main/images/Tableau%20Dashbpard%20Profit%20Analysis.png" /></a></p>
  
## Project References: 🔗

|**Sr.No. 🔢**|**References 👨‍💻**| **Links :link:**|
|------|--------------------|---------------------|
|1| **Tableau Project Dashboard :** Sales Insights - Data Analysis using Tableau | [Dashboard](https://public.tableau.com/views/SalesInsights-DataAnalysisProject/Dashboard-RevenueAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link)|
|2| **Tableau Public Profile** | [Tableau Public Dashboard](https://public.tableau.com/app/profile/mrankitgupta) |
|3| Tutorial | [YouTube 1](https://www.youtube.com/playlist?list=PLeo1K3hjS3utcb9nKtanhcn8jd2E0Hp9b) | 
|4| MySQL installation | [YouTube 2](https://www.youtube.com/watch?v=WuBcTJnIuzo) |
|5| OLTP & OLAP | [Geeks for Geeks](https://www.geeksforgeeks.org/difference-between-olap-and-oltp-in-dbms/) | 
|6| Star Schema: Fact Table & Dimension Table | [Microsoft docs.](https://docs.microsoft.com/en-us/power-bi/guidance/star-schema) | 
  
## Related Projects:question: 👨‍💻 🛰️

<code>[Spotify Data Analysis using Python](https://github.com/mrankitgupta/Spotify-Data-Analysis-using-Python)</code> 📊

<code>[Statistics for Data Science using Python](https://github.com/mrankitgupta/Statistics-for-Data-Science-using-Python)</code> 📊
 
<code>[Python Lessons](https://github.com/mrankitgupta/PythonLessons)</code> 📑

<code>[Python Libraries for Data Science](https://github.com/mrankitgupta/PythonLibraries)</code> 🗂️
  
  
### Liked my Contributions:question:[Follow Me](https://github.com/mrankitgupta/):point_right: [Nominate Me for GitHub Stars](https://stars.github.com/nominate/) :star: :sparkles:

## For any queries/doubts 🔗 👇 

### [Ankit Gupta](https://bio.link/AnkitGupta)
<p align="left"> <a href="https://twitter.com/MrAnkitGupta_/" target="blank"><img src="https://img.shields.io/twitter/follow/MrAnkitGupta_?logo=twitter&style=for-the-badge" alt="MrAnkitGupta_" /></a> </p>

<a href="https://www.linkedin.com/in/mrankitgupta" target="blank"><img align="center" src="https://img.shields.io/badge/-MrAnkitGupta-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/mrankitgupta/" alt="MrAnkitGupta" height="20" width="100" /></a>
<a href="https://www.instagram.com/MrAnkitGupta_" target="blank"><img align="center" src="https://img.shields.io/badge/-@MrAnkitGupta_-D7008A?style=flat-square&labelColor=D7008A&logo=Instagram&logoColor=white&link=https://www.instagram.com/MrAnkitGupta_" alt="MrAnkitGupta_" height="20" width="110" /></a>
<a href="https://bio.link/AnkitGupta" target="blank"><img align="center" src="https://img.shields.io/badge/website-000000?style=for-the-badge&logo=About.me&logoColor=white&link=https://bio.link/AnkitGupta" alt="AnkitGupta" height="20" width="90" /></a>
<a href="https://github.com/mrankitgupta/" target="blank"><img align="center" src="https://img.shields.io/github/followers/mrankitgupta?label=Follow&style=social&link=https://github.com/mrankitgupta/" alt="MrAnkitGupta" height="20" width="90" /></a>

  
