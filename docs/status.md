# Status and next steps

[Back to the project](../README.md)

## Available now

| Item | Status |
| --- | --- |
| Connector A and B contact maps | 800 contacts exported from the supplied workbook, with original evidence fields. |
| Six-group NVLink contact map | 192 contacts per module. The workbook records direct comparison of 128 contacts with the partial working dual carrier. |
| Two-GPU plan | Full six-group proposal derived from the documented pairing families. Not a claim that this complete arrangement was tested. |
| Four-GPU plan | All twelve group pairings copied from the workbook's `4GPU_Topology`. Not hardware-qualified by this repository. |
| KiCad starters | A single-module connector starter plus two-/four-module projects with all contacts labelled and the NVLink data lanes connected. Clocks, power and control remain unconnected. |
| Geometry renders | Visual references from an existing local preview, not an electrically verified carrier layout. |
| Reference edition | [v0.1.0-reference](https://github.com/pigeon-labs-stack/v100-sxm2-reference/releases/tag/v0.1.0-reference), with complete schematic PDFs, print editions and [change notes](../CHANGELOG.md). |
| Raw PCB footprint | Not included; provenance/reuse terms, physical identity and symbol-to-pad mapping remain open. See [footprint notes](footprint.md). |

## Questions retained from the source work

- Physical connector A/B identity, viewing direction and mating-footprint selection must be established before assigning a manufacturing footprint.
- NVHS physical group numbers have not been correlated with NVIDIA software Link IDs by measurement.
- Optional I2C/address, SMBus, presence, power-brake/power-good and JTAG contacts retain the qualifications recorded in the workbook.
- A schematic contact map and a complete digital connection list do not demonstrate high-speed routing performance, receiver compatibility or system bring-up.

The downloadable workbook covers this repository’s pin mappings, coordinate conventions, NVLink connection plans and source credits. Supporting power/clock circuit designs and private project planning are outside its scope.

## Roadmap

1. Improve the reference material, source credits and connection guides with community feedback.
2. Resolve the physical connector orientation and intended mating footprint.
3. Review the logical two- and four-GPU net assignments and identify opportunities for independent measurements.
4. Maintain the applied CERN-OHL-W-2.0 / CC BY-SA 4.0 terms and versioned reference downloads, retaining upstream credits and applicable terms. See [licence scope](../LICENSE.md).
5. Retain source attribution and image licence exclusions; establish the exact upstream footprint/model reuse terms before bundling those raw files.
6. Develop the supporting circuits, routed carrier design and hardware test records toward the longer-term open-source board goal.
