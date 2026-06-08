# 🤖 Global AI Job Market & Salary Trends 2025
### Power BI Dashboard

---

## 📌 Project Overview
Interactive Power BI dashboard analyzing **60,000+ AI job 
postings** across **50+ countries** to identify demand trends, 
salary patterns, and career insights.

---

## 🛠️ Tools Used
- **Power BI Desktop** — Dashboard & Visualizations
- **Power Query** — Data Cleaning & Transformation
- **DAX** — Measures & Calculations
- **Dataset** — Kaggle: Global AI Job Market 2025

---

## 📊 Dashboard Pages
| Page | Title | Purpose |
|------|-------|---------|
| 1 | Global Overview | Job demand by country and role |
| 2 | Salary Intelligence | Compensation analysis |
| 3 | Skills & Trends | Top skills and hiring patterns |

---

## 🔑 Key Insights
- 📈 Executive earns **3× more** than Entry ($189K vs $62K)
- 🐍 **Python** is the #1 most demanded skill
- 🌐 **32.77%** of AI roles are fully remote
- 🏆 **Machine Learning Researcher** is most in-demand role
- 🏢 Large companies pay **23% more** than small companies

---

## 🧮 DAX Measures

### Basic KPIs
| Measure | Formula |
|---------|---------|
| Total Jobs | `COUNTROWS(FactJobs)` |
| Avg Salary | `AVERAGE(FactJobs[Salary])` |
| Max Salary | `MAX(FactJobs[Salary])` |
| Median Salary | `MEDIAN(FactJobs[Salary])` |

### Advanced Measures
```dax
Remote Jobs = 
    CALCULATE(COUNTROWS(FactJobs), 
    FactJobs[RemoteRatio] = 100)

Remote Ratio = 
    DIVIDE([Remote Jobs], [Total Jobs], 0)

YoY Growth % = 
    VAR Current = [Total Jobs]
    VAR Previous = CALCULATE([Total Jobs],
        DATEADD(DimDate[Date], -1, YEAR))
    RETURN DIVIDE(Current - Previous, Previous, 0)

Role Rank = 
    RANKX(ALL(FactJobs[Role]), 
    [Total Jobs],, DESC, Dense)

Salary Rank = 
    RANKX(ALL(FactJobs[Role]), 
    [Avg Salary],, DESC, Dense)
```

---

## 🗂️ Data Model

**Star Schema Design**
| Table | Type | Description |
|-------|------|-------------|
| FactJobs | Fact | 60,000+ job records |
| DimDate | Dimension | Year, Month, Quarter |
| DimExperience | Dimension | Entry, Mid, Senior, Executive |

- Cardinality: **Many to One (*:1)**
- Filter Direction: **Single**
- All Relationships: **Active**

---

## ⚙️ Power Query Steps

1. ✅ Kept only 12 of 24 columns
2. ✅ Renamed columns for clarity
3. ✅ Mapped experience codes → EN/MI/SE/EX to readable labels
4. ✅ Standardized employment types → FT/PT/CT/FL
5. ✅ Fixed data types — Salary: Decimal, Date: Date
6. ✅ Removed nulls and duplicates
7. ✅ Renamed table to `FactJobs`

---

## 📸 Screenshots

### Page 1 — Global Overview
![Global Overview](screenshots/GLOBAL%20OVERVIEW.png)

### Page 2 — Salary Intelligence
![Salary Intelligence](screenshots/SALARY%20INTELLIGENCE.png)

### Page 3 — Skills & Trends
![Skills & Trends](screenshots/SKILLS%20AND%20TRENDS.png)

---

## 🔗 Connect With Me

- 💼 **LinkedIn:** [linkedin.com/in/eva-reji](https://linkedin.com/in/eva-reji)
- 🐙 **GitHub:** [github.com/EvaReji](https://github.com/EvaReji)
- 📧 **Email:** evareji01@gmail.com
