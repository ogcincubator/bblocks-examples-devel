This building block, together with [Gadget](../gadget), exists purely to give the
[`bbplugin-sample-build`](https://github.com/ogcincubator/bblocks-build-plugin-sample)
sample build plugin (declared under `plugins.build` in `bblocks-config.yaml`) more than
one bblock to run its `before_bblock`/`after_bblock` events against.

`SampleBuildHooks.after_register` stamps an `x-sampleBuildPlugin` extension field onto
this bblock's `register.json` entry - see the [Gadget](../gadget) example and
`register.json` itself for the result.
