PBI-Road-Acccident-Analysis

I created a interactive dashboard regarding Road Accident Analysis.

Dashboard Image
Tabl![Screenshot 2024-11-17 105932](https://github.com/user-attachments/assets/a2f1ee78-622b-4ef7-96da-53c5be421ebb)


Steps involved :
Extracting the data from Kaggle.
Transforming the data in Power Query in Power BI.
Loading it in the Power BI and creating dashboard using various charts and DAX queries.
DESCRIPTION : Accident Analysis & Prevention provides wide coverage of the general areas relating to accidental injury and damage, including the pre-injury and immediate post-injury phases.

TOOLS USED : Power BI To analyze, I did data cleaning in Power Query, used Time intelligence Function/ Calendar Date Table in Power BI, Data Modelling(Relationship between multiple tables) , YTD and Y0Y Growth Calculations using DAX, KPI and Advanced Generations, Created Custom columns and measures in the reports, Import Images.


Introduction
Dashboard Requirements
Installation / Usage
DAX Formulas Used in Measures
Bug / Feature Request
Authors
Introduction
This project is aimed at developing a Power BI Dashboard for generating insights about road accident data in the United Kingdom.
The dataset can be accessed from this link: Road Accident Data (UK)
Dashboard Requirements
Primary KPI's - Total Casualties and Total Accident values for Current Year and YoY Growth
Primary KPI's - Total Casualties by Accident Severity for Current Year and YoY Growth
Secondary KPI's - Total Casualties with respect to Vehicle Type for Current Year
Monthly Trend showing comparison of Casualties for Current Year and Previous Year
Casualties by Road Type for Current Year
Current Year Casualties by Area/Location & Day/Night
Total Casualties and Total Accident by Location
Installation / Usage
Install Power BI Desktop from Official Power BI Download Site
Download data files from link given in Introduction
Clone/download this repository to your local machine
Open Dashboard report file (Road Accidents Dashboard.pbix) in Power BI Desktop, to access the dashboard's interactivity
DAX Formulas Used in Measures
1. Total Casualties For Current Year and Year on Year Growth

(a) Current Year To Date Casualties -- CY Casualties Measure

CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])
(b) Previous Year Casualties -- PY Casualties Measure

PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))
(c) Year on Year Growth of Casualties - YoY Casualties Measure

YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]
2. Total Accidents for Current Year and Year on Year Growth

(a) Current Year Accidents Count -- CY Accidents Count Measure

CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])
(b) Previous Year Accidents Count -- PY Accidents Count Measure

PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))
(c) Year on Year Growth of Accidents - YoY Accidents Measure

YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]
