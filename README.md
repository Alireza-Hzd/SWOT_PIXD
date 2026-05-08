# Product: SWOT_L2_HR_PIXC_D — Level 2 Water Mask Pixel Cloud, Version D
Sample lake bounding box: (12.542019, 42.517160, 12.558057, 42.523060) — (lon_min, lat_min, lon_max, lat_max)
Clip shapefile: user-supplied lake mask
Output: per-acquisition median and mean water surface elevation (WSE) in metres

What is PIXC?
Unlike the gridded Raster product, PIXC delivers an unstructured point cloud: each water pixel is an independent observation with its own latitude, longitude, and height (ellipsoidal WSE in metres, WGS84).
The workflow here is therefore:

Download the PIXC NetCDF granule
Load pixel arrays (latitude, longitude, height, classification, cross_track)
Filter to water pixels inside the lake shapefile
Compute mean & median WSE over retained pixels
Run in Google Colab with Google Drive mounted.
