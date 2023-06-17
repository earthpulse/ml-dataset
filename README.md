# Machine Learning Dataset Extension Specification

- **Title:** Machine Learning Dataset
- **Identifier:** <https://stac-extensions.github.io/ml-dataset/v1.0.0/schema.json>
- **Field Name Prefix:** ml-dataset
- **Scope:** Catalog
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Proposal
- **Owner**: @earthpulse

This document explains the Machine Learning Dataset Extension to 
the [SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) 
(STAC) specification.

- Examples:
  - [Catalog example](examples/catalog.json): Shows the basic usage of the extension in a STAC Catalog
  - [Sub Catalog example](examples/sub-catalog.json): Shows the basic usage of the extension in a STAC Sub Catalog
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Fields

The fields in the table below can be used in these parts of STAC documents:
- [x] Catalogs
- [ ] Collections
- [ ] Item Properties (incl. Summaries in Collections)
- [ ] Assets (for both Collections and Items, incl. Item Asset Definitions in Collections)
- [ ] Links

| Field Name           | Type                      | Description |
| -------------------- | ------------------------- | ----------- |
| ml-dataset:name   | string                    | The name of the dataset |
| ml-dataset:tasks | array                 | List of (suggested) tasks that can be solved with the dataset |
| ml-dataset:type  | string    | Type of the dataset. Can be Training, test, validation, Reference, benchmark, legacy |
| ml-dataset:inputs-type | string | Type of the inputs (text, image, satellite image, video, ... or combination) |
| ml-dataset:annotations-type | string | Type of annotations (raster, vector, ...) (not present for unsupervised learning) |
| ml-dataset:quality | string | Quality level of the dataset |
| ml-dataset:version | float | Dataset version |
| ml-dataset:statistics | **TO DO** | Important values for describing the dataset at a high level and discover potential issues  like biases or data imbalance. |
 
### Additional Field Information

#### template:new_field

This is a much more detailed description of the field `template:new_field`...

### XYZ Object

This is the introduction for the purpose and the content of the XYZ Object...

| Field Name  | Type   | Description |
| ----------- | ------ | ----------- |
| x           | number | **REQUIRED**. Describe the required field... |
| y           | number | **REQUIRED**. Describe the required field... |
| z           | number | **REQUIRED**. Describe the required field... |

## Relation types

The following types should be used as applicable `rel` types in the
[Link Object](https://github.com/radiantearth/stac-spec/tree/master/item-spec/item-spec.md#link-object).

| Type                | Description |
| ------------------- | ----------- |
| ml-dataset:splits      | Links to train, test, validation splits if defined |

## Contributing

All contributions are subject to the
[STAC Specification Code of Conduct](https://github.com/radiantearth/stac-spec/blob/master/CODE_OF_CONDUCT.md).
For contributions, please follow the
[STAC specification contributing guide](https://github.com/radiantearth/stac-spec/blob/master/CONTRIBUTING.md) Instructions
for running tests are copied here for convenience.

### Running tests

The same checks that run as checks on PR's are part of the repository and can be run locally to verify that changes are valid. 
To run tests locally, you'll need `npm`, which is a standard part of any [node.js installation](https://nodejs.org/en/download/).

First you'll need to install everything with npm once. Just navigate to the root of this repository and on 
your command line run:
```bash
npm install
```

Then to check markdown formatting and test the examples against the JSON schema, you can run:
```bash
npm test
```

This will spit out the same texts that you see online, and you can then go and fix your markdown or examples.

If the tests reveal formatting problems with the examples, you can fix them with:
```bash
npm run format-examples
```
