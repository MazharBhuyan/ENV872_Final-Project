# ENV872_Final-Project


## Summary

This repository contains an analysis of low birth weight rates statistics with respect to air pollution levels in Ulaanbaatar. The aim is to assess the prevalence of low birth weight (under 2500 grams) among live births and investigate the relation between PM2.5 rates. The analysis focuses on the effects of air pollution in Ulaanbaatar on low birth weight rates in Ulaanbaatar. In order to understand the relation between these, linear and 3 months lagged regression analysis are used as it is expected that air pollution affects birth conditions in the last trimester. 


## Investigators

  Nilab Ahmedi  
  Master of Public Policy  
  nilab.ahmadi@duke.edu
  
  Darpan Barua  
  Master of Engineering Management  
  darpan.barua@duke.edu

  Mazhar Bhuyan  
  Master of International Development  
  mazhar.bhuyan@duke.edu  

  Kamil Burak Karayel  
  Master of International Development  
  burak.karayel@duke.edu


## Keywords

Birth weight, Ulaanbaatar, live births, health statistics, PM2.5


## Database Information

This repository uses fifteen datasets, two obtained from the official portal 
of National Statistics Office of Mongolia and eleven obtained from Embassy of 
United States in Ulaanbaatar.

- **Live Births**  
  [Dataset link](https://www.1212.mn/en/statistic/statcate/573056/table-view/DT_NSO_2100_018V5)

- **Birth Weight Lower Than 2500 Grams**  
  [Dataset link](https://www.1212.mn/en/statistic/statcate/573056/table-view/DT_NSO_2100_038V1)

The health data was accessed in 19 April 2025. Because of lack of API to collect data from National Statistics Office of Mongolia, data was saved from official portal as CSV files. 

- **Low Birth Weight Rate**  
  Data is created by taking the percentage of birth weights lower than 2500g in all live births.

- **Air Pollution**  
  [Current Website]: (https://www.airnow.gov/international/us-embassies-and-consulates/ 
  [Website from Feb 2025]: (https://web.archive.org/web/20250222221141/https://www.airnow.gov/international/us-embassies-and-consulates/#Mongolia$Ulaanbaatar)

The air pollution data was collected from the “Airnow.gov” website. This includes air pollution data collected by the U.S. Embassy in Ulaanbaatar. The data was retrieved on February 2025 when the data was publicly available. Due to administrative changes, the data has been since taken down. 


## Folder structure, file formats, and naming conventions

Code/:
Includes R Markdown (.Rmd) files used for data cleaning, analysis, and report generation and related LaTex files for reporting.

Data/:
Contains all the raw and processed datasets used for analysis. Raw files are in .csv format and file names are preserved as in the sources. Processed data file "pm25_all.csv" contains hourly PM2.5 data from 11 raw files. 

Output/:
Stores outputs from the scripts such as graphs, tables, and reports. These are typically in .pdf format.

References/:
Contains reference articles in .pdf format which were used to guide and make our analyses more accurate.


## Metadata

### LIVE BIRTHS.csv

| Column Name | Description               | Data Type | Unit         |
|:------------|:--------------------------|:----------|:-------------|
| Aimag       | Administrative Unit       | Character | -            |
| 2016-01     | Number of live births     | Integer   | Number       |
|   ...       |                           |           |              |
| 2025-03     | Number of live births     | Integer   | Number       |

The dataset was horizontal, we needed to rearrange in vertical form and excluded
aimag name which was only Ulaanbaatar.

| Column Name | Description               | Data Type | Unit         |
|:------------|:--------------------------|:----------|:-------------|
| Month       | Months in Y-m format      | Character | -            |
| Live_Births | Number of live births     | Integer   | Number       |


### BIRTH WEIGTH LOWER THAN 2500 GRAMS.csv

| Column Name | Description                            | Data Type | Unit         |
|:------------|:---------------------------------------|:----------|:-------------|
| Aimag       | Administrative Unit                    | Character | -            |
| 2016-01     | Number of live births under 2500 grams | Integer   | Number       |
|   ...       |                                        |           |              |
| 2025-03     | Number of live births under 2500 grams | Integer   | Number       |

The dataset was horizontal, we needed to rearrange in vertical form and excluded
aimag name which was only Ulaanbaatar.

| Column Name      | Description                  | Data Type | Unit         |
|:-----------------|:-----------------------------|:----------|:-------------|
| Month            | Months in Y-m format         | Character | -            |
| Low_Birth_Weight | Number of births under 2500g | Integer   | Number       |


### Ulaanbaatar_PM2.5_2015_YTD.csv (same for 11 files from 2015 to 2025)

| Column Name   | Description                               | Data Type | Unit         |
|:--------------|:------------------------------------------|:----------|:-------------|
| Site          | one value: Ulaanbaatar                    | Character | -            |
| Parameter     | one value: PM2.5 - Principal              | Character | -            |
| Date..LT.     | Local timestamp (Asia/Ulaanbaatar, UTC+8) | Character | -            |
| Year          | Date component                            | Integer   | Number       |
| Month         | Date component                            | Integer   | Number       |
| Day           | Date component                            | Integer   | Number       |
| Hour          | Tiem component                            | Integer   | Number       |
| NowCast.Conc. | Real-time weighted concentration          | Number    | µg/m³        |
| AQI           | U.S. Air Quality Index (AQI) value        | Integer   | Number       |
| AQI.Category  | AQI label (e.g., Good, Unhealthy)         | Character | -            |
| Raw.Conc.     | Measured PM2.5                            | Number    | µg/m³        |
| Conc..Unit    | Unit name                                 | Character | -            |
| Duration      | one value: 1 hour                         | Character | -            |
| QC.Name       | Quality control information or flags      | Character | -            |

## Scripts and code

- `v_2.Rmd`: Contains the entire data processing, analysis, and visualization workflow.
- Reads, cleans and rearranges both datasets.
- Merges and summarizes relevant statistics.
- Generates visualizations showing hourly, daily and monthly PM2.5 levels.
- Evaluate linear and lagged regressions of low birth rates and PM2.5 levels.  
- Outputs interpretable tables and charts.
