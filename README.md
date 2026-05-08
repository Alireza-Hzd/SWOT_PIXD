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

A single SWOT acquisition will look like this:
<img width="1252" height="495" alt="image" src="https://github.com/user-attachments/assets/c1c1d6d3-3fad-473f-acd9-576d9448a761" />


And the result for different acquisition for the entire lake would be like this:
Passes with valid lake pixels: 6 / 15

                        datetime  mean_wse_m  median_wse_m  std_wse_m  n_pixels
2024-10-08 19:03:13.622000+00:00  110.699968    110.909897   2.510686      1400
2024-10-10 08:20:19.776000+00:00  110.874430    110.869088   0.221112       860
2024-10-29 15:48:17.307000+00:00  110.986519    111.105186   1.237679       311
2024-10-31 05:05:23.341000+00:00  111.188449    111.188140   0.433152       538
2024-11-19 12:33:22.369000+00:00  111.134684    111.181436   0.977972      1029
2024-11-21 01:50:28.998000+00:00  110.923368    110.910925   0.351139       539
