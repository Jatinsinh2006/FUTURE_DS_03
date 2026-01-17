# FUTURE_DS_03
# Marketing Funnel & Conversion Performance Dashboard

## 📊 Lead Conversion Analysis Using Bank Marketing Dataset

**Created By:** Jatinsinh Solanki  
**Tool:** Power BI Desktop  
**Dataset:** Bank Marketing Dataset (bank-full.csv / bank.csv)

---

## 🎯 Project Purpose

The purpose of this Power BI dashboard is to analyze the marketing funnel performance, measure lead conversion efficiency, and identify drop-off stages throughout the customer journey.

This project helps me understand:
- How many leads enter each stage
- Where the biggest drop-offs occur
- Which job types, age groups, and education levels convert the most
- Monthly conversion trends
- Effectiveness of contact methods (cellular, telephone, etc.)

---

## 🛠 Tools Used

- Power BI Desktop
- Power Query Editor
- DAX (Data Analysis Expressions)

---

## 📂 Dataset Overview

This project uses the **Bank Marketing Dataset** with the following important fields:

**bank.csv fields included:**
- age
- job
- marital
- education
- balance
- housing
- loan
- contact
- month
- duration
- campaign
- previous
- poutcome
- y (conversion: yes/no)

---

## 🧹 Data Cleaning

I performed the following data cleaning steps:
- Removed null values and inconsistent data
- Converted necessary fields to correct data types (age, month, duration)
- Created Age Groups (Young, Adult, Senior)
- Categorized job and education types
- Converted "y" to numeric for conversion analysis
- Removed duplicate customer entries
- Created new calculated columns and measures

---

## 📏 Key Metrics (DAX)

### Total Leads
```dax
Total Leads = COUNT(bank[age])
```

### Total Conversions
```dax
Total Conversions = CALCULATE(COUNT(bank[y]), bank[y] = "yes")
```

### Conversion %
```dax
Conversion % = DIVIDE([Total Conversions], [Total Leads])
```

### Interested Leads
```dax
Interested Leads = [Total Leads] - [Qualified Leads]
```

### Qualified Leads
```dax
Qualified Leads = CALCULATE(COUNT(bank[previous]), bank[previous] > 0)
```

### Drop-off 1 to 2
```dax
Dropoff 1 to 2 = DIVIDE([Total Leads] - [Interested Leads], [Total Leads])
```

### Drop-off 2 to 3
```dax
Dropoff 2 to 3 = DIVIDE([Interested Leads] - [Qualified Leads], [Interested Leads])
```

### Drop-off 3 to 4
```dax
Dropoff 3 to 4 = DIVIDE([Qualified Leads] - [Total Conversions], [Qualified Leads])
```

---

## 📊 Dashboard Features

### KPI Cards Included:
- Total Leads
- Total Conversions
- Qualified Leads
- Drop-off Stage 1 to 2
- Drop-off Stage 2 to 3
- Drop-off Stage 3 to 4
- Conversion %

### Charts Included:
- **Bar Chart:** Converted by Job
- **Donut Chart:** Converted by Age Group
- **Line Chart:** Conversion % by Month
- **Funnel Chart:** Lead → Interested → Qualified → Converted
- **Treemap:** Campaign Contact Type (cellular, telephone, unknown)
- **Bar Chart:** Converted by Education
- **Matrix Table:** Job vs Age Group Conversions

---

## 🔍 Key Insights

Based on my dashboard analysis:

✅ Major drop-off occurs between Total Leads → Interested Leads  
✅ Technicians and Management roles convert the most  
✅ Adults account for more than 50% of all conversions  
✅ Cellular contact has the highest engagement  
✅ Conversion % gradually decreases month-by-month  
✅ Secondary education group converts the most

---

## 🎓 Skills Demonstrated

- Data Cleaning in Power Query
- Data Modeling in Power BI
- Advanced DAX Calculations
- KPI Design & UI Formatting
- Marketing Funnel Interpretation
- Analytical Storytelling

---

## 🌟 Support

⭐ If this project is useful, please star the repository!  
I appreciate your feedback and suggestions.

**Built by Jatinsinh Solanki** 📊
