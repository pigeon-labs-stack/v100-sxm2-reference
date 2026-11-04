# Reference changes

Versions identify the reference files someone used; they do not indicate hardware qualification. Future pinout corrections should name the connector/pad, previous assignment, new assignment and supporting evidence.

## 0.1.1-reference

- Clarified the difference between basic GPU operation and presence detection on reference carriers.
- Added Big Basin and OpenPOWER sources contributed by Michael Williams (@mtwilliams) in PR #2. Updated the evidence for sideband and reserved contacts and corroborated the Connector B NVHS clock polarity.
- Distinguished Quanta's 1.8 V control circuits from OpenPOWER's generic guidance and from reported community implementations.
- Qualified the legacy GND labels at Connector A B7 and A39. The CSVs, workbook and KiCad sheets describe grounding as a reported option for carriers that omit presence detection. The separate pin-renaming proposal remains in issue #1.

## 0.1.0-reference - 30 October 2026

First versioned reference snapshot, published as the initial public reference pre-release.

- Curated A/B pin maps covering 800 contacts per V100, with source/evidence fields and coordinate guidance.
- Two- and four-GPU NVLink tables and editable KiCad starters, using short net labels and a naming key. Every contact remains labelled; only NVLink data is connected.
- Standalone Catppuccin Mocha workbook, topology diagrams, schematic previews and native footprint image.
- Complete native schematic PDFs in Catppuccin Mocha and white-background monochrome print editions.
- Quick-start/download guidance, contribution and correction forms, and a citation file retaining upstream credits.
- CERN-OHL-W-2.0 for original hardware contributions and CC BY-SA 4.0 for original documentation/presentation, with separate upstream notices.

This release adds user guidance and exports to the existing mapping. No pin assignments or NVLink connections were changed while preparing it. Downloadable raw PCB footprints, routed boards and supporting power/clock circuits are not included; see [status](docs/status.md) and [footprint notes](docs/footprint.md).
