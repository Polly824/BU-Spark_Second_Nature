# Are US Higher-Ed Institutions Actually Reducing Emissions?  
**Second Nature x UNH Sustainability Institute — BU Spark! / CDS DS539 (Fall 2024)**

**Team:** Pei Liu, Freda Peng, Neveah Zhan, **Polly (Haoyang) Peng**, …  
**Client:** Second Nature & Sustainability Institute at the University of New Hampshire  
**Advisors / PMs:** Abby Gualda, Makayla Tajalle, Sindhuja Kumar  
**Tech stack:** Python (Colab), Power BI / Tableau, Excel

---

## TL;DR

We analyzed Second Nature’s SIMAP-based carbon & nitrogen footprint data to answer:  
**Which colleges are actually making progress toward carbon neutrality, and why?**  
We cleaned, normalized, and visualized institution-level emissions (Scopes 1–3), goals, offsets, and renewable energy engagement, then produced a public-facing, interactive map to support policy, accountability, and trend discovery.

---

## Problem

Colleges and universities publish **reduction goals** and report **emissions inventories**, but:
- Reporting is **voluntary and inconsistent**
- **FERA** (fugitive emissions from refrigerants & air conditioning) was added recently, distorting trends
- Not all institutions track the same **scopes/sources**, or report on the same timelines

**Goal:** Identify structural factors (e.g., commuter vs. residential, institution type, state, public/private) that **help or hinder** progress toward stated sustainability goals—and **recommend how lagging institutions can catch up**.

---

## Core Questions We Answered

1. **Are higher-ed institutions reducing emissions overall?**  
2. **Did COVID (2020–2021) slow progress?**  
3. **Are schools meeting their listed reduction goals** (by state, institution type, public/private)?  
4. **What’s the most common baseline year** for these goals?  
5. **Progress by scope (1, 2, 3):** Which scopes are improving vs. worsening?  
6. **Offsets:** Who purchased them, when, where from, and how much?  
7. **Renewable energy engagement:** Which sources, how much, and how does it vary by region & institution type?

> **Additional (time-permitting) analysis:** Congressional districts & climate report cards, NCA regions, MSAs, weather normalization (HDD/CDD), enrollment & sq. footage normalization.

---

## Data

- **SIMAP Public Reporting** (Results by categories, scopes, totals; mitigation; goals)
- **Second Nature Member lists** (Sig, UC3, Affiliate, GCSE)
- **Institution metadata:** NCA region, endowment, full-time enrollment, congressional district, address/city pop., building square footage
- **Weather / climate:** Heating & cooling degree days (weekly/monthly, 2007–2024)
- **Congressional climate report cards** (PDF-scraped, pages 44–81)

---

## Methodology (high level)

1. **Data cleaning & joining**
   - Resolved name mismatches, missing years, inconsistent baseline/goal year definitions
   - Standardized scope/category nomenclature; flagged FERA-related anomalies
2. **Goal tracking logic**
   - **Strict target** view: goal met = target fully achieved  
   - **Progress-based** view (exploratory): quantify “partial success”
   - Removed goals where **goal end-year > (latest available year + 2)** (per client guidance)
   - Linear regression to estimate missing values within a 2-year window around goal years
3. **COVID impact analysis**
   - Compared pre-, during-, and post-COVID emissions when data allowed
   - Weighted for reporting completeness (some institutions skipped years)
4. **Visualization**
   - Interactive Tableau/Folium maps (state + institution views, filters by type, scope, offsets, etc.)
   - Leaderboards, heatmaps, scope-wise trend summaries

---

## Key Findings (high-level, redact/adjust as needed)

- **Most institutions are reducing emissions overall**, especially in **Scope 2 (purchased electricity)**.  
- **COVID did not universally slow progress**—~50% slowed, but many still reduced emissions.  
- **Goal achievement is mixed**: many institutions set ambitious targets but lag on **Scope 1 stationary fuel** reductions.  
- **FERA additions in 2023 significantly shifted some trends**, especially for states with larger infrastructure overhauls or methodology changes.  
- **Offsets**: Only **~70 institutions** reported purchasing offsets (2006–2023); **engagement spiked around 2015 and peaked in 2020**. A few schools (e.g., Louisville) are consistent leaders.  
- **Renewable energy engagement** varies significantly by state/type; **large public institutions** tend to lead, but **smaller schools** contribute proportionally and need **supportive policy mechanisms**.

---

## Public-Facing Visualization (Demo)

- **Interactive Tableau Map**: Explore emissions change, scope reductions, offsets, renewable energy sources  
- Filters: **state, public/private, institution type**  
- Storylines: Overview, by scope, offsets, renewable energy, COVID impact, goal achievement

> _Link (replace with your actual Tableau/public link once you upload):_  
> `https://public.tableau.com/...`

---

## My Role (Polly / Haoyang Peng)

- Led **scope-wise emissions reduction analysis** (trends, outliers, FERA impact)  
- Co-designed and **built the interactive Tableau map** for public consumption  
- Implemented **goal-achievement logic** (strict vs. progress-based, with regression fill-ins)  
- Contributed to **data cleaning, normalization strategy (FTE & GSF)**, and documentation  
- Co-authored the **final report & presentation**, presented key findings to the client

---

## 📂 Repo / Drive Deliverables

