# Quarry Operations Direct Cost Analysis

 ## Overview

This project presents an end-to-end cost efficiency analysis of quarry operations using synthetic data. It focuses on evaluating cost per cubic meter (m³) and identifying key operational cost drivers across the full production cycle—from drilling to hauling.

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
-link:- https://colab.research.google.com/drive/1jPHbrKn9rcpHiS8hL6u4mWNKgmcM7Bte?usp=sharing
- Exported structured CSV files for analysis

### 2. Data Import & Preparation
- Imported datasets into Power BI
- Created Dimension Tables using DAX and Power Query

### 3. Data Modeling
- Designed a schema
- Ensured consistent filtering across multiple fact tables

### 4. Data Transformation & Integration
- Aggregated hauling data at the equipment-day level to avoid duplication
- Transformed and appended hauling data into the operations dataset
- Built a unified process-level fact table for end-to-end analysis

### 5. Measures & Visualization
- Developed DAX measures
 <img width="212" height="547" alt="Measures" src="https://github.com/user-attachments/assets/d8103c49-1e0a-4bee-af88-8d10488705fc" />
 
 - Built interactive Power BI dashboards to analyze cost drivers and operational performance






## Key Insights

Hauling is a major cost driver, significantly impacting total cost per m³

Fuel cost variability directly affects operational efficiency

Some sites show higher cost per m³ despite similar output, indicating inefficiencies

Equipment utilization differences contribute to cost inconsistencies across sites

Integrating hauling into operations reveals the true end-to-end cost structure

## Recommendations

Optimize hauling operations

Review hauling distances and routing efficiency

Improve truck utilization and scheduling

Improve fuel efficiency monitoring

Track fuel consumption per equipment and per process

Identify abnormal usage patterns

Standardize operational practices across sites

Benchmark high-performing sites

Apply best practices to underperforming locations

Enhance data tracking

Maintain consistent process-level data recording

Integrate all operational data into a unified system

## Tech Stack

Python (Google Colab) – Data cleaning

Power BI – Data modeling & visualization

DAX & Power Query – Data transformation and measures

## Disclaimer

This project uses AI-generated synthetic data designed to simulate realistic quarry operations. No real company data was used.



