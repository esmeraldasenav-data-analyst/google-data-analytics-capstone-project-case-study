# Cyclistic Bike-Share case study
### Google Data Analytics Capstone Project

## Business Task
The objective of this analysis is to understand how casual riders and annual members use Cyclistic bikes differently. This insight will support the marketing team in designing data-driven strategies at converting one time riders into annual members, this is key for the company future growth. 

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

## Tools Used
- SQL (Google BigQuery) for data cleaning and analysis  
- Google Sheets for data visualization  
- GitHub for project documentation

## Data Processing and Cleaning
The data was processed using Google BigQuery. A combined table was created by merging four monthly datasets (February–May 2025) using UNION ALL.
To ensure data quality, a new calculated field called `ride_length_minutes` was created by calculating the difference between `ended_at` and `started_at`.
Trips with zero or negative ride duration were identified as invalid records. A total of 29,546 invalid trips (approximately 2.2% of the dataset) were excluded from the analysis.

A cleaned view was created to include only trips with positive ride duration. This cleaned dataset was used for all subsequent analysis.

## Average Ride Length
Casual riders have an average ride duration of approximately 22 minutes, while annual members average approximately 11 minutes per ride.

This indicates that casual riders take rides nearly twice as long as members, reinforcing the hypothesis that casual usage is primarily recreational, while member usage is more routine and commute-oriented.
![Average Ride Length](descarga/avg_ride_length.png)

## Usage Patterned by Day of the Week 
Analysis of ride frequency by day of the week reveals clear behavioral differences between rider types.
Annual members show significantly higher usage during weekdays, particularly Tuesday and Thursday, suggesting commuting or routine transportation patterns.

Casual riders demonstrate increased activity during weekends, especially Saturday, indicating more recreational or leisure-based usage.
![Ride Frequency by Day of Week](rides_by_day.png)


## Usage Patterns by Hour of Day
Analysis by hour of day shows that both rider types experience peak usage between 4 PM and 6 PM.
However, annual members demonstrate significantly higher trip volumes during these hours, particularly at 5 PM. This pattern strongly suggests commuting behavior.

Casual riders also increase activity in the late afternoon, but at a much lower intensity, indicating more flexible or leisure-based usage patterns.
![Ride Frequency by Hour](rides_by_hour.png)

## Bike Type Usage
Both annual members and casual riders show a strong preference for electric bikes over classic bikes.
The proportional distribution of bike type usage is similar across both rider categories, indicating that bike type preference is not a primary differentiating factor between casual riders and annual members.

## Ride Duration by Day of Week
Casual riders consistently demonstrate longer ride durations across all days of the week compared to annual members.
Annual members maintain a stable average ride duration between 10 and 12 minutes, reinforcing a commuting or routine transportation pattern.

Casual riders show significantly longer ride durations, particularly on weekends, where average rides exceed 25 minutes. This further supports the conclusion that casual riders primarily use the service for leisure and recreational purposes.
![Average Ride Duration by Day](duration_by_day.png)

## Recommendations
Based on the analysis, the following strategies are recommended:

1. Weekend Membership Promotion  
Since casual riders demonstrate higher activity and longer ride durations during weekends, offering discounted annual memberships on Saturdays and Sundays could effectively target high-engagement users.

2. Group Subscription Incentives  
Given the recreational usage patterns of casual riders, introducing group-based membership promotions (e.g., discounts for multiple sign-ups) may encourage social conversions and increase membership adoption.

3. Behavior-Based Upgrade Campaigns  
Casual riders with longer ride durations or repeated weekend usage could be targeted with personalized upgrade offers, leveraging behavioral data to increase conversion likelihood.

## Conclusion
This analysis identified clear behavioral differences between casual riders and annual members.

Annual members primarily use Cyclistic bikes for commuting purposes, characterized by shorter ride durations, strong weekday activity, and pronounced late-afternoon peak hours.
In contrast, casual riders exhibit longer ride durations, increased weekend activity, and usage patterns consistent with recreational behavior.

These findings highlight a strategic opportunity to convert high-engagement casual riders into annual members through targeted weekend promotions, group-based incentives, and behavior-driven upgrade campaigns.
By leveraging data-driven insights, Cyclistic can design focused marketing strategies that align with actual rider behavior and maximize long-term membership growth.

## Key SQL Techniques Used

The analysis involved the following SQL techniques:

- UNION ALL to combine multiple monthly datasets
- CREATE TABLE and CREATE VIEW for structured data transformation
- TIMESTAMP_DIFF to calculate ride duration
- EXTRACT to analyze hourly usage patterns
- Aggregate functions such as COUNT() and AVG()
- GROUP BY to segment rider behavior
- Data filtering to remove invalid ride records




