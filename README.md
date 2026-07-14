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

Starbucks proprietary point-of-sale (POS) transaction data is not publicly available. Therefore, this project constructs a business-ready analytical dataset using four complementary public datasets:
- Starbucks menu data
- Synthetic transaction records
- Historical weather
- Macroeconomic indicators

The synthetic dataset is intended to provide a realistic environment for business analytics and portfolio strategy development rather than to reproduce Starbucks' internal operational data.

## 2. Data Architecture

```
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
```

## 3. Methodology

```
00 Business Understanding
        ↓
01 Data Audit
        ↓
02 Data Integration
        ↓
03 Data Cleaning
        ↓
04 Exploratory Data Analysis
        ↓
05 SQL Business Analytics
        ↓
06 Portfolio Strategy
        ↓
07 Executive Report
```

## 4. Project Structure

```
├── data/
│   ├── raw/            # Starbucks menu, synthetic transactions, weather, FRED macro
│   ├── external/        # External reference data
│   └── processed/       # Cleaned / integrated analytical datasets
├── notebooks/            # 00-07, one per methodology stage (see above)
├── sql/                  # Schema definitions and business analysis queries
├── docs/
│   └── data_dictionary.md  # Column-level definitions for all raw tables
├── dashboard/             # Interactive dashboard assets
├── reports/               # Exported reports / executive deliverables
└── src/                   # Reusable Python modules
```

## 5. Business Insights / Recommendations

_To be added once the portfolio analysis and business simulation stages are complete._
