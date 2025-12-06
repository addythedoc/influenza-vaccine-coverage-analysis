**Influenza Vaccine Coverage Analysis (2009–2024)**

An End-to-End Data Pipeline, SQL Analysis & Tableau Dashboard Project

**📌 Overview**

This project analyzes influenza vaccination coverage across U.S. states using public CDC/NIS-Flu data.
It demonstrates a complete data pipeline, including:

Data ingestion & cleaning (MySQL)

Calculating Healthy People 2030 metrics (70% target)

National, state, and regional trend analysis

Interactive Tableau visualization

Executive summary deck for stakeholders


**🛠️ Data Pipeline (MySQL)**
1. Create Database & Load Raw Table

The raw dataset is loaded into the flu_raw table and cleaned.

2. Convert Text Numbers → Numeric (coverage_pct)

MySQL regex cleaning converts percentage strings into decimals.

3. State-Level Extract (flu_state)

**Filters:**

Geography = State

Age = All Ages (≥ 6 months)

Removes null coverage

**Adds fields:**

target_pct = 70

gap_to_target = coverage_pct − 70


**4. Region Mapping**

A lookup table assigns each U.S. state to:

Northeast

Midwest

South

West

This produces flu_vax_state_region.

The full SQL pipeline is included in
sql/vaccine_coverage_pipeline.sql.

📈 **Key Findings**

📉 **National Trends (2009–2024)**

Average U.S. coverage: ~36%

Gap to 70% target: ~34 percentage points

No meaningful improvement in 15 years
(Trend results sourced from SQL analytics in pipeline file.)


🗺️ **Geographic Insights**

0 states meet the 70% target

Chronic underperformers (latest season):

Nevada

Florida

Mississippi

Georgia

Idaho

All U.S. regions show similar trends stabilizing around 30–40%.


📊 **Tableau Dashboard**

The dashboard contains 4 interactive views:

National vaccination trend (2009–2024)

State-level heatmap

Regional comparison over time

Top under-performing states

File: tableau/Influenza vaccine coverage viz.twbx


📝 **Presentation Deck**

The PPT summarizes key results, insights, and recommendations for stakeholders.

File: presentation/Influenza-Vaccine-Coverage-vs-Healthy-People-70percent-Target.pptx


Influenza-Vaccine-Coverage-vs-H…


🚀 **How to Reproduce the Analysis**
1. Load the dataset
LOAD DATA INFILE 'Influenza_Vaccination_Coverage_for_All_Ages__6__Months_.csv'
INTO TABLE flu_raw
...

2. Run the SQL pipeline

Open your SQL editor → run vaccine_coverage_pipeline.sql


vaccine_coverage SQL script

3. Open Tableau workbook

Connect Tableau to MySQL if needed → refresh extracts.


📌 **About This Project**

This project demonstrates:

Real public health surveillance workflow

Data cleaning + feature engineering

State & regional monitoring

Policy-oriented metrics (gap to target)

Communication of findings through dashboards & presentations

Ideal for portfolios in:

Public Health Analytics

Epidemiology

Data Science

Business Intelligence
