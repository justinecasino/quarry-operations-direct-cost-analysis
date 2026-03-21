# Quarry Operations Direct Cost Analysis

 ## Overview

This project presents an end-to-end cost efficiency analysis of quarry operations using synthetic data. It focuses on evaluating cost per cubic meter (m³) and identifying key operational cost drivers across the full production cycle - from drilling to hauling.



## Operational Context

In a typical quarry operation, the production cycle consists of the following processes:
- Drilling
- Blasting
- Extraction
- Loading
- Hauling
- Stockpiling

Operations can be executed either in-house or through external contractors, depending on the company’s strategy and resources.

In this dataset:

- **Drilling** and **Blasting** are treated as **external services**, with costs applied as bulk or contract-based values
- **Extraction, Loading, Hauling, and Stockpiling** are considered **in-house operations**, allowing detailed cost breakdown and analysis

The analysis focuses on **direct operational costs**, which include:
- Fuel Cost
- Manpower Cost
- Equipment Cost (rental or depreciation)
- Equipment Maintenance Cost

To simplify the model and focus on core operational efficiency, the dataset excludes indirect costs, such as:
- Permits and regulatory expenses
- Facilities and overhead
- Administrative or indirect manpower



## Problem Statement

Operational data in quarry operations is often fragmented across multiple datasets, limiting visibility into true cost per m³ and key cost drivers, which can lead to inefficient decision-making and cost control.

This project addresses this gap by building a unified data model to enable accurate process-level cost analysis and support better cost efficiency decisions across the full production cycle.



## Methodology

### 1. Data Generation & Cleaning

- Generated synthetic datasets using AI to simulate realistic quarry operations
- Cleaned and standardized data using Python (Google Colab)
 https://colab.research.google.com/drive/1jPHbrKn9rcpHiS8hL6u4mWNKgmcM7Bte?usp=sharing
- Exported structured CSV files for analysis

### 2. Data Import & Preparation
- Imported datasets into Power BI
- Created Dimension Tables using DAX and Power Query

### 3. Data Modeling
- Designed a star schema with conformed dimensions
<img width="887" height="683" alt="Final Star Schema" src="https://github.com/user-attachments/assets/38f80238-a796-405b-93fd-03bac2e21ed6" />

- Ensured consistent filtering across multiple fact tables

### 4. Data Transformation & Integration
- Aggregated hauling data at the equipment-day level to avoid duplication
- Transformed and appended hauling data into the operations dataset
- Built a unified process-level fact table for end-to-end analysis

### 5. Measures & Visualization
- Developed key DAX measures such as:
    - Cost per m³
    - Total Cost 
    - Fuel Cost
    - Equipment Cost
    - External Services Cost
    - Labor Cost
 - Built interactive Power BI dashboards to analyze cost drivers and operational performance



## Data Structure Overview

The final model is designed as a **star schema** centered on a unified fact table to support efficient and scalable analysis.

### Fact Table

- **`fact_ops_appended`**  
  Central table combining operations and hauling data at the process level.

  **Includes:**
  - Date  
  - Site  
  - Equipment ID  
  - Process  
  - Output (m³)
  - Cost components:
    - Fuel Liters 
    - Labor Cost  
    - Daily Equipment Cost - equipment rent + maintenance
    - Process Cost - external services

### Dimension Tables

- **`dim_date`** – supports time-based analysis  
- **`dim_site`** – enables site-level comparison  
- **`dim_equipment`** – contains equipment cost attributes  
- **`dim_process`** – standardizes operational stages  

### Supporting Table

- **`fact_fuelprice`** – stores daily fuel prices for cost calculations  



## Key Insights
- **Equipment cost is the dominant cost driver (~50%+)**
    The cost breakdown shows that equipment-related costs make up the largest share of total expenses, significantly influencing overall cost per m³.
- **Hauling is the most expensive operational process**
    Among all stages, hauling has the highest total cost, driven by combined fuel usage and equipment cost, making it the most critical area for optimization.
- **Fuel cost is the second major contributor (~25–27%)**
    Fuel expenses consistently represent a significant portion of total cost, especially in hauling and extraction activities.
- **Cost per m³ varies across locations**
    Site comparison indicates differences in cost efficiency, suggesting variability in operations, distance, or equipment utilization.
- **External services (drilling & blasting) are stable but less dominant**
    These costs remain relatively constant due to contract-based pricing and contribute less to variability compared to in-house operations.
- **Short-term trends show relatively stable total cost with fluctuations in fuel-driven processes**
    Variations in daily cost trends are mainly influenced by fuel consumption and operational activity levels.



## Recommendations
- **Optimize equipment utilization (Top Priority)**
   Review equipment deployment and idle time
   Align equipment capacity with production demand
   Evaluate cost-benefit of rental vs owned equipment
- **Improve hauling efficiency**
Optimize hauling routes and distances
Reduce cycle time and waiting time
Monitor truck utilization and dispatching
- **Strengthen fuel management**
Track fuel consumption per equipment and per process
Identify inefficiencies or abnormal usage
Implement fuel-saving operational practices

- **Benchmark and standardize site performance**

Identify best-performing sites in terms of cost per m³
Replicate efficient practices across other locations

- **Leverage cost per m³ as a core KPI**

Monitor regularly at site and process level
Use it as a basis for operational and financial decisions



## Tech Stack

Python (Google Colab) – Data cleaning

Power BI – Data modeling & visualization

DAX & Power Query – Data transformation and measures

## Disclaimer

This project uses AI-generated synthetic data designed to simulate realistic quarry operations. No real company data was used.



