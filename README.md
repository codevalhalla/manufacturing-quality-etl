# 🏭 Manufacturing Quality ETL Pipeline

## Overview

This project implements an **Extract, Transform, Load (ETL) pipeline** designed for multi-stage assembly line data. It aggregates **good units**, **rework**, and **scrap** counts per product and manufacturing shift, providing crucial insights into overall manufacturing quality and process efficiency.

---

## Features

* **Load Data:** Ingests raw stage-wise assembly line data (Stage 1, 2, 3) from Excel/CSV files.
* **Data Integration:** Merges stage-wise datasets using common keys: `shift_id` and `prod_id`.
* **Quality Calculation:** Computes stage-wise and **total** counts for good units, rework, and scrap.
* **Fact Table Creation:** Generates a final, consolidated fact table: `shift_prod_quality_fact.csv`.
* **Data Visualization:** Creates insightful bar charts to visualize the total rework and scrap counts.

---

## Project Structure

```bash
manufacturing-quality-etl/
│
├─ data/          # Raw stage-wise Excel/CSV files
├─ notebooks/     # Jupyter Notebook for ETL execution and visualization
│  └─ shift_quality_etl.ipynb
├─ output/        # Final fact table CSV & plot images
├─ README.md      # This file
├─ requirements.txt # Python dependencies
└─ .gitignore
