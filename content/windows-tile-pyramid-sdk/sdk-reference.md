+++
title = "Pyramid SDK Reference"
weight = 300
+++


# Core Classes

The following are the core classes of the SDK, and source code is provided for
all of them. They are encapsulated in the `Sdk.Core` project.

| Class | Description |
| :-- | :-- |
| Boundary | Defines a bounding rectangle. |
| Constants | Defines a range of global constants. |
| DataColorMap | Implements [IColorMap](#icolormap-interface), to generate color pixels corresponding to latitude and longitude from the source grid. |
| DataGrid | Implements [IGrid](#igrid-interface), providing a two dimensional array of data. |
| DemPlateFileGenerator | Implements [IDemPlateFileGenerator](#idemplatefilegenerator-interface), to produce a single file containing all the DEM data tiles. |
| DemTileSerializer | Implements [IDemTileSerializer](#idemtileserializer-interface) to save and load DEM tiles on the file system. |
| Enums | Defines the global enumerations. |
| EquirectangularGridMap | Implements [IProjectionGridMap](#iprojectiongridmap-interface), using equirectangular projection. |
| Helper| Defines a few utility methods related to unit conversions. |
| ImageColorMap | Implements [IColorMap](#icolormap-interface), and references [IProjectionGridMap](#iprojectiongridmap-interface). |
| ImageGrid | Implements [IGrid](#igrid-interface), providing a two dimensional array of image data. |
| ImageTileSerializer| Implements [IImageTileSerializer](#iimagetileserializer-interface) to save and load image tiles on file system. |
| MercatorDemTileCreator| Implements [ITileCreator](#itilecreator-interface) to create Mercator DEM tiles. |
| MercatorTileCreator| Implements [ITileCreator](#itilecreator-interface) to create Mercator image tiles. |
| MultipleDemPlateFileGenerator | Implements [IDemPlateFileGenerator](#idemplatefilegenerator-interface), to produce multiple DEM plate files containing DEM data tiles. |
| MercatorPlateFileDetails | Used to calculate and store the details of multiple plate files. |
| MultiplePlateFileGenerator | Implements [IPlateFileGenerator](#iplatefilegenerator-interface) to produce multiple plate files containing image tiles. |
| MultiTileCreator | Implements [ITileCreator](#itilecreator-interface) for different tile creator instances. |
| OctTileMap | Defines an octahedral tile map. |
| PlateFile | Defines utility methods for plate file operations. |
| PlateFileGenerator | Implements [IPlateFileGenerator](#iplatefilegenerator-interface), used to create plate files. |
| PlateFileHelper | Defines a range of utility methods for plate files. |
| Tile | Simple class holding tile coordinates. |
| TileChopper| Implements [ITileCreator](#itilecreator-interface) to create image tiles without changing the projection. |
| TileCreatorFactory | Creates an image or DEM tile creator instance for the specified projection type. |
| TileGenerator | This class contains the main control/workflow code for the tile generation process. |
| TileHelper | Defines a range of utility methods for tiles and bitmaps. |
| ToastDemTileCreator | Implements [ITileCreator](#itilecreator-interface) to create Toast DEM tiles. |
| ToastHelper | Helper class, in particular working with Toast coordinates. |
| ToastTileCreator| Implements [ITileCreator](#itilecreator-interface) to create Toast image tiles. |
| WtmlCollection | Defines a new Wtml collection, a WorldWide Telescope data file. |


# Interfaces

The Tile Pyramid SDK requires that the following interfaces are implemented.

| Interface | Description |
| :-- | :-- |
| [IColorMap](#icolormap-interface) | Used to retrieve color data. |
| [IDemPlateFileGenerator](#idemplatefilegenerator-interface)| Used to generate plate files for DEM tiles (plate files are single files containing all or part of a tile pyramid for easy copying, sharing and backup). |
| [IDemTileSerializer](#idemtileserializer-interface) | Used to serialize and deserialize (save and load) DEM data. |
| [IElevationMap](#ielevationmap-interface) | Used to retrieve elevation data. |
| [IGrid](#igrid-interface) | Used to read source data into a source grid which can be accessed using UV or XY co-ordinates. |
| [IImageTileSerializer](#iimagetileserializer-interface) | Used to serialize and deserialize (save and load) image data. |
| [IPlateFileGenerator](#iplatefilegenerator-interface) | Used to generate plate files for image tiles (plate files are single files containing all or part of a tile pyramid for easy copying, sharing and backup). |
| [IProjectionGridMap](#iprojectiongridmap-interface) | Used to query the data grid based on the projection. |
| [ITileCreator](#itilecreator-interface) | Used to build the tile pyramids. |

---

## IColorMap Interface

The `IColorMap` interface is used to retrieve color data, and exposes the
following methods. It does not inherit from another interface.

| Method | Description |
| :-- | :-- |
| [GetColor](#icolormap-getcolor)| Retrieves the color corresponding to a longitude and latitude. |

### Implemented in Classes

* [DataColorMap](#core-classes)
* [ImageColorMap](#core-classes)

### IColorMap.GetColor

The `GetColor` method retrieves the color corresponding to a longitude and latitude.

#### Syntax

```cs
Color GetColor(
  double longitude,
  double latitude
);
```

#### Parameters

- `longitude` — Specifies longitude in decimal degrees.
- `latitude` — Specifies latitude in decimal degrees.

#### Return Values

The method returns a `Color` object, containing the color of the pixel at the given latitude and longitude.

#### Remarks

Typically the color returned comes from the source image. Note the order of the parameters, longitude first.

---

## IDemPlateFileGenerator Interface

The `IDemPlateFileGenerator` interface is used to generate plate files for DEM
tiles (plate files are single files containing all or part of a tile pyramid
for easy copying, sharing and backup). It does not inherit from another
interface.

| Method | Description
| :-- | :-- |
| [CreateFromDemTile](#idemplatefilegenerator-createfromdemtile)| Used to create a plate file from a DEM tile pyramid. |

| Property | Type | Get/Set | Description
| :-- | :-- | :-- | :-- |
| TilesProcessed | long | Get only. | Number of tiles for the level that have been processed. |

### Implemented in Classes

* [DemPlateFileGenerator](#core-classes)
* `MultipleDemPlateFileGenerator`

### IDemPlateFileGenerator.CreateFromDemTile

The `CreateFromDemTile` method is used to create a plate file from a DEM tile pyramid.

#### Syntax

```cs
void CreateFromDemTile(
  IDemTileSerializer serializer
);
```

#### Parameters

- `serializer` — Specifies the [IDemTileSerializer](#idemtileserializer-interface) object.

#### Return Values

The method does not return a value.

#### Remarks

None.

---

## IDemTileSerializer Interface

The `IDemTileSerializer` interface is used to serialize and deserialize (save
and load) DEM data, and exposes the following methods. It does not inherit
from another interface.


| Method | Description
| :-- | :-- |
| [Deserialize](#idemtileserializer-deserialize) | Deserializes a binary object from the file system. |
| [Serialize](#idemtileserializer-serialize) | Serializes the binary file to the file system. |

### Implemented in Class

* [DemTileSerializer](#core-classes)

### IDemTileSerializer.Deserialize

The `Deserialize` method deserializes (loads) a DEM tile from the file system.

#### Syntax

```cs
short[] Deserialize(
  int level,
  int tileX,
  int tileY
);
```

#### Parameters

- `level` — Specifies the tile level, from zero to the maximum level for the data.
- `tileX` — Specifies the X index of the tile in the tile pyramid.
- `tileY` — Specifies the Y index of the tile in the tile pyramid.

#### Return Values

The method returns an array of `short` values, containing the binary data.

#### Remarks

The size of a DEM tile is fixed depending on the projection, refer to the
remarks for [Serialize](#idemtileserializer-serialize).

### IDemTileSerializer.Serialize

The `Serialize` method serializes (saves) the DEM tile to the file system.

#### Syntax

```cs
void Serialize(
  short[] tile,
  int level,
  int tileX,
  int tileY
);
```

#### Parameters

- `tile` — Specifies the array of values that make up the DEM tile.
- `level` — Specifies the tile level, from zero to the maximum level for the
  data.
- `tileX` — Specifies the X index of the tile in the tile pyramid.
- `tileY` — Specifies the Y index of the tile in the tile pyramid.4

#### Return Values

The method does not return a value.

#### Remarks

The size of a DEM tile is fixed depending on the projection, for Mercator it
is 1089 values (33 rows of 33), organized by rows. Refer to the
`MercatorDemTileCreator` class. For TOAST it is 513 values, these values are
not in a perfect grid. Refer to the static tables listed first in the
`ToastDemTileCreator` class.

---

## IElevationMap Interface

The `IElevationMap` interface is used to retrieve elevation data, and exposes
the following methods. It does not inherit from another interface.

| Method | Description
| :-- | :-- |
| [GetElevation](#ielevationmap-getelevation)| Retrieves the elevation corresponding to the longitude and latitude. |

### Implemented in Class

This interface is implemented in the `ShadedReliefColorMap` class in the
[SpecificRegionDataSet](worldwidetelescopetilepyramidsdksamples.html) sample.

### IElevationMap.GetElevation

The `GetElevation` method retrieves the elevation corresponding to the
longitude and latitude.

#### Syntax

```cs
short GetElevation(
  double longitude,
  double latitude
);
```

#### Parameters

- `longitude` — Specifies longitude in decimal degrees.
- `latitude` — Specifies latitude in decimal degrees.

#### Return Values

The method returns a `short`, containing the elevation value.

#### Remarks

Note the order of the parameters, longitude first.

---

## IGrid Interface

The `IGrid` interface is used to read source data into a source grid which can
be accessed using UV or XY co-ordinates. It does not inherit from another
interface.

| Method | Description
| :-- | :-- |
| [GetValue](#igrid-getvalue)| Retrieves the value contained at the specified coordinate. |
| [GetValueAt](#igrid-getvalueat)| Retrieves the value contained at the specified pixel location. |
| [GetXIndex](#igrid-getxindex)| Retrieves the X pixel index for the given coordinate. |
| [GetYIndex](#igrid-getyindex)| Retrieves the Y pixel index for the given coordinate. |

| Property | Type | Get/Set | Description
| :-- | :-- | :-- | :-- |
| Height | int | Get/Set | Height of the grid. |
| Width | int | Get only | Width of the grid. |

### Implemented in Classes

* [DataGrid](#core-classes)
* [ImageGrid](#core-classes)

### IGrid.GetValue

The `GetValue` method retrieves the value contained at the specified
coordinate.

#### Syntax

```cs
double GetValue(
  double u,
  double v
);
```

#### Parameters

- `u` — Specifies u coordinate.
- `v` — Specifies v coordinate.

#### Return Values

The method returns a `double`, containing the value for the given coordinate.

#### Remarks

UV coordinates are floating point in the range 0 to 1. The top left hand
corner of the map is 0,0.

### IGrid.GetValueAt

The `GetValueAt` method retrieves the value contained at the specified pixel
location.

#### Syntax

```cs
double GetValueAt(
  int i,
  int j
);
```

#### Parameters

- `i` — Specifies X index.
- `j` — Specifies Y index.

#### Return Values

The method returns a `double`, containing the value.

#### Remarks

These coordinates are in pixels, from 0 to the full width or height of the
map. The top left hand corner of the map is 0,0.

### IGrid.GetXIndex

The `GetXIndex` method retrieves the X pixel index for the given *u*
coordinate.

#### Syntax

```cs
int GetXIndex(
  double u
);
```

#### Parameters

- `u` — Specifies u coordinate  in decimal degrees.

#### Return Values

The method returns an `int`, containing the X pixel value for the given
coordinate.

#### Remarks

The U coordinate is in the range 0 to 1.

### IGrid.GetYIndex

The `GetYIndex` method retrieves the Y pixel index for the given V coordinate.

#### Syntax

```cs
int GetYIndex(
  double v
);
```

#### Parameters

- `v` — Specifies v coordinate in decimal degrees.

#### Return Values

The method returns an `int`, containing the Y pixel value for the given
coordinate.

#### Remarks

The V coordinate is in the range 0 to 1.

---

## IImageTileSerializer Interface

The `IImageTileSerializer` interface is used to serialize and deserialize
(save and load) image data, and exposes the following methods.

| Method | Description |
| :-- | :-- |
| [Deserialize](#iimagetileserializer-deserialize) | Deserializes an image from the file system. |
| [Serialize](#iimagetileserializer-serialize) | Serializes the image to the file system. |

### Implemented in Class

[ImageTileSerializer](#core-classes)

### IImageTileSerializer.Deserialize

The `Deserialize` method deserializes (loads) an image from the file system.

#### Syntax

```cs
Bitmap Deserialize(
  int level,
  int tileX,
  int tileY
);
```

#### Parameters

- `level` — Specifies the tile level, from zero to the maximum level for the
  data.
- `tileX` — Specifies the X index of the tile in the tile pyramid.
- `tileY` — Specifies the Y index of the tile in the tile pyramid.

#### Return Values

The method returns a `Bitmap`, containing the binary image.

#### Remarks

Indexes of the tile pyramid are zero based. The size of an image tile is fixed
at 256×256 pixels.

### IImageTileSerializer.Serialize

The `Serialize` method serializes (saves) the tile image to the file system.

#### Syntax

```cs
void Serialize(
  Bitmap tile,
  int level,
  int tileX,
  int tileY
);
```

#### Parameters

- `tile` — Specifies the Bitmap for the tile.
- `level` — Specifies the tile level, from zero to the maximum level for the
  data.
- `tileX` — Specifies the X index of the tile in the tile pyramid.
- `tileY` — Specifies the Y index of the tile in the tile pyramid.

#### Return Values

The method does not return a value.

#### Remarks

Indexes of the tile pyramid are zero based. The size of an image tile is fixed
at 256 x 256 pixels.

---

## IPlateFileGenerator Interface

The `IPlateFileGenerator` interface is used to generate plate files for image
tiles (plate files are single files containing all or part of a tile pyramid
for easy copying, sharing and backup). It does not inherit from another
interface.

| Method | Description |
| :-- | :-- |
| [CreateFromImageTile](#iplatefilegenerator-createfromimagetile) | Used to create a plate file from an image tile pyramid. |

#### Properties

| Property | Type | Get/Set | Description |
| :-- | :-- | :-- | :-- |
| TilesProcessed | long | Get only. | Number of tiles for the level that have been processed. |

### Implemented in Classes

* [PlateFileGenerator](#core-classes)
* [MultiplePlateFileGenerator](#core-classes)

### IPlateFileGenerator.CreateFromImageTile

The `CreateFromImageTile` method is used to create a plate file from an image
tile pyramid.

#### Syntax

```cs
void CreateFromImageTile(
  IImageTileSerializer serializer
);
```

#### Parameters

- `serializer` — Specifies the
  [IImageTileSerializer](#iimagetileserializer-interface) object.

#### Return Values

The method does not returns a value.

#### Remarks

The image pyramid must be created before a plate file can be generated. Plate
files are single files that make it easier to send or archive the tile
pyramid.

---

## IProjectionGridMap Interface

The `IProjectionGridMap` interface is used to query the data grid based on the
projection. It does not inherit from another interface.

| Method | Description |
| :-- | :-- |
| [GetValue](#iprojectiongridmap-getvalue) | Retrieves the value contained at the specified coordinate. |
| [GetXIndex](#iprojectiongridmap-getxindex) | Retrieves the X pixel index for the given coordinate. |
| [GetYIndex](#iprojectiongridmap-getyindex) | Retrieves the Y pixel index for the given coordinate. |
| [IsInRange](#iprojectiongridmap-isinrange) | Retrieves a Boolean indicating whether a given coordinate falls within the scope of the map. |

#### Properties

| Property | Type | Get/Set | Description |
| :-- | :-- | :-- | :-- |
| InputBoundary | Boundary | Get only | Bounding box of the map. |
| InputGrid | [IGrid](#igrid-interface)| Get only | The source grid for the map. |

### Implemented in Class

* [EquirectangularGridMap](#core-classes)

### IProjectionGridMap.GetValue

The `GetValue` method retrieves the value contained at the specified
coordinate.

#### Syntax

```cs
double GetValue(
  double longitude,
  double latitude
);
```

#### Parameters

- `longitude` — Specifies longitude in decimal degrees.
- `latitude` — Specifies latitude in decimal degrees.

#### Return Values

The method returns a `double`, containing the value for the given coordinate,
depending on the projection.

#### Remarks

Note the order of the parameters, longitude first.

### IProjectionGridMap.GetXIndex

The `GetXIndex` method retrieves the X pixel index for the given longitude.

#### Syntax

```cs
int GetXIndex(
  double longitude
);
```

#### Parameters

- `longitude` — Specifies longitude in decimal degrees.

#### Return Values

The method returns an `int`, containing the X pixel value for the given
longitude, depending on the projection.

#### Remarks

None.

### IProjectionGridMap.GetYIndex

The `GetYIndex` method retrieves the Y pixel index for the given latitude.

#### Syntax

```cs
int GetYIndex(
  double latitude
);
```

#### Parameters

- `latitude` — Specifies latitude in decimal degrees.

#### Return Values

The method returns an `int`, containing the Y pixel value for the given
latitude, depending on the projection.

#### Remarks

None.

### IProjectionGridMap.IsInRange

The `IsInRange` method retrieves a Boolean indicating whether a given
coordinate falls within the scope of the map.

#### SySyntax

```cs
bool IsInRange(
  double longitude,
  double latitude
);
```

#### Parameters

- `longitude` — Specifies longitude in decimal degrees.
- `latitude` — Specifies latitude in decimal degrees.

#### Return Values

The method returns a `bool`.

#### Remarks

Note the order of the parameters, longitude first.

---

## ITileCreator Interface

The `ITileCreator` interface is used to build the tile pyramids, and exposes
the following methods. It does not inherit from another interface.

| Method | Description |
| :-- | :-- |
| [Create](#itilecreator-create) | Creates tiles of the pyramid at the specified level. |
| [CreateParent](#itilecreator-createparent) | Create tiles of the pyramid at the parent of the specified level. |

#### Properties

| Property | Type | Get/Set | Description |
| :-- | :-- | :-- | :-- |
| ProjectionType | ProjectionTypes | Get only. | Specifies or retrieves the projection type, one of: Toast, Mercator |

### Implemented in Classes

* [ToastTileCreator](#core-classes)
* [MercatorTileCreator](#core-classes)
* [ToastDemTileCreator](#core-classes)
* [MercatorDemTileCreator](#core-classes)
* [MultiTileCreator](#core-classes)
* [TileChopper](#core-classes)

### ITileCreator.Create

The `Create` method creates tiles of the pyramid at the specified level.

#### Syntax

```cs
void Create(
  int level,
  int tileX,
  int tileY
);
```

#### Parameters

- `level` — Specifies the tile level, from zero to the maximum level for the
  data.
- `tileX` — Specifies the X index of the tile in the tile pyramid.
- `tileY` — Specifies the Y index of the tile in the tile pyramid.

#### Return Values

This method does not return a value.

#### Remarks

If the input to this method was `Create(N,X,Y)`, the output would be the tile
with coordinates (X,Y) at level N.

### ITileCreator.CreateParent

The `CreateParent` method creates tiles for the parent of the specified level.

#### Syntax

```cs
void CreateParent(
  int level,
  int tileX,
  int tileY
);
```

#### Parameters

- `level` — Specifies the tile level, from zero to the maximum level for the
  data.
- `tileX` — Specifies the X index of the tile in the tile pyramid.
- `tileY` — Specifies the Y index of the tile in the tile pyramid.

#### Return Values

This method does not return a value.

#### Remarks

If the input to this method was `CreateParent(N,X,Y)`, the output would be the
tile with coordinates (X/2,Y/2) at level N-1.
