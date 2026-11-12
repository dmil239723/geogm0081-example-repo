# Data

## Included

 - `effis_modis_powys_20260427.gpkg` – MODIS-derived perimeter of the April 2026 Powys wildfire, downloaded from the [European Forest Fire Information System (EFFIS)](https://forest-fire.emergency.copernicus.eu/applications/data-and-services).
 - `timeseries/burned_area.csv` – the area (km²) with dNBR > 0.27 on each date, with lower and upper estimates using thresholds of 0.28 and 0.26.
 - `timeseries/dnbr_zonal_stats.csv` – the mean and standard deviation of dNBR within the EFFIS fire perimeter on each date.

## Not included (recreated by the notebooks)

GeoTIFF files are excluded by `.gitignore`. Running the notebooks in order will recreate:

 - `multispectral` directory: Landsat Collection 2 Level-2 surface reflectance (blue, green, red, NIR, SWIR1, SWIR2), one file per date, named `powys_<date>_<platform>.tif`.
 - `nbr` directory:  NBR for each date (`powys_<date>_nbr.tif`), and the standard deviation of NBR across all dates (`powys_nbr_std.tif`).
 - `dnbr` directory: dNBR for each date, relative to the 22 April 2026 pre-fire image (`powys_<date>_dnbr.tif`).

All rasters are in UTM zone 30N (EPSG:32630) at 30 m resolution.

Landsat data courtesy of the U.S. Geological Survey, accessed via [Microsoft Planetary Computer](https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2).
