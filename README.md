# 📊 Marketing Analytics Dashboard

This project presents an interactive Marketing Analytics Dashboard created using **Looker Studio** and **Google Sheets**. The dashboard provides valuable insights into customer behavior, spending habits, and campaign effectiveness, all built from marketing customer data.

---

## 1. 📌 Overview

This report summarizes the key visualizations and metrics developed using marketing customer data. The dashboards provide insights into:

- Customer behavior  
- Spending patterns  
- Campaign effectiveness  

...based on various **demographic** and **behavioral** dimensions.

---

## 2. 📈 Calculated Metrics

| Metric Name                   | Formula / Description |
|------------------------------|------------------------|
| **Total Spend**              | `MntWines + MntFruits + MntMeatProducts + MntFishProducts + MntSweetProducts + MntGoldProds` |
| **Household Size**           | `Kidhome + Teenhome` |
| **Campaign Acceptance Rate** | `(AcceptedCmp1 + AcceptedCmp2 + AcceptedCmp3 + AcceptedCmp4 + AcceptedCmp5 + Response) / 6` |
| **Preferred Purchase Channel** | See SQL logic below |
| **Income Range**             | See SQL logic below |

---

### 🧠 SQL Logic for Derived Fields

#### Preferred Purchase Channel
```sql
CASE
  WHEN NumWebPurchases >= NumCatalogPurchases AND NumWebPurchases >= NumStorePurchases THEN "Web"
  WHEN NumCatalogPurchases >= NumWebPurchases AND NumCatalogPurchases >= NumStorePurchases THEN "Catalog"
  WHEN NumStorePurchases >= NumWebPurchases AND NumStorePurchases >= NumCatalogPurchases THEN "Store"
  ELSE "Unknown"
END
```

#### Income Range
```sql
CASE
  WHEN Income <= 30000 THEN "≤30k"
  WHEN Income > 30000 AND Income <= 60000 THEN "30k-60k"
  WHEN Income > 60000 AND Income <= 90000 THEN "60k-90k"
  WHEN Income > 90000 AND Income <= 120000 THEN "90k-120k"
  WHEN Income > 120000 THEN "120k+"
END
```

> ✅ **Note:** “Unknown” values were filtered out for a cleaner and more meaningful visualization.

---

## 3. 📊 Visualizations

- **🟢 Pie Chart**: *Education‑wise Total Spending*  
  - **Dimension**: `Education`  
  - **Metric**: `Total Spend`  
  - ➤ Shows how customer spending varies with education level.

- **🔵 Bar Chart**: *Campaign Acceptance by Marital Status*  
  - **Dimension**: `Marital_Status`  
  - **Metric**: `Campaign Acceptance Rate`  
  - ➤ Identifies which marital groups are more receptive to marketing campaigns.

- **🔴 Line Chart**: *Avg. Recency by Income Range*  
  - **Dimension**: `Income Range`  
  - **Metric**: `Average Recency`  
  - ➤ Shows how recently customers have interacted with the brand.

- **🟠 Table**: *KPI Summary by Segment*  
  - **Dimension**: `Education + Marital_Status`  
  - **Metrics**:  
    - Total Spend  
    - Campaign Acceptance Rate  
    - Recency  
    - Income  
    - Household Size  
    - Preferred Purchase Channel  
  - ➤ A complete view of performance across customer segments.

- **🟡 Scorecards / Heatmaps**: *Conversion Metrics*  
  - **Metrics**: Response, Campaign Acceptance Rate  
  - ➤ Quick evaluation of campaign performance by segment.

---

## 4. 🧰 Tools Used

- **📈 Looker Studio** – For visual dashboard design  
- **📊 Google Sheets** – Used as the data source  

---

## 5. 🖼 Dashboard Preview

🔗 **[View the Live Dashboard on Looker Studio](https://lookerstudio.google.com/reporting/2c543769-b616-4397-8b33-c4b9a1f05882)**


_Optional: Add a screenshot preview below if you want._

```markdown
![Dashboard Screenshot](assets/dashboard-screenshot.png)
```

---

## 6. 📁 Repository Structure

```bash
.
├── README.md
├── assets/
│   └── dashboard‑screenshot.png   # Optional visual preview
├── data/
│   └── sample‑data.csv            # Optional anonymized data sample
└── docs/
    └── report.pdf                 # Optional detailed report or analysis
```

---

## 7. 👤 Author

**Pathan Khaleedh Khan**  
📧 [pathankhaleedhkhan@gmail.com](mailto:pathankhaleedhkhan@gmail.com)  
🔗 [LinkedIn Profile](https://www.linkedin.com/in/khaleedhkhanpathan/)

---

## 📜 License

This project is open-source and available for learning and educational use. Attribution appreciated.
