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




- **Cost per m³ varies across locations**
    Site comparison indicates differences in cost efficiency, suggesting variability in operations, distance, or equipment utilization.
- **External services (drilling & blasting) are stable but less dominant**
    These costs remain relatively constant due to contract-based pricing and contribute less to variability compared to in-house operations.
- **Short-term trends show relatively stable total cost with fluctuations in fuel-driven processes**
    Variations in daily cost trends are mainly influenced by fuel consumption and operational activity levels.




## 📈 Key Insights

- **Equipment cost is the primary cost driver (~50%+)**  
  Across all sites, equipment-related costs consistently make up the largest portion of total expenses, significantly impacting cost per m³.
- **Hauling is the most expensive operational stage**  
  The operations cycle breakdown shows that hauling contributes the highest cost due to combined fuel and equipment usage.

- **Fuel cost is the second largest contributor (~25–30%)**  
  Fuel expenses play a major role, especially in hauling and extraction processes, driving variability in daily costs.

- **Cost structure is consistent across sites, but efficiency varies**  
  While cost composition is similar, differences in cost per m³ suggest variations in operational efficiency and execution.

- **External services (drilling & blasting) are stable and predictable**  
  These costs remain relatively constant due to contract-based pricing and have minimal impact on cost fluctuations.

- **Daily cost fluctuations are driven by operational activity and fuel usage**  
  Variations in trends are mainly influenced by changes in fuel consumption and equipment utilization.

---

## 💡 Recommendations

- **Optimize equipment utilization (Highest Impact)**
  - Minimize idle time and improve deployment planning  
  - Align equipment usage with production requirements  
  - Evaluate cost efficiency of owned vs rented equipment  

- **Improve hauling efficiency**
  - Optimize hauling routes and reduce travel distance  
  - Improve truck dispatching and cycle time  
  - Monitor load efficiency and trip productivity  

- **Strengthen fuel cost management**
  - Track fuel consumption per equipment and per process  
  - Identify abnormal usage patterns  
  - Implement fuel efficiency practices  

- **Benchmark and standardize site performance**
  - Identify best-performing sites in terms of cost per m³  
  - Apply best practices across all locations  

- **Use cost per m³ as a core KPI**
  - Monitor regularly at both site and process levels  
  - Use it to guide operational and financial decisions  

---

## ⚠️ Disclaimer

This project uses **AI-generated synthetic data** designed to approximate realistic quarry operations.  
It is intended for analytical and portfolio purposes only and does not represent actual company data.




















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



