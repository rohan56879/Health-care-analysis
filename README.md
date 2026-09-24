# Health-care-analysis
Healthcare Data Analysis using Python — cleaned and analyzed 55K+ hospital records to explore patient demographics, admission patterns, billing amounts, insurance providers, medical conditions, emergency admissions, and length of stay using Pandas, NumPy, Matplotlib, and Seaborn.
# Healthcare Data Analysis

## 📌 Project Overview

This project focuses on analyzing healthcare and hospital admission data using Python. The analysis explores patient demographics, medical conditions, admission patterns, billing amounts, insurance providers, medications, test results, and hospital stay duration.

The project follows a complete data-analysis workflow:

**Data Loading → Data Exploration → Data Cleaning → Feature Engineering → Analysis → Visualization**

The dataset contains **55,500 records and 15 original columns** covering patient and hospital-related information.

---

## 🎯 Objectives

The main objectives of this analysis are to:

* Understand the structure and characteristics of the healthcare dataset.
* Identify and handle duplicate records and data-quality issues.
* Convert date columns into appropriate datetime formats.
* Analyze patient age and demographic distribution.
* Examine different types of hospital admissions.
* Calculate average billing amounts and length of stay.
* Analyze billing patterns across medical conditions and insurance providers.
* Measure the proportion of emergency admissions.
* Study billing trends over time.
* Create meaningful visualizations to communicate healthcare insights.

---

## 📊 Dataset

The dataset contains the following original columns:

| Column             | Description                            |
| ------------------ | -------------------------------------- |
| Name               | Patient name                           |
| Age                | Patient age                            |
| Gender             | Patient gender                         |
| Blood Type         | Patient blood group                    |
| Medical Condition  | Primary medical condition              |
| Date of Admission  | Hospital admission date                |
| Doctor             | Doctor associated with the admission   |
| Hospital           | Hospital associated with the admission |
| Insurance Provider | Patient's insurance provider           |
| Billing Amount     | Amount billed for the admission        |
| Room Number        | Assigned room number                   |
| Admission Type     | Elective, Urgent, or Emergency         |
| Discharge Date     | Patient discharge date                 |
| Medication         | Medication prescribed                  |
| Test Results       | Test result category                   |

---

## 🛠️ Technologies Used

* **Python**
* **Pandas** – data manipulation and analysis
* **NumPy** – numerical operations
* **Matplotlib** – data visualization
* **Seaborn** – statistical visualization
* **Jupyter Notebook**

---

## 🔍 Data Exploration

Initial exploration included:

* Viewing the first and last records
* Checking dataset dimensions
* Inspecting column names
* Checking data types
* Generating descriptive statistics
* Checking missing values
* Identifying duplicate records

The original dataset contains **55,500 rows and 15 columns**.

The analysis identified **534 duplicate records** before cleaning.

---

## 🧹 Data Cleaning

Several data-quality issues were addressed during preprocessing:

### 1. Standardized column names

Column names were converted to lowercase and spaces were replaced with underscores.

### 2. Removed duplicate records

Duplicate rows were removed using Pandas `drop_duplicates()`.

### 3. Standardized patient names

Patient names were converted to lowercase and then formatted using title case.

### 4. Converted date columns

`date_of_admission` and `discharge_date` were converted to Pandas datetime format.

### 5. Handled invalid billing values

Negative billing amounts were identified during exploratory analysis and replaced using the median billing amount.

---

## ⚙️ Feature Engineering

Three additional features were created.

### Duration of Stay

Calculated the number of days between admission and discharge:

```python
df['duration_of_stay'] = (
    df['discharge_date'] - df['date_of_admission']
).dt.days
```

### Age Group

Patients were divided into four age groups using quartiles:

* Teenage
* Adult
* Mid-Age
* Senior

### Emergency Status

A binary feature was created to identify emergency admissions:

* `1` → Emergency admission
* `0` → Non-emergency admission

A separate `year` feature was also extracted from the discharge date for time-based analysis.

---

## 📈 Analysis Performed

The project investigates several healthcare-related questions.

### Patient & Demographic Analysis

* Age distribution
* Gender distribution
* Age-group distribution

The cleaned data contains **27,496 male records and 27,470 female records**.

### Hospital Admission Analysis

* Admission type distribution
* Average length of stay by admission type
* Emergency admission percentage

The analysis found that approximately **32.9% of admissions were emergency admissions**.

### Billing Analysis

The project analyzes:

* Overall average billing amount
* Average billing by medical condition
* Billing by gender
* Average billing by insurance provider
* Billing trends by year
* Average billing by age group

The calculated overall average billing amount after cleaning was approximately **25,594.53**.

### Insurance Analysis

The project examines both:

* Number of patients associated with each insurance provider
* Average billing amount by insurance provider

### Medical Condition Analysis

Average billing amounts were compared across:

* Arthritis
* Asthma
* Cancer
* Diabetes
* Hypertension
* Obesity

---

## 📊 Visualizations

The notebook uses Matplotlib and Seaborn to visualize the analysis.

Current visualizations include:

* **Age-wise distribution**
* Distribution and comparison of healthcare-related metrics
* Billing-related comparisons
* Category-based analysis

The age distribution is visualized using a histogram with age on the x-axis and patient count on the y-axis.

---

## 💡 Key Metrics

Some of the metrics calculated in the analysis include:

| Metric                         |    Result |
| ------------------------------ | --------: |
| Original records               |    55,500 |
| Original columns               |        15 |
| Duplicate records identified   |       534 |
| Average billing amount         | 25,594.53 |
| Average duration of stay       |   15 days |
| Emergency admission percentage |     32.9% |
| Male records                   |    27,496 |
| Female records                 |    27,470 |

## These metrics are based on the calculations present in the notebook.

## 📁 Project Structure

```text
healthcare-analysis/
│
├── healthcare analysis.ipynb
├── healthcare_dataset.csv
└── README.md
```

---

## 🚀 Skills Demonstrated

This project demonstrates practical skills in:

* Data Cleaning
* Exploratory Data Analysis (EDA)
* Data Preprocessing
* Feature Engineering
* Pandas
* NumPy
* Data Aggregation
* GroupBy Analysis
* Date/Time Analysis
* Statistical Analysis
* Data Visualization
* Healthcare Data Analysis

---

## 📌 Conclusion

This project demonstrates an end-to-end exploratory data analysis workflow on healthcare admission data. It combines data cleaning, feature engineering, aggregation, and visualization to understand patient demographics, hospital admissions, billing patterns, insurance distribution, medical conditions, and length of stay.

The project was developed as a practical exercise in applying Python-based data analytics techniques to a real-world-style healthcare dataset.
