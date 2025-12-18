# Outlier Detection in Election Data Using Geospatial Analysis

## Project Overview
This project applies geospatial and statistical techniques to detect potential voting irregularities in election results. By comparing voting patterns at each polling unit with those of neighbouring units within a defined geographic radius, the analysis identifies polling units whose results significantly deviate from local norms. Such deviations may indicate anomalies, reporting errors, or areas requiring further investigation to ensure election integrity.

The case study focuses on polling unit–level election data from Kwara State, Nigeria.

## Objective
The primary objectives of this project are to:
- Identify neighbouring polling units using geographic proximity
- Detect polling units with abnormal voting patterns relative to nearby units
- Quantify deviations using statistical outlier scores
- Highlight polling units that may require further review

## Dataset
- **Source:** INEC Cross-Checked Election Results (Polling Unit Level)
- **Region:** Kwara State, Nigeria
- **Granularity:** Polling Unit
- **Data Includes:**
  - Polling unit identifiers
  - Votes per political party
  - Ward and LGA information
  - Latitude and longitude coordinates (geocoded)

> Note: Raw datasets are not included in this repository. Cleaned and enriched datasets were hosted externally as part of the project submission.

## Tools & Technologies
- Python (Jupyter Notebook)
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Sheets (Geocoding using Awesome Table)
- Excel (sorting and reporting outlier scores)

## Methodology

### 1. Data Preparation
- Loaded polling unit–level election data.
- Added missing latitude and longitude values using geocoding techniques in Google Sheets.
- Cleaned and validated voting records for analysis.

### 2. Neighbour Identification
- Defined a 1-kilometre radius to identify neighbouring polling units.
- Used the Haversine formula to calculate distances between polling units based on geographic coordinates.
- Assigned each polling unit a list of neighbours within the defined radius.

### 3. Outlier Score Calculation
- For each polling unit and political party:
  - Computed the mean and standard deviation of votes among neighbouring units.
  - Calculated Z-scores to measure deviations from local voting patterns.
- Derived a maximum absolute Z-score per polling unit to represent its strongest deviation.

### 4. Sorting and Reporting
- Ranked polling units by outlier scores.
- Identified the most extreme positive and negative outliers.
- Analyzed party-level patterns among detected outliers.

## Key Insights
- Most polling units exhibited voting patterns consistent with their neighbours.
- A small number of polling units showed extreme deviations, indicating potential anomalies.
- The Labour Party (LP) and APC recorded the highest number of outlier polling units.
- Some polling units recorded unusually high vote counts relative to nearby units, while others showed significantly lower values.

## Top Outliers Identified
- **OSERE JUNCTION (23-08-10-008):** Unusually high votes for the Labour Party compared to neighbouring polling units.
- **ODE ILE EGBA (23-08-05-055):** Significantly lower votes across major parties relative to neighbours.
- **COMM SCH OREKE (23-05-05-015):** Consistently lower vote counts, particularly for APC, compared to surrounding polling units.

These polling units may warrant closer review to verify data accuracy or understand local voting dynamics.

## Visualizations
The project includes:
- Distribution of outlier scores
- Party-level outlier counts
- Comparisons of top outlier polling units vs neighbouring averages
- Geographic scatter plots showing spatial distribution of outliers

## Limitations
- Outliers do not automatically imply manipulation; local factors may influence results.
- Geocoding accuracy depends on polling unit naming consistency.
- Analysis is limited to a single state.

## Future Work
- Extend the analysis to additional states.
- Incorporate ward- and LGA-level aggregation.
- Integrate interactive geospatial dashboards.
- Apply machine learning techniques for anomaly detection.

## Links
- Full project report available in the `report/` folder
