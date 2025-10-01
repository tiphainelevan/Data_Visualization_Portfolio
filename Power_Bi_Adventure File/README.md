# AdventureWorks Power BI

> Reproducible Power BI projects that connect to **AdventureWorks (Excel)**, clean and aggregate data in **Power Query**, and deliver **multi-page dashboards** with KPIs, trends, category mix, geo distribution, and interactive filtering. Built by following the in-class *AdventureWorks* exercises.

---
## 📦 Data Source
- Excel: *AdventureWorks exercise* (connected via **Get Data → Excel**)
---
# Project A — AdventureWorks Power BI: **Dashboard Build & Data Prep**

> Connect to AdventureWorks (Excel), clean & type-cast in Power Query, aggregate for performance, and publish a multi-page dashboard with KPIs, time series (with forecast), category mix, map, and interactive filters.

## 🎯 Objectives
- Connect to the AdventureWorks Excel workbook and stage tables for reporting.  
- Clean, type-cast, and enrich data in **Power Query**.  
- Aggregate transactions by **product**, **customer**, and **time** for fast visuals.  
- Publish a clear dashboard with **KPIs**, **time series (forecast)**, **category mix**, and a **map**.

## 🧰 Tech & Skills Demonstrated
- **Power BI Desktop** (model, visuals, formatting)
- **Power Query (M)**: choose/remove columns, keep/remove rows, sort, **Change Type**, **Group By**, **Custom Columns**, query naming, **Column Quality** checks
- **Data Modeling**: simple measures for KPIs and visuals
- **Visualization**: cards, **line (trend + forecast)**, donut, bar, table, **map** with bubble sizing/style
- **Interactivity**: Basic & Advanced filters (incl. **Year = 2015**)

## 🧽 Data Preparation (Power Query)
- Select/remove columns; keep/remove rows; sort as needed  
- **Change Type** for numeric/date fields  
- **Add Column → Custom Column** for derived attributes  
- Rename queries (e.g., `Product`)  
- Use **Column Quality** to validate Valid/Error/Empty, then fix issues  
- **Group By** examples:
  - Total Quantity by **ProductKey** from transaction-level sales (“Sales 4”)
  - Advanced group by **ProductKey + CustomerKey** (+ ShipDate when needed) for summarized facts
- Review sort ops (e.g., `Product 3 → Standard Cost → Sort Descending`) and finalize types  
- If a step is wrong, **Undo/Cancel Last Step** in *Applied Steps*

## 📊 Measures (DAX) for KPIs & Charts
```DAX
Sales Amount   := SUM(Sales[SalesAmount])
Order Quantity := SUM(Sales[OrderQuantity])
```
## 🗂 Report Pages

### Dashboard Exercise 1
- Sales vs Budget analysis by Year/Month
- Country-wise performance charts

### Dashboard Exercise 2
- Order counts by Month/Country/Fiscal Year
- Stacked bar charts with fiscal year breakdown

### Dashboard Exercise 3
- Category performance analysis
- Education segment analysis
- Time series trends

## 📈 Visuals Built

### Core Metrics
- **Cards**: Sum of SalesAmount, Sum of OrderQuantity
- **Line (Time Series)**: X = OrderDate (collapse levels), Y = SalesAmount; variant with shaded area + zoom slider
- **Trend & Forecast**: Enable trend line + forecast on sales
- **Donut (Category Mix)**: Legend = Product Category, Values = SalesAmount; Bikes recolored blue
- **Bar (Top Categories)**: X = SalesAmount, Y = Category, with data labels
- **Table**: ProductName, Sum OrderQuantity

### Interactive Elements
- **Filters**: Basic on Accessories; Advanced on OrderDate → Year = 2015
- **Map**: Enable Map visuals (Options → Security); Location = Country; Bubble size = OrderQuantity; Dark style; orange bubbles

## 🧪 How to Reproduce

### Data Setup
1. Open Power BI Desktop → Get Data → Excel → select the AdventureWorks exercise file
2. In Power Query, apply transforms (Change Type, Group By, Custom Column, Rename, Quality checks)
3. Close & Apply

### Dashboard Creation
1. Create the DAX measures shown
2. Build visuals (cards, line+forecast, donut, bar, table, map) and apply filters (Accessories; Year=2015)
3. Arrange visuals across Dashboard Exercise 1–3

---

# Project B — AdventureWorks Power BI: Session 8 Dashboards & Data Modeling

## 🎯 Objectives

- Use a proper Date dimension to slice Sales/Budget
- Build KPI & analysis visuals with correct aggregation, sorting, formatting
- Use forecasting, trend lines, median/90th percentile reference lines, and filters
- Practice relationship switching (OrderDate → ShipDate) for different business questions

## 🧰 Tech & Skills Demonstrated

### Power BI Desktop
- Data Model view, Report view, formatting, filters, interactions

