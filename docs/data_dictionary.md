# Data Dictionary

All column names used in this project are defined here.

---

## Tables Overview

| Table | Source File | Description |
|---|---|---|
| `Menu` | `data/raw/starbucks_menu.csv` | Starbucks product catalog with nutritional and pricing info |
| `Transaction` | `data/raw/synthetic_transactions.csv` | Synthetic customer purchase records |
| `Macro` | `data/raw/fred_macro.csv` | Monthly U.S. macroeconomic indicators (FRED) |
| `Weather` | `data/raw/weather_daily.csv` | Daily weather observations by city |

---

## Menu

| Column | Type | Meaning | Table |
|---|---|---|---|
| `product_name` | string | Beverage name | Menu |
| `category` | string | Product category (e.g. Coffee, Tea, Espresso) | Menu |
| `size` | string | Serving size (Short / Tall / Grande / Venti) | Menu |
| `price_usd` | float | Listed menu price in USD | Menu |
| `calories` | int | Caloric content (kcal) | Menu |
| `sugar_g` | float | Sugar content in grams | Menu |
| `caffeine_mg` | float | Caffeine content in milligrams | Menu |
| `seasonal_flag` | int | 1 = seasonal/limited item, 0 = year-round item | Menu |

---

## Transaction

| Column | Type | Meaning | Table |
|---|---|---|---|
| `transaction_id` | string | Unique transaction identifier (e.g. TXN-000001) | Transaction |
| `date` | date | Transaction date (YYYY-MM-DD) | Transaction |
| `hour` | int | Hour of day the purchase occurred (0–23) | Transaction |
| `time_slot` | string | Named time-of-day bucket (morning_rush / late_morning / afternoon / evening) | Transaction |
| `city` | string | City where the transaction took place | Transaction |
| `persona` | string | Customer segment label (e.g. morning_commuter, student) | Transaction |
| `is_weekend` | int | 1 = Saturday or Sunday, 0 = weekday | Transaction |
| `temp_f` | float | Outdoor temperature in °F at time of purchase | Transaction |
| `cpi` | float | CPI value for the month of the transaction (joined from Macro) | Transaction |
| `category` | string | Product category of the purchased item | Transaction |
| `product_name` | string | Beverage name purchased | Transaction |
| `size` | string | Serving size purchased (Short / Tall / Grande / Venti) | Transaction |
| `base_price` | float | Base menu price before customizations (USD) | Transaction |
| `customizations` | string | Description of add-ons/modifications; "none" if none | Transaction |
| `n_customizations` | int | Number of customizations applied | Transaction |
| `upcharge` | float | Additional charge for customizations (USD) | Transaction |
| `total_price` | float | Final amount paid by customer (base_price + upcharge) in USD | Transaction |
| `calories` | int | Caloric content of the purchased item (kcal) | Transaction |
| `sugar_g` | float | Sugar content of the purchased item in grams | Transaction |
| `caffeine_mg` | float | Caffeine content of the purchased item in milligrams | Transaction |

---

## Macro

| Column | Type | Meaning | Table |
|---|---|---|---|
| `date` | date | First day of the month the observation covers (YYYY-MM-DD) | Macro |
| `cpi` | float | Consumer Price Index — all urban consumers, U.S. city average | Macro |
| `avg_hourly_earnings` | float | Average hourly earnings of U.S. production workers (USD) | Macro |
| `real_wage_index` | float | Inflation-adjusted wage index (avg_hourly_earnings / CPI × 100) | Macro |

---

## Weather

| Column | Type | Meaning | Table |
|---|---|---|---|
| `date` | date | Calendar date of the observation (YYYY-MM-DD) | Weather |
| `city` | string | City the observation belongs to | Weather |
| `temp_mean_f` | float | Mean daily temperature in °F | Weather |
| `temp_max_f` | float | Maximum daily temperature in °F | Weather |
| `temp_min_f` | float | Minimum daily temperature in °F | Weather |

---

## Shared / Derived Columns

Columns that appear in multiple tables or are computed during analysis.

| Column | Type | Meaning | Created In |
|---|---|---|---|
| `date` | date | Calendar date, always formatted YYYY-MM-DD | All tables |
| `city` | string | City name, consistent across Transaction and Weather | Transaction, Weather |
| `category` | string | Product category, consistent across Menu and Transaction | Menu, Transaction |
| `product_name` | string | Beverage name, consistent across Menu and Transaction | Menu, Transaction |
| `size` | string | Serving size, consistent across Menu and Transaction | Menu, Transaction |
| `calories` | int | Caloric content, consistent across Menu and Transaction | Menu, Transaction |
| `sugar_g` | float | Sugar in grams, consistent across Menu and Transaction | Menu, Transaction |
| `caffeine_mg` | float | Caffeine in mg, consistent across Menu and Transaction | Menu, Transaction |
| `revenue` | float | Alias for total_price when aggregated across transactions | Derived |
| `margin` | float | Estimated gross margin per transaction (if cost data added later) | Derived |
