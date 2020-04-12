+++
title = "Process Overview"
weight = 200
+++

The input for visualization is a dataset (typically in the form of an image,
but could for example be a list of X,Y,Z values) that contains a specific
value (depth, elevation or any other magnitude value) for different pairs of
latitude and longitude.

The output is a WorldWide Telescope Collection which is a pyramid of images.
The lowest level of this pyramid is the one at the maximum supported level of
zoom. The upper levels correspond to the lower levels of zoom. The process of
converting the input into a collection requires the following steps:

1. Process the Input

   Input data should be read into a data structure that is capable of
   efficiently looking up a value given a pair of latitude and longitude
   values. For most datasets, a two-dimensional array indexed by latitude and
   longitude values will suffice. The SDK requires that the input be regularly
   gridded which means that the data should be read into a two dimensional
   array indexed by latitude and longitude, where each pair of neighboring
   latitudes has the same delta. Similarly, for longitudes.

2. Build the Base Image

   The base image is the lowest level of the pyramid. At this level there are
   (2^ Level) * (2^Level) images. Each of these images is 256×256 pixels in
   size. This image can be built at any desired level of zoom.

3. Fill the Tile Pyramid.

   Filling the pyramid is the process of building upper levels of the pyramid.
   This is accomplished independent of the data by using the base image. Every
   four neighboring images at the base level are aggregated to form one image
   at the current level. This is recursively done for all the levels.

4. Generate a Plate File.

   A Plate file contains every tile of the pyramid, and a header section
   encodes the format of the pyramid. The purpose of this single file is that
   it enables much easier copying of the pyramid, to send to a colleague, make
   a backup, or any similar purpose.

5. Generate a Thumbnail Image.

   The thumbnail image that appears in the upper panel of WorldWide Telescope
   should be created now.

6. Generate a Collection File.

   A collection file (`*.wtml`) is the XML metadata file that WorldWide
   Telescope uses to load the images generated. For more details refer to
   WorldWide Telescope Data Reference Guide.
