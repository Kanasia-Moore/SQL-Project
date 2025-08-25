# BigQuery Data Exploration

## Overview

A brief description of the project, its purpose, and the key insights or findings. This section should provide a high-level understanding of what the analysis aimed to achieve and what conclusions were drawn.

## Data

### Data Sources

This project uses the data collected from the BigQuery public dataset on homelessness: 

https://console.cloud.google.com/bigquery?ws=!1m5!1m4!4m3!1sbigquery-public-data!2ssdoh_hud_pit_homelessness!3shud_pit_by_coc

### Data Description

Information about the dataset:
- **CoC** = Continuum of Care
- **Sheltered_ES** = Emergency Shelter
- **Sheltered_TH** = Transitional Housing
- **Sheltered_SH** = Safe Haven Housing


## Methodology

### Analysis Approach

- Previewed the table to understand key data such as:
  - **Column Names:** Checked for descriptive columns and acronyms
  - **Data types:** Made sure data stored was consistent with column data type
  - **Completness:** Looked for missing or null values and checked for accuracy and reliability

- Created a table with the relevant data needed for analysis:
```sql
CREATE TABLE
  Exploration_Project.homelessness AS
SELECT
  CoC_Number,
  LEFT(CoC_Number, 2) AS State,
  CoC_Name,
  Overall_Homeless,
  Sheltered_ES_Homeless,
  Sheltered_TH_Homeless,
  Sheltered_SH_Homeless,
  Sheltered_Total_Homeless,
  Unsheltered_Homeless,
  Homeless_Individuals,
  Homeless_People_in_Families,
  Chronically_Homeless,
  Homeless_Veterans,
  Homeless_Unaccompanied_Youth_Under_18,
  Count_Year
FROM
  `bigquery-public-data.sdoh_hud_pit_homelessness.hud_pit_by_coc`
```


### Tools and Technologies

- BigQuery
- SQL
