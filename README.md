# Starbucks-Menu-Portfolio-Optimization-Analysis
A data-driven analysis of the topic: “How should Starbucks optimize its menu mix to maximize revenue while maintaining a balanced product portfolio?”

**!!"Note on Data: Starbucks proprietary transaction data is strictly confidential. To demonstrate the analytical framework, this project utilizes a comparable coffee retail dataset (149k transactions) of Maven Roasters as a realistic proxy. The underlying Python/SQL models are fully transferable to genuine brand data."!!**

## 1. Project Overview / Business Question: 
Hey, before jumping into the project overview, I wanna tell you some secrets: 
- One, I am a coffee lover. 
- Two, I used to manage a coffee shop during high school.
- Three, I purchase drinks at Starbucks every day. 

When I was drinking Starbucks last year, I noticed several menu adjustments, including launching new/seasonal products and discontinuing some others. I am curious about how those menu adjustments are made. In other words, I am very interested in Starbucks’ menu portfolio optimization.

The business question that I want to solve is: **How Should Starbucks Optimize Its Menu Portfolio to Maximize Revenue While Maintaining a Balanced Product Mix?**

I aim to use historical transaction data to provide data-driven insights and recommendations on how the menu portfolio should evolve for the next quarter’s menu adjustments as a Business Analyst. 

The **objective** is not only to identify top-selling beverages, but also to determine:
- Which products should be expanded
- Which products should be maintained
- Which products should be retired
- How marketing resources should be allocated across product categories
- How external factors, such as weather and macroeconomic conditions, influence product performance

To answer these questions, this project builds an integrated analytical dataset by combining Starbucks menu information, transaction records, weather observations, and macroeconomic indicators. Because Starbucks proprietary POS data is not publicly available, synthetic transaction data generated under real-world business constraints is used as a **realistic analytical proxy**.

## 2. Data Architecture: 
///////draft/example

Starbucks Menu
        │
        │ product_name
        ▼
Transactions
        │
        │ city + date
        ▼
Weather
        │
        │ month
        ▼
FRED Macro
        │
        ▼
Master Analytical Dataset

## 3. Methodology: 简述你的分析流程（EDA -> SQL 统计 -> BCG 矩阵分析 -> 营销预算模拟）。
///////draft/example

Business Understanding

↓

Data Integration

↓

Data Cleaning

↓

Exploratory Data Analysis

↓

SQL Business Analytics

↓

Portfolio Analysis

↓

Business Simulation

↓

Executive Recommendations

## 4. Business Insights / Recommendations: 亮出你的核心结论（比如：调高 Coffee 预算至 40%，因为 Margin 最高）。
