
# Pre and Post Semantic Uplift example (Schema)

`ogc.bbr.examples.semantic-uplift.pre-and-post-uplift` *v0.1*

A sample building block to show how semantic uplift can be customized

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This building block defines two custom semantic uplift steps:

* A pre-processing (i.e, on the JSON documents, before applying the JSON-LD context) JQ step to create two
  properties (`three` with the value `3`, and `doubleString` with the value of the `string` property twice).
* A post-processing (i.e., on the RDF graph, after the JSON-LD context has been applied) SPARQL Update
  query where two new predicates (`ex2:hasFour` and `ex2:nineBound`) are added to all subjects of `ex:hasTwo`.

## Examples

### Example for uplift
#### json
```json
{
  "one": 1,
  "two": 2,
  "string": "value"
}
```

#### jsonld
```jsonld
{
  "@context": "https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/semantic-uplift/pre-and-post-uplift/context.jsonld",
  "one": 1,
  "two": 2,
  "string": "value",
  "three": 3,
  "doubleString": "valuevalue"
}
```

#### ttl
```ttl
@prefix ex: <http://example.com/> .
@prefix ns1: <https://example.net/2/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] ex:exHasGenThree 3 ;
    ex:hasGenDoubleString "valuevalue" ;
    ex:hasOne 1 ;
    ex:hasString "value" ;
    ex:hasTwo 2 ;
    ns1:hasFour 4 ;
    ns1:nineBound false .


```

## Schema

```yaml
type: object
properties:
  one:
    type: number
    x-jsonld-id: http://example.com/hasOne
  two:
    type: number
    x-jsonld-id: http://example.com/hasTwo
  string:
    type: string
    x-jsonld-id: http://example.com/hasString
required:
- one
x-jsonld-extra-terms:
  three: http://example.com/exHasGenThree
  doubleString: http://example.com/hasGenDoubleString
x-jsonld-prefixes:
  ex: http://example.com/

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/semantic-uplift/pre-and-post-uplift/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/semantic-uplift/pre-and-post-uplift/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "three": "ex:exHasGenThree",
    "doubleString": "ex:hasGenDoubleString",
    "one": "ex:hasOne",
    "two": "ex:hasTwo",
    "string": "ex:hasString",
    "ex": "http://example.com/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/semantic-uplift/pre-and-post-uplift/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples-devel](https://github.com/ogcincubator/bblocks-examples-devel)
* Path: `_sources/semantic-uplift/pre-and-post-uplift`

