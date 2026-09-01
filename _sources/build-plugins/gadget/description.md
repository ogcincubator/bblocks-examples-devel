This building block demonstrates the [`bbplugin-sample-build`](https://github.com/ogcincubator/bblocks-build-plugin-sample)
sample build plugin, declared under `plugins.build` in `bblocks-config.yaml`.

`SampleBuildHooks` implements every event in the build-plugin lifecycle
(`before_run`, `before_bblock`/`after_bblock` across all five per-bblock stages,
`after_register`, `after_uplift`, `after_run`, `on_error`), logging each one during
the run. `after_register` also stamps an `x-sampleBuildPlugin` extension field onto
this bblock's `register.json` entry - check that entry (and this bblock's
[Widget](../widget) companion) to see the result.
