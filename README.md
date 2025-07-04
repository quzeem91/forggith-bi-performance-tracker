# Forggith BI Performance Tracker 📈


## Project Background 📜
Forggith, a German-based pharmaceutical company operating on a B2B model, manufactures drugs distributed to consumers through their network of distributors. The company possesses a substantial dataset encompassing sales, targets, product type, distribution channel, and distributor information spanning four years.

This project undertakes a thorough analysis and synthesis of their data to develop Power BI reports, as per their requirements, aimed at informing their strategic, tactical, and operational decision-making.

---

<details>
<summary> Click to view Forggith’s reporting requirements</summary>

![Report requirements](./Snapshots/Report_requirement.png)

</details>

---

Insights and recommendations are provided in the following key areas:

- **Distributor Contribution:** Analyze revenue and volume contributions by distributors across the years.

- **Product Performance:** Analyze revenue and volume contributions from different product classes to identify key sales drivers and areas for strategic focus.

  
- **Sales Team Performance:** Evaluate the performance of the sales teams, focusing on achieved revenue, volume, and progress toward targets.

---
## Data Structure and Modeling 🛢

From the datasets provided, the **Sales** fact table contains **213,598 rows** spanning four years of transactions (2022–2025). A **multi-fact table modeling approach** was used due to differences in granularity between the Sales and Target datasets.
Below is a snapshot of the data model created:

![Data Model](./Snapshots/Data_model_snapshot.png)
<details>
<summary><ins>Why a multi-fact table approach was employed 💭</ins></summary>
<br>
The sales data and target data exist at different levels of granularity. Each row in the sales data represents a unique transaction by distributor, location, sales employee, and product ID, while the target data is defined at a monthly level by product and sales representative. Directly linking these two tables would create granularity conflicts and lead to incorrect aggregations. By modeling them as separate fact tables connected through shared dimensions, we preserve data integrity and enable accurate comparisons and performance metrics.
</details>

Before building the model, several data transformation steps were carried out using **Power Query**, including:

- Cleaning and standardizing field entries  
- Merging the 2023–2025 sales data with the 2022 records  
- Unpivoting the yearly columns in the Target dataset to match the Sales structure
- Writing a Python script to derive the State column from Latitude and Longitude coordinates using the Geopy library 

These steps ensured consistency and compatibility across all datasets used in the reporting model.

<details>
<summary>Download the Excel file containing DAX measures</summary>

Below is the Excel file containing all DAX measures used in the report, with clear descriptions. This file serves as documentation and can be incorporated into other models for reuse.

📎 [DAX Measures File](./Forggith_report_metric_and_measures.xlsx)
</details>

The final data model includes two fact tables — **FactSales** and **Target** — connected to shared dimension tables:

- `DimProduct`  
- `DimEmployee`  
- `DimLocation`  
- `DimChannel`  
- A generated `Calendar` table for time intelligence

---

## Executive Summary 📊

### Overview of Findings

Forggith Pharmaceuticals saw consistent revenue growth from 2022 to 2024, peaking at **$2.99 billion**, before falling slightly to **$2.78 billion** in 2025, though revenue exceeded targets each year. <br>

Sales volume and distributor count declined steadily, with active distributors halving from **14** in 2022 to **7** by 2025, yet **90%** of total revenue was driven by just six distributors. This concentrated revenue reliance, paired with shrinking distribution, signals potential risk to sustained growth.

Below is the **Sales Performance Overview** page from the Power BI dashboard. Additional report pages with further breakdowns are included throughout this report.

