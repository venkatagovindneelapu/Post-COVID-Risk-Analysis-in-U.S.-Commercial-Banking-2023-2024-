**Post-COVID Risk Analysis in U.S. Commercial Banking (2023–2024)**

---

### 📅 Project Overview
This Power BI dashboard presents in-depth analytical views into three post-COVID risk zones across large U.S.-chartered commercial banks. It analyzes quarterly financial performance from March 2023 to December 2024 using publicly available Federal Reserve data.

The objective is to highlight systemic weaknesses and operational patterns across three dimensions:

- Asset stagnation and shrinkage
- Foreign exposure vs. domestic focus
- Capital concentration in top banks

---

### 🧰 Technology Stack
- **Python**: Used to clean and convert fixed-width `.txt` files into structured CSVs
- **Excel**: Merged monthly CSVs into one consolidated sheet for Power BI
- **Power BI**: Primary dashboard development environment
- **DAX**: Created KPIs, conditional formats, TopN logic, and dynamic titles
- **Power Query**: Pre-processed date labels, quarter columns, and string parsing

---

### 🔄 Data Source & Processing
- Source: Federal Reserve "Large Commercial Banks" data
- Format: Fixed-width text files per quarter (March, June, September, December)
- Period: 2023 Q1 to 2024 Q4
- Tools: Python + Pandas to read and convert `.txt` → `.csv`
- Excel used to concatenate all 8 files into a single table
- Imported into Power BI with Quarter and Year logic added via Power Query

---

### 📊 Dashboard Page Explanations

---

#### 📈 Page 1: Executive Overview
Insight: This page delivers a high-level diagnostic summary to help stakeholders rapidly identify system-wide trends and select which risk area to explore further in the following pages.

---

#### 📊 Page 2: Asset Trends & Shrinkage Risk

**Display Name:** Asset Performance Analysis: Growth vs. Shrinkage

**KPI Cards:**
- **Overall Asset Growth**: +443.3% — Calculated as the percentage increase in the total consolidated assets across all U.S. commercial banks from Q1 2023 to Q4 2024, using DAX measures (`TotalAssets_Q1_2023`, `TotalAssets_Q4_2024`).
- **Top Gainer Bank**: MAIN ST BK CORP — Identified using a TopN DAX logic applied to each bank’s percentage change in consolidated assets between Q4 2023 and Q4 2024.
- **Top Gainer % Growth**: +133.6% — Represents the highest asset growth rate among all banks over the final year, computed via `TopGainerGrowth` measure.

**Charts:**
- **Line Chart**: Tracks asset fluctuations of the top 10 banks by total assets (as of Q4 2024) across all quarters. The x-axis is `Quarter`, and y-axis is `Consol Assets ($M)`, with `Bank Name` as the legend.
- **Bar Chart**: Compares % asset change per bank between Q4 2023 and Q4 2024 using `%_Asset_Change_Q4`. Banks are sorted ascending to bring worst performers to the top.

**Slicers:** Interactive slicers allow selection of `Year` and `Quarter` for dynamic filtering of visuals.

**Insight:** This page exposes trends in bank growth or decline over the post-COVID recovery period. It helps identify banks that may be shrinking or stagnating—an early warning for restructuring, divestment, or risk review.

---

#### 🌐 Page 3: Domestic Exposure & Branch Strategy

**Focus Area:** Foreign Exposure & Branch Network Imbalance

**Charts & Cards:**
- **Clustered Column Chart**: Visual comparison of total consolidated assets vs. domestic assets per bank. This chart helps detect large institutions with disproportionately low domestic exposure, flagging possible foreign dependency.
- **Line Chart**: Plots the number of domestic vs. foreign branches per bank, highlighting disparities in physical presence. This chart reveals inefficiencies in branch strategy across international markets.
- **Bar Chart**: Ranks banks by absolute domestic asset values, showcasing which institutions hold the most U.S.-based assets.
- **KPI Card**: Identifies the **Most Foreign-Exposed Bank** — NORTHERN TC — based on the lowest percentage of domestic assets relative to total consolidated holdings.

**Insight:**
- Banks with <60% domestic asset % are flagged for overexposure to international markets, suggesting vulnerability to foreign currency shifts or geopolitical tensions.
- A mismatch between domestic and foreign branch counts may point to outdated or overextended brick-and-mortar strategies, particularly in a digital banking era.

---

#### 🏛️ Page 4: Capital Concentration & Systemic Risk

**Display Name:** Capital Concentration & Systemic Risk

**KPI Card:**
- **Largest Bank by Asset Share**: GOLDMAN SACHS BK USA

**Visuals:**
- **TreeMap**: Top 20 banks by consolidated assets
- **Pie Chart**: Top 5 banks hold ~**84%** of total banking assets
- **Line Chart**: Asset Concentration Over Time (Q1 2023 to Q4 2024)

**Insight:** Reveals high dependency on a few institutions, signaling systemic risk and regulatory vulnerability.

---

### 📊 Key DAX Measures
```DAX
TotalAssets_Q1_2023 = CALCULATE(SUM([Consol Assets ($M)]), Year = 2023, Quarter = "Q1")
TotalAssets_Q4_2024 = CALCULATE(SUM([Consol Assets ($M)]), Year = 2024, Quarter = "Q4")
Overall_Asset_Growth_% = DIVIDE([TotalAssets_Q4_2024] - [TotalAssets_Q1_2023], [TotalAssets_Q1_2023]) * 100

%_Asset_Change_Q4 = ...  -- % Change from Q4 2023 to Q4 2024
TopGainerBank = ...
TopGainerGrowth = ...
```

---

### 🤔 Why This Project Matters
Post-COVID, U.S. commercial banks face shifts in capital flow, global exposure, and operational models.

This dashboard identifies:
- Banks likely to shrink without intervention
- Institutions overexposed to global risk
- Sector concentration that may endanger the financial system

Each visual and KPI is designed to help analysts, regulators, and strategists make sense of financial stability trends.

---

### 📊 Summary of Business Insights
| Page | Key Metric | Value / Insight |
|------|------------|-----------------|
| Executive | Asset Growth | +443.3% across all banks |
| Asset Trends | Top Gainer | MAIN ST BK CORP (+133.6%) |
| Exposure | Most Foreign-Exposed | NORTHERN TC (Domestic % lowest) |
| Systemic Risk | Top 5 Banks | Control ~84% of all assets |

---

### 🚀 Next Steps / Enhancements
- Add YOY asset growth trendline
- Add sector (commercial, retail, investment) breakdown
- Predict future asset trends using ML models (e.g., Prophet)

---


## 📊 Dashboard Previews

### 🧾 **Executive Overview**
![image alt]([asserts/Overview Page.png](https://github.com/venkatagovindneelapu/Post-COVID-Risk-Analysis-in-U.S.-Commercial-Banking-2023-2024-/blob/main/asserts/Overview%20Page.png?raw=true))

---

### 📈 **Asset Trends & Shrinkage Risk**
![image alt]()

---

### 🌍 **Domestic Exposure & Branch Strategy**
![image alt]()

---

### 🏦 **Capital Concentration & Systemic Risk**
![image alt]()


