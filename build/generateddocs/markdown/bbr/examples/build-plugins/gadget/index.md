
# Build plugins example: Gadget (Schema)

`ogc.bbr.examples.build-plugins.gadget` *v0.1*

A second trivial building block used to demonstrate build (postprocessing lifecycle) plugins

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This building block demonstrates the [`bbplugin-sample-build`](https://github.com/ogcincubator/bblocks-build-plugin-sample)
sample build plugin, declared under `plugins.build` in `bblocks-config.yaml`.

`SampleBuildHooks` implements every event in the build-plugin lifecycle
(`before_run`, `before_bblock`/`after_bblock` across all five per-bblock stages,
`after_register`, `after_uplift`, `after_run`, `on_error`), logging each one during
the run. `after_register` also stamps an `x-sampleBuildPlugin` extension field onto
this bblock's `register.json` entry - check that entry (and this bblock's
[Widget](../widget) companion) to see the result.

## Examples

### Example 1
#### json
```json
{
  "gadgetName": "Right sprocket"
}

```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Example Gadget
allOf:
- type: object
  properties:
    gadgetName:
      type: string
  required:
  - gadgetName

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/build-plugins/gadget/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/build-plugins/gadget/schema.yaml)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples-devel](https://github.com/ogcincubator/bblocks-examples-devel)
* Path: `_sources/build-plugins/gadget`

