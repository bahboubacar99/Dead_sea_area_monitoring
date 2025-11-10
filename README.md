# Dead_sea_area_monitoring
In this project, we will monitoring the Dead Sea surface area variation between 1984 and 2025 using Landsat 5 and 8 images.
### Requirements for running this notebook:
Have a Google Earth Engine (GEE) account
Have a GEE project
Install the necessary libraries
### Notebook contents:
This notebook processes Landsat 5 images from 1984 to 2013 and Landsat 8 images from 2013 to 2025, from GEE.

#### The processing consists of:
- Masking cloud pixels, snow cloud shadows, and values outside the valid range due to sensor saturation and oversaturation. These unusable pixels are masked with QA pixel bands.
- Converting DNs to surface reflectance (SR) using the formula: **SR = pixel X 0.0000275 - 0.2.**
The tiles are then cut according to the study area, and if the percentage of valid pixels exceeds 75%, the image is kept.
- Next, the NDWI spectral index is calculated, then thresholded, and values greater than 0.05 are considered to be water.
- The evolution of this water surface is tracked between 1984 and 2025 and its correlation with the SPEI, which is a standardized precipitation and evapotranspiration index.


