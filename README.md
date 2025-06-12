# 🌦️ Seattle Weather Trends Dashboard (1948–2017)

This project presents a Power BI dashboard that visualizes Seattle’s weather patterns from 1948 to 2017. The dashboard helps users explore changes in temperature, rainfall trends, and the frequency of rainy days using simple and interactive visuals.

---

## 📁 Files Included

| File Name                                  | Description                                                   |
|-------------------------------------------|---------------------------------------------------------------|
| `Seattle_Weather_1948-2017_Dashboard.pbix` | Power BI file containing all visuals, data model, and DAX     |
| `Seattle_Weather_1948-2017_Data.csv`       | CSV file with original daily weather data from 1948 to 2017   |
| `Dashboard_Screenshot.png`                 | Image preview of the final Power BI dashboard                 |
| `README.md`                                | Project documentation (this file)                             |

---

## 📊 Dashboard Visuals

| Visual Type     | Title                            | Description                                                                 |
|------------------|----------------------------------|-----------------------------------------------------------------------------|
| 📈 Line Chart     | **Max & Min Temperature Over Time** | Displays yearly trends of maximum and minimum daily temperatures.           |
| ☁️ Bar Chart      | **Total Rainfall Per Year**        | Shows the sum of yearly precipitation (rainfall).                           |
| 📅 Slicer         | **Year & Month Filters**           | Enables filtering by specific year (dropdown) and month (button-style).     |
| 📉 Area Chart     | **Monthly Temperature Pattern**     | Shows average high and low temperatures for each month across all years.    |
| 🥧 Pie Chart      | **Days With and Without Rain**      | Visualizes the proportion of rainy vs. non-rainy days in the dataset.       |

---

## 🗂️ Dataset Details

Daily weather data is sourced for Seattle between **January 1, 1948**, and **December 31, 2017**.

### 🔹 Original Columns
- **DATE** – Observation date  
- **PRCP** – Daily precipitation (in inches)  
- **TMAX** – Maximum daily temperature (°F)  
- **TMIN** – Minimum daily temperature (°F)  
- **RAIN** – Boolean (TRUE/FALSE) indicating whether it rained that day  

### 🔸 Derived Columns (Created in Power BI)
- **Year** – Extracted from `DATE`  
- **Month** – Month abbreviation (e.g., Jan, Feb) from `DATE`  
- **Rain Status** – Categorizes days as `"Rainy"` or `"Not Rainy"` based on the `RAIN` column  

---

## 📌 Key Insights

- Seattle shows strong seasonal temperature patterns across decades.
- Some years had significantly more rainfall than others.
- Rain occurs more frequently in winter months.
- A large portion of days from 1948–2017 were classified as rainy.

---

## 🛠️ Tools & Techniques

- **Power BI** – Used for data modeling, transformation, and visualization  
- **DAX (Data Analysis Expressions)** – Used to create custom columns and logic  

### 📄 Example DAX Code:
```DAX
Rain Status = IF([RAIN] = TRUE(), "Rainy", "Not Rainy")
Year = YEAR([DATE])
Month = FORMAT([DATE], "MMM")

