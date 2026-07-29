# Track 3 – How to deploy and how predictions would be used in the real world

## Do we need churn predictions instantly or is overnight OK?
For a telecom company like TruSource, **overnight predictions are sufficient**. Churn is not an event that requires real‑time scoring; customers do not churn within minutes or hours. Instead, churn risk builds gradually based on tenure, billing patterns, service issues, and engagement. 

Running predictions overnight allows the company to:
- Refresh churn scores daily or weekly
- Push updated risk levels into CRM systems before business hours
- Give retention teams time to plan outreach
- Avoid the cost and complexity of real‑time infrastructure

Instant scoring would only be necessary if churn decisions happened in real time (e.g., during a cancellation call), but for this business case, **batch scoring is more efficient and operationally realistic**.

---

## Would this run on a schedule or on demand, and where would results be saved?
A real company would run churn predictions on a **scheduled batch process**, typically:
- **Nightly** (for daily updates), or  
- **Weekly** (if churn patterns change slowly)

The predictions would be saved in a centralized location accessible to business teams, such as:
- A **database table** (e.g., churn_scores table)
- A **CRM dashboard** (Salesforce, HubSpot, Microsoft Dynamics, Zoho)
- A **customer insights dashboard** used by retention and marketing teams

Each row would include:
- customer_id  
- churn_probability  
- risk_segment (e.g., high, medium, low)  
- date_scored  
- recommended action (optional)

This makes the predictions actionable for retention teams, marketing, and customer support.

---

## High‑level software approach
A realistic deployment approach for a telecom company would be:

### **Option 1: Scheduled Python Pipeline (most common)**
- A Python script loads the latest customer, billing, and service data
- Applies the same preprocessing steps used in training (feature engineering, encoding)
- Loads the trained CatBoost model
- Scores all active customers
- Writes predictions to a database table or CRM integration

### **Option 2: SQL + Python Hybrid**
- SQL handles feature creation and aggregation
- Python handles model scoring
- Results are written back to the warehouse

### **Option 3: API‑based scoring (only if needed)**
- A FastAPI/Flask service exposes a `/predict` endpoint  
- CRM or support tools call the API when needed  
- Useful for real‑time scoring during cancellation calls  

For this business case, **a scheduled Python job is the simplest and most realistic**.

---

## What would we monitor to trust the model over time?

A real company must monitor three categories of drift and quality issues:

### **1. Data Quality Check**
Ensure the input data is complete and consistent.
Examples:
- Missing values in key fields (tenure, monthly_fee, internet_tech)
- Sudden drops in row counts (e.g., missing billing cycles)
- Unexpected new categories (e.g., new plan types)

If data quality breaks, predictions become unreliable.

---

### **2. Input Drift Check (Feature Drift)**
Monitor whether the distribution of key features changes over time.
Examples:
- Tenure distribution shifts (e.g., more new customers)
- Monthly fees change due to new pricing plans
- Service counts change due to new bundles

If the model was trained on old patterns, drift can reduce accuracy.

Tools:  
- Population Stability Index (PSI)  
- KL divergence  
- Rolling feature histograms  

---

### **3. Outcome Check (Performance Monitoring)**
Compare predicted churn risk to actual churn outcomes.
Examples:
- Are high‑risk customers actually churning more often?
- Is the model’s AUC dropping over time?
- Are certain segments (e.g., fiber customers) becoming less predictable?

If performance declines, the model may need retraining.

---

## Summary
A real‑world deployment of the churn model would use:
- **Overnight batch scoring**
- **Scheduled Python or SQL pipelines**
- **Database or CRM storage for predictions**
- **Monitoring for data quality, drift, and real‑world performance**

