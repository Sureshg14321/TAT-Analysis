# 📊 TAT (Turn Around Time) Analytics Dashboard – Power BI

## 🚀 Project Overview
This project focuses on analyzing **Turn Around Time (TAT)** performance in laboratory operations.  
The dashboard helps identify operational bottlenecks, monitor SLA compliance, and improve efficiency.

---

## 🎯 Business Objectives
- Monitor total test volume and TAT compliance  
- Identify labs/departments with poor performance  
- Analyze impact of rejected, outsourced, and re-run tests  
- Track sample journey delays  
- Enable data-driven decision making  

---

## Data source
- 2TAT_Report(Over All TAT(Processing Centre Based))_24.11.25 to 30.11.25 1.xlsx 
- TAT_Report(Over All TAT(Processing Centre Based))_14.12.25 to 21.12.25 1.xlsx 
- 1TAT_Report(Over All TAT(Processing Centre Based))_17.11.25 to 23.11.25 1.xlsx

---

## Data Preparation 
- Removed inconsistencies using Trim and Clean functions
- Verified correct data types (Date, Numeric fields)
- Checked and handled missing values
- Ensured consistent naming across tables
  
---

## 📌 Key KPIs
- Total Tests Performed  
- Tests In TAT / Out TAT  
- % In TAT  
- Rejected Tests  
- Outsourced Tests  
- Tests on Hold  
- Re-run Tests  

---

## 📊 Dashboard Pages

---

### 🟦 1. Index Page (Navigation)
Provides a clean navigation interface for all dashboards.

---

### 🟦 2. Executive Summary
- KPI cards for overall performance  
- % In TAT trend over time  
- In TAT vs Out TAT distribution  

---

### 🟦 3. Performance Analysis
- Department-wise performance  
- Test-wise analysis  
- Processing center efficiency  

---

### 🟦 4. Geography Insights
- State-wise performance  
- City-level test distribution  
- Regional comparisons  

---

### 🟦 5. Sample Journey Analysis
- Hourly trends  
- SLA analysis  
- Stage-wise delay tracking  

---

## 🎛️ Filters & Interactivity
The dashboard includes dynamic slicers:  
- Booking Center  
- Department  
- Test Name  
- State  
- City    

All visuals are interactive and cross-filtered.

---

## 📐 DAX Measures (Sample)

```DAX
Total Tests = COUNT('Final_Data'[TestID])

Tests In TAT = CALCULATE(COUNTROWS(Final_Data),Final_Data[INOutTAT] = "In TAT")

% In TAT = DIVIDE([Tests In TAT], [Total Tests], 0)

Avg TAT = AVERAGE(Final_Data[TAT_Hours])

Hold Tests = SUM(Final_Data[Hold])

In TAT Count = CALCULATE(COUNTROWS(Final_Data),Final_Data[INOutTAT] = "In TAT")

Out TAT Count = CALCULATE(COUNTROWS(Final_Data),Final_Data[INOutTAT] = "Out TAT")

Outsourced Tests = CALCULATE(COUNTROWS(Final_Data),Final_Data[OutSource] = 1)

Rejected Tests = CALCULATE(COUNTROWS(Final_Data),Final_Data[IsSampleReject] = "Y")

Rerun Tests = CALCULATE(COUNTROWS(Final_Data),Final_Data[Rerun] = "Y")

Tests In TAT = CALCULATE(COUNTROWS(Final_Data),Final_Data[INOutTAT] = "In TAT")

Tests Out TAT = CALCULATE(COUNTROWS(Final_Data),Final_Data[INOutTAT] = "Out TAT")

Total TAT Completed = CALCULATE(SUM(Final_Data[TAT_Hours]),NOT(ISBLANK(Final_Data[ApprovedDateTime])))

```

---

## 🔍 Key Insights
The dashboard includes dynamic slicers:  
-  Certain departments show lower TAT compliance 
-  Specific processing centers contribute to delays  
-  Geographic variation exists in SLA performance  
-  Rejected and outsourced tests impact turnaround time

---

## 🔷 Conclusion

This project successfully demonstrates how Power BI can be used to transform raw laboratory data into meaningful insights for monitoring Turn Around Time (TAT) performance. 
By integrating multiple dimensions such as lab, department, test type, and geography, the dashboard provides a comprehensive view of operational efficiency.

---

## 📸 Screenshots

<img width="1366" height="768" alt="Index" src="https://github.com/user-attachments/assets/6cdcb863-b69e-4982-8f0b-f8906918635b" />


<img width="1366" height="768" alt="Summary" src="https://github.com/user-attachments/assets/73201909-313d-4845-aecc-02c466516369" />




