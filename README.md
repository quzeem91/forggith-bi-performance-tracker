# 📊 Forggith BI Performance Tracker

## 👋 Introduction

Hi, I'm Olamide Quzeem, an aspiring Data Analyst passionate about transforming raw data into actionable business insights. This Power BI project was developed to solve a real-world challenge for a fictional pharmaceutical company — Forggith Pharmaceuticals — and showcases my skills across the full data analytics pipeline: data cleaning, modeling, analysis, and visualization.

Whether you're a recruiter, hiring manager, or fellow data enthusiast, I invite you to explore this project. I built it with business impact, storytelling, and usability in mind.

---

## 🧠 Business Context

**Forggith Pharmaceuticals** is a Germany-based pharmaceutical manufacturing company that sells products through a distribution network. They don’t sell directly to retailers but maintain sales visibility via their Sales and Marketing teams.

To support smarter decision-making, Forggith requested a **2-page Power BI dashboard** tailored for:
- **Sales Executives**: for strategic KPIs
- **Team Leads**: for performance management
- **Sales Reps**: for personal tracking

The ask was clear — visualize both **Sales** and **Marketing performance**, allowing slicing by team, product, time, and more.

---

## 🎯 Objectives

- Monitor revenue and volume performance (monthly, YTD).
- Compare actuals to targets.
- Provide insights at team, product, rep, and channel levels.
- Build an intuitive dashboard for dynamic slicing and stakeholder navigation.

---

## 📂 About the Dataset

This project used synthetic yet realistic sales and marketing data, structured around:

- Revenue & Volume transactions
- Monthly Targets per Rep & Team
- Channel & Product hierarchies
- Team/Rep assignments over time

---

## 🧹 Data Cleaning & Transformation

- Performed in **Power Query**
- Removed inconsistencies and duplicates
- Normalized column types and formats
- Built a robust **date table** for time intelligence
- Filtered for relevant timeframes and active reps

---

## 🧱 Data Modeling

- Created a **star schema** with fact and dimension tables
- Modeled:
  - Sales
  - Volume
  - Targets
- Built relationships with:
  - Teams
  - Reps
  - Products
  - Channels
- Enabled **time intelligence** with a custom date table

---

## 📊 Report Pages

### 1. **Sales Performance Overview**
- Total Revenue
- Revenue vs Target (YTD & Monthly)
- MoM Revenue % Change
- Revenue by Product Class, Region, Channel
- Drill-downs by Team and Rep

### 2. **Marketing Performance**
- Revenue & Volume vs Target
- Contribution by Product Class
- Rep-level analysis
- Channel-specific breakdown

---

## 📌 Key KPIs Tracked

- Total Revenue
- YTD Revenue vs Target
- % Target Achieved
- Month-over-Month Revenue Change
- Volume & Revenue per Team, Rep, Channel

---

## 🔎 Key Insights

- Product Class 3 showed consistent underperformance, suggesting need for a strategic review.
- Certain reps and teams consistently over-delivered, indicating scalable best practices.
- The Open Market and Pharmacy channels drove the bulk of revenue.

---

## ✅ Recommendations

- Incentivize top reps and scale their practices across teams.
- Refocus marketing spend away from consistently underperforming product classes.
- Empower team leads with rep-level dashboards to monitor performance weekly.

---

## 🛠 Tools & Skills Demonstrated

- **Power BI Desktop & Power BI Service**
- **Power Query** for data transformation
- **DAX** for calculated measures and KPIs
- Multi-table Data Modeling
- UX/UI best practices: slicers, reference labels, card visuals
- Dashboard embedding and troubleshooting Pro license rendering issues

---

## 🔗 Interactive Report

> Click below to explore the full report (best on desktop):

[🔗 View Forggith Power BI Report](https://app.powerbi.com/view?r=eyJrIjoiZjMxMDM5YWMtZGFjZi00NmNjLTk2ODEtNzkyZmEzYjNlNDZjIiwidCI6IjczZmFkNzQwLTYwNzgtNDk5My04NTZhLTM0YzNjOThhYjlmZSJ9)

📄 [Download PDF version](./Report%20PDF%20Export/Forggith_Report.pdf)  
📊 [Download DAX Measures File](./Measures.xlsx)

---

## 🧠 What I Learned

- Building multi-fact table models in Power BI
- Applying advanced DAX (YTD, MoM, % Target)
- Designing for usability and performance
- Troubleshooting Pro license limitations in embedded dashboards
- Using visual storytelling for business alignment

---

## 🪜 What's Next

- Add forecasting based on historical trends.
- Introduce row-level security for individualized views.
- Automate underperformance alerts via Power BI Service.

---

## 🙌 Final Note

This project reflects how I approach analytics — combining technical fluency with business understanding and a drive to tell stories that stakeholders care about.

If you're hiring for an **Entry-Level or Junior Data Analyst** who can hit the ground running with Power BI, DAX, and a strategic mindset, I’d love to hear from you.

---

## 📬 Contact

- **LinkedIn**: [linkedin.com/in/yourprofile](#)
- **Email**: [youremail@example.com](#)

Thanks for reading 🙌
