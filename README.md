# 🪔 Diwali Sales Data Analysis

A complete data analysis project on Diwali sales data — data cleaning with Python, visualizations, and an AI-powered interactive dashboard.

---

## 📁 Repository Structure

```
diwali-sales-analysis/
│
├── data/
│   ├── Sales_Data_raw.csv          # Original raw dataset (11,251 rows, 15 cols)
│   └── Sales_Data_cleaned.csv      # Cleaned dataset (11,239 rows, 13 cols)
│
├── notebook/
│   └── Sales_Analysis.ipynb        # Python notebook — cleaning + EDA + visualizations
│
├── dashboard/
│   └── index.html                  # AI-powered interactive dashboard
│
└── README.md
```

---

## 📊 Dataset Overview

| Property | Raw Data | Cleaned Data |
|----------|----------|--------------|
| Rows | 11,251 | 11,239 |
| Columns | 15 | 13 |
| Null Values | 12 (Amount) | 0 |

**Columns:** `User_ID`, `Cust_name`, `Product_ID`, `Gender`, `Age Group`, `Age`, `Marital_Status`, `State`, `Zone`, `Occupation`, `Product_Category`, `Orders`, `Amount`

---

## 🧹 Data Cleaning Steps

1. **Dropped empty columns** — `Status` and `unnamed1` (100% null)
2. **Removed null rows** — 12 rows with missing `Amount` values
3. **Fixed data types** — `Amount` converted from `float` to `int`

```python
import pandas as pd

df = pd.read_csv("Sales_Data.csv", encoding='unicode_escape')
df.drop(['Status', 'unnamed1'], axis=1, inplace=True)
df.dropna(inplace=True)
df['Amount'] = df['Amount'].astype('int')
```

---

## 📈 Key Findings

### 💰 Revenue
- **Total Revenue:** ₹10.6 Crore
- **Total Orders:** 27,981
- **Average Order Value:** ₹9,454

### 👥 Demographics
- **Female customers** dominate — 69.7% of buyers, 70% of revenue
- **26-35 age group** is the largest segment (46.9% of customers)
- **Unmarried customers** spend more than married ones

### 🗺️ Geography
- **Top State:** Uttar Pradesh (₹1.94 Cr)
- **Top Zone:** Central & Western India

### 💼 Occupation
- **IT Sector** employees are the highest spenders (₹1.48 Cr)
- Followed by Healthcare and Aviation

### 🛍️ Products
- **Food** is the top category (₹3.39 Cr — 32% of revenue)
- **Clothing & Apparel** and **Electronics** follow closely

---

## 🤖 AI-Powered Dashboard

The dashboard (`dashboard/index.html`) includes:

- **10 interactive charts** — built with Chart.js
- **Real-time AI chat** — ask questions about the data in Urdu or English
- **Dark theme** — professional analytics UI

### How to use the AI Chat:
1. Open `dashboard/index.html` in a browser
2. Use quick-question buttons OR type your own question
3. Ask in **Urdu** or **English** — AI responds accordingly

Example questions:
- *"Sabse zyada revenue kis state mein hua?"*
- *"Which age group buys the most?"*
- *"Data cleaning mein kya kiya gaya?"*

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Python 3 | Data processing |
| pandas | Data cleaning & analysis |
| seaborn | Statistical visualizations |
| matplotlib | Plotting charts |
| Chart.js | Interactive dashboard charts |
| Claude API | AI chat assistant |
| Jupyter Notebook | Development environment |

---

## 🚀 How to Run

### Jupyter Notebook
```bash
pip install pandas numpy matplotlib seaborn openpyxl
jupyter notebook notebook/Sales_Analysis.ipynb
```

### Dashboard
Just open `dashboard/index.html` in any web browser — no server needed!

---

## 📌 Conclusion

The typical Diwali shopper is a **young, unmarried female (age 26-35)** working in the **IT sector**, living in **Uttar Pradesh or Maharashtra**, buying **Food and Clothing** products.

---

*Project by: [Your Name] | Data Analysis with Python*
