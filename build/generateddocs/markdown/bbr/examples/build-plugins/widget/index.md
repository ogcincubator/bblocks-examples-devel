
# Build plugins example: Widget (Schema)

`ogc.bbr.examples.build-plugins.widget` *v0.1*

A trivial building block used to demonstrate build (postprocessing lifecycle) plugins

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This building block, together with [Gadget](../gadget), exists purely to give the
[`bbplugin-sample-build`](https://github.com/ogcincubator/bblocks-build-plugin-sample)
sample build plugin (declared under `plugins.build` in `bblocks-config.yaml`) more than
one bblock to run its `before_bblock`/`after_bblock` events against.

`SampleBuildHooks.after_register` stamps an `x-sampleBuildPlugin` extension field onto
this bblock's `register.json` entry - see the [Gadget](../gadget) example and
`register.json` itself for the result.

## Examples

### Example 1
#### json
```json
{
  "widgetName": "Left flange"
}

```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Example Widget
allOf:
- type: object
  properties:
    widgetName:
      type: string
  required:
  - widgetName

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/build-plugins/widget/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples-devel/build/annotated/bbr/examples/build-plugins/widget/schema.yaml)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples-devel](https://github.com/ogcincubator/bblocks-examples-devel)
* Path: `_sources/build-plugins/widget`

