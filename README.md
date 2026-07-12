# SaaS & E-Commerce Cohort Retention & CLTV Analysis

## 📊 Executive Summary & Problem Statement
Acquiring new customers is up to five times more expensive than retaining existing ones. High-growth startups often celebrate rapid user acquisition milestones but fail to track whether those users actually stick around. If a business loses customers faster than it acquires them, it will inevitably collapse.

This project performs a deep-dive **Cohort Analysis** to evaluate user retention dynamics and calculate **Customer Lifetime Value (CLTV)**. By grouping users into cohorts based on their acquisition month, we isolate exactly when users churn, analyze behavior differences across segments (SaaS vs. E-Commerce), and provide data-backed strategic recommendations to maximize customer equity.

---

## ⚙️ Project Architecture & Layout
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
