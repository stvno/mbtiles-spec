# MBTiles Specification -RDTiles fork!!

This spec is almost an exact copy of the MBTiles spec, except it is using 
the geonovum RD_scales tilescheme as basis

RDTiles is a specification for storing tiled map data in
[SQLite](http://sqlite.org/) databases for immediate usage and for transfer.
RDTiles files, known as **tilesets**, must implement the specification below
to ensure compatibility with devices.

## UTFGrid

The RDTiles specification previously contained the
[UTFGrid specification](https://github.com/mapbox/utfgrid-spec).
It was removed in version 1.2 and moved into its own specification
with synced version numbers - so RDTiles 1.2 is compatible with
UTFGrid 1.2. The specs integrate but do not require each other
for compliance.

# Versions

* **Development** - NOT USABLE: [1.2](https://github.com/stvno/mbtiles-spec/blob/master/1.2/spec.md)
* **Stable**: [1.1](https://github.com/stvno/mbtiles-spec/blob/master/1.1/spec.md)
* [1.0](https://github.com/stvno/mbtiles-spec/blob/master/1.0/spec.md)

# Changelog

## Roadmap

* The format will switch tile ordering to the XYZ schema popularized by
  OpenStreetMap and away from the Tile Map Service specification.

## 1.1

* `name='format'` row **required** in `metadata` table.
* `name='bounds'` row suggested in `metadata` table.
* optional UTFGrid-based interaction spec.

# Concept

RDTiles is a compact, restrictive specification. It supports only
tiled data, including image tiles and interactivity grid tiles. Only the
Rijksdriehoekstelsel projection is supported for presentation - tile display -
and only latitude-longitude coordinates are supported for metadata such
as bounds and centers.

It is a minimum specification - only specifying the ways in which data
must be retrievable. Thus RDTiles files can internally compress and optimize
data, and construct views that adhere to the RDTiles specification.

Unlike [Spatialite](http://www.gaia-gis.it/spatialite/), GeoJSON,
and Rasterlite, RDTiles is not raw data storage - it is storage
for presentational data, like rendered map tiles.

One RDTiles file represents a single tileset, optionally including grids
of interactivity data. Multiple tilesets - layers, or maps in other terms,
can be represented by multiple RDTiles files.

# Implementations

[Implementing software is tracked on the Wiki](https://github.com/mapbox/mbtiles-spec/wiki/Implementations).

# License

The text of this specification is licensed under a
[Creative Commons Attribution 3.0 United States License](http://creativecommons.org/licenses/by/3.0/us/).
However, the use of this spec in products and code is entirely free:
there are no royalties, restrictions, or requirements.

# Authors

* Tom MacWright (tmcw)
* Will White (willwhite)
* Konstantin Kaefer (kkaefer)
* Justin Miller (incanus)
* Steven Ottens (stvn) - just the RD bit