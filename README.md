# Enterprise Healthcare Claims Operations Dashboard (Tableau)

<img width="1254" height="836" alt="image" src="https://github.com/user-attachments/assets/6355efb2-1dec-4205-9bfa-6d255577d7c5" />

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

## How the Dashboard Answers the Business Questions

**1. Are healthcare claims being processed within SLA targets across all service types and providers?**  
The SLA Compliance KPI and Average Processing Days metric provide an immediate view of overall SLA performance. Reference lines and threshold indicators highlight whether processing times meet defined SLA targets at an aggregate level.

**2. Which service lines or providers are driving the longest processing times and contributing most to SLA breaches?**  
Provider-level and service-type breakdowns surface variability in average processing days. Bar charts ranked by processing time make it easy to identify providers and services that exceed SLA thresholds and contribute disproportionately to delays.

**3. Where are the largest cost and claim volume concentrations, and how are they trending over time?**  
Claims volume trends and service-type distribution charts show how demand and workload change over time. These views help pinpoint high-volume and high-impact areas that drive operational complexity and resource strain.

## Recommendations

- **Prioritize SLA remediation for underperforming providers**  
  Focus operational reviews and process improvements on providers with average processing times exceeding SLA targets, as they account for a disproportionate share of delays.

- **Allocate resources based on service complexity and volume**  
  Inpatient and emergency services exhibit higher processing times and volumes, indicating a need for targeted staffing, automation, or workflow optimization in these areas.

- **Strengthen backlog monitoring and early-warning indicators**  
  Use backlog aging and SLA trend metrics to proactively identify emerging risks before SLA breaches accumulate.

- **Standardize SLA performance tracking across regions and plans**  
  Ensure consistent KPI definitions and thresholds are applied enterprise-wide to enable fair comparison and governance.

- **Leverage trend analysis for capacity planning**  
  Use historical volume and processing trends to anticipate seasonal spikes and adjust operational capacity in advance.
