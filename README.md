# 📊 Population Analysis Dashboard

A comprehensive data analytics project that processes over **11.56 Million records** to analyze regional population distributions, gender splits, and annual trends. This project showcases an end-to-end data pipeline built using **Microsoft Excel**, **SQL Server**, and **Power BI (DAX)**.

---

## 🖥️ Dashboard Preview

![Population Analysis Dashboard](PASTE_YOUR_IMAGE_LINK_HERE)

> *Tip: To add your image here on GitHub, just edit this file, delete "PASTE_YOUR_IMAGE_LINK_HERE", and drag-and-drop your dashboard screenshot directly into this space!*

---

## 🛠️ Data Preparation & Cleaning Workflow

To ensure data integrity and total accuracy, the raw dataset went through a rigorous three-stage cleaning pipeline:

### 1. Microsoft Excel (Initial Ingestion & Audit)
* 🔍 **Data Assessment:** Reviewed the raw structure to understand row and column constraints.
* 🧹 **Blank Handling:** Found and isolated incomplete records using *Go To Special > Blanks*.
* 🚫 **Deduplication:** Applied *Remove Duplicates* on unique IDs to avoid double-counting.

### 2. SQL Server (Data Standardization)
* 🔠 **Text Normalization:** Used `TRIM()` and `UPPER()` to fix extra spacing issues (e.g., fixing `"BATANGAS "` to `"BATANGAS"`).
* 🔢 **Type Casting:** Cast the population column as an integer (`INT`) data type instead of text for mathematical calculations.
* 🛑 **Null Filtering:** Filtered out irregular values using queries before loading the database.

### 3. Power BI (Data Modeling & DAX)
* 🗂️ **Logical Sorting:** Used the *Sort by Column* feature to arrange regions and years in proper chronological order.
* 🧮 **Dynamic DAX Measures:** Created dynamic calculations for real-time filtering:
  ```dax
  Total Population = SUM('Population Data'[Sum of Population])
  ```
  ```dax
  Male Population = CALCULATE(SUM('Population Data'[Sum of Population]), 'Population Data'[Gender] = "Male")
  ```

---

## 🎯 Key Findings & Insights

* 👥 **Overall Profile:** Analyzed **11.56 Million people** across **133 unique regions** and sub-areas.
* 🚻 **Gender Distribution:** Males outnumber females consistently across the dataset, making up **6.02 Million (52.07%)** compared to females at **5.54 Million (47.93%)**.
* 📍 **Top Density Hubs:** **Batangas** records the highest population, followed closely by **Bukidnon** and **Albay**.
* 📉 **Population Trend:** The line chart reveals a clear **downward trajectory** starting from the year **2020 towards 2023 and 2021**.

---

## 💡 Strategic Recommendations

1. 💰 **Targeted Resource Allocation:** Focus government budgets, economic infrastructure, and healthcare resources on high-density hubs like Batangas, Bukidnon, and Albay.
2. 🔬 **Investigate Population Decline:** Conduct a deeper study on the post-2020 population drop to understand if it is caused by migration, lower birth rates, or registration issues.
3. 👔 **Demographic Programming:** Align job creation and social programs with the prominent 52.07% male sector (e.g., agriculture and industrial work) while maintaining strong support for female welfare.
