# Tiphaine Levan — Analytics & Visualization Portfolio

Welcome! This portfolio brings together three end-to-end data projects that highlight my ability to **clean, model, and visualize** data to drive decisions. Across the work, I’ve designed **60+ production-ready visuals** and multi-page dashboards in **Power BI** and **Tableau**, supported by clear methods, documentation, and reproducibility.

---

## 🚀 What this portfolio shows (at a glance)

* **Scope & depth:** 3 projects · **60+ visuals** · multi-page dashboards · geospatial analysis · forecasting · clustering · parameterized what-ifs.
* **Data scale:** Up to **900k rows** (Vestiaire → engineered down to ~450k for compute).
* **Methods:** Feature engineering, dimensional modeling, DAX measures, Power Query transforms, Tableau sets/parameters/LODs, quick tree model (sanity check) ~**0.8 accuracy**.
* **Outcomes:** Actionable insights on **conversion drivers**, **pricing vs. condition**, **brand mix**, **seasonality**, and **regional performance**.
* **Communication:** Executive-ready slides, annotated dashboards, and README guides for fast handoff.

---

## 👜 Project 1 — Vestiaire Collective: Product & Seller Analytics (Power BI + Slides)

**Goal:** Understand **what drives items to sell** and how sellers can optimize listings.

**Highlights**

* **Data:** `Vestiaire_Collective_Dataset` (products + sellers); label extract `sold_true`.
* **Engineering:** Condition/material groupings, authentication & badge flags, seasonality, engagement proxies (likes).
* **Model (quick check):** Decision tree on `sold` (~**0.8** accuracy) to rank drivers.
* **Visuals built:** **10** core visuals

  * Product lens (Power BI): sell-through by condition; material×sold; category performance; seasonality; brand split; price vs condition; gender mix.
  * Seller lens (deck/Tableau-style): badge effects; location clusters; engagement vs outcomes.
* **Key takeaways:**

  * **Condition is king**: ~**70%** of sales from “Very good”/“Never worn.”
  * **Brand-market mismatch** creates unsold pockets; refine brand mix and pricing ladders.
  * **Seasonality & materials** meaningfully affect conversion; time listings and price accordingly.

**Open next:**

* Data folder (Dropbox) and Power BI dashboards (see links in your repo’s *Data/Access* sections).

---

## 🧪 Project 2 — AdventureWorks: Reproducible Power BI Dashboards

**Goal:** Build clean, performant **Power BI** models from Excel, with DAX measures and polished visuals.

**Highlights**

* **Data ops:** Power Query (**Change Type**, **Group By**, **Custom Columns**, column quality checks).
* **Modeling:** Star-style relationships (OrderDate ↔ Calendar, then ShipDate), KPI measures.
* **Visuals built:** **~28** across two PBIX builds (Session dashboards & modeling exercises)

  * KPIs, time-series with **trend + forecast**, category mix donut, top-category bars, tables, **map** with bubbles.
  * Advanced pages with medians, 90th-percentile reference lines, relationship switching (Order vs Ship date), and combo charts.
* **What it proves:** I can **stand up a BI model** from raw files, enforce data types, build measures, and deliver multi-page dashboards with correct filtering, formatting, and interactivity.

**Open next:**

* PBIX files and exported PDFs for a quick scan of the final pages.

---

## 🛒 Project 3 — Superstore: Tableau Technique Gallery

**Goal:** Compact, didactic gallery of Tableau patterns tied to real business questions.

**Highlights**

* **Techniques:** sets, bins, clustering, **parameters** (dynamic thresholds), **forecasting**, geospatial, reference/median lines.
* **Visuals built:** **23** named worksheets across 10 themes

  * Category & sub-category performance (profit-colored bars), customer sets (Top-10), profitability thresholds (static + parameterized), cost heatmaps, YoY deltas, **US map** (profit vs sales), market reference lines, discount **clustering**, monthly **forecast**, word cloud, correlation diagnostics, shipping-profit trade-offs.
* **What it proves:** I use Tableau beyond “pretty charts”—parameterized analysis, clustering, and multi-view storytelling that answers concrete questions.

**Open next:**

* `Superstore-Analysis-Workbook.twb` and the `Superstore-Visualizations.pdf` gallery.

---

## 📈 Visuals & Deliverables — Tally

* **Vestiaire Collective:** **10** visuals
* **AdventureWorks (Power BI):** **~28** visuals
* **Superstore (Tableau):** **23** visuals
  **→ Total:** **60+ visuals** across 3 projects (maps, forecasts, clusters, KPI cards, diagnostics, parameterized scenarios).

---

## 🔗 Access & Repro

* **Data (Dropbox):** Use the shared folder links in the repo’s *Data Access* section (`dl=1` for direct download).
* **Power BI:** Open `.pbix` in **Power BI Desktop** → point to local data if prompted.
* **Tableau:** Open `.twb` (Tableau Desktop 2021.4+).
* **Reproduce:** Each project folder includes steps to connect data, run transforms, and rebuild visuals.

---

## 💡 Why this matters (for leadership)

* **Decision-ready**: I translate messy data into **clear, quantified insights** (e.g., 70% sales in top two conditions) that managers can act on.
* **Speed + rigor**: I design models that refresh cleanly, document assumptions, and package dashboards for **fast adoption** by non-technical stakeholders.
* **Scalable habits**: Naming conventions, modular measures, parameterized thresholds, and README guides ensure **handoff-friendly** analytics.
* **Range**: From **marketplaces** (conversion, pricing, seasonality) to **retail sales** (P&L, category mix), the toolkit adapts—Power BI for operations, Tableau for exploration and storytelling.

---

### Contact

If this resonates, I’m excited to discuss how I can replicate these results on your data—faster, cleaner, and with business impact front and center.
