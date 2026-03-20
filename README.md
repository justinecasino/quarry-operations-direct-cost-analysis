# Quarry Operations Direct Cost Analysis

 ## Overview

This project presents an end-to-end cost efficiency analysis of quarry operations using synthetic data. It focuses on evaluating cost per cubic meter (m³) and identifying key operational cost drivers across the full production cycle—from drilling to hauling.

## Operational Context

In a typical quarry operation, the production cycle consists of the following processes:
 • Drilling
 • Blasting
 • Extraction
 • Loading
 • Hauling
 • Stockpiling

Operations can be executed either in-house or through external contractors, depending on the company’s strategy and resources.

In this dataset:

Drilling and Blasting are treated as external services, with costs applied as bulk or contract-based values

Extraction, Loading, Hauling, and Stockpiling are considered in-house operations, allowing detailed cost breakdown and analysis

The analysis focuses on direct operational costs, which include:

Fuel Cost

Manpower Cost

Equipment Cost (rental or depreciation)

Equipment Maintenance Cost

To simplify the model and focus on core operational efficiency, the dataset excludes indirect costs, such as:

Permits and regulatory expenses

Facilities and overhead

Administrative or indirect manpower

## Problem Statement

Quarry operations involve multiple interconnected processes (drilling, blasting, extraction, loading, hauling, and stockpiling), each contributing to total production cost.

However:

Costs are often fragmented across different datasets

Hauling and operations are analyzed separately

There is limited visibility into true cost per m³ per process

Decision-makers lack a unified view of cost drivers

👉 The goal of this project is to integrate and model operational data to enable accurate, process-level cost analysis and performance monitoring.

## Methodology
### 1. Data Generation

Created realistic synthetic datasets using AI

Simulated quarry scenarios (production, fuel usage, hauling activities)

### 2. Data Cleaning

Processed data using Python (Google Colab)

Standardized formats and ensured data consistency

### 3. Data Modeling

Built a star schema model in Power BI

Created conformed dimensions:

Date

Site

Equipment

### 4. Data Transformation

Created a Process Dimension Table

Transformed hauling data and aligned structure with operations

Aggregated hauling data at equipment-day level to avoid duplication

### 5. Data Integration

Appended hauling data into operations dataset

Built a unified process-level fact table for end-to-end analysis

### 6. Measures & Visualization

Developed DAX measures:

Total Cost

Total Output

Cost per m³

Fuel Cost

Built interactive dashboards in Power BI

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



