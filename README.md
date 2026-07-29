# MSBA Case Competition — TruSource Telecom Churn Prediction

## Why this project matters to employers
This repository showcases a complete end-to-end analytics solution for predicting customer churn in a subscription-based telecom business. It highlights my ability to translate business problems into data-driven insights, engineer predictive features, build and compare models, and turn results into actionable retention strategies.

Employers can use this project to evaluate my skills in:
- business problem framing and stakeholder communication
- exploratory data analysis and feature engineering
- supervised modeling and model validation
- customer segmentation and deployment planning
- clear documentation and organized delivery

## Project summary
TruSource faced a churn rate of **26.54%**. I built a pipeline to:
- analyze churn drivers across customer demographics, service usage, and billing
- engineer meaningful features for customer behavior and service intensity
- evaluate multiple models and select the best-performing solution
- segment customers with clustering to make retention recommendations more actionable

The final model used **CatBoost** and earned an out-of-sample **ROC–AUC of 0.896**.

## What I delivered
This repository contains:
- `notebooks/telecom_churn_analysis.ipynb` — the full individual analysis and modeling workflow
- `notebooks/holdout_scoring.ipynb` — holdout scoring and unseen data results
- `projects/final-msba-case-competition/docs/personal_contribution.md` — my personal contribution summary
- `projects/final-msba-case-competition/docs/data_sources_analysis.md` — Track 1 business data source analysis
- `projects/final-msba-case-competition/docs/implementation_strategy.md` — Track 2 implementation and success metrics
- `projects/final-msba-case-competition/docs/deployment_recommendations.md` — Track 3 deployment and production usage plan
- `group/presentation/telecom_churn_presentation.pptx` — team presentation slides

## Skills demonstrated
- Python analytics and notebook development
- feature engineering for customer churn and billing signals
- model selection with Decision Tree, Random Forest, XGBoost, and CatBoost
- handling class imbalance and avoiding overfitting
- interpreting model output for business decisions
- customer segmentation with PCA and K-Means clustering
- business-focused recommendation development

## Business impact
The analysis identifies high-risk customer segments and retention levers, including:
- early-tenure customers on month-to-month contracts
- customers without tech support
- fiber-optic customers with billing or service dissatisfaction

Recommended actions focus on batch scoring, CRM integration, targeted outreach, and measuring churn reduction without sacrificing ARPU.

## What to look for first
Or view the curated project page for a recruiter-friendly layout: [projects/final-msba-case-competition/README.md](projects/final-msba-case-competition/README.md)
1. Open `notebooks/telecom_churn_analysis.ipynb` for the full data science workflow.
2. Review `projects/final-msba-case-competition/docs/personal_contribution.md` for the specific role I played.
3. Read `projects/final-msba-case-competition/docs/implementation_strategy.md` and `projects/final-msba-case-competition/docs/deployment_recommendations.md` for deployment-ready recommendations and operational thinking.
4. Open `group/presentation/telecom_churn_presentation.pptx` for the polished team summary.

## How to run
1. Install Python packages used in the notebook: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `catboost`.
2. Open the notebooks in Jupyter or VS Code.
3. Run cells from top to bottom to reproduce the analysis.

## Notes for future employers
This repository is intentionally organized for review:
- notebooks are separated from write-ups
- individual deliverables are easy to find
- business insights are distilled into short, employer-facing summaries
- the model and recommendations are grounded in measurable churn-reduction priorities

---

**Miranda Pachini**
MSBA Candidate, University of Louisville
Business Analytics & Predictive Modeling
