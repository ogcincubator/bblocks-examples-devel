
# Custom GeoJSON Feature (Schema)

`ogc.bbr.examples.feature.geojsonFeature` *v1.0*

This example shows a simple customisation method for OGC API Feature schemas

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Custom Feature Type 

This building block illustrates a typical "Feature Type" - where an object is modelled as a "Feature with geometry", but has its own "native schema" - or "domain model".

This is an **interoperable** approach to defining a Feature, allowing re-use of a well-defined domain model.

i.e. the attributes (properties) are managed independently of the packaging container (Feature) 

the **propertySet** building block referenced by this container may be used independently of the FeatureModel structure, and is where semantic annotations are provided.

This building block **inherits** reusable semantic annotations for the Feature structure from a common library, simplifying implementation. 




## Examples

### GeoJSON - specialisation example.
#### json
```json
{
  "id": "f1",
  "type": "Feature",
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
  "@context": "https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/geojsonFeature/context.jsonld",
  "id": "f1",
  "type": "Feature",
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
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix myNamespace: <http://example.org/myModel/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.com/features/f1> a geojson:Feature ;
    myNamespace:myProp "Mandatory property example" ;
    geojson:geometry [ a geojson:LineString ;
            geojson:coordinates ( ( -1.116718e+02 4.005671e+01 ) ( -1.1171e+02 4.015671e+01 ) ) ] .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Example of a simple GeoJSON Feature specialisation. This example adds
  some custom properties from a reusable building block that could define properties
  for different Feature structures. This means that the semantic uplift (JSON-LD)
  context for the properties is simple and reusable, without the complications of
  mapping the Feature model to RDF - which is supported by the generic Feature building
  block, and combined here by the BuildingBlock tooling.
$defs:
  MyFeature:
    allOf:
    - $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/features/feature/schema.yaml
    - properties:
        properties:
          $ref: https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/propertySet/schema.yaml
anyOf:
- $ref: '#/$defs/MyFeature'

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/geojsonFeature/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/geojsonFeature/schema.yaml)


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
    "geometry": {
      "@context": {
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        }
      },
      "@id": "geojson:geometry"
    },
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
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "myNamespace": "http://example.org/myModel/",
    "myProp": "myNamespace:myProp",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/feature/geojsonFeature/context.jsonld)

## Sources

* [OGC API - Features, Part 1, 7.16.2: Feature Response](https://docs.ogc.org/is/17-069r3/17-069r3.html#_response_7)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples-devel](https://github.com/ogcincubator/bblocks-examples-devel)
* Path: `_sources/feature/geojsonFeature`

