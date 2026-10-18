# 🚕 NYC Taxi Data Pipeline with Databricks Asset Bundles (DABs) & CI/CD

**Author:** Eng. Omar Elsoudy  
**Project Role:** Lead Data Engineer  
**Platform:** Databricks  

---

## 📌 Executive Summary

This project demonstrates an enterprise-grade, end-to-end Data Engineering pipeline using **Databricks Asset Bundles (DABs)** and **Delta Live Tables (DLT)**. The core objective is to ingest, clean, transform, and aggregate NYC Taxi trip datasets using a **Medallion Architecture** (Bronze ➔ Silver ➔ Gold), fully automated and managed via CI/CD workflows and multi-environment deployment (`dev` / `prod`).

---

## 🛠 Tech Stack & Tools

- **Orchestration & Deployment:** Databricks Asset Bundles (DABs), Databricks CLI
- **Data Processing:** Delta Live Tables (DLT), PySpark, Spark SQL, Delta Lake
- **Architecture:** Medallion Architecture (Bronze, Silver, Gold Layers)
- **Version Control & CI/CD:** Git, GitHub, Feature Branching Strategy
- **Environment:** Databricks Workspaces, Unity Catalog / Hive Metastore

---

## 🏗 Pipeline Architecture & Data Flow

```text
[ Raw Data Files ] 
       │
       ▼
 🥉 BRONZE LAYER  ──► Ingestion & Raw Data Storage (Autoloader / DLT)
       │
       ▼
 🥈 SILVER LAYER  ──► Data Cleaning, Schema Enforcement & Null Handling
       │
       ▼
 🥇 GOLD LAYER    ──► Incremental Aggregations (Daily Summaries & Zone Performance)
