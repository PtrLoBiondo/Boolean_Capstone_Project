# Boolean Capston Project - Data Analytics

An end-to-end data analytics and business intelligence project exploring the statistical relationship between circulating vehicle fleets, population metrics, and road accidents across Italian regions and municipalities over a 10-year historical period.

---

## 📌 Project Overview & Objectives
The main objective of this project is to gain data-driven insights into road accident rates across Italy to identify high-risk areas where interventions are needed. 

Rather than focusing purely on absolute figures, which may penalize massive hubs like Rome or Milan, this study normalizes accident records against local population, surface area, and vehicle fleet sizes to evaluate the actual **severity and risk index** of each territory.

## 🛠️ Tools
- **Data Engineering & Analysis (Python):** VS Code (IDE), Selenium, Pandas, Matplotlib, Seaborn, Scikit-Learn, Requests, Time
- **Business Intelligence & Visualization:** Power BI, Power Query, DAX.

---

## 🔄 Methodology & Pipeline

### Phase 1: Python Data Pipeline
1. **Data Acquisition:** Integrated data from multiple sources:
   - **ISTAT** (Road accident historical data via API queries).
   - **Situas** (Specific local/infrastructure indicators via web scraping with Selenium).
   - **ACI** (Public registry data regarding the active circulating vehicle fleet).
2. **Data Processing & Feature Engineering:** Cleaned datasets, handled missing values, checked column consistency, and engineered relative risk metrics (e.g., Accident Rates per 1,000 vehicles).
3. **Exploratory Data Analysis (EDA):** Visualized historical temporal trends and benchmarked municipalities using Seaborn and Matplotlib.
4. **Machine Learning:** Implemented unsupervised clustering (**K-Means & DBSCAN**) to group geographical accident hotspots and applied **Logistic Regression** for initial predictive behavior modeling.

### Phase 2: Power BI Modeling & Dashboarding
1. **Data Modeling:** Imported the refined Python `.csv` outputs and established a **Star Schema** relational model connecting fact tables and dimension tables.
2. **Advanced Metrics (DAX):** Developed custom KPIs to track crash severity:
   - **Fatality Rate:** $\text{Deaths} / \text{Total Accidents}$.
   - **Injury Rate:** $\text{Injuries} / \text{Total Accidents}$.
3. **Statistical Noise Filtering:** Applied a methodological threshold to filter the municipality visual elements, including **only municipalities with 1,000 inhabitants or more**. This constraint eliminates statistical anomalies caused by micro-villages, where a single isolated accident can skew rates artificially.

---

## 📊 Key Insights & Results
- **Trend Stability:** The total volume of accidents nationwide remained relatively constant over the 10-year span.
- **The COVID-19 Anomaly:** During the 2020 pandemic lockdown, total accidents dropped significantly due to reduced mobility; however, the **fatality rate spiked** noticeably.
- **Volume vs. Risk:** In absolute terms, major metropolitan hubs like Milan and Rome dominate the charts. However, once correlated with population and surface area, smaller nodes (particularly high-density tourist areas) emerge as high-risk environments.
- **Regional Investment Hotspot:** At a regional level of granularity, **Liguria** stands out as the primary critical area requiring targeted safety investments.

---

## 🚀 How to Run the Project

### Prerequisites
Make sure you have Python (3.12.12) installed. You can install all the required libraries using the provided `requirements.txt` file:
```bash
pip install -r requirements.txt 
```

**Power BI Path Configuration:** Open the `.pbix` file in Power BI Desktop. Before refreshing, navigate to *Home > Transform Data > Data Source Settings* and update the file paths to match the local directory where the `.csv` files are saved.