### Modeling
- Relationships Sales[OrderDate] ↔ Calendar[Date] (later ShipDate)

### DAX Measures
```dax
Total Orders = COUNT(Sales[SalesOrderNumber])
```

## 📊 Visual Analytics & Display

**Visual Analytics:** forecasts, trend lines, median/90th percentile refs, stacked & combo charts, hierarchy drill

**Display:** currency formatting, Month sorted by MonthNumber, Don't summarize for Year in tables

## 🔧 Data Model & Formatting

**Relationships:** Sales[OrderDate] → Calendar[Date] (Exercises 1–5); then Sales[ShipDate] → Calendar[Date] (Exercise 6)

**Formatting:** SalesAmount, BudgetAmount as Currency (US$, 2dp); Year not summarized; Month sorted by MonthNumber

## 📊 Visuals Built (by Exercise)

### Exercise 1 — Sales vs Budget, Year/Month
- Two tables: SalesAmount by Year (no summarize); copy for BudgetAmount
- Page filter: Year = 2016
- Add Month under Year (sort by MonthNumber)
- Country column chart: SalesAmount by Country

### Exercise 2 — Counts by Month/Country/Fiscal Year
- Orders by Month: column chart; set SalesOrderNumber to Count; labels on
- Total Orders measure used
- Stacked bar: Total Orders by Country, Legend = Fiscal Year

### Exercise 3 — Category Performance & Education Segments
- Bar: Sales by Category (labels inside center, orange)
- Bar: Avg Sales by Education for two levels (labels inside end, values as decimal, black bars)
- Line: SalesAmount by FiscalYear → FiscalQuarter
- Column: SalesAmount by Order Date filtered 2014-05-01 → 2015-10-01

### Exercise 4 — Product Hierarchy & Advanced Lines
- Build hierarchy: Category → Subcategory → Product Name
- Hierarchy bar filtered to Bikes
- Monthly line (MonthYearLong):
  - Chart 1: SalesAmount by MonthYearLong with Forecast = 12 months
  - Chart 2 (copy): remove forecast; add Median + 90th percentile reference lines (labels on) and a Trend line

### Exercise 5 — Multi-metric time views & Combo
- Line: SalesAmount and OrderQuantity by Year & Month; filter Jan–May
- Line + Stacked Column: SalesAmount + Sum OrderQuantity by Year & Month; filters Jan–May, 2015 & 2016; legend top-center; markers on

### Exercise 6 — Ship-Date analysis & styling
- Switch model to ShipDate
- Column: TotalProductCost and UnitPrice by Year & Month; filters 2015–2016, Sep–Dec
- Labels: inside center; then change Sum → Average for both
- Clean formatting: hide Y values/title, hide X title, remove legend

## 🧪 How to Reproduce

1. Open Power BI Desktop → Get Data → Excel → Session 8 workbook
2. In Model view, connect OrderDate to Calendar (Exercises 1–5)
3. Build visuals page-by-page (aggregation, sorting, formatting, filters as above)
4. Create Total Orders measure
5. For Exercise 6, switch relationship to ShipDate and adjust visuals
  
---

## 🗂 Repository Structure & Where to Find Things

Power_BI_Adventure File/  
├─ DATA/  
│ └─ AdventureWorks exercise (1).xlsx # Source data used by the PBIX files  
│  
├─ POWERBI_FILES/  
│ ├─ powerBI adventure file.pbix # Version 1 — full editable Power BI file  
│ └─ power bi aventure file 2.pbix # Version 2 — updated/iterated PBIX  
│  
├─ PDF_VIZ_FILES/  
│ ├─ powerBI adventure file.pdf # Printed/exported PDF of V1 dashboard  
│ └─ power bi aventure file 2.pdf # Printed/exported PDF of V2 dashboard  
│  
└─ README.md # You are here  

**Folder details**
- **DATA/** – Raw **Excel** input connected from Power BI (`Get Data → Excel`).  
  If you move/rename this file, update it in **Transform data → Data source settings**.
- **POWERBI_FILES/** – The **editable** projects (**.pbix**). Open in **Power BI Desktop** to view pages, visuals, DAX, and the model.  
  - `powerBI adventure file.pbix` → **Version 1** (baseline build)  
  - `power bi aventure file 2.pbix` → **Version 2** (refinements/extra visuals)  
  *Note:* the “aventure” spelling mirrors the uploaded filenames on purpose.
- **PDF_VIZ_FILES/** – **Printed/exported PDFs** of the corresponding PBIX for **quick overview** without Power BI.

**Navigate by goal**
- *Just want to see the dashboards?* Open the matching PDF in `PDF_VIZ_FILES/`.
- *Inspect/modify visuals, DAX, or the model?* Open the PBIX in `POWERBI_FILES/` (point it to `DATA/` if prompted).
- *Reuse with your own data?* Duplicate a PBIX, swap the Excel source (same schema), then **Refresh**.

---


