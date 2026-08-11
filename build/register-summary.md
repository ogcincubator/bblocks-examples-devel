# Building Blocks Examples

This register provides a collection of **examples** designed to illustrate capabilities and implementation patterns for [Building Blocks (see more)](https://ogcincubator.github.io/bblocks-docs). 

*These buildings blocks may be copied and edited into a new repository based on the [template](https://github.com/opengeospatial/bblock-template) - but should not be referenced and extended for reuse*


The aim of the highlighted examples is to illustrate implementation patterns for reusing OGC building blocks. The emphasis is on typical requirements to extend or constrain generic or abstract models such as OGC API Features, Observations etc. 

Other examples will illustrate different possible ways to use the Building Block machinery to semantically annotate externally defines schemas, develop and test logical constraints, or simply test examples using a published specification.

More complex examples will include transformation testing - testing a format can be transformed into a related structure and/or data model.


## Building Blocks

### `ogc.bbr.examples.feature.propertySet` — Example property set for Features

**Type:** schema

This shows how to define a propertyset for a feature - which can be re-used in different containers - such as a GeoJSON Feature schema

### `ogc.bbr.examples.linkeddata.forest-ontology` — Forest Ontology

**Type:** model

Example ontology for forest sample datae

### `ogc.bbr.examples.ogcapi.processes.schemas.buffer-geometry.outputSchema` — Buffer geometry process output schema

**Type:** schema

Output schema for the buffer geometry process

### `ogc.bbr.examples.semantic-uplift.override-binding.base` — Override Binding - Base

**Type:** schema

A base building block binding 'note' and 'label' to generic SKOS predicates, to be narrowed by a profile that extends it.

### `ogc.bbr.examples.semantic-uplift.pre-and-post-uplift` — Pre and Post Semantic Uplift example

**Type:** schema

A sample building block to show how semantic uplift can be customized

### `ogc.bbr.examples.transforms.transforms-example` — Transforms example

**Type:** schema

A sample building block to showcase transforms

### `ogc.bbr.examples.transforms.transforms-reuse` — Transforms reuse example

**Type:** schema

Demonstrates calling a component bblock's Python transform from a composite bblock using get_transformer.

### `ogc.bbr.examples.validators.validator-plugins` — Validator plugins example

**Type:** schema

A sample building block to showcase validator plugins (ZIP integrity, WKT geometry, XSD/XML validation)

### `ogc.bbr.examples.ogcapi.processes.schemas.buffer-geometry.inputSchema` — Buffer geometry process input schema

**Type:** schema

Input schema for the buffer geometry process

### `ogc.bbr.examples.linkeddata.forestStandProperties` — Forest Stand Properties

**Type:** schema

Example schema defining the properties of a forest stand, including forest type classification, forest region, target management unit, field verification status, area, and data provenance.

### `ogc.bbr.examples.semantic-uplift.override-binding.child` — Override Binding - Child (Profile)

**Type:** schema

A profile of 'Override Binding - Base' that narrows its inherited 'note' and 'label' bindings by redeclaring them in its own context.jsonld.

### `ogc.bbr.examples.feature.externalSchema` — External Schema (Smart Data Models)

**Type:** schema

This example shows a simple customisation for OGC API Feature using an externally defined domain schema.

### `ogc.bbr.examples.feature.geojsonFeature` — Custom GeoJSON Feature

**Type:** schema

This example shows a simple customisation method for OGC API Feature schemas

### `ogc.bbr.examples.feature.geosparqlFeature` — GeoJSON transformed to GeoSPARQL geometry

**Type:** schema

This example includes an uplift step to use a GeoSPARQL geometry in a GeoJSON object

### `ogc.bbr.examples.observation.vectorObservation` — Observation Result (Vector based on GeoPose)

**Type:** schema

This building block defines the *property set* for an example specialisation of a SOSA Observation using the GeoPose standard as a result. These two patterns are defined by other Building Blocks.

### `ogc.bbr.examples.linkeddata.forestStandFeature` — Semantic Feature

**Type:** schema

GeoJSON Feature where attributes are semantically described using multilingual definitions. The actual properties are based on Czech examples, representing a spatially delineated forest stand classified according to the forest typology system, with properties describing forest type, region, management unit, area, and data provenance.

### `ogc.bbr.examples.feature.geojsonFeatureFGLenient` — Custom JSON-FG (lenient) Feature

**Type:** schema

This example shows a simple customisation method for a JSON-FG (lenient) feature

### `ogc.bbr.examples.feature.overrideContext` — Test Context Override

**Type:** schema

This example shows a simple customisation for OGC API Feature using an externally defined domain schema.

### `ogc.bbr.examples.ogcapi.processes.schemas.buffer-geometry.inputDescription` — Buffer geometry process input description

**Type:** schema

Description for the inputs of the buffer geometry process

### `ogc.bbr.examples.ogcapi.processes.schemas.buffer-geometry.outputDescription` — Buffer geometry process output description

**Type:** schema

Description for the output of the buffer geometry process

### `ogc.bbr.examples.linkeddata.forestStandCollection` — Forest Stand Feature Collection

**Type:** schema

GeoJSON FeatureCollection of forest stands, providing a spatial dataset of forest units classified by forest type, region, and management unit.

### `ogc.bbr.examples.ogcapi.processes.schemas.inputDescriptions` — Example OGC API Processes instance input descriptions

**Type:** schema

Collection of input descriptions

### `ogc.bbr.examples.ogcapi.processes.schemas.buffer-geometry.processDescription` — Buffer geometry process description

**Type:** schema

Description of the buffer geometry process

### `ogc.bbr.examples.ogcapi.processes.schemas.outputDescriptions` — Example OGC API Processes instance output descriptions

**Type:** schema

Collection of output descriptions

### `ogc.bbr.examples.observation.vectorObservationFeature` — Custom Result for Observation Feature

**Type:** schema

This building block defines an example specialisation of an existing Feature specialisation (SOSA Observation), using another schema to define a result set - in this case the GeoPose model

### `ogc.bbr.examples.rules.topo-edges` — Topo rules examples

**Type:** schema

Demonstrates inheritance of rules (in this case for topology using feature references - that cannot be expressed in schemas.

### `ogc.bbr.examples.ogcapi.processes.custom-api` — Custom OGC API processes instance

**Type:** api

An example of an OGC API Processes implementation using building blocks

