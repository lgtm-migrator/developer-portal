
## **Terms**

Term | Description
:--- | :---
**Raster Geodetic Datum**  | World Geodetic System of WGS 84 (also known as WGS 1984 ensemble: EPSG:4326 for 2D coordinate reference system (CRS))
**Raster Map projection**  | Latitude / Longitude Projection
**Raster Best Practice Protocol**  | WMTS
**Raster Tiling scheme**  | InspireCRS84Quad (World CRS84 TileMatrixSet), That tiling schemes consists of two 256x256 tiles at its zoom level 0, in EPSG:4326 CRS, with extent in longitude in the range [-180,180] and in latitude in the range [-90,90].
**Raster Tile Size**  | 256*256
**Raster Tile Format**  | PNG
**Auth token** | A JWT token (you can aquire it by contacting our product owner) for raster services passed via http QUERY_PARAM. There are different kinds of token permissions (raster serving CSW, WMTS, WMS, export, etc.)
**Zoom Level**  | The layer zoom level is determined by the field *mc:maxResolutionDeg*, the zoom level is calculated by the tiling scheme below (Pixel Size (degrees) is maxResolutionDeg), for example, for the following *mc:maxResolutionDeg* 2.14577E-05 >= resolution > 1.07288E-05 a zoom level of **15** will be created.


## **Raster Tiling scheme In Detail**

Zoom Level Id  | Matrix Width (tiles) | Matrix Height (tiles) | Tile Size (degrees) | Pixel Size (degrees) | Tile Size* (meters) | Pixel Size* (meters)
:--- | ---: | ---: | ---: | ---: | ---: | ---:
0 |	2 |	1 |	180 | 0.703125 | 20,037,508.34 | 78,271.52
1 |	4 |	2 |	90 | 0.3515625 | 10,018,754.17 | 39,135.76
2 | 8 | 4 | 45 | 0.17578125 | 5,009,377.09 | 19,567.88
3 | 16 | 8 | 22.5 | 0.087890625 | 2,504,688.54 | 9,783.94
4 | 32 | 16 | 11.25 | 0.043945313 | 1,252,344.27 | 4,891.97
5 | 64 | 32 | 5.625 | 0.021972656 | 626,172.14 | 2,445.98
6 | 128 | 64 | 2.8125 | 0.010986328 | 313,086.07 | 1,222.99
7 | 256 | 128 | 1.40625 | 0.005493164 | 156,543.03 | 611.50
8 | 512 | 256 | 0.703125 | 0.002746582 | 78,271.52 | 305.75
9 | 1024 | 512 | 0.3515625 | 0.001373291 | 39,135.76 | 152.87
10 | 2048 | 1024 | 0.17578125 | 0.000686646 | 19,567.88 | 76.44
11 | 4096 | 2048 | 0.087890625 | 0.000343323 | 9,783.94 | 38.22
12 | 8192 | 4096 | 0.043945313 | 0.000171661 | 4,891.97 | 19.11
13 | 16384 | 8192 | 0.021972656 | 8.58307E-05 | 2,445.98 | 9.55
14 | 32768 | 16384 | 0.010986328 | 4.29153E-05 | 1,222.99 | 4.78
15 | 65536 | 32768 | 0.005493164 | 2.14577E-05 | 611.50 | 2.39
16 | 131072 | 65536 | 0.002746582 | 1.07288E-05 | 305.75 | 1.19
17 | 262144 | 131072 | 0.001373291 | 5.36442E-06 | 152.87 | 0.60
18 | 524288 | 262144 | 0.000686646 | 2.68221E-06 | 76.44 | 0.30
19 | 1048576 | 524288 | 0.000343323 | 1.34110E-06 | 38.22 | 0.15
20 | 2097152 | 1048576 | 0.000171662 | 6.70552E-07 | 19.11 | 0.075
21 | 4194304 | 2097152 | 0.000085831 | 3.35276E-07 | 9.55 | 0.037





