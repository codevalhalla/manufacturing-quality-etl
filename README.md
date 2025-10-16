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
```
## Setup

### 1. Clone the repository

```bash
git clone git@github.com:codevalhalla/manufacturing-quality-etl.git
cd manufacturing-quality-etl
```
### 2. Install Dependencies
(Optional: Create and activate a virtual environment first)
```bash
pip install -r requirements.txt
```
### 3. Place Data Files
Ensure your raw stage-wise data files are placed inside the data/ folder. The pipeline expects files named similar to:

- assembly_shift_count_stage1.xlsx
- assembly_shift_count_stage2.xlsx
- assembly_shift_count_stage3.xlsx

### Usage
Run the Jupyter Notebook to execute the ETL process:

```bash
jupyter notebook notebooks/shift_quality_etl.ipynb
```

The notebook will automatically load, transform, and save the results:

- The fact table is saved to output/shift_prod_quality_fact.csv.
- Visualizations (bar charts) are saved to the output/ folder.

### Output Example
The final fact table provides a clear summary of quality issues per shift and product:

| quality\_id | shift\_id | prod\_id | stage1\_good\_unit\_count | ... | stage3\_scrap\_count | total\_rework\_count | total\_scrap\_count |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 12346700 | 12346 | 700 | 395 | ... | 5 | 24 | 24 |
| 12346800 | 12346 | 800 | 750 | ... | 10 | 40 | 35 |

### Dependencies
- Python 3.x
- Pandas
- NumPy
- Matplotlib

### License
This project is licensed under the MIT License.
