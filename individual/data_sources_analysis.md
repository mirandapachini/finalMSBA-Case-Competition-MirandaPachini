# Track 1 – Where does the data come from?

## Source Tables

In a real telecom company, churn prediction would rely on several core operational data sources. Based on our project, the 3–5 most important source tables would be:

### 1. **Customer Table**
- **One row represents:** one customer  
- **Contains:** demographic information, tenure, contract type, dependents, referrals  
- **Why it matters:** captures long‑term relationship indicators and early‑tenure churn risk

### 2. **Account / Billing Table**
- **One row represents:** one billing cycle per customer or account  
- **Contains:** monthly fees, total billed, extra fees, payment history, billing issues  
- **Why it matters:** churn is strongly tied to billing consistency, perceived value, and unexpected charges

### 3. **Service Usage Table**
- **One row represents:** one customer’s service usage for a given period (e.g., monthly)  
- **Contains:** internet usage, phone usage, streaming usage, add‑on services  
- **Why it matters:** service intensity and product depth are strong stabilizers against churn

### 4. **Support / Tech Interaction Table**
- **One row represents:** one support ticket or tech support interaction  
- **Contains:** issue type, resolution time, number of support calls  
- **Why it matters:** customers without tech support or with unresolved issues churn at much higher rates

### 5. **Product / Plan Table**
- **One row represents:** one plan or service package  
- **Contains:** plan type, internet technology (fiber, DSL), add‑on availability  
- **Why it matters:** fiber customers and customers on month‑to‑month plans showed higher churn risk

---

## Keys to Connect the Data

A real telecom company would join these tables using consistent identifiers:

- **customer_id** → links customer table to account, usage, and support tables  
- **account_id** → links billing cycles and service plans  
- **date / billing_period** → aligns usage, billing, and churn timing  
- **service_id or plan_id** → connects customers to specific service offerings  

These keys ensure that each customer’s behavior, billing history, and service usage can be combined into a single modeling dataset.

---

## Two Risks and How to Reduce Them

### **Risk 1: Data Leakage (using information that occurs after churn)**
For example:
- Billing totals after the customer already left  
- Support tickets opened after cancellation  
- Usage dropping to zero because the customer already churned  

**Mitigation:**  
Use only features available **before** the churn date. Freeze feature windows (e.g., last 30 days before churn) and validate with time‑based splits.

---

### **Risk 2: Duplicates or Misaligned Keys**
Telecom systems often have:
- Multiple accounts per customer  
- Multiple billing cycles per month  
- Inconsistent customer IDs across systems  

**Mitigation:**  
- Deduplicate using business rules (e.g., latest active account)  
- Standardize customer_id across systems  
- Validate row counts and join quality before modeling  

---

### **Risk 3: Missing or Inconsistent Service Data**
Examples:
- Missing internet_tech values  
- Missing recent_offer fields  
- New customers with no billing history  

**Mitigation:**  
- Replace missing categorical values with meaningful labels (“none”)  
- Drop rows only when missingness is extremely low (e.g., <1%)  
- Use domain‑informed imputation rather than generic methods  

---

