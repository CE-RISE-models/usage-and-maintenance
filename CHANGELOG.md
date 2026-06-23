# Changelog

All notable changes to the CE-RISE Usage and Maintenance Data Model will be documented in this file.

## [Unreleased]

### Changed
- **Breaking:** `MaintenanceHistory.parts_replaced` and `RepairHistory.components_replaced` changed from free-text `string` to a structured, repeatable `ReplacedComponent` object (feedback item #12).

### Added
- `ReplacedComponent` class (component name, old/new part number, old/new serial number, manufacturer, quantity, reason, condition), typed with schema.org / Dublin Core via `slot_uri`. Harmonised with the diagnostic-results `ReplacedPart` class and the structured replacement object planned for traceability `RefurbishmentEvent` (item #33).

## [0.1.0] - 2026-05-12

### Added
- Optional links from usage metrics, operational conditions, performance tracking, maintenance history, and repair history records to the CE-RISE uncertainty quantification, metrological traceability, and data quality framework utility models.

## [0.0.2] - 2025-12-16

### Added
- Missing references from Beta release of data model.

## [0.0.1] - 2025-12-04

### Added
- Initial data model implementation with three-stage structure (static → dynamic)
- **Stage 1 - Reference Information (Static)**:
  - `UseInstructions` class with operating manuals, safety precautions, troubleshooting guides
  - `MaintenanceInstructions` class with maintenance procedures, cleaning, calibration, decommissioning
  - `MaintenanceSchedule` class for preventive and predictive maintenance scheduling
  - `SparePartsInformation` class for parts catalog and supplier information
  - `ServiceProviderInformation` class for service centers and support contacts
- **Stage 2 - Usage Data Collection (State-Based)**:
  - `UsageMetrics` class tracking operating hours, energy consumption, cycles
  - `OperationalConditions` class for environmental parameters
  - `UsagePatterns` class for use cases and patterns
  - `PerformanceTracking` class for efficiency and reliability metrics
- **Stage 3 - Maintenance/Repair Events (Event-Based)**:
  - `MaintenanceHistory` class with multivalued support for event records
  - `RepairHistory` class with multivalued support for repair events
  - Full event tracking with dates, technicians, costs, effectiveness
- Ontology integrations:
  - Schema.org for instructions and services
  - QUDT for units of measurement
  - SSN/SOSA for sensor-based observations
  - PROV-O for event provenance
  - GoodRelations for spare parts
  - Time Ontology for temporal aspects
- SQL identifiers using `uam_` prefix pattern for database integration
- No required fields - all attributes are optional
- Mixed temporal approach combining state-based and event-based data
