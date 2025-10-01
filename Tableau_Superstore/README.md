# 📊 Superstore Visualization 

It showcases a range of analysis techniques (sets, bins, LODs, clustering, forecasts, geospatial, reference lines) and clean presentation patterns you can reuse in your own dashboards. The overview below maps each workbook view to a business question and the Tableau features it demonstrates. 

---
## 🧠 Project goals

* Build a compact, didactic gallery of Tableau techniques over retail sales data.
* Answer core commercial questions (top customers, unprofitable lines, regional trends, discount policies, shipping tradeoffs).
* Demonstrate analysis patterns you can lift into production dashboards.

---

## 🚀 What’s inside

### Renamed, clearer filenames

To make the repo self-explanatory, files are organized and renamed as follows:

```
.
├─ data/
│  └─ Additional_exercise.xlsx              
├─ tableau/
│  └─ Superstore-Analysis-Workbook.twb      
├─ docs/
│  └─ Superstore-Visualizations.pdf        
└─ README.md
```

> Notes
> • `Additional_exercise.xlsx` keeps its exact original name.
> • The PDF in `docs/` captures static exports of the workbook’s views for quick browsing.
> • The `.twb` workbook holds the interactive versions of all listed visuals.

---

## 🗂 Report pages & key views

Below, each view is summarized with the business question it answers and the Tableau features it highlights. (View titles match the renamed worksheet titles in the `.twb`.)

### 1) Category & Sub-Category Performance

* **Sales by Sub-Category (with Labels)** — “Where does revenue concentrate?”

  * *Techniques:* Sorted bars, nested category → subcategory, data labels.
* **Sales by Sub-Category Colored by Profit** — “Which big sellers underperform on margin?”

  * *Techniques:* Diverging color by Profit, dual encodings (size/label + color).
* **Profit vs Sales by Category (Side-by-Side)** — “Which categories are efficient?”

  * *Techniques:* Side-by-side bar layout; two measures aligned.

### 2) Grouping & Business Rules

* **Small Office Supplies (Manual Group)** — “Bundle long tail SKUs for quick reads.”

  * *Techniques:* Manual groups for category consolidation.
* **Rule-Based Group (IF/THEN)** — “Flag items programmatically as Small vs Other.”

  * *Techniques:* Calculated fields for dynamic grouping.

### 3) Customer Focus

* **Top-10 Customers (Static Set)** — “Who are the revenue anchors?”

  * *Techniques:* Static Set; bar chart colored by set membership.
* **Top-10 Customers Scatter: Sales vs Profit** — “Are top customers profitable?”

  * *Techniques:* Scatter, Set color, detail on Customer Name.

### 4) Profitability Classification

* **High-Profit (Static Threshold)** — “Which sub-categories exceed a fixed profit bar?”

  * *Techniques:* Boolean calc; conditional color; thresholding.
* **High-Profit (Dynamic Parameter)** — “How does the picture change if the bar moves?”

  * *Techniques:* Parameter control; dynamic calc; interactive segmentation.

### 5) Cost & P&L over Time

* **Cost Heatmap by Category/Sub-Category** — “Where do costs pile up?”

  * *Techniques:* Heatmap (color by Cost), labels for totals.
* **Profit Δ vs Prior Year (Year–Category–Sub-Category)** — “Where did profit improve or erode?”

  * *Techniques:* Table calc for YoY difference; dense matrix read.
* **Quarterly Sales by Category** — “Seasonality and category cyclicality?”

  * *Techniques:* Small multiples by category; time on columns.

### 6) Geography & Market Mix

* **US Map (Sales Size, Profit Color)** — “Which cities drive profit (or losses)?”

  * *Techniques:* Filled/point map, size=Sales, color=Profit; category filter.
* **Sales by Market with Reference Line** — “Which regions beat the average?”

  * *Techniques:* Reference line (average Sales); segmented stacked bars.
