# 👩‍💼 ScienceQtech – Employee Performance Mapping Using SQL

This project focuses on analyzing employee performance for **ScienceQtech**, a startup specializing in Data Science solutions including fraud detection, market basket analysis, self-driving cars, supply chain optimization, customer sentiment analysis, and drug discovery.

The HR department requested an in-depth employee performance mapping ahead of the annual appraisal cycle.  
As a **Junior Data Analyst**, the goal was to analyze employee data, evaluate job role alignment, compute bonuses, and generate insights using SQL.

---

## 🚀 Project Objective

- Analyze employee performance ratings  
- Compute salary ranges, bonuses, and experience-based role standards  
- Validate job role alignment with expected experience levels  
- Generate insights to support HR appraisal decisions  
- Evaluate departmental strengths and project assignments  
- Optimize database performance using indexing and structured queries  

---

# 🗂️ Dataset Overview

The project uses **three relational tables**:

---

## 📘 1. emp_record_table  
Contains comprehensive employee details.

**Columns:**  
`EMP_ID`, `FIRST_NAME`, `LAST_NAME`, `GENDER`, `ROLE`, `DEPT`,  
`EXP`, `COUNTRY`, `CONTINENT`, `SALARY`, `EMP_RATING`,  
`MANAGER_ID`, `PROJ_ID`

---

## 📗 2. proj_table  
Stores project-related information.

**Columns:**  
`PROJECT_ID`, `PROJ_NAME`, `DOMAIN`, `START_DATE`,  
`CLOSURE_DATE`, `DEV_QTR`, `STATUS`

---

## 📙 3. data_science_team  
A filtered subset of employees belonging to the Data Science department.

---

# 🧩 Tasks Completed

### ✔️ 1. Database & Table Creation  
- Created `employee` database  
- Imported all CSV datasets in MySQL

---

### ✔️ 2. ER Diagram Creation  
Designed an ERD illustrating relationships:

- `emp_record_table` ↔ `proj_table` (via `PROJ_ID`)  
- `emp_record_table` ↔ itself (via `MANAGER_ID`)  
- `data_science_team` as a subset table

---

### ✔️ 3. Department-Wise Employee List  
Queried basic details such as employee name, gender, department.

---

### ✔️ 4. Employee Rating Filters  
Extracted employees based on rating intervals:

- Ratings `< 2`  
- Ratings `2–4`  
- Ratings `> 4`

---

### ✔️ 5. Name Concatenation for Finance Department  
Merged `FIRST_NAME` + `LAST_NAME` as `NAME` for finance employees.

---

### ✔️ 6. Manager Identification  
Identified all managers and counted their direct reportees.

---

### ✔️ 7. UNION Query – Healthcare + Finance  
Combined employee lists from two departments using `UNION`.

---

### ✔️ 8. Group Employees by Department with Max Rating  
Grouped by department and extracted max rating within each group.

---

### ✔️ 9. Salary Range by Role  
Extracted `MIN()` and `MAX()` salary values role-wise.

---

### ✔️ 10. Rank Employees by Experience  
Applied ranking functions such as:

- `RANK()`  
- `DENSE_RANK()`

---

### ✔️ 11. View for High-Earning Employees  
Created a view for employees earning **> 6000**, grouped by country.

---

### ✔️ 12. Nested Query – Senior Employees  
Fetched employees with **> 10 years of experience** using subqueries.

---

### ✔️ 13. Stored Procedure – Experience > 3 Years  
Procedure outputs all employees with more than 3 years' experience.

---

### ✔️ 14. Stored Function – Validate Job Role Standards  
Experience-to-role mapping:

| Experience (Years) | Expected Role            |
|--------------------|--------------------------|
| ≤ 2                | Junior Data Scientist     |
| 2–5                | Associate Data Scientist  |
| 5–10               | Senior Data Scientist     |
| 10–12              | Lead Data Scientist       |
| 12–16              | Manager                   |

Compared expected roles with actual roles in `data_science_team`.

---

### ✔️ 15. Index Creation  
Created an index on `FIRST_NAME` (with prefix `FIRST_NAME(20)`) to optimize search speed.

---

### ✔️ 16. Bonus Calculation  
Bonus formula:

Bonus = 5% of Salary × Employee Rating
---

### ✔️ 17. Average Salary by Country & Continent  
Grouped employees region-wise to calculate average salaries.

---

# 📈 Insights & Observations

- Employee experience strongly correlates with expected job roles and compensation.  
- Rating patterns vary significantly across departments.  
- Some roles do **not** match expected experience standards → indicates training/promotion needs.  
- Managers with high reportee counts may require role restructuring.  
- Indexing significantly improves database search performance.  
- Bonus calculations inform HR financial planning.  

---

# 🏁 Conclusion

This project demonstrates the effective use of SQL for:

- Employee performance assessment  
- Organizational role mapping  
- HR appraisal insights  
- Salary and bonus evaluation  
- Database optimization and query efficiency  

Using ER modeling, SQL analytics, stored procedures, functions, and indexing, the project provides a complete performance-mapping solution for ScienceQtech’s HR department.

---


---
