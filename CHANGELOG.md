# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2025-11-25

### Added

- Initial release of STAC Common Operating Picture (COP) Extension
- Core COP fields for operational data exchange:
  - `cop:mission` - Mission/operation identifier
  - `cop:classification` - Security classification level
  - `cop:releasability` - Data releasability specification
  - `cop:dggs_zone_id` - DGGS zone identifier
  - `cop:dggs_crs` - DGGS Coordinate Reference System
  - `cop:asset_type` - Type of COP asset
  - `cop:integrity_hash` - Asset integrity verification
  - `cop:manifest_ref` - Reference to COP manifest
  - `cop:service_provider` - Service/data provider
  - `cop:volume_of_interest` - 3D volume definition
- JSON Schema for validation
- Complete documentation with use cases and best practices
- Example STAC Items (POI, web service)
- Example STAC Collection

### Changed

### Deprecated

### Removed

### Fixed

[Unreleased]: https://github.com/luciocola/cop/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/luciocola/cop/releases/tag/v1.0.0
