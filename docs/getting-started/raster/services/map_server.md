# Map Server :world_map:

The raster map service uses the [WMTS](/ogc-protocols/ogc-wmts.md) protocol which is a READ-ONLY Web Map Tile Service.
It's a standard protocol for serving pre-rendered or run-time computed georeferenced map tiles over the Internet.

It provides facilities for searching and retrieving raster layers data with the `GetCapabilities` and `GetTile` operations, all other operations are invalid.
For the full capabilities provided by the service see [GetCapabilities](#getcapabilities)

> :no_entry: **Authentication must be integrated in order to communicate with MAP And CSW servers.**<br/>
> **See the principles [here](/getting-started/raster/raster_authentication.md)**

## GetCapabilities
A WMTS server responding to a **GetCapabilities** request returns metadata about the service, including supported operations and parameters, and a list of the available layers.

An example of a GetCapabilities request is:
```
GET request

https://ows.terrestris.de/osm/service?
REQUEST=GetCapabilities&
SERVICE=WMTS
```

### ***WMTS layer consumption example***
```<MAP_SERVER-RASTER_URL>/wmts/{Layer}/{TileMatrixSet}/{TileMatrix}/{TileCol}/{TileRow}.png```

**{Layer}** - the name of the layer (ex. ***Ortho_25cm***)

**{TileMatrixSet}** - define the grid name of the layer,
> :information_source: **How to get Grid name?** Grid name (`TileMatrixSet`) can be reached by **GetCapabilities** response [Raster - Get Started / Step 4](/getting-started/raster/raster_step-by-step.md?id=step-4)
<figure>
    <img src="./assets/images/map_proxy_getcap_ortho_example.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%;">
</figure>

See `<TileMatrixSetLink>` element for supported Grid names.

**{TileMatrix}** - define the zoom level (Z)

**{TileCol}** - define the column (X)

**{TileRow}** - define the row (Y)

Final request example:
```<MAP_SERVER-RASTER_URL>/wmts/bluemarble-1.0-OrthophotoHistory/newGrids/2/0/2.png```
Will bring a requested tile image

> :bangbang: **Do not change** the “/{TileMatrixSet}/{TileMatrix}/{TileCol}/{TileRow}.png” with custom values while consuming in applications - see examples below.
> MapProxy  automatically relates to those keys and parse the values “on the fly”.

## GetTile
In response to a **GetTile** KVP request, or under a resource-oriented style, a Tile resource that complies with the requested parameters would be returned. A correctly formulated request will bring a tile requested image.
```
GET request

http://cite.deegree.org/deegree-webservices-3.4-RC3/services/wmts100?
service=WMTS&
request=GetTile&
version=1.0.0&
Layer=cite&
Style=default&
Format=image/png&
TileMatrixSet=InspireCrs84Quad&
TileMatrix=17&
TileRow=4&
TileCol=4
```