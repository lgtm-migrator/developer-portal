# CSW Service :card_file_box:
 [Catalogue Service for the Web (CSW)](/ogc-protocols/ogc-csw.md) is a standard for exposing a catalogue of geospatial records in XML on the Internet (over HTTP). The catalogue is made up of records that describe geospatial data, geospatial services (e.g. [WMTS](/ogc-protocols/ogc-wmts.md)), and related resources.

 > :no_entry: **Authentication must be integrated in order to communicate with MAP And CSW servers.**<br/>
> **See the principles [here](/getting-started/raster/raster_authentication.md)**

| **Request** | **HTTP method binding(s)** |
| ----------- | ----------- |
| GetCapabilities | GET (KVP) / POST (XML) / SOAP |
| DescribeRecord | GET (KVP) / POST (XML) / SOAP |
| GetRecords | GET (KVP) / POST (XML) / SOAP |
| GetRecordById | GET (KVP) / POST (XML) / SOAP |
| GetRepositoryItem | GET (KVP) |
| GetDomain | GET (KVP) / POST (XML) / SOAP |


