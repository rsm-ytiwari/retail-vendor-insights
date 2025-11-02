
# Retail Vendor Insights

> **A report that shows goes deep into analyzing vendor performance in retail sector.**
>
> I wanted to see which vendors drive growth, who quietly protect margins, and where money just... sits.
> Using **Python, SQL, and a bit of statistical firepower**, I turned millions of transactions into a model that answers a simple question:
> **“Who gives us the most control over growth, pricing, and cash flow?”**
>
> 🚀 Along the way, I:
>
> * Found **high-margin, low-sales** brands hiding in plain sight.
> * Measured **vendor dependency** — top 10 suppliers = 65% of total spend.
> * Quantified **inventory drag** and **$2.7M in capital stuck on shelves.**
> * Proved, statistically, that **small vendors earn higher margins** than the big guys (p < 0.001).
>
> The result? A data story that links vendor performance to business leverage.
>
> 🔗 **Live HTML Report:** [Retail Vendor Performance Analysis →](https://rsm-ytiwari.github.io/retail-vendor-insights/)

---

### ✨ What I Worked On

* **Data Engineering (PostgreSQL + SQLAlchemy):** Built a pipeline from six messy operational tables — cleaned, joined, and modeled **15M+** rows into a usable analytics mart.
* **Data Analysis (Python | Pandas | NumPy | SciPy):** Explored margins, pricing, and turnover; validated patterns with t-tests and confidence intervals.
* **Visualization (Matplotlib | Seaborn):** Created visuals that explain, not decorate — vendor concentration, inventory flow, and profitability trends.
* **Business Analytics:** Turned raw transactions into vendor segments and actionable KPIs for negotiation, marketing, and procurement.
* **Automated Reporting (Quarto):** Built a reproducible pipeline that combines SQL, Python, and visuals into one seamless narrative.

---

###  Overview

This project digs into retail vendor performance — understanding **sales efficiency, pricing power, and inventory balance**.
It’s a full-stack analysis: **data engineering + statistics + storytelling**, designed to answer how vendor behavior shapes profitability.

---

### Data Overview

I worked with a relational dataset of **15M+ records** pulled from six core retail systems:

| Table                               | Description                   | Key Columns                                                 |
| :---------------------------------- | :---------------------------- | :---------------------------------------------------------- |
| `sales`                             | Individual sales transactions | `vendor_number`, `brand`, `sales_amount`                    |
| `purchases`                         | Purchase orders               | `vendor_number`, `brand`, `quantity_purchased`, `unit_cost` |
| `purchase_prices`                   | SKU-level vendor pricing      | `vendor_number`, `brand`, `unit_price`                      |
| `begin_inventory` / `end_inventory` | Periodic stock levels         | `brand`, `quantity`, `inventory_value`                      |
| `vendor_invoice`                    | Payment and billing records   | `vendor_number`, `invoice_id`, `amount_due`                 |

A lightweight demo dataset (`data/sample_*.csv`) is included for reproducibility.

---

### Data Pipeline

I modeled the pipeline in three layers — **Raw → Staging → Mart** — to keep it clean, scalable, and explainable.

```
RAW
 ├─ begin_inventory (206K)
 ├─ end_inventory (224K)
 ├─ purchase_prices (12K)
 ├─ purchases (2.37M)
 ├─ sales (12.8M)
 └─ vendor_invoice (5.5K)
      │
      ▼
STAGING — normalize, dedupe, validate joins
      │
      ▼
MART — mart.vendor_sales_summary (~10.7K rows)
      │
      └─→ EDA → Pareto → Bulk Efficiency → Inventory → Profitability
```

The mart layer became the analytical foundation — a single table where every vendor’s **sales, margins, and inventory turnover** live in one place.

---

###  Objectives

* Spot **high-margin, low-sales** brands — the hidden promotion candidates.
* Measure **vendor concentration** and purchasing dependency.
* Quantify **inventory turnover** and capital trapped in unsold stock.
* Compare **profitability** between top and low-performing vendors with statistical rigor.
* Test whether **bulk purchasing** actually reduces unit cost (spoiler: it does, by ~72%).

---

###  Tech Stack

* **Language:** Python (Pandas, NumPy, SciPy, Seaborn, Matplotlib)
* **Database:** PostgreSQL via SQLAlchemy
* **Framework:** Quarto for integrated analytics and storytelling
* **Statistical Methods:** Confidence Intervals, T-tests
* **Visualization:** Matplotlib, Seaborn

---

###  Key Insights

| Insight                  | Description                                                            |
| :----------------------- | :--------------------------------------------------------------------- |
| **Vendor Concentration** | Top 10 vendors control ~66% of total purchases — efficiency with risk. |
| **High-Margin Brands**   | Several low-volume brands earn >70% margins.                           |
| **Bulk Savings**         | Large orders cut unit cost by ~72%.                                    |
| **Inventory Drag**       | ~$2.71M of stock still waiting to sell.                                |
| **Profit Gap**           | Small vendors outperform big ones on margin (p < 0.001).               |

---

###  Business Takeaways

* **Promote** low-sales, high-margin products to unlock hidden profit.
* **Negotiate** bulk terms with dominant suppliers to leverage scale.
* **Clear** or realign slow inventory to free working capital.
* **Support** small vendors with reach; help large vendors optimize margin.

---

### 📁 Repo Structure

```
retail-vendor-insights/
│
├── notebooks/
│   └── 06_vendor_performance_analysis.qmd
├── data/
│   └── sample_vendor_data.csv
├── outputs/
│   └── charts, tables, figures
├── README.md
└── requirements.txt
```

---

### Results Summary

The data tells a simple story:
**Big vendors move the volume; small vendors move the profit.**

The smart play is balance — optimize cost where scale pays off, protect margins where they hide, and let data make the call.

---

## 👋 Author

**Yash Tiwari**
*Data | Product | Strategy | Design*
📊 *Data Analyst & Business Analyst — 🏗️ builder @ ❤️*

📧 [yashtiwari.ty@gmail.com](mailto:yashtiwari.ty@gmail.com)
🌐 [LinkedIn](https://www.linkedin.com/in/yash-tiwari-here/) • [Portfolio](https://leaf-allspice-531.notion.site/Hey-there-I-am-Yash-28a9c4819e1680a48f15c39ad54bd9d6?source=copy_link)

---

> *I build data stories that bridge analysis and business strategy.*
> *Curious about the “why” behind every number — and how to make it move.*
