# Identifying-Uninhabitable-Regions-in-South-Island-New-Zealand
![output](https://github.com/user-attachments/assets/650e2706-c41f-46f7-b870-77a5d4d7215a)


## Project Overview
This repository contains the code and data for a spatial analysis project aimed at identifying uninhabitable regions in South Island, New Zealand. The project uses Geographic Information Systems (GIS) and open-source data to map areas unsuitable for habitation based on elevation, slope, forest density, and road accessibility.

## Motivation
With the increasing demand for land and infrastructure development in South Island, it is crucial to identify regions where development is either impractical or could be detrimental to the environment. This project aids in making informed decisions for sustainable land use and infrastructure planning.

## Data Sources
The analysis utilizes several open-source datasets:
- **SRTM Digital Elevation Model:** For elevation and slope data.
 ![NZ_South_Elevation_EPSG2193](https://github.com/user-attachments/assets/fd511318-5053-40c6-a04f-947f833fd81c)
 ![NZ_South_Slope_EPSG2193](https://github.com/user-attachments/assets/5d23eb50-028a-4f4f-8946-7e74b8ecc11e)

- **Road Section Geometry:** From Land Information New Zealand, for road accessibility data.
 ![NZ_Road_Network_Map](https://github.com/user-attachments/assets/6c2dcaea-2bca-40f8-8d9a-8cfdb1eefbb9)

- **MODIS Land Cover Dataset:** Accessed via Google Earth Engine, for forest density data.
 ![NZ_South_Forest_EPSG2193](https://github.com/user-attachments/assets/ee06594c-bc68-4770-9e53-df396c4ce341)

## Methodology

This project employs a Geographic Information System (GIS)-based Multi-Criteria Evaluation (MCE) approach to identify uninhabitable regions in South Island, New Zealand. Below are the key steps involved in the methodology:

### Data Preprocessing
1. **Data Extraction and Cleanup:** Automated Python scripts are used to extract and initially process data from various sources such as SRTM for topography and MODIS for forest density.
2. **Data Masking and Reprojection:** The data is masked to focus solely on South Island and reprojected to match the local coordinate reference system using Python libraries for precise spatial analysis.

### Criteria Weighting
- **Weight Assignment:** Weights are assigned to each criterion based on its impact on habitability:
  - **Roads:** 50% (critical for accessibility)
  - **Forest Density:** 30% (affects habitability due to potential natural hazards)
  - **Elevation and Slope:** 10% each (geographical constraints on development)

### Multi-Criteria Evaluation (MCE)
- **Score Calculation:** Scores are computed for each grid cell in the dataset using the assigned weights, determining the habitability of each area.
- **Integration of Criteria:** Scores from different criteria are integrated using GIS software, resulting in a unified uninhabitability score across the dataset.

### Visualization
- **Heatmap Generation:** Final scores are visualized as a heatmap with color gradations from green (habitable) to red (uninhabitable), using Python’s Matplotlib library.

### Tools and Libraries Used
- **Python:** For scripting and automation. Libraries such as Geopandas, Rasterio, and Matplotlib are used for handling geospatial data and visualization.
- **Google Earth Engine:** Accessed for high-resolution satellite imagery and other environmental data processing.
