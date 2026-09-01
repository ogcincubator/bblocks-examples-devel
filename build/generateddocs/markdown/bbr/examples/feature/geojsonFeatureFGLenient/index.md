
# Custom JSON-FG (lenient) Feature (Schema)

`ogc.bbr.examples.feature.geojsonFeatureFGLenient` *v1.0*

This example shows a simple customisation method for a JSON-FG (lenient) feature

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Custom Feature Type

This building block illustrates a typical "Feature Type" - where an object is modelled as a "Feature with geometry",
but has its own "native schema" - or "domain model". It uses JSON-FG (lenient) as its base.

This is an **interoperable** approach to defining a Feature, allowing re-use of a well-defined domain model.

i.e. the attributes (properties) are managed independently of the packaging container (Feature)

the **propertySet** building block referenced by this container may be used independently of the FeatureModel structure,
and is where semantic annotations are provided.

This building block **inherits** reusable semantic annotations for the Feature structure from a common library,
simplifying implementation. 




## Examples

### GeoJSON - specialisation example.
#### json
```json
{
  "id": "f1",
  "type": "Feature",
  "featureType": "app:building",
  "coordRefSys": "http://www.opengis.net/def/crs/EPSG/0/5555",
  "time": { "interval": ["2014-04-24T10:50:18Z", ".."] },
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -111.67183507997295,
        40.056709946862874
      ],
      [
        -111.71,
        40.156709946862874
      ]
    ]
  },
  "properties": {
    "myProp": "Mandatory property example"
  }
}

```

#### jsonld
```jsonld
{
  "@context": "https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/context.jsonld",
  "id": "f1",
  "type": "Feature",
  "featureType": "app:building",
  "coordRefSys": "http://www.opengis.net/def/crs/EPSG/0/5555",
  "time": {
    "interval": [
      "2014-04-24T10:50:18Z",
      ".."
    ]
  },
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -111.67183507997295,
        40.056709946862874
      ],
      [
        -111.71,
        40.156709946862875
      ]
    ]
  },
  "properties": {
    "myProp": "Mandatory property example"
  }
}
```

#### ttl
```ttl
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix myNamespace: <http://example.org/myModel/> .
@prefix ns1: <http://www.opengis.net/def/glossary/term/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix time: <http://www.w3.org/2006/time#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.com/features/f1> a <app:building>,
        geojson:Feature ;
    myNamespace:myProp "Mandatory property example" ;
    dcterms:time [ time:hasTime ( "2014-04-24T10:50:18Z" ".." ) ] ;
    ns1:CoordinateReferenceSystemCRS "http://www.opengis.net/def/crs/EPSG/0/5555" ;
    geojson:geometry [ a geojson:LineString ;
            geojson:coordinates ( ( -1.116718e+02 4.005671e+01 ) ( -1.1171e+02 4.015671e+01 ) ) ] .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Example of a sinmple GeoJSON Feature specialisation
allOf:
- $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/json-fg/feature-lenient/schema.yaml
- properties:
    properties:
      $ref: https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/propertySet/schema.yaml

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "Feature": "geojson:Feature",
    "FeatureCollection": "geojson:FeatureCollection",
    "GeometryCollection": "geojson:GeometryCollection",
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "features": {
      "@container": "@set",
      "@id": "geojson:features"
    },
    "type": "@type",
    "id": "@id",
    "properties": "@nest",
    "geometry": "geojson:geometry",
    "bbox": {
      "@container": "@list",
      "@id": "geojson:bbox"
    },
    "links": {
      "@context": {
        "href": {
          "@type": "@id",
          "@id": "oa:hasTarget"
        },
        "rel": {
          "@context": {
            "@base": "http://www.iana.org/assignments/relation/"
          },
          "@id": "http://www.iana.org/assignments/relation",
          "@type": "@id"
        },
        "type": "dct:type",
        "hreflang": "dct:language",
        "title": "rdfs:label",
        "length": "dct:extent"
      },
      "@id": "rdfs:seeAlso"
    },
    "featureType": "@type",
    "time": {
      "@context": {
        "date": {
          "@id": "owlTime:hasTime",
          "@type": "xsd:date"
        },
        "timestamp": {
          "@id": "owlTime:hasTime",
          "@type": "xsd:dateTime"
        },
        "interval": {
          "@id": "owlTime:hasTime",
          "@container": "@list"
        }
      },
      "@id": "dct:time"
    },
    "coordRefSys": "http://www.opengis.net/def/glossary/term/CoordinateReferenceSystemCRS",
    "place": "dct:spatial",
    "Polyhedron": "geojson:Polyhedron",
    "MultiPolyhedron": "geojson:MultiPolyhedron",
    "Prism": {
      "@id": "geojson:Prism",
      "@context": {
        "base": "geojson:prismBase",
        "lower": "geojson:prismLower",
        "upper": "geojson:prismUpper"
      }
    },
    "MultiPrism": {
      "@id": "geojson:MultiPrism",
      "@context": {
        "prisms": "geojson:prisms"
      }
    },
    "coordinates": {
      "@container": "@list",
      "@id": "geojson:coordinates"
    },
    "geometries": {
      "@id": "geojson:geometry",
      "@container": "@list"
    },
    "myProp": "myNamespace:myProp",
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "owlTime": "http://www.w3.org/2006/time#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "myNamespace": "http://example.org/myModel/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples-devel](https://github.com/ogcincubator/bblocks-examples-devel)
* Path: `_sources/feature/geojsonFeatureFGLenient`

