# Reference changes

Versions identify the reference files someone used; they do not indicate hardware qualification. Future pinout corrections should name the connector/pad, previous assignment, new assignment and supporting evidence.

## 0.1.0-reference - 30 October 2026

First versioned reference snapshot, published as the initial public reference pre-release.

- Curated A/B pin maps covering 800 contacts per V100, with source/evidence fields and coordinate guidance.
- Two- and four-GPU NVLink tables and editable KiCad starters, using short net labels and a naming key. Every contact remains labelled; only NVLink data is connected.
- Standalone Catppuccin Mocha workbook, topology diagrams, schematic previews and native footprint image.
- Complete native schematic PDFs in Catppuccin Mocha and white-background monochrome print editions.
- Quick-start/download guidance, contribution and correction forms, and a citation file retaining upstream credits.
- CERN-OHL-W-2.0 for original hardware contributions and CC BY-SA 4.0 for original documentation/presentation, with separate upstream notices.

This release adds user guidance and exports to the existing mapping. No pin assignments or NVLink connections were changed while preparing it. Downloadable raw PCB footprints, routed boards and supporting power/clock circuits are not included; see [status](docs/status.md) and [footprint notes](docs/footprint.md).
