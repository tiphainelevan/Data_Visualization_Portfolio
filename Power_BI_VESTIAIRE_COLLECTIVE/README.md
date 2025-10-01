# Vestiaire Collective — Product & Seller Analytics (README)

This repo explores **what drives an item to sell on Vestiaire Collective** and how sellers can optimize listings. It couples data prep + lightweight modeling with **Power BI** dashboards (product lens) and **Tableau/slide** storytelling (seller lens). 

---

## 🎯 Goals

* Identify **factors associated with the “sold” outcome** (True/False).
* Surface **brand, condition, material, season, and category** patterns tied to conversion.
* Examine **seller signals** (badges, followers, geography, pricing behaviors) that correlate with sales.
* Translate findings into **actionable recommendations** for inventory, pricing, and merchandising. 

---

## 📦 Data sources

* `Vestiaire_Collective_Dataset.xlsx` — main dataset (products + sellers; 900k rows originally; reduced to ~450k for compute).
* `sold_true.xlsx` — convenience extract for the binary target and key features.
* `vestiaire_collectif_power_bi.pdf` — static exports of the product dashboards built in Power BI.
* `Vestiaire Collective Presentation (1) (3).pdf` — project deck (context, methods, seller insights, and recommendations).  

> Notes
>
> * Data reduction used random sampling to 450k rows due to hardware limits.
> * A simple **decision tree** on `sold` achieved ~**0.8 accuracy** as a sanity check and feature scoping step. 

---

## 🧪 Methods (high level)

* **Cleaning & grouping:** consolidated sparse dimensions (e.g., **color, material, brand**) via IF/AND rules.
* **Feature engineering:** authentication flag, badge tiers, popularity proxies (likes), seasonal grouping.
* **Exploration:** brand popularity vs. sell-through, price vs. condition, material × condition mixes, category/season imbalance.
* **Modeling (quick check):** decision tree classifier on `sold` to rank driver importance and validate patterns. 

---

## 📊 Dashboards & visuals

**Product lens (Power BI):**

* **Sell-through by condition** → *“Very good”* and *“Never worn”* dominate successful sales; poorer conditions trail. 
* **Material × sold** → natural fabrics (leather, cotton, silk, wool) appear most frequently among sold items; plastic behaves differently (best when *never worn*). 
* **Category performance** → women’s shoes/clothing lead sold counts; men’s clothing over-indexes in **unsold** inventory. 
* **Seasonality** → unsold stock skews toward **Autumn/Winter**; sold skew differs. 
* **Brand split** → Gucci tops both listings and sold; **brand disparity** exists (e.g., Burberry has many listings but relatively fewer sold vs. Prada). 
* **Price vs. condition** → price must align with condition; mispricing (e.g., high price in *fair* condition) correlates with non-sale. 
* **Gender mix** → slightly more women’s items listed; women’s items sell at a higher share. 

**Seller lens (deck/Tableau):**

* **Badges & trust** → *Trusted/Expert* sellers convert better; there are far more *Common* sellers, but badge presence is advantageous. 
* **Location** → top seller performance clusters in **France, Italy, UK, US**. 
* **Engagement** → more followers ≠ guaranteed engagement; quality signals matter. 

---

## 🔑 Key insights

* **Condition is king:** ~**70%** of sales come from *“Very good”* & *“Never worn”*—price accordingly. 
* **Brand-market mismatch:** supply (listings) doesn’t always match demand (sold), creating unsold pockets (e.g., Burberry vs. Prada). 
* **Materials matter:** natural materials track better with buyer expectations; plastics sell best when *never worn*. 
* **Seasonal imbalance:** surplus **Autumn/Winter** inventory among unsold items suggests timing/merchandising opportunities. 
* **Seller signals:** **Trusted** badge and professional listing behaviors correlate with sales lift. 

---

## ✅ Recommendations (from analysis)

1. **Price to condition:** ensure price ladders reflect item state (avoid premium pricing on *fair/good* condition). 
2. **Rebalance brand mix:** temper oversupply in lagging brands; replicate **partnership playbooks** beyond Gucci. 
3. **Nudge listing timing:** seasonal prompts (e.g., push **summer dresses** pre-season) to lift conversion on lagging categories. 
4. **Seller enablement:** promote badge pathways; share **personalized tips** based on likes, materials, and past sell-through. 

---

## 🗂 Repo structure 

```
data/
  Vestiaire_Collective_Dataset.xlsx
  sold_true.xlsx
dashboards/
  vestiaire_collectif_power_bi.pdf
docs/
  Vestiaire-Collective-Presentation.pdf
src/
  modeling/
  transforms/
README.md
```

---

## 🔧 Reproduce

* Open **Power BI Desktop** → connect to `Vestiaire_Collective_Dataset.xlsx` (or the prepared extracts) → explore visuals referenced in `vestiaire_collectif_power_bi.pdf`. 
* Review **methods & seller findings** in the deck: variable groupings, authentication flag, sampling rationale, quick tree model, and the final recommendations. 

---

*Prepared for INSY 442 — Data Analysis & Visualization. Authors: Lisa Gauthier, Tiphaine Levan, Nicole Lazarovici* 

