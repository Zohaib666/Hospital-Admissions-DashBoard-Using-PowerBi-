# Hospital Performance Dashboard

This Power BI project analyzes hospital performance metrics to provide actionable insights into patient outcomes, department loads, and overall trends. The dataset includes details such as admission/discharge dates, patient outcomes, departments, and readmissions.

## 📊 Dashboard Overview

The dashboard provides insights on the following key areas:

- **Hospital Performance**
- **Mortality Rate**
- **Readmission Rate**
- **Department Load**
- **Patient Outcomes**
- **Trends by Month**

## 📁 Dataset

The data used includes columns such as:

- `Patient_ID`
- `Department`
- `Admission_Date`
- `Discharge_Date`
- `Discharge_Status`
- `Readmission_Within_30_Days`

## 🧮 Calculated Columns & Measures

### ➕ Columns (using Power Query)
- **Admit Month**  
  Extracted from `Admission_Date` using:
  ```m
  = Date.MonthName([Admission_Date])
Stay_Duration
Calculated as:

m
Copy
Edit
= Duration.Days([Discharge_Date] - [Admission_Date])
📐 Measures (using DAX)
Mortality Rate

DAX
Copy
Edit
MortalityRate = 
DIVIDE(
    CALCULATE(COUNTROWS('YourTable'), 'YourTable'[Discharge_Status] = "Expired"),
    COUNTROWS('YourTable')
)
Readmission Rate

DAX
Copy
Edit
ReadmissionRate = 
DIVIDE(
    CALCULATE(COUNTROWS('YourTable'), 'YourTable'[Readmission_Within_30_Days] = "Yes"),
    COUNTROWS('YourTable')
)
Tip: Format these measures as Percentages (Modeling > Format > %)

📈 Visualizations Used
Cards – Show KPI metrics like Mortality and Readmission Rates

Bar/Column Charts – Department load, Monthly trends

Pie Chart – Discharge Status distribution

Line Chart – Trend of Admissions or Discharges by Month

🧱 Report Layout (Sample)
Top Section

Mortality Rate (Card)

Readmission Rate (Card)

Middle Section

Bar Chart: Patient Count by Department

Line Chart: Monthly Admissions Trend

Bottom Section

Pie Chart: Discharge Status

Table: Patient Details or Outcomes

📦 Tools & Tech
Power BI Desktop

Power Query for transformations

DAX for KPI calculations

🧑‍💻 Author
Zohaib Hassan

Power BI Developer | Data Analyst

📝 License
This project is for educational and learning purposes.


<img width="598" height="332" alt="image" src="https://github.com/user-attachments/assets/68d517e0-7ce4-4d07-98c1-2820e8548069" />
