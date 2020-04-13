+++
title = "WWT Data Guide"
sort_by = "weight"
insert_anchor_links = "right"
+++

This guide documents the different data formats used by
[AAS WorldWide Telescope][wwt] software, as well as some of the tools used to
generate or manipulate them.

[wwt]: https://worldwidetelescope.org/home

{% warning() %}
This guide synthesizes several manuals that were written separately.
Cross-references are still being updated.
{% end %}

The WWT ecosystem involves many more data formats and standards than you might
think. Links that are internal to this guide are marked **in bold**.

- Individual color images that can be placed upon the sky if they are tagged
  with [AVM][avm] metadata. **TODO**: cross-reference to Layers Guide.
- Scientific image data in the [FITS] format, whose visualization properties
  can be manipulated interactively. The most straightforward way to load and
  visualize FITS data with WWT is in the [JupyterLab] scientific computing
  environment [with pywwt][pywwt-images].
- In order to efficiently display large images, they must be broken into
  pieces and downsampled, a process referred to as “tiling”. This can by done
  with the Python package [toasty] or the Windows programs known as the
  [**Study Chopper**][study-chopper] or the
  [**Sphere Toaster**][sphere-toaster]. Either [toasty] or the
  [**Windows Tile Pyramid SDK**][tile-pyramid-sdk] allow you to write custom
  software to drive the process, which is generally needed when the input
  images are gigabytes or larger in size.
- In order to display images that cover most or all of the sky, one also must
  be careful about how to map between the spherical shape of the sky and the
  flat, 2D nature of computer imagery. The mathematics behind this mapping are
  described in the [**Spherical Projections**][spherical-projections] section.
  The [toasty] and [**Sphere Toaster**][sphere-toaster] software packages
  implement the necessary mathematics.
- The technology that WWT uses to manage all-sky imagery can also be used to
  [**process 360° panoramas**][processing-panoramas], as described later in this
  guide.
- Information *about* all of these sorts of data must be exchanged in order
  for WWT software to know how to locate and properly display the underlying
  data sets. The foundational way to exchange WWT metadata is *WTML*, an
  [XML]-based format for describing [**data collections**][collections]. WTML
  files can be created and manipulated using the low-level [wwt_data_formats]
  Python package.
- WWT uses additional specialized XML data formats that have not yet been
  documented, including:
  - The `wtt` format for serializing WWT Tours.
  - The `wwtl` format for serializing groups of layers.
  - The “File Cabinet” format for bundling up a group of files.

[avm]: https://www.virtualastronomy.org/avm_metadata.php
[FITS]: https://fits.gsfc.nasa.gov/fits_documentation.html
[JupyterLab]: https://jupyterlab.readthedocs.io/
[pywwt-images]: https://pywwt.readthedocs.io/en/stable/layers.html#image-layers
[toasty]: https://toasty.readthedocs.io/
[study-chopper]: @/windows-data-tools/study-chopper/index.md
[tile-pyramid-sdk]: @/windows-tile-pyramid-sdk/_index.md
[sphere-toaster]: @/windows-data-tools/sphere-toaster/index.md
[spherical-projections]: @/spherical-projections/_index.md
[processing-panoramas]: @/processing-panoramas/_index.md
[XML]: https://en.wikipedia.org/wiki/XML
[collections]: @/data-file-formats/collections/index.md
[wwt_data_formats]: https://wwt-data-formats.readthedocs.io/
