# CMIP6 Extension Specification

- **Title:** cmip6
- **Identifier:** <https://stac-extensions.github.io/cmip6/v1.0.0/schema.json>
- **Field Name Prefix:** cmip6
- **Scope:** Item, Collection, Asset
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Proposal
- **Owner**: @TomAugspurger

This document explains the CMIP6 Extension to the [SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification.

This extensions defines how to encode metadata using the [CMIP6 Controlled Vocabulary](https://github.com/WCRP-CMIP/CMIP6_CVs) in STAC.

When specified in Item properties, the values are assumed to apply to all Assets in that Item.

- Examples:
  - [Item example](examples/item.json): Shows the basic usage of the extension in a STAC Item
  - [Collection example](examples/collection.json): Shows the basic usage of the extension in a STAC Collection
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Item Properties and Collection Fields

These are the required global attributes from https://github.com/WCRP-CMIP/CMIP6_CVs/blob/master/CMIP6_required_global_attributes.json. See 
[CMIP6 Global Attributes, DRS, Filenames, Directory Structure, and CV's](http://goo.gl/v1drZl) for more.

|         Field Name         |  Type  |                     Description                     |
| -------------------------- | ------ | --------------------------------------------------- |
| cmip6:Conventions          | string | convention version                                  |
| cmip6:activity_id          | string | activity  identifier(s) (part of DRS)               |
| cmip6:creation_date        | string | date file was created                               |
| cmip6:data_specs_version   | string | version identifier                                  |
| cmip6:experiment           | string | short experiment description                        |
| cmip6:experiment_id        | string | root experiment identifier (part of DRS)            |
| cmip6:forcing_index        | number | index for variant of forcing                        |
| cmip6:frequency            | string | sampling frequency                                  |
| cmip6:further_info_url     | string | location of documentation                           |
| cmip6:grid                 | string | grid                                                |
| cmip6:grid_label           | string | grid identifier (part of DRS)                       |
| cmip6:initialization_index | number | Index for variant of initialization method          |
| cmip6:institution          | string | institution name                                    |
| cmip6:institution_id       | string | institution identifier (part of DRS)                |
| cmip6:license              | string | license restrictions                                |
| cmip6:mip_era              | string | activity's associated CMIP cycle (part of DRS)      |
| cmip6:nominal_resolution   | string | approximate horizontal resolution                   |
| cmip6:physics_index        | number | index for model physics variant                     |
| cmip6:product              | string | product type (part of DRS)                          |
| cmip6:realization_index    | number | realization number                                  |
| cmip6:realm                | string | realm(s) where variable is defined (part of DRS)    |
| cmip6:source               | string | full model name / version                           |
| cmip6:source_id            | string | model identifier (part of DRS)                      |
| cmip6:source_type          | string | model configuration                                 |
| cmip6:sub_experiment       | string | description of sub-experiment                       |
| cmip6:sub_experiment_id    | string | sub-experiment identifier (part of DRS "member_id") |
| cmip6:table_id             | string | table identifier (part of DRS)                      |
| cmip6:tracking_id          | string | unique file identifier                              |
| cmip6:variable_id          | string | variable identifier (part of DRS)                   |
| cmip6:variant_label        | string | "variant" label (part of DRS "member_id")           |

### Additional Field Information

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
