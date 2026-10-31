ondo-ekiti-geomorph v1.0.0: code and data for terrain-unit mapping and river-profile analysis of Ondo and Ekiti States, south-western Nigeria

This release contains the code, processing workflow and derived data behind two companion papers on the terrain of Ondo and Ekiti States, south-western Nigeria (19,700 km²):

Terrain units of Ondo and Ekiti States, south-western Nigeria: a hierarchical, DEM-based geomorphological map
River profiles of Ondo and Ekiti States, south-western Nigeria: low concavity and a heterogeneous knickpoint population on a stepped tropical landscape

All results are reproduced from a single 1-arc-second (~30 m) DEM.

Contents

Google Earth Engine script (gee/01_export_dem.js) to extract and export the DEM for the study area.
Python scripts for terrain classification (scripts/01–05):
DEM reprojection to UTM zone 31N (EPSG:32631) at 30 m and 90 m;
land-surface parameters (slope, local relief, topographic position index at 500 m and 2 km);
geomorphons;
Ward hierarchical clustering with validity and bootstrap-stability diagnostics;
a two-level classification into 3 terrain systems and 6 terrain units;
hypsometry, low-slope elevation levels and swath profiles.
Python scripts for river-profile analysis (scripts/06–09):
depression breaching and D8 flow routing;
basin delineation;
χ (chi) analysis and concavity estimation by disorder minimisation;
normalised channel steepness (k_sn);
optimal segmentation of χ–elevation profiles;
knickpoint detection with sensitivity tests;
Monte Carlo tests of knickpoint elevation clustering and χ alignment.
Output tables (outputs/tables): every statistic reported in both papers, as CSV and JSON. These include cluster diagnostics, terrain-unit statistics, the geomorphon composition of each unit, basin metrics, a full knickpoint inventory and the sensitivity runs.
Derived rasters (data/processed): terrain units (90 m), terrain systems (90 m), geomorphons (90 m), drainage basins (30 m) and the study-area polygon.
run_all.sh: regenerates every table and figure in order (about 15 minutes on 2 cores and 8 GB RAM). README.md lists every adjustable parameter.

The input DEM and intermediate rasters are not included because of their size. They can be regenerated with the Earth Engine script and run_all.sh. Figures are produced by scripts 05 and 09.

Software: Python 3.13, rasterio, NumPy, SciPy, scikit-learn, GeoPandas, pyproj, Matplotlib, Numba and WhiteboxTools (via whitebox-workflows). Versions are pinned in requirements.txt.

Licence: code under MIT; derived data under CC BY 4.0.

Author: Adenegan Opeyemi Rapheal (ORCID 0009-0004-0305-3420), Department of Geography, Obafemi Awolowo University, Ile-Ife, Nigeria.
