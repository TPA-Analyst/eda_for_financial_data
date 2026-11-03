# 📊 Exploratory Data Analysis for Financial Data

<p align="center">
  <img src="https://img.shields.io/badge/Python-Data%20Analysis-blue?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Processing-150458?logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Polars-Data%20Processing-CD792C" alt="Polars">
  <img src="https://img.shields.io/badge/Seaborn-Visualization-4C72B0" alt="Seaborn">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C" alt="Matplotlib">
</p>

<p align="center">
  <i>Exploring financial data quality, transaction patterns, and potential anomalies using Python.</i>
</p>

---

## 📌 1. Project Overview

This project applies **Exploratory Data Analysis (EDA)** techniques to a simulated General Ledger dataset for FY2025.

The analysis focuses on understanding financial transaction distributions, validating accounting data, comparing transaction patterns across departments, and detecting unusual debit transactions using statistical methods.

By combining data validation, descriptive statistics, outlier detection, and visualization, this project demonstrates how Python can support preliminary financial data analysis and identify areas requiring further investigation.

## 🎯 2. Business Objectives

The project addresses five key analytical questions:

- 🔍 **Data Integrity:** Are journal entries balanced between total debits and credits?
- 📈 **Transaction Patterns:** What are the typical transaction values and how are debit amounts distributed?
- 🏢 **Departmental Analysis:** How do transaction amounts and variability differ across departments?
- 🚨 **Outlier Detection:** Which transactions deviate significantly from normal patterns?
- 💡 **Risk Identification:** Do unusual transactions exhibit characteristics that warrant further review?

## 📂 3. Dataset

The project uses `general_ledger_large.csv`, a simulated General Ledger dataset containing:

<p align="center">
  <img src="https://img.shields.io/badge/Transaction%20Lines-1%2C504-blue?style=for-the-badge" alt="Transaction lines">
  <img src="https://img.shields.io/badge/Journal%20Entries-752-green?style=for-the-badge" alt="Journal entries">
  <img src="https://img.shields.io/badge/Period-FY2025-orange?style=for-the-badge" alt="Period">
</p>

### Dataset Fields

| Column | Description |
|---|---|
| `entry_id` | Unique journal entry identifier |
| `entry_date` | Transaction posting date |
| `account` | General ledger account |
| `debit` | Debit amount |
| `credit` | Credit amount |
| `department` | Department associated with the transaction |
| `posted_by` | User who posted the journal entry |

> 📝 **Note:** The dataset is simulated and does not represent actual company financial records.

## 🛠️ 4. Tools & Technologies

| Tool | Application |
|---|---|
| 🐍 Python | Data analysis and processing |
| Pandas | Data manipulation and statistical analysis |
| Polars | Data processing and analytical operations |
| Seaborn | Statistical data visualization |
| Matplotlib | Chart creation and customization |
| Jupyter Notebook | Interactive analysis and documentation |

## ⚙️ 5. Analytical Workflow

### ① Data Loading & Exploration

- Imported the General Ledger dataset using Pandas and Polars.
- Examined dataset dimensions, column structures, and data types.
- Reviewed transaction records to understand the dataset.

### ② Data Validation & Integrity Checks

- Evaluated the double-entry accounting principle by checking whether total debits equaled total credits.
- Validated debit-credit balance at the journal entry level using `entry_id`.
- Focused subsequent debit analysis on transactions with positive debit amounts.

### ③ Descriptive Statistical Analysis

Calculated key statistical measures:

- Mean and median
- Standard deviation and variance
- Quartiles and Interquartile Range (IQR)
- Coefficient of Variation (CV)
- Skewness and kurtosis

Compared transaction characteristics across departments to understand differences in transaction size and variability.

### ④ Outlier Detection

Applied two statistical methods to identify unusual debit transactions:

- **Z-score Method:** Flagged observations with an absolute Z-score greater than 3.
- **IQR Method:** Flagged observations above the upper fence, calculated as Q3 + 1.5 × IQR.

Compared the results of both methods to understand their differences and identify transactions requiring further examination.

### ⑤ Data Visualization

Created visualizations to communicate transaction patterns and statistical findings:

- 📊 Bar charts and line charts
- 📉 Histograms and distribution plots
- 🔵 Scatter plots
- 📦 Boxplots and violin plots
- 🌡️ Heatmaps and faceted visualizations

Also considered chart design principles, including the impact of truncated axes on financial data interpretation.

## 📈 6. Key Findings

### 💰 Transaction Distribution

