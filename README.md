# Common Operating Picture Extension Specification

- **Title:** COP
- **Identifier:** <https://stac-extensions.github.io/cop/v1.0.0/schema.json>
- **Field Name Prefix:** cop
- **Scope:** Item, Collection
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Proposal
- **Owner**: @luciocola @https://github.com/securedimesions

This document explains the Common Operating Picture Extension to the [SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification.
A Common Operating Picture (COP) file is a standardized format used to transfer data from one system to another. It's designed to facilitate the exchange of information between different systems, platforms, and applications. Based on the work of OGC --OWS Context Conceptual Model 12-080r2.

In general, a COP file should contain the following characteristics:

1. **Standardized Format**: The file should be in a widely accepted format, such as XML (Extensible Markup Language) in the OGC document only XML and atom georss, JSON (JavaScript Object Notation), or CSV (Comma-Separated Values).
2. **Well-Defined Structure**: The file should have a clear and well-defined structure, including:
	* A header section that provides metadata about the file, such as timestamp, version number, and sender information.
	* One or more data sections containing the actual information being transferred (e.g., sensor readings, system status, etc.).
	* A trailer section that indicates the end of the file and may include error-checking or checksum values.
3. **Interoperability**: The COP file should be designed to be compatible with multiple systems, platforms, and applications, ensuring that information can be exchanged seamlessly across different environments.
4. **Data Consistency**: The file should ensure data consistency by providing a single, unified view of the information being transferred. This means that the data is presented in a consistent format, without duplication or inconsistencies.
5. **Error Handling**: The COP file should include mechanisms for handling errors, such as:
	* Error detection: The file should be designed to detect errors during transmission or processing.
	* Error correction: The file should provide mechanisms for correcting errors or rejecting corrupted data.

Some common examples of COP files include:

1. Sensor data exchange formats like the Aerospace Information Agency's (AIA) SENSORS message format.
2. Log files from network devices, such as routers and switches, in a standard format like syslog.
3. Data transfer protocols used in industrial automation, like the OPC Unified Architecture (OPCU).

When designing a COP file, it's essential to consider the specific use case, the systems involved, and the requirements for data exchange. A well-designed COP file can facilitate efficient information sharing, improve system interoperability, and reduce errors during transmission or processing. In the Context of the AI-DGGS we are referring to Emergency (flooding) and we can extend it to Defence scenarios. In the later case it should be revised accrodingly to OGC COnnected Systems.

- Examples:
  - [Item example](examples/item.json): Shows the basic usage of the extension in a STAC Item
  - [Collection example](examples/collection.json): Shows the basic usage of the extension in a STAC Collection
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Fields

The fields in the table below can be used in these parts of STAC documents:

- [ ] Catalogs
- [x] Collections
- [x] Item Properties (incl. Summaries in Collections)
- [x] Assets (for both Collections and Items, incl. Item Asset Definitions in Collections)
- [ ] Links

| Field Name           | Type                      | Description                                  |
| -------------------- | ------------------------- | -------------------------------------------- |
| cop:collection   | string                    | **REQUIRED**. Describe the required field... |
| cop:id         | [id Object](#id-object) | object identifier                       |
| cop:title | COP Feature Assets for....                       |
| cop:description | A collection of real-time feature query results related to the operational area, filtered by DGGS cells.                      |
| cop:license | "propertary", "public"                 |license type                       |
| cop:extent | "spatial","temporal"              | geographic/temporal extent of the area..                |
| cop:summaries | "dggs_crs","asset_type","id"              | dggrs, feature_query POI, idcop
| cop:links | "rel": "about", "href": "s3://cop-manifests/123456.json", "title": "COP Master Manifest" | COP manifest


### Additional Field Information

#### cop:collection

This is a much more detailed description of the field `cop:feature`...

### feature Object

This is the introduction for the purpose and the content of the XYZ Object...

| Field Name | Type      | Description                                  |
| ---------- | --------- | -------------------------------------------- |
| id         | number    | **REQUIRED**. Describe the required field... |
| title      | text      | **REQUIRED**. Describe the required field... |
| description| text      | **REQUIRED**. Describe the required field... |
| license    | text      | **REQUIRED**. Describe the required field... |
| extent     | geography | **REQUIRED**. Describe the required field... |
| summarie   | text      | **REQUIRED**. Describe the required field... |
| links      | href      | **REQUIRED**. Describe the required field... |



## Relation types

The following types should be used as applicable `rel` types in the
[Link Object](https://github.com/radiantearth/stac-spec/tree/master/item-spec/item-spec.md#link-object).

| Type           | Description                           |
| -------------- | ------------------------------------- |
| fancy-rel-type | This link points to a fancy resource. |

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
npm run cop-examples
```
