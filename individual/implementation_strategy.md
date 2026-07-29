# Track 2 – How does a recommendation become reality?

## What would be implemented
Based on our churn modeling, feature engineering, and customer segmentation, our team recommended implementing a targeted retention program focused on the customers with the highest predicted churn risk. Our CatBoost model (ROC–AUC = 0.896) consistently identified short‑tenure customers, month‑to‑month contract holders, customers without tech support, and fiber‑optic users with high performance expectations as the most vulnerable groups. 

In practice, the implementation would involve:
- Early‑tenure onboarding support during the 3–6 month “danger window”
- Proactive outreach to customers lacking tech support
- Personalized offers such as simplified plans or unlimited data upgrades
- Tailored messaging based on cluster membership (Cluster 1, 2, or 0)
- CRM‑integrated churn alerts for real‑time intervention

This recommendation directly reflects the behavioral patterns, nonlinear interactions, and cluster profiles uncovered in our analysis.

## Success metric and baseline
The primary success metric would be a reduction in churn among the high‑risk customers identified by the model.  
Our dataset showed a baseline churn rate of **26.54%**, meaning more than one in four customers leave the service.

A metric we would not want to worsen is **average revenue per user (ARPU)**. While incentives can reduce churn, they can also reduce revenue if discounts are too aggressive or poorly targeted. We also want to avoid increasing **support call volume**, since operational strain could reduce service quality and customer satisfaction.

## Measuring impact and risks
We would measure impact using a controlled A/B test or phased rollout. One group of high‑risk customers would receive the retention intervention (e.g., onboarding outreach, unlimited data upgrade, proactive tech support), while a matched control group would not. After a defined period, we would compare churn rates, plan upgrades, service usage, and customer satisfaction between the groups.

Two risks or unintended consequences include:

1. **Incentive overuse or “training” customers to wait for offers.**  
   If customers learn that threatening to cancel leads to discounts, long‑term revenue may decline and customer behavior may shift in unintended ways.

2. **Operational overload and inconsistent execution.**  
   If too many customers are flagged as high‑risk at once, support teams may not have capacity to deliver personalized outreach, reducing the effectiveness of the intervention and potentially harming customer experience.

To mitigate these risks, we would:
- Prioritize the highest‑risk customers first (e.g., top 10–20% risk scores)
- Cap incentive frequency and ensure offers follow clear business rules
- Use segmentation insights to tailor interventions:
  - **Cluster 1:** onboarding + simplified plans  
  - **Cluster 2:** loyalty rewards + upsell opportunities  
  - **Cluster 0:** VIP support + proactive issue resolution  
- Monitor operational load and adjust outreach volume accordingly


