
# Override Binding - Base (Schema)

`ogc.bbr.examples.semantic-uplift.override-binding.base` *v1.0*

A base building block binding 'note' and 'label' to generic SKOS predicates, to be narrowed by a profile that extends it.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Override Binding - Base

A plain building block with two properties, `note` and `label`, each bound in [context.jsonld](context.jsonld)
to a generic SKOS predicate:

* `note` &rarr; `skos:note`
* `label` &rarr; `skos:prefLabel`

On its own this block is unremarkable. It exists to be extended by
[Override Binding - Child](bblocks://ogc.bbr.examples.semantic-uplift.override-binding.child), which redeclares
these same property names in its own context to narrow their meaning — see that block's description, and the docs
on [overriding an inherited binding](https://ogcincubator.github.io/bblocks-docs/create/semantic-uplift#overriding-an-inherited-binding),
for what that demonstrates.

## Examples

### Base example
#### json
```json
{
  "note": "A generic remark about this resource.",
  "label": "Generic Label"
}

```

#### jsonld
```jsonld
{
  "@context": "https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/semantic-uplift/override-binding/base/context.jsonld",
  "note": "A generic remark about this resource.",
  "label": "Generic Label"
}
```

#### ttl
```ttl
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] skos:note "A generic remark about this resource."^^xsd:string ;
    skos:prefLabel "Generic Label"^^xsd:string .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Base schema binding "note" and "label" to generic SKOS predicates. See
  the "Override Binding - Child" building block for how a profile can narrow these.
type: object
properties:
  note:
    type: string
    x-jsonld-id: http://www.w3.org/2004/02/skos/core#note
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#string
  label:
    type: string
    x-jsonld-id: http://www.w3.org/2004/02/skos/core#prefLabel
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#string

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/semantic-uplift/override-binding/base/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/semantic-uplift/override-binding/base/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "note": {
      "@id": "http://www.w3.org/2004/02/skos/core#note",
      "@type": "http://www.w3.org/2001/XMLSchema#string"
    },
    "label": {
      "@id": "http://www.w3.org/2004/02/skos/core#prefLabel",
      "@type": "http://www.w3.org/2001/XMLSchema#string"
    },
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/semantic-uplift/override-binding/base/context.jsonld)

## Sources

* [SKOS Simple Knowledge Organization System Reference](https://www.w3.org/TR/skos-reference/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples-devel](https://github.com/ogcincubator/bblocks-examples-devel)
* Path: `_sources/semantic-uplift/override-binding/base`

