## Override Binding - Child (Profile)

This block joins its schema with the
[Override Binding - Base](bblocks://ogc.bbr.examples.semantic-uplift.override-binding.base) building block's via
an `allOf`/`$ref` in [schema.yaml](schema.yaml) — the same composition `extends` in `bblock.json` sets up — and
redeclares both of the base block's property names in its own [context.jsonld](context.jsonld):

* `note` — only `@id` is redeclared, narrowing `skos:note` down to `skos:definition`. Its `@type`
  (`xsd:string`) isn't redeclared here, so it's still inherited from the base block's binding.
* `label` — both `@id` and `@type` are redeclared, fully replacing `skos:prefLabel` (`xsd:string`) with
  `skos:altLabel` (`xsd:language`).

This works because the postprocessor annotates each block's schema from its own context in isolation, then
assembles the final context by walking the compiled schema's `allOf` branches in order — base branch first, own
branch last — so a property mapped on both sides resolves to whichever branch comes later. Placing the base
block's `$ref` before this block's own properties in the `allOf` is what makes this block's mapping win.

Look at the assembled JSON-LD context for this block (Examples tab &rarr; RDF/Turtle, or the annotated schema) and
compare it to the [base block](bblocks://ogc.bbr.examples.semantic-uplift.override-binding.base)'s: `note` should
carry `skos:definition` as `@id` but keep `xsd:string` as `@type`, and `label` should be fully remapped to
`skos:altLabel` / `xsd:language`.

See [overriding an inherited binding](https://ogcincubator.github.io/bblocks-docs/create/semantic-uplift#overriding-an-inherited-binding)
in the OGC Blocks docs for the full explanation of this mechanism, including the caveat that it isn't opt-in — any
property name reused from the base schema's chain is overridden the same way, whether or not that was intended.
