# Enterprise Healthcare Claims Operations Dashboard (Tableau)

<img width="1600" height="800" alt="image" src="https://github.com/user-attachments/assets/566fb6bf-e0b2-4bcc-b6b7-14c971270b25" />

## Project Background
Healthcare organizations process large volumes of claims across multiple service lines, providers, and member populations. As claim volumes grow, operations teams face increasing pressure to maintain processing efficiency, meet SLA targets, and control medical costs while ensuring consistent reporting across business units.

This project simulates an enterprise healthcare environment and delivers a Tableau dashboard built to support operational oversight at scale. 

The dashboard is designed for enterprise stakeholders, including operations leaders and performance management teams, who require reliable, governed metrics and the ability to quickly identify operational bottlenecks across services, providers, and regions.

Here are examples of some pre-defined business questions the dashboard can answer: 
1. Are healthcare claims being processed within SLA targets across all service types and providers?
2. Which service lines or providers are driving the longest processing times and contributing most to SLA breaches?
3. Where are the largest cost and claim volume concentrations, and how are they trending over time?

## Data Structure and Intial Checks
The dataset is organized using an enterprise-style fact and dimension model to support scalable analysis in Tableau.

- **Fact Table**
  - `fact_claims.csv`: Contains claim-level transactions, including service type, processing dates, and claim amounts.

- **Dimension Tables**
  - `dim_members.csv`: Member attributes such as age group, plan type, and region.
  - `dim_providers.csv`: Provider attributes including provider type and region.

Before building the dashboard, the following validation steps were performed:
- Verified record counts and primary keys for each table
- Confirmed join integrity between fact and dimension tables
- Checked date fields for invalid or missing values
- Reviewed distributions of processing time and claim amounts for outliers
- Ensured categorical fields (service type, plan type, region) were standardized

<img width="672" height="193" alt="image" src="https://github.com/user-attachments/assets/6a0524c9-5462-4aa7-8599-ca83401a8f46" />

Datasets can be dowdloaded [here](https://github.com/kietn1/enterprise-healthcare-claims-operations-tableau/tree/main/datasets)

---
## Executive Summary

**Key Findings**
- Claims volume remains high (427,599 claims) with clear seasonality, declining mid-year before rebounding toward year-end.
- SLA compliance is at 72.0%, falling short of the defined target and indicating elevated operational risk.
- Average processing time (7.01 days) is at or slightly above the SLA threshold, leaving limited buffer during volume spikes.
- SLA breaches are concentrated among a subset of providers whose average processing days exceed the target.
- Inpatient and pharmacy services drive the highest claim volumes, while backlog aging indicates a meaningful portion of claims extending beyond SLA limits.
  
<img width="1886" height="889" alt="claims" src="https://github.com/user-attachments/assets/c820b9ee-4fd8-4f0e-a8ba-792953ab08cf" />