* **Segment Drop-Line: Profit vs Sales** — “How segments trade off growth vs margin?”

  * *Techniques:* Drop line; segment encoding (shape/detail).

### 7) Discounting & Clustering

* **K-Means: Sales vs Discount (by Sub-Category)** — “Are there distinct discount regimes?”

  * *Techniques:* Tableau clustering; color by cluster.
* **Avg Discount by Sub-Category (Cluster Bands)** — “Which sub-cats rely on heavier discounting?”

  * *Techniques:* Average marks; color by assigned cluster.

### 8) Forecast & Signals

* **Monthly Profit: Actual vs Forecast** — “Where are margins headed?”

  * *Techniques:* Built-in forecast; confidence bands; Month/Year dual timeline.

### 9) At-a-Glance & Diagnostics

* **Word Cloud (Sub-Category Frequency)** — “What dominates the assortment?”

  * *Techniques:* Text mark sizing; categorical overview.
* **Correlation: Profit vs Sales by Category** — “Are we buying revenue or healthy growth?”

  * *Techniques:* Per-category scatter with labeled correlation.
* **Shipping Cost vs Profit (by Priority & Category)** — “Does rush shipping erode margin?”

  * *Techniques:* Scatter with shape (Category), color (Priority).

### 10) Market x Category & Profit Over Time

* **Sales by Category × Market (Two Variants)** — “Which combinations carry the portfolio?”

  * *Techniques:* Trellis by Market; color by Market; category split.
* **Profit per Category by Year** — “Long-run margin trajectory per category”

  * *Techniques:* Year on columns; color=Profit; consistent scale.

> All views are captured in `docs/Superstore-Visualizations.pdf` for quick reference and in the `.twb` for interaction. 

---

## 🔧 How to run

1. **Open the workbook**

   * Install Tableau Desktop (2021.4+ recommended).
   * Open `tableau/Superstore-Analysis-Workbook.twb`.

2. **Connect data (if a view prompts for data)**

   * Use the built-in Superstore sample or point to `data/Additional_exercise.xlsx` when a worksheet references that file (the filename must remain exactly `Additional_exercise.xlsx`).
   * If Tableau asks to “Find Data Source,” browse to `/data` and select it.

3. **Recreate/inspect the visuals**

   * Open each worksheet listed above to interact with filters, parameters, clustering, and forecast options.

---

## 🔍 Data notes & assumptions

* Measures: **Sales**, **Profit**, **Cost**, **Discount**, **Shipping Cost**
* Dimensions: **Category**, **Sub-Category**, **Customer Name**, **Market**, **Segment**, **Order Date**, **Country/City**
* Time logic: YoY and quarterly views rely on discrete **Year/Quarter** from `Order Date`.
* Forecasts: Tableau’s built-in ETS model with default settings to keep the gallery reproducible. 

---

## 🧪 Reproduce (from scratch)

1. Launch Tableau → **Connect** to the Superstore sample (or `data/Additional_exercise.xlsx`).
2. Create calculated fields:

   * `HighProfitFlag` (static): `SUM([Profit]) > 100000`
   * `HighProfitThreshold` (parameter) + `HighProfit2`: `SUM([Profit]) > [HighProfitThreshold]`
3. Build views in the sequence listed above (bars → heatmaps → scatters → map → cluster → forecast).
4. Add **Reference Line** (Average Sales) on the Market view; **Drop Lines** on Segment scatter.
5. Create **Set** → `Top 10 Customers by Sales` and color by set membership.
6. Use **Analytics → Cluster** on the Sales vs Discount view to form 3–4 clusters.
7. Enable **Forecast** on the monthly Profit line.

*(Screens and final outputs correspond to the PDF export in `docs/`.)* 

---

## 📜 License

MIT for the workbook and README. Dataset terms follow Tableau’s Superstore sample licensing (or your organization’s internal license if you replace the data source).

---

### Change log

* **v1.0** — Initial release, repo structure cleanup, meaningful filenames, and comprehensive README.
