# Individual Contribution

## What I Contributed Most To
I contributed heavily across the technical and analytical workflow, including:
- **Modeling and Feature Engineering**: I helped build and tune the CatBoost, XGBoost, Random Forest, and Decision Tree models. I worked on class imbalance handling, stratified sampling, and hyperparameter tuning. I also engineered key features such as service counts, billing averages, and service intensity.
- **Exploratory Data Analysis (EDA)**: I analyzed tenure patterns, monthly fees, service usage, billing behavior, and nonlinear interactions. I created visualizations that revealed early‑tenure churn, service count effects, and billing‑related churn drivers.
- **Clustering and Segmentation**: I performed PCA, selected k=3 using elbow and silhouette methods, and interpreted the cluster profiles. I helped define the business meaning of Cluster 1 (high‑risk), Cluster 2 (core customers), and Cluster 0 (high‑value customers).
- **Narrative Writing and Report Structure**: I wrote the majority of the analytical narrative, structured the report, created visuals for the slides, and translated technical findings into business‑ready insights. I also handled the business framing for the modeling, EDA, and segmentation sections.

The only major section I did not write was the executive summary, which another teammate completed.

---

## A Decision or Approach I Personally Advocated For
I strongly advocated for using **CatBoost as the final model** because:
- It handles categorical variables natively  
- It captured nonlinear interactions that other models missed  
- It achieved the highest ROC–AUC (0.896)  
- It aligned best with the business need to rank customers by churn risk  

I also pushed for **engineering service‑based features** (service counts, streaming counts, add‑on counts) because they revealed meaningful behavioral patterns that were not visible in the raw dataset.

Additionally, I advocated for **k=3 clustering** because it produced segments that were both analytically distinct and operationally actionable for retention strategy design.

---

## Lessons Learned and What I Would Improve With More Time
One lesson I learned is how important it is to connect technical modeling decisions to real business actions. The more we tied our findings to operational workflows—like onboarding, tech support, and CRM integration—the more valuable the analysis became.

If I had more time, I would:
- Build a **time‑based validation** to better simulate real‑world deployment  
- Incorporate **support ticket text data** or customer notes for richer behavioral signals  
- Test multiple **retention strategy simulations** to estimate ROI for each cluster  
- Automate the **feature engineering pipeline** to make the model easier to deploy  

Overall, this project strengthened my ability to combine technical modeling, data storytelling, and business strategy into a cohesive analytical solution.
