
# Validator plugins example (Schema)

`ogc.bbr.examples.validators.validator-plugins` *v0.1*

A sample building block to showcase validator plugins (ZIP integrity, WKT geometry, XSD/XML validation)

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This building block demonstrates the three sample validator plugins:

- **ZipValidator** — verifies ZIP archive integrity using Python's stdlib `zipfile`.
- **WktValidator** — validates WKT geometry syntax and topology using [Shapely](https://shapely.readthedocs.io/).
- **XsdValidator** — validates XML/GML documents against XSD schemas declared as bblock validation resources.

These plugins are loaded from the [`bbplugin-sample-validators`](https://github.com/ogcincubator/bblocks-sample-validator-plugins) package via the `plugins.validators` entry in `bblocks-config.yaml`.
## Examples

### ZIP archive (integrity check)
The ZipValidator plugin checks that the ZIP file is not corrupt. The snippet is passed by file reference.

#### application/zip
[Download binary content](https://ogcincubator.github.io/bblocks-examples-devel/build/tests/bbr/examples/validators/validator-plugins/example_1_1.application.application.zip)


### WKT geometry (syntax and topology validation)
The WktValidator plugin parses the WKT string and checks that the geometry is syntactically correct and topologically valid using Shapely.

#### text/wkt
```text/wkt
POLYGON ((0 0, 4 0, 4 4, 0 4, 0 0), (1 1, 1 2, 2 2, 2 1, 1 1))

```


### XML document (XSD validation)
The XsdValidator plugin validates the XML document against the XSD schema declared as a validation resource in bblock.json (assets/schema.xsd).

#### application/xml
```application/xml
<?xml version="1.0" encoding="UTF-8"?>
<Point>
  <coordinates>51.5 -0.1</coordinates>
  <srs>CRS:84</srs>
</Point>
```


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples-devel](https://github.com/ogcincubator/bblocks-examples-devel)
* Path: `_sources/validators/validator-plugins`

