# Urbanisation Prospects – Data Engineering Assessment

## Overview
End-to-end data pipeline and analytics solution built on 
Microsoft Fabric and Databricks to analyse global urbanisation 
trends and income data for investment market assessment.

## Architecture
Medallion Architecture (Bronze → Silver → Gold) implemented 
in both Microsoft Fabric and Databricks, with visualisations 
served via PowerBI.

## Data Sources
- UN World Urbanisation Prospects 2018
- World Inequality Database – Pretax Income
- Countries & Continents reference
- OWID Country to WHO Regions

## Implementations

### Microsoft Fabric
Located in /fabric folder. Uses Fabric Lakehouse
and native PowerBI integration.

### Databricks
Located in /databricks folder. Uses Databricks
Delta Lake and medallion architecture.
Both implementations produce identical outputs
demonstrating platform flexibility.

## Notebooks
| Notebook | Purpose |
|---|---|
| 00_country_mapping | Builds master country dimension table |
| 01_ingest_bronze | Raw ingestion to Bronze Delta tables |
| 02_transform_silver | Cleaning joining Silver layer |
| 03_build_gold | Business aggregates Gold layer |
| 04_data_quality | DQ checks and validation reports |

## How to Run
1. Upload CSV files to Lakehouse Files section
2. Run notebooks in order 00 to 04
3. Connect PowerBI to Gold layer tables

## Key Design Decisions
- Medallion architecture for data quality and maintainability
- Regional aggregates filtered out from UN dataset
- Left joins preserve urbanisation data where income is unavailable
- Manual country name fixes applied for renamed countries
- Single Lakehouse used for simplicity and performance
