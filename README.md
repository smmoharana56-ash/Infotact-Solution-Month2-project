# SaaS & E-Commerce Cohort Retention & CLTV Analysis

## 📊 Executive Summary & Problem Statement
Acquiring new customers is up to five times more expensive than retaining existing ones. High-growth startups often celebrate rapid user acquisition milestones but fail to track whether those users actually stick around. If a business loses customers faster than it acquires them, it will inevitably collapse.

This project performs a deep-dive **Cohort Analysis** to evaluate user retention dynamics and calculate **Customer Lifetime Value (CLTV)**. By grouping users into cohorts based on their acquisition month, we isolate exactly when users churn, analyze behavior differences across segments (SaaS vs. E-Commerce), and provide data-backed strategic recommendations to maximize customer equity.

---

 ⚙️ Project Architecture & Layout
```text
saas-ecommerce-cohort-retention/
│
├── data/                  # Local transactional datasets (Git-ignored)
├── notebooks/             # Step-by-step development pipeline
│   └── 01_cohort_analysis.ipynb
├── src/                   # Production-ready Python scripts
│   └── __init__.py
├── README.md              # Executive summary and engineering progress
└── requirements.txt       # Environment dependencies# Infotact-Solution-Month2-project
### Phase 1: Architecture Initialization & Data Isolation Logic
*   **Day 1 (July 12, 2026): Data Ingestion & Security Routing Engine**
    *   Engineered a raw operational log pipeline generating 1,000 distinct tracking data profiles across 4 multi-tenant organizations.
    *   Constructed a `TenantDataRouter` engine in Python to enforce dynamic multi-tenant row isolation.
    *   Validated asset security parameters to prevent data leakage during multi-user sessions.
*   **Day 2 (July 13, 2026): Data Sanitation & Feature Engineering Pipeline**
    *   Ingested the raw multi-tenant tracking log asset file containing 1,000 corporate records across operational clusters.
    *   Executed pipeline data type parsing, successfully converting absolute temporal vectors to operational datetime formats.
    *   Engineered composite analytical indicators including binary `is_churned` metrics and platform `usage_intensity` metrics.
    *   Exported finalized sanitized master arrays to `cleaned_saas_tenant_analytics.csv` to ensure project-wide data audit readiness.
*   **Day 3 (July 14, 2026): Multi-Tenant Statistical Aggregation Engine**
    *   Constructed a data aggregation pipeline using multi-variable matrix grouping by organizational tenants.
    *   Synthesized executive business KPIs, including total Monthly Recurring Revenue (MRR) and aggregate cloud storage metrics.
    *   Formulated tenant-specific churn velocity percentages to track active customer retention rates.
    *   Generated and exported the corporate operations matrix to `tenant_executive_summary.csv`.
*   **Day 4 - Time-Based Feature Engineering
* Successfully parsed the corporate customer `activation_date` strings into standardized Python datetime objects.
* Engineered a new granular feature `activation_date_only` to isolate calendar dates for clean day-over-day tracking.
* Engineered a new feature `activation_hour` to capture the exact hour integer (0–23) of account activations.
* Staged the main dataset (`analytics_df`) with structural time intelligence features to prepare for future hourly behavioral profiling and operational deep-dives.
* ** Day 5 - Multi-Tenant Operational Metrics Isolation
* Grouped the master `analytics_df` dataset across `tenant_id` and the engineered `activation_hour` feature.
* Isolated key behavioral and financial footprints, including active accounts, total MRR, average API intensity, and storage consumption per hourly window.
* Formatted execution outputs into a structured data frame (`hourly_tenant_performance`) to enable granular, multi-tenant performance audits.
* ** Day 6 - Tenant Segmentation & Risk Profile Mapping
* Rolled up multi-tenant account records into a flat, tenant-level corporate health matrix (`tenant_risk_profiles`).
* Formulated localized `tenant_churn_rate_%` calculations to measure the exact churn density per tenant ecosystem.
* Applied conditional logic structures to segments tenants into actionable health tiers (`Low Risk`, `Moderate Risk`, `High Risk/Critical`) based on actual corporate churn percentages.
* ** Day 7 - Pipeline Standardization & Data Export
* Joined localized tenant risk mapping features back into the primary master DataFrame (`analytics_df`).
* Enforced schema validation and structural data hygiene across all active operational variables.
* Exported final production-ready analytical assets (`final_processed_saas_analytics.csv` and `executive_tenant_risk_profiles.csv`) to enable seamless downstream BI integration.
* ** Day 8 - Hourly Activity Visualization & EDA
* Integrated `matplotlib` and `seaborn` plotting frameworks into the notebook environment.
* Built dynamic operational trend plots tracking `average_api_calls` against isolated `activation_hour` features.
* Mapped peak usage hours to identify multi-tenant platform load windows and potential infrastructure bottlenecks.
* ** Day 9 - Revenue at Risk Distribution Analysis
* Engineered categorical visualizations mapping total aggregated MRR across defined risk segments (`Low Risk`, `Moderate Risk`, `High Risk/Critical`).
* Evaluated capital exposure across high-vulnerability tenant accounts to prioritize customer success intervention strategies.
* Standardized reporting aesthetics using custom color palettes and formatted currency axes for stakeholder reporting.
* ** Day 10 - Operational Feature Correlation & Heatmap
* Isolated primary numerical features (`monthly_recurring_revenue`, `api_requests_count`, `cloud_storage_used_gb`, `is_churned`) to calculate a Pearson correlation matrix.
* Rendered an operational heat map using `seaborn` to detect feature interplay and usage intensity patterns across tenant environments.
* Evaluated direct linear dependencies between heavy API call volume and cloud storage consumption to inform infrastructure auto-scaling parameters.
* ** Day 11 - ML Data Pipeline & Train-Test Partitioning
* Isolated predictor variables (`monthly_recurring_revenue`, `api_requests_count`, `cloud_storage_used_gb`, `activation_hour`) into feature matrix `X` and designated `is_churned` as target `y`.
* Executed an 80/20 train-test split utilizing `scikit-learn`'s `train_test_split`.
* Applied class stratification (`stratify=y`) to maintain proportion consistency of churned vs. active tenants across training and testing environments.
* **Day 12 - Baseline ML Model Training & Benchmarking
* Instantiated a baseline `LogisticRegression` classification model using `scikit-learn`.
* Fitted the baseline model on `X_train` and evaluated predictions against the unseen `X_test` dataset.
* Generated baseline performance metrics including overall accuracy, precision, recall, and F1-score to set a benchmark for future model iterations.
* **Day 13 - Non-Linear ML Modeling (Random Forest)
* Advanced predictive analytics by training an ensemble `RandomForestClassifier` with 100 decision trees.
* Leveraged non-linear feature interactions between API usage volume, cloud storage consumption, and account churn probability.
* Evaluated precision and recall improvements over the baseline Logistic Regression model.
* **Day 14 - Model Interpretability & Feature Importance Analysis
* Extracted Gini importance scores from the trained `RandomForestClassifier` to determine primary churn drivers.
* Constructed visual ranking plots isolating high-impact behavioral indicators (e.g., API activity vs. storage utilization vs. MRR tier).
* Translated technical ML insights into actionable retention signals for customer success and operations teams.
* ** Day 15 - Model Persistence & Pipeline Preservation
* Implemented model serialization utilizing `joblib` to preserve the trained `RandomForestClassifier` asset.
* Exported input feature schemas (`model_feature_names.pkl`) to guarantee input alignment during real-time batch and API scoring operations.
* Validated pipeline persistence with an automated reload dry-run test on test samples.
* **Day 16 - Real-Time Tenant Scoring & Inference Engine
* Constructed a modular inference scoring function (`score_tenant_churn`) to ingest live tenant payload variables.
* Automated real-time probability extraction (`predict_proba`) using reloaded model artifacts.
* Integrated actionable, rule-based decision triggers (`CRITICAL`, `WARNING`, `HEALTHY`) mapped directly to churn probabilities for downstream customer success workflows.
* ** Day 17 - RESTful API Microservice (FastAPI & Pydantic)
* Built a lightweight microservice (`app.py`) leveraging `FastAPI` and `Pydantic` for real-time payload parsing and data validation.
* Exposed `/predict` POST endpoint to serve dynamic churn predictions and intervention workflows from serialized model artifacts.
* Implemented OpenAPI standard documentation (Swagger UI) for seamless backend integration.
* ** Day 18 - Automated API Testing Suite (`pytest` & `httpx`)
* Developed a modular unit and integration testing suite (`test_app.py`) using FastAPI's `TestClient`.
* Automated assertion checks for route availability, schema validation (`422 Unprocessable Entity`), and inference structure correctness.
* Validated API resilience prior to Docker containerization and deployment pipelines.
