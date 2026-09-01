
# Transforms example (Schema)

`ogc.bbr.examples.transforms.transforms-example` *v0.1*

A sample building block to showcase transforms

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This showcases the potential to define and execute **transforms**

This capability is still in early development.

Transforms are defined in the file [transforms.yaml](transforms.yaml) in the form:

```yaml
  - id: inline-transform
    description: A transform's code can also be defined inside the transform's object
    type: jq
    code: |
      .explanation = "for example - adding an element to define an implicit type"
      .type = "ex:Foo"
```

Current transform types supported are:

- **jq** 
- **sparql-update**
- **sparql-construct**
- **xslt**

Depending on the language of the example all available transforms will be executed and visible via the **transform results** button in the **examples tab**.

## Future planned functionality

### Pluggable transformation engines

Ability to define a custom transformer in a specific repository

### Post transform validation 

Ability to define target profiles to validate post-transform results

### FAIR transforms

standardisation of publication of transformation specifications

### Improved user experience

TBD

### Inheritance of sub-schema transformations

Ability to create a transformation for a composite using multiple transformable building block dependencies.


## Examples

### Example for transforms
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
  "@context": "https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/transforms/transforms-example/context.jsonld",
  "one": 1,
  "two": 2,
  "string": "value"
}
```

#### ttl
```ttl
@prefix ex: <http://example.com/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] ex:hasOne 1 ;
    ex:hasString "value" ;
    ex:hasTwo 2 .


```


### Example for XSLT transform
#### xml
```xml
<?xml version="1.0"?>
<Article>
  <Title>My Article</Title>
  <Authors>
    <Author>Mr. Foo</Author>
    <Author>Mr. Bar</Author>
  </Authors>
  <Body>This is my article text.</Body>
</Article>
```


### HTML example
#### html
```html
<!doctype html>
<html>
  <body>
    <p>This is a <strong>paragraph</strong>!</p>
  </body>
</html>
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
x-jsonld-prefixes:
  ex: http://example.com/

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/transforms/transforms-example/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/transforms/transforms-example/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "one": "ex:hasOne",
    "two": "ex:hasTwo",
    "string": "ex:hasString",
    "ex": "http://example.com/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/transforms/transforms-example/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples-devel](https://github.com/ogcincubator/bblocks-examples-devel)
* Path: `_sources/transforms/transforms-example`

