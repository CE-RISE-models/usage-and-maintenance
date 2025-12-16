# Changelog

All notable changes to the CE-RISE Usage and Maintenance Data Model will be documented in this file.

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
