# Constructing an Intermodal U.S. Hurricane Relief Network

Team A01

## Team Members

- Alexander Renaud
- Julian LaLonde
- Alejandra Hurtado Burghardt
- Chao-Tsun (Sonic) Hsu

## Project Overview

This project looks at how intermodal transportation networks could support hurricane relief efforts in the United States. We used historical hurricane records, population data, rail infrastructure, intermodal facility locations, and trucking routes to evaluate how relief supplies could be transported to cities affected by hurricanes.

Our main objective was to identify potential relief destinations, evaluate transportation options, and examine whether a combination of rail and trucking could help meet a three-day relief delivery target.

## Project Objectives

We focused on several questions throughout the project:

- Which cities have experienced greater historical hurricane exposure?
- How does prioritizing cities by hurricane exposure compare with prioritizing them by population?
- Which intermodal facilities offer reasonable transportation access to potential relief destinations?
- How much do actual road distances differ from straight-line distances?
- What alternative trucking routes are available if the quickest route cannot be used?
- How can rail and trucking networks be combined to evaluate relief transportation options?

## Data Sources

The analysis uses data from the following sources:

| Data | Source |
|---|---|
| Historical Atlantic hurricanes | NOAA National Hurricane Center (HURDAT2) |
| Atlantic sea surface temperatures | NOAA Climate Prediction Center |
| Atlantic Multidecadal Oscillation | NSF NCAR Climate Data Guide |
| U.S. population estimates | U.S. Census Bureau |
| U.S. rail network | Federal Railroad Administration / Bureau of Transportation Statistics |
| Intermodal facility locations | Bureau of Transportation Statistics |
| City coordinates | SimpleMaps |
| Truck routing | openrouteservice (HeiGIT) |

These datasets were cleaned and combined in Python before being used in the analysis.

## Methodology

### 1. Data Cleaning and Preparation

We started by cleaning the hurricane, population, intermodal, and rail datasets. This included checking missing values, removing unnecessary records, standardizing geographic information, and preparing the datasets for merging.

QGIS was also used to associate intermodal facilities with nearby rail segments.

### 2. Hurricane and Weather Analysis

We used NOAA's historical hurricane records to examine hurricane activity and geographic exposure.

The analysis also considered hurricane seasonality, Atlantic sea surface temperatures, and historical changes in hurricane activity.

We compared historical hurricane exposure with population to understand how different prioritization methods could affect the selection of relief destinations.

### 3. Population and Intermodal Analysis

Population data were used to identify potential relief destinations and larger cities that could serve as supply hubs.

We then combined the population information with intermodal facility and rail network data to evaluate transportation accessibility.

### 4. Truck Routing Analysis

Truck routes were calculated using the openrouteservice API from HeiGIT, using its heavy goods vehicle routing profile.

The primary analysis focused on five cities identified through our corrected hurricane-exposure calculations:

- West Palm Beach, Florida
- Boca Raton, Florida
- North Charleston, South Carolina
- Charleston, South Carolina
- Cape Coral, Florida

New Orleans, Louisiana, was also included as a separate historical case related to Hurricane Katrina.

We evaluated 241 intermodal hubs across these six destinations, resulting in 1,446 hub-to-destination routes.

The trucking analysis compared straight-line distances with road network distances, identified the quickest modeled routes, and examined alternative transportation options.

The routing results represent normal road conditions rather than conditions during or immediately after a hurricane.

### 5. Rail–Truck Optimization

We also examined how rail and trucking could be combined to transport relief supplies.

The optimization section incorporates population eligibility, rail network connections, intermodal facilities, trucking routes, and transportation assumptions.

This allowed us to evaluate possible combinations of rail and trucking for relief delivery.

### 6. Exploratory Data Analysis

The notebook includes a series of analytical questions covering hurricane exposure, population, transportation distances, alternative routes, and rail network characteristics.

We used tables, maps, charts, and statistical analysis to examine the results and explain their relevance to hurricane relief planning.

## Key Findings

Several findings stood out during the analysis.

**Hurricane exposure and population:** Prioritizing cities by population does not necessarily produce the same results as prioritizing them by historical hurricane exposure. Both measures provide useful information for relief planning.

**Truck routing:** Straight-line distances can underestimate actual road travel distances. Using a road network provides a better starting point for evaluating trucking options.

**Alternative routes:** The quickest modeled route is not always the only reasonable option. Comparing additional routes helps identify alternatives worth considering if the preferred route becomes unavailable.

**Rail and intermodal transportation:** Rail connectivity and intermodal facility locations affect which transportation options are available. These factors need to be considered alongside trucking distances and travel times.

## Tools and Technologies

- Python
- Google Colab
- Jupyter Notebook
- pandas and NumPy
- GeoPandas and Shapely
- Matplotlib, Seaborn, and Plotly
- scikit-learn
- NetworkX
- QGIS
- openrouteservice API (HeiGIT)
- Microsoft Excel

## Repository Contents

The main notebook for this project is:

`A01_Intermodal_US_Hurricane_Relief_Network.ipynb`

It contains the data preparation, exploratory analysis, transportation modeling, visualizations, and conclusions from our team project.

Supporting Excel and CSV datasets are required for certain sections of the notebook.

## Running the Project in Google Colab

The project was prepared for use in Google Colab so that the notebook could be run without setting up a separate local Python environment.

To open and run the notebook:

1. Open [Google Colab](https://colab.research.google.com/).
2. Select **File → Open notebook → GitHub**.
3. Enter the GitHub repository URL and select `A01_Intermodal_US_Hurricane_Relief_Network.ipynb`.
4. Run the package installation and import cells at the beginning of the notebook.
5. Make sure the required datasets are accessible through Google Drive and that the file paths are correct.
6. Run the notebook cells in order.

Some sections use previously generated trucking and optimization results rather than recalculating everything from the beginning.

The trucking analysis uses saved openrouteservice routing outputs, so new API requests are not required to reproduce those calculations.

**Note:** Running the complete notebook requires access to the supporting datasets and workbooks. These files must be available in the expected locations for the corresponding cells to execute successfully.

## Limitations

There are several limitations to consider when interpreting the results.

- Historical hurricane exposure does not directly measure the damage a city would experience during a future hurricane.
- The trucking routes were calculated under normal road conditions and do not account for closures, flooding, or damaged infrastructure.
- Some routes require additional validation of truck restrictions or geographic coordinates.
- The West Palm Beach analysis uses a Palm Beach routing coordinate as a proxy, which would need to be corrected before operational use.
- The rail–truck optimization depends on assumptions about network connectivity, transportation speeds, and available infrastructure.
- Actual relief delivery times would depend on conditions that cannot be fully captured by the available data.

## Conclusion

Our analysis shows how hurricane records, population data, and transportation networks can be combined to evaluate potential relief routes.

One of the main takeaways is that identifying where relief may be needed is only part of the problem. It is also important to understand how supplies could reach those locations and what transportation alternatives may be available.

Although the results would require additional validation before being used in an actual disaster response, the project provides a starting point for evaluating intermodal transportation options for hurricane relief.

## Team Contributions

Alexander Renaud served as project manager and coordinated the integration of the team's work.

Alexander Renaud and Julian LaLonde worked on the population, routing, rail, intermodal, and transportation network portions of the project.

Alejandra Hurtado Burghardt and Chao-Tsun (Sonic) Hsu worked on the hurricane and weather portions of the project.

## References and AI Disclosure

The full list of references, methodology details, and individual generative AI disclosures are included in the final Jupyter Notebook.

---
