
# **Influenza Vaccine Coverage Analysis (2009–2024)**

### End-to-End SQL Analytics & Tableau Dashboard Project

---

## 📌 **Overview**

This project analyzes **influenza vaccination coverage across U.S. states** using publicly available CDC / NIS-Flu data. It demonstrates a complete **public health analytics workflow**, from data ingestion and transformation to visualization and stakeholder-ready reporting.

The project includes:

* Data ingestion, cleaning, and transformation in **MySQL**
* Calculation of **Healthy People 2030 metrics** (70% vaccination target)
* National, state, and regional trend analysis
* Interactive **Tableau dashboard**
* Executive summary presentation for policy and public health audiences

---

## 🛠️ **Data Pipeline (MySQL)**

### **1. Database Creation & Raw Data Loading**

* Raw influenza vaccination data are loaded into a staging table (`flu_raw`)
* Initial cleaning and standardization are performed at ingestion

---

### **2. Data Cleaning & Type Conversion**

* Percentage values stored as text are converted to numeric format (`coverage_pct`)
* Invalid and missing values are handled using SQL transformations

---

### **3. State-Level Analytical Dataset (`flu_state`)**

**Filters applied:**

* Geography: State-level
* Age group: All ages (≥ 6 months)
* Records with missing coverage removed

**Derived variables added:**

* `target_pct` = 70 (Healthy People benchmark)
* `gap_to_target` = coverage_pct − 70

---

### **4. Regional Mapping**

* A lookup table assigns each state to one of four U.S. regions:

  * Northeast
  * Midwest
  * South
  * West
* Produces the final analytical table: `flu_vax_state_region`

📄 The complete SQL pipeline is documented in:
`scripts/vaccine_coverage_pipeline.sql`

---

## 📈 **Key Findings**

### 📉 **National Trends (2009–2024)**

* Average U.S. influenza vaccination coverage: **~36%**
* Persistent **~34 percentage point gap** from the 70% target
* No sustained improvement over the 15-year period

(All trend estimates are derived directly from SQL-based analytics.)

---

### 🗺️ **Geographic Insights**

* **No U.S. state** meets the 70% vaccination target
* Chronic underperformers in the most recent season include:

  * Nevada
  * Florida
  * Mississippi
  * Georgia
  * Idaho
* All regions show similar stagnation, with coverage plateauing between **30–40%**

---

## 📊 **Tableau Dashboard**

The interactive Tableau dashboard includes four core views:

1. National influenza vaccination trend (2009–2024)
2. State-level coverage heatmap
3. Regional comparisons over time
4. Identification of top underperforming states

Dashboard file:
`dashboard/Influenza_vaccine_coverage.twbx`

---

## 🚀 **How to Reproduce the Analysis**

1. Load the influenza vaccination dataset into MySQL
2. Run the SQL pipeline using `vaccine_coverage_pipeline.sql`
3. Open the Tableau workbook and refresh data connections if required

---

## 📌 **About This Project**

This project demonstrates:

* Real-world **public health surveillance workflows**
* SQL-based data cleaning and feature engineering
* State and regional performance monitoring
* Policy-oriented benchmarking using national targets
* Clear communication of epidemiologic insights through dashboards and presentations

**Well-suited for portfolios in:**

* Public Health Analytics
* Epidemiology
* Data Science
* Business Intelligence


