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
