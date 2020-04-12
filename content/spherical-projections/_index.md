+++
title = "Spherical Projections in WWT"
sort_by = "weight"
insert_anchor_links = "right"
+++

WorldWide Telescope is a viewer for spheres. As a viewer zooms in the spheres
are of ever increasing size and resolution. Sometimes, for panoramas and
all-sky surveys – WorldWide Telescope renders the inside of a sphere. Other
times, for the surfaces of planets and moons, it renders the outside of a
sphere. WorldWide Telescope does _not_ model the irregular shape of the Earth
usually referred to as an oblate spheroid. The east-west diameter of the earth
is 7,926 miles (or 12,756 kilometers), whereas the north-south diameter is
slightly shorter at 7,901 miles (or 12,715 kilometers). The program treats the
Earth, and other planets and moons, as perfect spheres.

The classic problem with mapping is obtaining a useful 2D flat image of a
round 3D surface. There are several well known projection systems, the most
popular are briefly discussed here, though all distort areas of the surface to
a degree. Distortions which are acceptable to a mapping system designed to
show the populated areas of the Earth, are much less acceptable if the object
is to display the topography. In WorldWide Telescope the projection of flat
images onto a sphere is done using a method called TOAST projection -- a
projection system that does not prioritize one area of a sphere over another.

This document provides background information on the theory and practice of
TOAST projection. Equirectangular, Mercator and Gnomonic maps can be converted
to the TOAST format, and are discussed as _source_ projections.
