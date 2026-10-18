# 🚕 NYC Taxi Data Pipeline with Databricks Asset Bundles (DABs) & CI/CD

<p align="center">
  <img src="https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white" alt="Databricks">
  <img src="https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apache-spark&logoColor=white" alt="Spark">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  <img src="https://img.shields.io/badge/CI%2FCD-20232A?style=for-the-badge&logo=github-actions&logoColor=61DAFB" alt="CI/CD">
</p>

**Author:** Eng. Omar Elsoudy  
**Project Role:** Lead Data Engineer  
**Platform:** Databricks  

---

## 📌 Executive Summary

This project demonstrates an enterprise-grade, end-to-end Data Engineering pipeline using **Databricks Asset Bundles (DABs)** and **Delta Live Tables (DLT)**. The core objective is to ingest, clean, transform, and aggregate NYC Taxi trip datasets using a **Medallion Architecture** (Bronze ➔ Silver ➔ Gold), fully automated and managed via CI/CD workflows and multi-environment deployment (`dev` / `prod`).

---

## 🚖 About NYC Taxi Dataset

The **New York City Taxi and Limousine Commission (TLC)** trip record dataset contains rich information on urban mobility:
* **Trip Metrics:** Pick-up and drop-off dates/times, trip distances, itemized fare breakdowns, tip amounts, and payment types.
* **Geospatial Data:** Pick-up and drop-off zone IDs mapped to specific NYC boroughs (Manhattan, Brooklyn, Queens, etc.).
* **Business Value:** Enables deep analytical insights into traffic patterns, high-revenue spatial routes, peak operational hours, and driver tipping behaviors.

---

## 🛠 Tech Stack & Tools

- **Orchestration & Deployment:** Databricks Asset Bundles (DABs), Databricks CLI
- **Data Processing:** Delta Live Tables (DLT), PySpark, Spark SQL, Delta Lake
- **Architecture:** Medallion Architecture (Bronze, Silver, Gold Layers)
- **Version Control & CI/CD:** Git, GitHub, Feature Branching Strategy
- **Environment:** Databricks Workspaces, Unity Catalog

---

## 🏗 Pipeline Architecture & Data Flow

<img width="1493" height="700" alt="Capture" src="https://github.com/user-attachments/assets/1a860748-8d49-4061-b616-78bcfd14edbf" />


```text
[ Raw Taxi Data Files ] 
          │
          ▼
 🥉 BRONZE LAYER  ──► Ingestion & Raw Data Storage (Autoloader / DLT)
          │
          ▼
 🥈 SILVER LAYER  ──► Data Cleaning, Schema Enforcement & Null Handling
          │  
          ▼
 🥇 GOLD LAYER    ──► Incremental Aggregations (Daily Summaries & Zone Performance)
---

## 💻 Terminal Commands & Deployment Guide

### 1. Authentication & Setup
Run the following command to login to Databricks CLI:
`databricks auth login`

### 2. Bundle Validation
Run the following command to validate the bundle for development:
`databricks bundle validate -t dev`

### 3. Deploy to Environment
Run the following command to deploy the bundle:
`databricks bundle deploy -t dev`

### 4. Execute Pipeline
Run the following command to trigger the pipeline execution:
`databricks bundle run -t dev`