[![Sales Overview Dashboard](./Snapshots/Sales_updated.png)](https://app.powerbi.com/view?r=eyJrIjoiZjMxMDM5YWMtZGFjZi00NmNjLTk2ODEtNzkyZmEzYjNlNDZjIiwidCI6IjczZmFkNzQwLTYwNzgtNDk5My04NTZhLTM0YzNjOThhYjlmZSJ9&pageName=115c6479416b24895d0a)

**Click the image above to interact with the live Sales Overview Dashboard.**


### Distributors 🚚

- **Distributor Count Decline:** Forggith Pharmaceuticals had a total of 16 distributors between 2022 and 2025. The number of active distributors declined each year, from 14 in 2022 to just 7 by 2025.

- **Revenue Resilience:** Despite the drop in distributors, overall revenue remained relatively unaffected. This is because the top 6 distributors alone accounted for 90% of the total revenue.

- **Emerging Risk:** If the trend of distributor loss continues, and any of the top contributors exit, a significant revenue decline is likely.

![Revenue by Distributors](./Snapshots/distributors_updated.png)


### Product Class Performance 💊

- Among the **6 product classes**, Analgesics, Antiseptics, and Mood Stabilizers are the top revenue drivers, contributing **20.25%, 18.87%, and 17.34%** respectively, together accounting for over **56%** of total revenue.

- Analgesics hit a revenue peak of **$662M** in 2024 but dipped below their historical average in 2025, aligning with the overall revenue slowdown.

- Analgesics also led in quantity sold (5.4M units), followed closely by Antiseptics (5.3M) and Mood Stabilizers (5M), despite fewer total orders.

- Antimalarials sold more units (4.1M) than Antipyretics (4M) and Antibiotics (3.9M), yet generated the least revenue overall, pointing to lower price points.

![Product Performance](./Snapshots/Product_performance.png)

### Sales Team Performance 🎯

- Delta team pulled the highest cumulative revenue at $3.4B, contributing 30% of total revenue, partly due to having **four** members, while other teams had **three**.
  However, the revenue dip in 2025 was most evident in the Delta team, as they achieved only 96.80% of their target, with 2 of 4 members hitting their set individual targets.

- Charlie team, led by Manager **Alisha Cordwell**, followed with $2.73B (24% contribution) and stood out as the most efficient, achieving **150%** of their 2025 revenue target despite the broader market dip.

- Bravo team maintained consistent target achievements across the years but experienced a gradual decline, from **149.7%** in 2022 down to **114%** in 2025, which showed shrinking margins.

- Alpha team mirrored this pattern, dropping from 153% in 2022 to 109% in 2025, consistently meeting targets, but with declining year-over-year performance.

![Team Performance](./Snapshots/Rev_by_team.png)



Below is a Marketing Performance Dashboard developed for Forggith, enabling dynamic tracking of Revenue vs Target across years, product classes, and sales teams.


[![Marketing Perfomance Dashboard](./Snapshots/Marketing_perfromance.png)](https://app.powerbi.com/view?r=eyJrIjoiZjMxMDM5YWMtZGFjZi00NmNjLTk2ODEtNzkyZmEzYjNlNDZjIiwidCI6IjczZmFkNzQwLTYwNzgtNDk5My04NTZhLTM0YzNjOThhYjlmZSJ9&pageName=115c6479416b24895d0a)

---

## Recommendations for Forggith 💡

1. <ins>**Launch a Distributor Loyalty Programme**</ins>: Forggith should establish a comprehensive reward and recognition system to motivate and celebrate distributor performance. Contributions will be tracked across several key areas, including revenue generated, product class performance, order volume, and geographic coverage. At the end of each fiscal year (or at the start of a new one), Forggith will host a prestigious **Distributor Loyalty Awards Night**, inviting all active distributors to celebrate shared successes. Awards and gifts will be presented across various categories, including:

 - **Product Class Champion**: For top revenue contribution in specific product categories.
 - **Order Volume Leader**: For the highest number of purchase orders fulfilled.
 - **Market Expansion Pioneer**:  For distributors who successfully penetrate new or underserved markets.
 - **Top New Distributor**: Recognizing new joiners who show strong early performance.

 This initiative will:

  - Help strengthen loyalty and recognition for high-performing partners.
  - Reignite engagement from dormant or underperforming distributors.
  - Drive targeted growth in lagging product classes.
  - Provide a strategic platform to introduce new products and share upcoming business goals.

2. <ins>**Expand the Sales Force Strategically**</ins>: Each sales team should be assigned an additional Sales Representative, supported by a structured onboarding process, and clearly defined KPIs focused on:
   
 - Acquiring new distributors in both existing and untapped territories
 - Reactivating lapsed distributors who have stopped engaging in recent years
  
 This strategic expansion will help mitigate the yearly decline of distributors and expand market penetration.

3. <ins>**Introduce Targeted Incentive For Reps and Managers**</ins>: Forggith should implement an incentive structure that rewards:

 - Individual sales reps for exceeding targets
 - Sales teams for collaborative success
 - Team managers for strategic leadership
 - Product-specific performance to drive focus on underperforming categories.
 This will aid Forggith in driving engagement, accountability, and performance across tiers.

4. <ins>**Facilitate Knowledge Sharing Across Teams**</ins>: Given Charlie team’s outstanding efficiency, under the leadership of **Alisha Cordwell**, Forggith should host periodic inter-team strategy seminars. These should:

 - Promote sharing of successful tactics and approaches
 - Encourage a collaborative “Team Forggith” culture
 - Help underperforming teams adopt proven strategies to improve outcomes

---

### Assumptions and Caveats 📝

1. The report content consists of two pages, Sales Performance Overview and Marketing Performance Overview, structured according to Forggith’s reporting requirements. Each page was designed to be concise and focused.

2. Sales data was provided at a **city-level granularity**, limiting state-level analysis. To enhance regional insights, a Python script using the Geopy library was written to derive the State from each location's Latitude and Longitude. This enriched location data was then exported and integrated into Power BI, enabling drill-down from State to City level. To access the Python file used to derive the state column, click [here](./Forggith%20RLS%20Enforced.ipynb).

3. Row-Level Security (RLS) was initially implemented with three roles: *Sales Rep, Manager, and Executive*, enabling role-based data access. However, publishing the report with these roles disabled the embed report link due to tenant restrictions. As a result, RLS was removed in this version. To access the PBIX file with RLS, click [here](./forggith_geolocation_state_extraction.pbix).
   
4. A total of 2,613 rows had negative quantity values, ranging from -1 to -7,200. Since these rows included key identifiers such as distributor name, customer name, location, and sales ID, they were retained, and the quantities were converted to positive values.
   
5. The U.S. dollar ($) was assumed as the currency for this report, as none was explicitly stated.



