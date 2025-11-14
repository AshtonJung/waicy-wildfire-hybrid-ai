# Wildfire Vulnerability Prediction (WAICY 2025)

This project builds a Wildfire Vulnerability Index (WVI) for California census tracts and trains a Deep Learning MLP model to predict WVI from geospatial, environmental, and socio-demographic factors.

Developed by Ashton Jung for the  
World Artificial Intelligence Competition for Youth (WAICY)

-----------------------------------------------------------------------------------------------

## Project Overview

This project integrates multiple real-world datasets:

- US Census TIGER/Line 2023 tracts
- CAL FIRE wildfire perimeter records
- CDC Social Vulnerability Index (SVI)
- USGS Fire Stations (Structures dataset)

These datasets are combined to compute:
- Wildfire hazard metrics  
- Social vulnerability indicators  
- Distance-to-fire-station response metrics  

Together, these form the Wildfire Vulnerability Index (WVI).

Finally, a Deep Learning MLP Regressor is trained to predict WVI using the engineered features.

-------------------------------------------------------------------------------------------------

## What the Pipeline

The single script (`WAICY_final.ipynb`) performs:

1. Downloads California census tracts  
2. Downloads CAL FIRE wildfire perimeters  
3. Spatially joins fires with census tracts  
4. Aggregates wildfire features per tract  
5. Loads CDC SVI data and merges via FIPS/GEOID  
6. Downloads USGS fire station data  
7. Computes distance to nearest fire station  
8. Normalizes features using MinMaxScaler  
9. Computes:
   - Hazard Score  
   - Vulnerability Score  
   - Response Score  
   - WVI_score
10. Trains an MLP Regressor to model WVI  
11. Evaluates the model and visualizes predictions  

Everything runs in a single file, from data building → WVI → prediction.

------------------------------------------------------------------------------------------------------------------------

## How to Run

Run in Google Colab
1. Upload WAICY_final.ipynb to Google Colab
2. Upload SVI_2022_US.csv into /content/data/
3. Click Runtime → Run all
4. All steps (dataset building → WVI → MLP training → visualization) will run automatically

Note:
The CDC SVI dataset (SVI_2022_US.csv) must be downloaded manually from the CDC website and placed in the data/ folder.

------------------------------------------------------------------------------------------------------------------------

