
# 📊 Atlas Labs HR Analytics - Professional Business Intelligence Solution 🚀

> An end-to-end data analytics and business intelligence project built to evaluate workforce dynamics, employee performance trends, demographic distributions, and organizational attrition risks using **Power BI**, **Star Schema Modeling**, and **DAX**.

---

## 🖼️ Project Dashboards Preview
*(Here you can showcase your 4 core dashboard screenshots to give recruiters and visitors an immediate visual overview)*

### 1️⃣ Executive Overview Dashboard
> *High-level tracking of active headcount, total employee metrics, and overall company attrition benchmarks.*
<div align="center">

  
  <img width="629" height="356" alt="لقطة الشاشة 2026-09-21 011926" src="https://github.com/user-attachments/assets/396fbfe7-3167-4dec-9ce8-a0a558f6beaf" />

  
  <img width="635" height="356" alt="لقطة الشاشة 2026-09-21 012344" src="https://github.com/user-attachments/assets/09d3dc0e-14fc-41a2-b56d-4b564cc55a68" />

  
  <img width="633" height="360" alt="لقطة الشاشة 2026-09-21 012448" src="https://github.com/user-attachments/assets/3e042238-24d2-48a8-b950-fc2f8dd0d85a" />



<img width="635" height="356" alt="لقطة الشاشة 2026-09-21 012200" src="https://github.com/user-attachments/assets/1b38826e-943e-4576-91a3-382384cc0194" />


  <img width="748" height="380" alt="SCIMA" src="https://github.com/user-attachments/assets/ad4ce9f6-780b-4370-9f5e-4b1541cdf0a4" />

  

### 2️⃣ Demographics & Diversity Dashboard
> *Deep-dive workforce breakdown covering age distributions, gender diversity, marital status, and educational levels.*
<div align="center">
  <img src="path_to_your_screenshot_2.png" alt="Demographics Dashboard" width="100%"/>
</div>

### 3️⃣ Performance Tracker Dashboard
> *Comprehensive evaluation of employee review cycles, performance brackets, and productivity ratings.*
<div align="center">
  <img src="path_to_your_screenshot_3.png" alt="Performance Tracker Dashboard" width="100%"/>
</div>

### 4️⃣ Attrition & Turnover Analysis Dashboard
> *Investigative view identifying the root causes of employee turnover, department risk levels, and OverTime burnout impact.*
<div align="center">
  <img src="path_to_your_screenshot_4.png" alt="Attrition Analysis Dashboard" width="100%"/>
</div>

---

## 🎯 Project Overview & Objectives
The **Atlas Labs HR Analytics Project** transforms raw human resources data into actionable, executive-ready insights. The primary goal is to empower senior management with a clear diagnostic tool to monitor employee lifecycle, optimize retention strategies, and enhance overall organizational productivity.

---

## 🛠️ Tech Stack & Tools Used
* 📊 **Power BI Desktop:** For interactive data visualization and report design.
* 📐 **DAX (Data Analysis Expressions):** For building complex calculated measures and dynamic KPIs.
* 🗄️ **Star Schema Modeling:** To ensure optimal database relationships, query performance, and filter propagation.
* 🐙 **GitHub & Markdown:** For professional project documentation and portfolio presentation.

---

## 📐 Data Modeling & Architecture
The underlying data model relies on a clean, relational **Star Schema** to eliminate redundancy and maximize analytical speed:
* 🟢 **Fact Table:** `Fact Performance Rating` (capturing granular evaluation scores and satisfaction metrics).
* 🔵 **Dimension Tables:** 
  * `Dim Employee` (Core employee profile and demographic attributes)
  * `Dim Date` (Time-intelligence foundation)
  * `Dim Education Level` & `Dim Satisfaction Level` (Categorical metadata)
* 🔗 **Relationships:** Strict One-to-Many ($1:*$) relationship enforcement with optimized cross-filter directions.

---

## 💡 Advanced DAX Measures Implemented
Key formulas engineered to drive dynamic visuals and interactive KPI cards:

```dax
-- 1. Total Employees Count
TOTAL EMPLOYEE = DISTINCTCOUNT('Dim Employee'[EmployeeID])

-- 2. Active Workforce Headcount
ACTIVE EMPLOYEE = CALCULATE([TOTAL EMPLOYEE], 'Dim Employee'[Attrition] = "No")

-- 3. Inactive / Resigned Employees
IN ACTIVE EMPLOYEE = CALCULATE([TOTAL EMPLOYEE], 'Dim Employee'[Attrition] = "Yes")

-- 4. Organizational Attrition Rate
ATTRITION RATE = DIVIDE([IN ACTIVE EMPLOYEE], [TOTAL EMPLOYEE], 0)

-- 5. Average Performance Rating Score
Average Performance = AVERAGE('Fact Performance Rating'[PerformanceRating])
