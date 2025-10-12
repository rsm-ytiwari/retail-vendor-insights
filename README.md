# 🏬 Retail-vendor-insights
> 📊 **Data-driven retail-vendor-insights and Analysis**
> Analyze sales, profitability, and inventory efficiency across vendors using **Python, SQL, and statistical modeling**.
>
> 🚀 Highlights:
> - Identify **high-margin, low-sales** brands for targeted promotions.
> - Quantify **procurement dependency** (top 10 vendors = 65% of total purchases).
> - Assess **inventory efficiency** and **capital locked in unsold stock**.
> - Compare **profit margins statistically** between top and low performers (p < 0.001).
>
> 💡 *Actionable insights for optimizing pricing, vendor strategy, and profit growth.*

### 📊 Overview
This project analyzes retail- vendor performance data to uncover insights about **sales efficiency, pricing strategies, profit margins, and inventory management**.
It combines **data engineering, exploratory analysis, and statistical inference** to support business decisions on vendor optimization.

### 🧱 Data Pipeline

The project integrated data from **6 source tables** (`begin_inventory`, `end_inventory`, `purchase_prices`, `purchases`, `sales`, and `vendor_invoice`), totaling over **15 million rows**.
Using PostgreSQL, data was modeled into three layers — **raw**, **staging**, and **mart** — to create a consolidated analytical dataset:

- **Raw Layer:** Original transactional data from multiple sources.
- **Staging Layer:** Cleaned and joined intermediate tables for consistency.
- **Mart Layer:** Final analytical table (`mart.vendor_sales_summary`) with ~10K vendor-brand records used for performance evaluation.

This modular approach ensured data accuracy, consistency, and scalability for analysis and visualization.


---

```markdown
RAW
 ├─ begin_inventory (206,529)
 ├─ end_inventory (224,489)
 ├─ purchase_prices (12,261)
 ├─ purchases (2,372,474)
 ├─ sales (12,825,363)
 └─ vendor_invoice (5,543)
      │
      ▼
STAGING  — normalize types, dedupe, validate joins, align inventory periods
      │
      ▼
MART — mart.vendor_sales_summary (~10,692 rows)
      │
      └─→ EDA, Top Vendors/Brands, Pareto, Bulk Efficiency,
          Inventory Turnover & Unsold Capital, CI & T-tests

---

### 🎯 Objectives
- Identify **high-margin, low-sales brands** suitable for promotional campaigns.
- Measure **vendor concentration** and procurement dependency.
- Evaluate **inventory turnover** and **unsold capital**.
- Compare **profitability differences** between top- and low-performing vendors using statistical testing.
- Assess the **impact of bulk purchasing** on unit costs.

---

### ⚙️ Tech Stack
- **Language:** Python (Pandas, NumPy, SciPy, Seaborn, Matplotlib)
- **Database:** PostgreSQL (via SQLAlchemy)
- **Notebook Framework:** Quarto (.qmd)
- **Statistical Methods:** Confidence Intervals, T-tests
- **Visualization Tools:** Matplotlib, Seaborn

---

### 🧾 Key Insights
| Insight | Description |
|:--|:--|
| **Vendor Concentration** | Top 10 vendors account for ~66% of total purchases. |
| **High-Margin Brands** | Several low-volume brands have profit margins >70%. |
| **Bulk Purchase Savings** | Large orders reduce unit costs by ~72%. |
| **Inventory Value** | ~$2.71M locked in unsold stock. |
| **Profit Margin Gap** | Low-performing vendors have significantly higher margins (95% CI confirmed, p < 0.001). |

---

### 💡 Business Recommendations
- Promote **high-margin, low-sales** products through pricing or marketing adjustments.
- Negotiate **bulk discounts** with top suppliers to leverage economies of scale.
- Reduce **inventory holding costs** by clearing slow-moving stock.
- Support **small vendors** with expansion strategies while optimizing **large vendors’ margins**.

---

### 📁 Repository Structure
vendor-performance-analysis/
│
├── notebooks/
│ └── 06_vendor_performance_analysis.qmd # Main Quarto analysis
├── data/
│ └── vendor_sales_summary.csv # (or SQL-based source)
├── outputs/
│ └── charts, tables, figures
├── README.md # You are here
└── requirements.txt # (Optional: libraries list)


---

### 🧩 Results Summary
The study reveals a **dual vendor ecosystem**:
- Large vendors dominate sales but operate at lower margins.
- Smaller vendors maintain higher profitability through niche pricing.

Optimizing both through **strategic pricing, procurement efficiency, and vendor diversification** can enhance long-term profitability and resilience.

---

### 👋 Author

**Yash Tiwari**
*Data | Product | Strategy | Design*
📊 *Data Analyst & Business Analyst — 🏗️ builder @ ❤️*

📧 [yashtiwari.ty@gmail.com](mailto:yashtiwari.ty@gmail.com)
🌐 [LinkedIn](https://www.linkedin.com/in/yash-tiwari-here/) • [Portfolio](https://leaf-allspice-531.notion.site/Hey-there-I-am-Yash-28a9c4819e1680a48f15c39ad54bd9d6?source=copy_link)

---

> I build data stories that drive product, strategy, and design decisions.
> Passionate about blending analytical rigor with creative problem-solving.
