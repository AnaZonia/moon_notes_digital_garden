---
{"dg-publish":true,"permalink":"/qgis/"}
---


GDAL
Translate tool
- generate NAs

GRASS
[QGIS User Guide — QGIS Documentation documentation](https://docs.qgis.org/3.28/en/docs/user_manual/index.html)



- frequency within 100m?
- iterative biomass predictions - use one prediction to infer the next? 
	- bayesian?
	- imputation

model - get mean predicted value by squares and compare that with the individual ones

dont forget that high sd would regardless introduce bias at some levels more than others even if it has biological drivers!


## masking
You could convert "raster 2" to a polygon (_Raster > Conversion > polygonize_). Then run the **Clipper** tool (_Raster > Extraction > Clipper..._) and use the polygonized "raster 2" as the mask layer.

## Changing layer colors
