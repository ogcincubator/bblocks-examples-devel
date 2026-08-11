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
