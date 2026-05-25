# Geospatial Elevation Profiling & Terrain Mapping

A collection of Jupyter Notebooks leveraging python-based digital elevation data (`elevation`) and geospatial visualization libraries to generate high-fidelity topographic maps, absolute elevation profiles, and comparative grid collages. 

The underlying pipeline utilizes SRTM (Shuttle Radar Topography Mission) data, which natively provides global digital elevation model (DEM) extraction between 60° N and 54° S latitude.

## Notebooks Overview

### 1. Regional Elevation Mapping (`AZ_State_Map_Example.ipynb`)
- **Description:** Clips and processes a Digital Elevation Model (DEM) for a broad geographic boundary.
- **Default Config:** Generates a high-resolution, custom spectral hillshade map (`Arizona_Spectral_Hillshade.png`) complete with localized scalar mappable colorbars.
- **Bounding Box:** `(-114.816, 31.332, -109.045, 37.004)` (Arizona)
- **Examples of other Bounding Boxes:** `(-114.052, 36.998, -109.041, 42.001)` (Utah), `(-109.060, 36.992, -102.041, 41.003)` (Colorado) 

### 2. Global Volcanic Profiles (`Volcano_Example.ipynb`)
- **Description:** Downloads precise 0.20° × 0.20° elevation grids centered directly on the peaks of iconic worldwide volcanoes (e.g., Mt. Fuji, Mt. Vesuvius, Mt. Kilimanjaro, Mt. St. Helens).
- **Output:** Combines absolute elevation raster arrays into a beautifully structured grid collage with transparent background capabilities and explicit sea-level handling.

### 3. Super Volcano Caldera Systems (`Super_Volcano_Example.ipynb`)
- **Description:** Broadens the geographic scope to capture massive regional calderas using 1.00° × 1.00° bounding matrices perfectly centered over global supervolcano sites (e.g., Yellowstone, Lake Toba, Taupo, Campi Flegrei, Long Valley).
- **Output:** Compiles large-scale topographic variations to contrast local valley floors against vast volcanic structures.

---



## 🛠️ System Requirements & Dependencies

The `elevation` Python package relies on standard command-line tools to fetch and process regional terrain grids. If these are not installed on your operating system, the code will fail during the initial data download step.

### 1. Pre-requisites (System Packages)
For Linux/Ubuntu environments, you must install `gdal-bin` and `curl` via your system package manager before running the Python scripts:

```bash
sudo apt update
sudo apt install gdal-bin curl


## Packages for local python

pip install numpy matplotlib elevation rasterio geopandas cartopy


## 🌍 How to Adapt This for Other Regions

The scripts are modularly built so you can easily repurpose them for any other state, country, or point of interest globally. 

### Bounding Box Coordinate Standard
Whenever modifying geographic boundaries in these notebooks, coordinates must follow the standard bounding box tuple format:
```python
region_bounds = (Minimum Longitude, Minimum Latitude, Maximum Longitude, Maximum Latitude)
# Or: (Left, Bottom, Right, Top)