| Metric | Result |
|---|---:|
| Positive-debit transactions | 752 |
| Mean debit amount | $4,044.07 |
| Median debit amount | $2,457.11 |
| Skewness | 10.89 |
| Transactions below $10,000 | 97.2% |

**Key Insight:** The debit distribution was highly right-skewed. Most transactions were relatively small, while a limited number of high-value transactions increased the overall average.

### 🚨 Outlier Detection Results

| Detection Method | Flagged Transactions | Percentage |
|---|---:|---:|
| Z-score (|z| > 3) | 7 | 0.93% |
| IQR (Upper Fence) | 38 | 5.05% |

**Key Insight:** The IQR method identified more potentially unusual transactions than the Z-score method, highlighting the importance of selecting appropriate detection techniques when analyzing skewed financial data.

### 🔎 Potential Risk Indicators

Further examination of the Z-score results identified two high-value journal entries posted on weekends:

| Journal Entry | Debit Amount | Posting Date |
|---|---:|---|
| JE3903 | $176,500 | August 30, 2025 |
| JE3904 | $87,000 | November 2, 2025 |

**Key Insight:** These transactions were highlighted as potential risk indicators for further review, not as evidence of errors or fraudulent activity.

### 🏢 Departmental Analysis

Compared transaction values and variability across departments using:

- Mean and median
- Standard deviation
- Coefficient of Variation (CV)
- IQR

The analysis highlighted differences in transaction patterns across departments and demonstrated why both average transaction values and relative variability matter when interpreting financial data.

## 🖼️ 7. Visualizations

The following charts illustrate transaction distributions, departmental comparisons, and unusual patterns.

> Replace the image paths below with actual screenshots from your project.

### Debit Distribution
<!-- ![Debit Distribution](images/debit_distribution.png) --> <img width="1707" height="441" alt="image" src="https://github.com/user-attachments/assets/cacb62c6-d9d0-4424-943a-528c8a522e1a" />

### Outlier Analysis
<!-- ![Outlier Analysis](images/outlier_analysis.png) --> <img width="850" height="550" alt="image" src="https://github.com/user-attachments/assets/4c1432f1-ea6d-4717-aa6c-02a298bc27ed" />

### Departmental Comparison
<!-- ![Departmental Comparison](images/department_comparison.png) --> <img width="907" height="681" alt="image" src="https://github.com/user-attachments/assets/3db8b430-884e-440f-b781-cee8deeba35a" />

### General Ledger Dashboard
<!-- ![General Ledger Dashboard](images/general_ledger_dashboard.png) --> <img width="1247" height="717" alt="image" src="https://github.com/user-attachments/assets/26de6ce8-e239-4e62-9712-95c0b2c5cb75" />

## 📁 8. Project Structure

```text
Exploratory-Data-Analysis-for-Financial-Data/
│
├── 📂 data/
│   └── general_ledger_large.csv
│
├── 📂 notebooks/
│   └── financial_data_eda.ipynb
│
├── 📂 images/
│   ├── debit_distribution.png
│   ├── outlier_analysis.png
│   ├── department_comparison.png
│   └── general_ledger_dashboard.png
│
├── 📄 README.md
└── 📄 requirements.txt
```

*Update the filenames and folders to match the actual repository.*

## 🚀 9. How to Run

### Step 1: Clone the repository

```bash
git clone <your-repository-url>
cd Exploratory-Data-Analysis-for-Financial-Data
```

### Step 2: Install dependencies

```bash
pip install -r requirements.txt
```

Alternatively:

```bash
pip install pandas polars seaborn matplotlib jupyter
```

### Step 3: Launch Jupyter Notebook

```bash
jupyter notebook
```

### Step 4: Run the analysis

Open the notebook in the `notebooks/` directory and execute the cells sequentially.

Make sure the dataset is stored in the expected `data/` directory before running the notebook.

## ⚠️ 10. Limitations

- The dataset is simulated and does not represent actual company financial information.
- Statistical outliers are not necessarily errors or fraudulent transactions.
- Z-score and IQR are screening techniques; flagged transactions require supporting documentation and further investigation before conclusions can be made.
- The project focuses on exploratory data analysis and preliminary risk identification rather than a complete financial audit.

---

## 👩‍💻 Project Focus

`Financial Data Analysis` · `Data Validation` · `Exploratory Data Analysis` · `Statistical Analysis` · `Outlier Detection` · `Data Visualization`

<p align="center">
  <i>Turning financial data into meaningful analytical insights.</i>
</p>
