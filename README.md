# 🛍️ Customer Shopping Behavior Analysis

A full-stack data analysis project exploring customer shopping patterns across **3,900 transactions**, using **Python**, **PostgreSQL**, and **Power BI** to uncover actionable business insights.

---

## 📁 Project Structure

```
customer-behavior-analysis/
│
├── customer_shopping_behavior.csv     # Raw dataset (3,900 rows, 18 columns)
├── data_processing.ipynb              # Python EDA & data cleaning notebook
├── customer_behavior_sql.sql          # SQL queries for business analysis
├── customer_behavior_dashboard.pbix   # Power BI interactive dashboard
└── customer_behavior_report.pdf       # Final project report
```

---

## 📊 Dataset Overview

| Property        | Details                                         |
|-----------------|-------------------------------------------------|
| **Rows**        | 3,900 transactions                              |
| **Columns**     | 18 features                                     |
| **Missing Data**| 37 values in `review_rating` column             |

### Key Features
- **Customer Demographics** — Age, Gender, Location, Subscription Status  
- **Purchase Details** — Item Purchased, Category, Purchase Amount, Season, Size, Color  
- **Shopping Behavior** — Discount Applied, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type  

---

## 🧹 Data Cleaning & Feature Engineering (Python)

Performed in `data_processing.ipynb` using **pandas**:

- **Missing values** — Imputed `review_rating` nulls using the **median rating per product category**
- **Column standardization** — Renamed all columns to `snake_case`
- **Feature engineering**:
  - `age_group` — Created by binning customer ages (Young Adult / Middle Age / Adult / Senior)
  - `purchase_frequency_days` — Derived from purchase frequency data
- **Redundancy check** — Confirmed `discount_applied` and `promo_code_used` were redundant; dropped `promo_code_used`
- **Database integration** — Loaded the cleaned DataFrame into **PostgreSQL** for SQL analysis

---

## 🗄️ SQL Analysis

Ten business questions answered via **PostgreSQL** in `customer_behavior_sql.sql`:

| # | Question | Key Finding |
|---|----------|-------------|
| Q1 | Revenue by gender | Male: **$157,890** vs Female: **$75,191** |
| Q2 | Discount users above average spend | Identified high-value discount customers |
| Q3 | Top 5 products by review rating | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| Q4 | Standard vs Express shipping spend | Express: **$60.48** avg vs Standard: **$58.46** avg |
| Q5 | Subscribers vs Non-subscribers | Avg spend similar (~$59); Non-subscribers drive more total revenue |
| Q6 | Top discounted products | Hat (50%), Sneakers (49.66%), Coat (49.07%) |
| Q7 | Customer segmentation | Loyal: **3,116** \| Returning: **701** \| New: **83** |
| Q8 | Top 3 products per category | Blouse, Jacket, Jewelry, Sandals among leaders |
| Q9 | Repeat buyers & subscriptions | 2,518 repeat buyers are **non-subscribers** vs 958 subscribers |
| Q10 | Revenue by age group | Young Adults lead with **$62,143** |

---

## 📈 Power BI Dashboard

An interactive dashboard (`customer_behavior_dashboard.pbix`) was built with the following KPIs and visuals:

<img width="1337" height="730" alt="image" src="https://github.com/user-attachments/assets/aacce4eb-c9a4-40e8-b2f8-c4b6124538fe" />


| KPI | Value |
|-----|-------|
| Total Customers | **3.9K** |
| Average Purchase Amount | **$59.76** |
| Average Review Rating | **3.75** |

**Visuals included:**
- % of Customers by Subscription Status (92.7% non-subscribed)
- Revenue & Sales by Category
- Revenue & Sales by Age Group
- Slicers for Gender, Category, and Shipping Type

---

## 💡 Business Recommendations

1. **Boost Subscriptions** — Promote exclusive perks for subscribers; only 7.3% are currently subscribed despite similar spend levels
2. **Customer Loyalty Programs** — Reward repeat buyers to accelerate movement into the "Loyal" segment
3. **Review Discount Policy** — ~50% of Hat and Sneaker purchases use discounts; balance promotions with margin control
4. **Product Positioning** — Feature top-rated items (Gloves, Sandals, Boots) prominently in marketing campaigns
5. **Targeted Marketing** — Prioritize Young Adult and Middle Age groups, and upsell Express shipping users

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/your-username/customer-behavior-analysis.git
cd customer-behavior-analysis
```

### 2. Install Python dependencies
```bash
pip install pandas numpy matplotlib seaborn psycopg2
```

### 3. Run the notebook
Open `data_processing.ipynb` in Jupyter and run all cells to clean the data and load it into PostgreSQL.

### 4. Run SQL queries
Connect to your PostgreSQL database and execute `customer_behavior_sql.sql`.

### 5. View the dashboard
Open `customer_behavior_dashboard.pbix` in **Power BI Desktop**.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
