# Google Data Analytics Capstone Project

# Cyclistic Bike-Share case study

## Business Task
The objective of this analysis is to understand how casual riders and riders with annual memberships use Cyclistic bikes differently. This insight will supportthe marketing team in designing data-driven strategies at converting one time riders into annual members, this is key for the company future growth. 

## Stakeholders
- Lily Moreno, Director of Marketing Department
- Cyclistic Marketing Analytics Team
- Cyclistic Executive Team

## Data Source 
The analysis uses Cyclistic historical bike trips data made publicly available by Motivate International Inc. 
For this case study, data from February to May 2025 was selected. Each month was provided as a separate csv file and uploaded into BigQuery as individual tables. 

The datasets include trip-level information such as ride start and end times, station details, bike type and rider category (casual or member). No personally indentifiable information is included in the data. 

## Data Limitations
Due to platform upload limitations, the analysis was conducted using four months of data instead of a full year. 
Despite this limitation, the selected data provides sufficient volume and variability to identify usage patterns between casual riders and annual members. 

## Process (Data Cleaning)

The data was processed using Google BigQuery. A combined table was created by merging four monthly datasets (February–May 2025) using UNION ALL.
To ensure data quality, a new calculated field called `ride_length_minutes` was created by calculating the difference between `ended_at` and `started_at`.
Trips with zero or negative ride duration were identified as invalid records. A total of 29,546 invalid trips (approximately 2.2% of the dataset) were excluded from the analysis.

A cleaned view was created to include only trips with positive ride duration. This cleaned dataset was used for all subsequent analysis.

