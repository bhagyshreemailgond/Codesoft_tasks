# Employee Data Analytics Project

A three-part data analytics project covering data cleaning, exploratory data analysis (EDA) and data visualization on an employee dataset.

**Tools:** Python, Pandas, Matplotlib, Seaborn, Jupyter Notebook, Power BI

---

## Project Structure

| File | Description |
|------|-------------|
| `employee_data_raw.csv` | Original messy dataset (63 rows, 7 columns) |
| `Task1_Data_Cleaning.ipynb` | Data cleaning and preprocessing notebook |
| `employee_data_cleaned.csv` | Cleaned dataset (60 rows) |
| `Task2_EDA.ipynb` | Exploratory data analysis notebook |
| `Task3_Visualization.ipynb` | Matplotlib/Seaborn charts and dashboard |
| `dashboard.png` | Static dashboard image |
| `Task3_Dashboard.pbix` | Interactive Power BI dashboard |

**Dataset columns:** employee_id, name, age, city, department, salary, join_date

---

## Task 1: Data Cleaning & Preprocessing

**Problems found in the raw data**
- Missing values: 6 in age, 3 in city, 1 in salary
- 3 duplicate rows
- Inconsistent text: mixed case and extra spaces in city and department (e.g. `" MUMBAI "`, `delhi`)
- 4 salaries stored as text with a `$` sign
- 10 dates written with `/` instead of `-`

**Steps taken**
1. Imported the CSV with Pandas and inspected it with `head()`, `info()` and `describe()`.
2. Standardized column names (lowercase, underscores).
3. Removed duplicate rows (63 to 60 rows).
4. Cleaned text columns (trimmed spaces, title case).
5. Converted data types: salary to numeric, join_date to datetime.
6. Filled missing age and salary with the **median** (robust to outliers) and missing city with `"Unknown"`.
7. Verified 0 missing values and 0 duplicates, then saved `employee_data_cleaned.csv`.

---

## Task 2: Exploratory Data Analysis

**Key findings**
- 60 employees across 5 departments; **Sales** is the largest (13), and the others are close (11 to 12).
- Average salary is about **74,983** and median is **78,000** (range 25,000 to 119,000).
- **Delhi** has the highest average salary (about 86,800) and **Pune** the lowest (about 59,900).
- **IT** has the highest median salary (93,500).
- Age and salary show **no correlation** (r = -0.02).
- No salary outliers were found using the IQR method.
- Hiring peaked in **2019 and 2022** (10 hires each).

**Conclusion:** Salary appears to depend more on department and city than on age. The dataset is small, so these trends are indicative rather than conclusive.

---

## Task 3: Data Visualization Dashboard

**Python charts (Matplotlib and Seaborn)**
- Bar chart: average salary by department
- Line chart: hires per year
- Pie chart: employees by department
- Histogram: salary distribution
- Scatter plot: age vs salary, colored by department
- Combined 2x2 dashboard saved as `dashboard.png`

**Power BI dashboard (bonus)**
- Bar, line, pie, column (salary bins) and scatter visuals
- Slicers for department and city, which filter every chart
- Cards for total employees and average salary

**Insights**
- IT has the highest average salary (about 83,900); Marketing the lowest (about 69,500).
- Employees are evenly spread across departments (18% to 22% each).
- Hiring is steady at 7 to 10 per year, with a dip to 7 in 2020.
- Salaries are spread evenly, with 14 employees earning 100,000 or more.
- Average pay by age group stays between about 71,000 and 79,000, so older staff do not earn more.

---

## How to Run

```bash
pip install pandas matplotlib seaborn notebook
jupyter notebook
```
Open the notebooks in order (Task 1, then 2, then 3). Open `Task3_Dashboard.pbix` with Power BI Desktop.

## Author
*Your Name* | Data Analytics Intern
