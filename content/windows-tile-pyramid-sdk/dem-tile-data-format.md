+++
title = "DEM Tile Data Format"
weight = 500
+++

A digital elevation model is a 3-D representation of a terrain's surface
created from terrain [Elevation](http://en.wikipedia.org/wiki/Elevation) data.
For each image tile, there can be a corresponding DEM tile which encodes the
elevation at a set of pre-specified vertices. The pre-specified vertices are
sampled at fixed grid intervals depending on the projection. The tile contains
only the elevation value and does not contain the actual location associated
with the vertex. There are both short and float formats for DEM tiles.

WWT will access the DEM tile through a different URL from that of the image
tile URL. The DEM URL needs to be specified in the WTML file by setting the
value ofthe **DemUrl** attribute. The **DemUrl** template URL string is
parameterized with {0}=zoom level, {1}=x and {2}=y. The DEM files are binary
files which contain the elevation values at the specific grid point locations.
The contents of the DEM tiles will vary depending on the projection.

## TOAST DEM Tile

Each DEM tile consists of 513 16-bit signed values written in Intel byte
order. The signed value represents the elevation/depth in meters. The zero
elevation point corresponds to the reference for the spheroid surface. The
index in the list of 513 signed values indicates where the elevation/depth is
sampled. The vertex list is created by subdivision of a tile. The order of the
vertices changes depending on the slash/backslash type of tile. Each vertex is
a point in 3D space that corresponds to a latitude and longitude for the
chosen projection. Each triangle is decomposed into smaller triangles, each
point in the triangle is added to the vertex list and then the list is walked
and the 3D points are offset by the altitude values in the DEM array. Each
tile shares its adjacent edge with its neighbor, so the bottom and right edges
have the same values as their neighbor's top and left edges, but the data is
redundant so each tile has its own copy of that edge for performance reasons.
The altitude values are sampled from the 2D latitude/longitude array with
bi-linear filtering to remove any stair-step effects or sampling artifacts.

Refer to the `ToastDemTileCreator` class in the SDK for sample implementation.

## Mercator DEM Tile

Each DEM tile consists of 1089 16-bit signed values written in Intel byte
order. Each DEM tile is built using an array of 33×33 values. The U/V values
vary from 0.0 to 1.0, and array indexes vary from 0 to 32 for x and y. The U/V
values and index array are assuming the top, left of the image is (0,0). The
actual distance between elevation data points/vertices for this projection
varies depending on the tile location, zoom level and the latitude boundary
values. The vertex list is rectangular and is created by subdivision of y
values from top to center and then from center to bottom of the tile. For
every y value, the x value varies from 0 to 32. The vertex position in
latitude and longitude is calculated for each x and y. The elevation value at
the given latitude and longitude values is then calculated from the source
data and added to the vertex list.

Refer tothe  `MercatorDemTileCreator` class in the SDK for sample implementation.
