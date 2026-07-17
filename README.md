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
